# Authentication System Architecture Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — architecture plan only. No code, dependency, provider, or credential is added by this document.
- **Version:** 1.1 — restructured to the 15-section outline; content carried forward from v1.0, plus new §1 (Authentication Goals) and §2 (User Roles).
- **Prepared:** 2026-07-27
- **Scope:** `afaqalhayatae-app` identity, session, and account-linking architecture.
- **Depends on:** `08_DIGITAL_SYSTEMS/DATA_MODEL.md` (v0.2/v0.3), `99_STANDARDS/SECURITY_STANDARD.md`, `08_DIGITAL_SYSTEMS/CRM_AND_PORTALS.md`, `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`, `00_GOVERNANCE/AGENT_REGISTRY.md`, and the app's existing `src/types/identity.ts`, `src/lib/services/identity-service.ts`, `src/lib/adapters/types.ts`.

## Note on scope

This document plans the architecture only. It does not write application code, add a new dependency, register an OAuth application with Google or Apple, generate or store any client secret/private key, or create a Prisma migration. Every irreversible or externally-visible step named below (provider registration, credential issuance, schema migration) remains its own future, explicitly-approved action.

## Governing Constraint — Read Before §12

The app already has a working email/password identity layer (`JOB-AGT-WEB-20260726-M2.1`), and its own source code already flags the exact blocker this plan must respect: `src/types/identity.ts`'s header comment states identity types are *"deliberately kept separate from `src/types/domain.ts`... Identity is a distinct concern... not yet part of that approved model [`DATA_MODEL.md`]."*

Confirmed against `08_DIGITAL_SYSTEMS/DATA_MODEL.md` (Approved, v0.2/v0.3): its Core Entities list — Service, Service Area, Customer, Contact Point, Consent, Enquiry, Booking Request, Quote Request, Work Order, Approval, Interaction, Audit Event — **contains no `User`, `Credential`, `Session`, or `OAuthAccount` entity.** Every identity-related Prisma model §12 proposes therefore requires a `DATA_MODEL.md` governance amendment **before** it can be added to `prisma/schema.prisma`, per `06_DEPLOYMENT_PLAN.md` §4's rule: *"any schema change beyond that approved model requires a governance update to `DATA_MODEL.md` first, not a schema drift silently introduced in code."* This is the single most important prerequisite in this plan.

**Current state, verified in code (baseline for every section below):**

- Password auth is implemented, in-memory only: `registerWithPassword`, `loginWithPassword`, `logout`, `getCurrentUser`, `updateProfile` in `src/lib/services/identity-service.ts`.
- Password hashing: Node `crypto.scrypt`, per-user salt, `timingSafeEqual` comparison — sound, no change needed.
- Sessions: random session id in an `httpOnly`, `sameSite=lax`, production-`secure` cookie; session id never appears in a JSON response body.
- Extension points already reserved, unimplemented: `AuthProvider = "password" | "google" | "phone_otp"` (note: `"apple"` is not yet in this union); `GoogleAuthProviderAdapter.verifyIdToken()` interface already exists, explicitly commented *"prepare for... not implemented... none should be [added] without separate approval."*
- Known gaps: no rate limiting/lockout on `/api/auth/login`; no email verification; no password reset; all identity/session/credential data is in-memory (lost on restart).
- `BookingRequest`/`QuoteRequest`/`Enquiry` already carry a `customerId` field (`DATA_MODEL.md` v0.3), and the customer dashboard already resolves the signed-in user through it — the wiring §13 needs is largely already in place at the domain-model level.

---

## 1. Authentication Goals

- **Let a real customer securely identify themselves** to see and manage their own bookings, quotes, and enquiries — the entire reason identity exists in this app (per `CRM_AND_PORTALS.md`'s Customer Portal Minimum: "secure access and session management").
- **Offer a choice of sign-in method** (password today; Google and Apple planned) without fragmenting a customer's history across multiple disconnected accounts — one person, one account, regardless of how they signed in (§7).
- **Never invent or assume an identity fact** — no assumed email, no guessed linkage between two sign-in methods without provider-verified proof (§7), consistent with this repository's broader "never fabricate" rule applied to identity data specifically.
- **Keep the transport mechanism boring and correct** — httpOnly cookies, hashed credentials, hashed tokens — rather than novel or clever, since authentication is the wrong place for invention.
- **Stay within the approval model** — no credential, provider registration, or schema change happens without its own explicit Owner gate, exactly like every other `A4` item in this repository.
- **Support what the business actually is today**, not a speculative enterprise structure — see §2.

## 2. User Roles

The business has exactly one internal human (the Owner, per `CURRENT_PROJECT_STATUS.md`'s operating model) and no staff. This shapes roles directly:

| Role | Exists today? | Notes |
|---|---|---|
| **Customer** | Yes (implicit) | The only role the current `User`/identity code models. Anyone who registers is a customer; there is no signup-time role selection. |
| **Owner/Admin** | No | `CRM_AND_PORTALS.md`'s "Owner Dashboard Minimum" (pending approvals, enquiries, bookings, audit evidence) implies an eventual owner-facing role, but no such account type, permission model, or route exists in the app today. Proposed as future scope, not designed in detail here — it would need its own architecture pass when the Owner Dashboard is actually started. |
| **Technician/Staff** | No, and not planned as internal accounts | Per `CURRENT_PROJECT_STATUS.md`, external licensed providers may perform physical work but are "not represented as internal staff" — this plan does not propose technician login accounts. If a future technician portal is approved, it is a separate decision, not assumed here. |
| **AI Agent** | Governed separately | Agents acting on a customer's behalf authenticate through the customer's own session/consent context (§15), not a distinct "agent role" with elevated identity privileges. |

**Implication for the data model (§12):** no `role` enum is proposed on `User` yet — a single implicit Customer role needs none. Adding Owner/Admin later is an additive change (a `role` field plus route guards), not a redesign, when that work is actually approved.

## 3. Registration Flow

- Input: display name, a contact point (phone, WhatsApp, or email — per the existing `ContactPoint["channel"]` union), and a password.
- Validation (already implemented): all three fields required, password ≥ 8 characters (`WeakPasswordError` if not), contact value not already registered (`ContactAlreadyRegisteredError` if it is).
- On success: a `User` is created (`emailVerified: false`, `phoneVerified: false`, `status: "active"`), a password credential is hashed and stored, and a `user.registered` audit event is written.
- **New in this plan:** registration should also kick off email verification (§11) if the chosen contact channel is email, and should be rate-limited per IP to prevent automated mass account creation (§14).
- No role or plan selection occurs at registration — see §2.

## 4. Email/Password Flow

Extends, does not replace, the existing `registerWithPassword`/`loginWithPassword` functions.

- **Login:** contact value + password → `loginWithPassword` looks up the user, verifies the password via `PasswordAuthProviderAdapter.verify()` (scrypt + `timingSafeEqual`), checks `status === "active"`, and issues a session. Every attempt (success or failure) is already audit-logged.
- **Add:** rate limiting and progressive lockout on login attempts (by contact value and by IP) — none exists today. Recommend a fixed-window or token-bucket counter persisted the same place sessions eventually persist (§9), not in application memory alone.
- **Add:** stronger password-strength checking beyond raw length (e.g., reject common/breached passwords) — a policy decision for the Owner or a delegated technical reviewer, not invented here.
- **Unchanged:** the existing error taxonomy (`ContactAlreadyRegisteredError`, `WeakPasswordError`, `AccountDisabledError`, `InvalidCredentialsError`) — new flows reuse it rather than inventing parallel error types.

## 5. Google OAuth Flow

Builds directly on the already-reserved `GoogleAuthProviderAdapter` interface.

- **Flow (Authorization Code + PKCE):** redirect to Google's OAuth consent screen → Google redirects back with a code → server exchanges it for tokens → server verifies the ID token (`GoogleAuthProviderAdapter.verifyIdToken()`) → resolve or create a `User` via the account-linking rule in §7 → issue a session through the existing, unchanged `createSession` path.
- **New dependency required:** verifying a Google ID token needs a small JOSE/JWT-verification library or `google-auth-library` — **not added by this document**; selecting and approving one is a separate, explicit decision.
- **Credential requirement (Owner-executed, not performed here):** a Google Cloud project, OAuth consent screen, and a Client ID/Secret — an `A4` "change credentials" item per `AUTONOMY_AND_APPROVAL_MATRIX.md`.
- **Redirect URI allowlisting:** configured explicitly server-side and in the Google Cloud console; never derived dynamically from request headers (a classic open-redirect/host-header-injection risk).

## 6. Apple Sign In Flow

### 6.1 Apple-specific constraints (distinct from Google)

- Apple issues a client secret as a **short-lived JWT you generate yourself**, signed with an ES256 private key tied to a Services ID, Team ID, and Key ID — not a static pasted secret, and Apple caps its validity at 6 months, requiring periodic regeneration.
- Apple only returns the user's name **on the very first authorization** — if not captured then, it cannot be retrieved again.
- Apple supports **Hide My Email** (a private relay address) — the stored contact value may not be the user's real email and must be treated as a legitimate, permanent contact channel, not an error.
- Apple requires HTTPS redirect URIs even in development — local `http://localhost` testing doesn't work the way Google's does, affecting the local dev workflow.

### 6.2 Proposed interface (architecture only, not implemented)

```ts
// Proposed addition to src/lib/adapters/types.ts — NOT created by this document
export interface AppleAuthProviderAdapter {
  verifyIdToken(idToken: string): Promise<{
    providerAccountId: string; // Apple's "sub"
    email?: string;            // may be a private relay address, or absent on non-first auth
    emailVerified: boolean;
  }>;
}
```

- `"apple"` must be added to the `AuthProvider` union in `src/types/identity.ts` alongside this.
- **Credential requirement (Owner-executed, not performed here):** an active Apple Developer Program membership (paid, annual), a registered Services ID, and a generated private key — another `A4` action.

## 7. Social Login Strategy

A single `User` may end up with more than one way to sign in (password + Google, Google + Apple, etc.). One deliberate strategy, not an accretion of special cases:

- **Linking key:** match on verified email where available. If a Google/Apple sign-in presents an email matching an existing `User`'s verified contact, link the new provider identity to that user — but **only if the incoming email is itself provider-verified** (`emailVerified: true`), never on an unverified claim.
- **No email available** (e.g., Apple private relay on a returning user, or phone-only accounts): require explicit user action — "sign in your existing way, then link this one from your profile" — rather than guessing a match.
- **One `User`, many linked identities:** requires a new `LinkedIdentity` entity (§12), not multiple provider fields bolted onto `User`.
- **Unlinking:** a user must always retain at least one working sign-in method; the profile UI (§8) must block removing the last remaining linked identity/credential.

## 8. User Profile Architecture

Extends the existing `updateProfile`/`profile-form.tsx` (currently: display name only).

- **Add:** a linked-identities list (which providers are connected, masked contact value per identity, "linked on" date) with unlink actions per §7's last-identity guard.
- **Add:** primary-contact-channel management now that a user might have a password-based phone contact and a Google-verified email simultaneously — which one is "the" contact for notifications needs a clear, user-visible setting, not an implicit default.
- **Unchanged:** no new personal-data field is added beyond what's needed for the above — per `DATA_MODEL.md`'s own rule that personal data is minimized.

## 9. Session Management

- **Unchanged mechanism:** httpOnly/sameSite/secure cookie holding an opaque session id — already correct, no change to the transport.
- **Add:** move session storage from in-memory to the Prisma/MySQL-backed store proposed in §12, so sessions survive a restart and can be queried/revoked centrally.
- **Add:** a "sign out of all devices" action (revoke all sessions for a `userId`), not just the current one — today's `logout()` only revokes a single session by id.
- **Add:** confirm active `expiresAt` enforcement inside `validateSession` (the field exists; active expiry checking should be verified, not assumed) plus a sliding-vs-fixed expiry policy decision (not decided here).

## 10. Password Recovery

Not implemented today.

- **Flow:** user submits their contact value → system issues a single-use, short-lived (recommend 1h) reset token if — and only if — an account exists, but **always returns the same generic response either way** ("if an account exists, a reset link has been sent") to prevent account enumeration.
- **Reset completion:** token validated, new password set through the existing `PasswordAuthProviderAdapter.hash()`, all existing sessions for that user revoked (forces re-login everywhere), and a `user.password_reset` audit event recorded, matching the existing pattern in `identity-service.ts`.
- **Data model need:** a token-storage entity, likely shared with §11 rather than duplicated (a single `VerificationToken` entity distinguishing `purpose`).

## 11. Email Verification

Not implemented today (`User.emailVerified` exists as a field but nothing ever sets it).

- **Flow:** on registration (or on adding/changing an email `ContactPoint`), issue a single-use, time-limited (recommend 24h) verification token, emailed via a link to `/[locale]/verify-email?token=...`. On visit, the token is validated (exists, unexpired, unused), `emailVerified` is set `true`, and the token is invalidated.
- **Resend policy:** rate-limited (e.g., 1 request/minute/account) to prevent email-bombing a third party's inbox.
- **Never blocks core account use** unless the Owner later decides unverified accounts should be restricted from a specific action (e.g., booking) — a business-policy decision, not assumed here.
- **Data model need:** tokens must be hashed at rest (store a hash, not the raw token), mirroring the existing password-hash discipline — never store a usable raw token.

## 12. Prisma/MySQL Data Requirements

**Blocked on the Governing Constraint above.** Proposed entities are a direct, minimal-field mapping of the already-existing in-memory TypeScript contracts — no new field is invented beyond what the current code already models, so the eventual `DATA_MODEL.md` amendment should be a narrow, easy-to-review addition, not a redesign.

| Proposed entity | Mirrors | Key fields |
|---|---|---|
| `User` | `src/types/identity.ts` `User` | id, displayName, emailVerified, phoneVerified, status, createdAt |
| `Credential` | `PasswordCredential` | userId, passwordHash, passwordSalt, updatedAt |
| `LinkedIdentity` (new, §7) | — | id, userId, provider (`password`\|`google`\|`apple`\|`phone_otp`), providerAccountId, linkedAt |
| `Session` | `Session` | id, userId, createdAt, expiresAt |
| `VerificationToken` (new, §10–11) | — | id, userId, purpose (`email_verification`\|`password_reset`), tokenHash, expiresAt, usedAt |

- No `role` field is proposed on `User` yet, per §2.
- No relation is proposed as an enforced Prisma foreign key beyond what `DATA_MODEL.md` already permits (IDs as references, not FKs) — consistent with the existing schema's stated philosophy.

## 13. Booking/Customer Portal Integration

Largely already wired at the domain level — this section connects what exists, it does not redesign it:

- `BookingRequest.customerId`, `QuoteRequest.customerId`, `Enquiry.customerId` already exist (`DATA_MODEL.md` v0.3).
- Once `User` is a real, persisted entity (§12), `User.id` becomes the value stored in those `customerId` fields — the account dashboard (`src/app/[locale]/account/*`) already reads/writes through this shape today against the in-memory store; moving to Prisma is a persistence-layer swap, not a new customer-linkage design.
- No change to `CRM_AND_PORTALS.md`'s stated Customer Portal Minimum — this plan is exactly how that minimum gets satisfied technically.

## 14. Security Requirements

Consolidated from every section above, plus baseline items from `99_STANDARDS/SECURITY_STANDARD.md` (least privilege, no secrets in source control or documentation):

1. **Rate limiting/lockout** on login, registration, password-reset request, and email-verification-resend (§3–4, §10–11) — the single largest concrete gap versus the current implementation.
2. **No account enumeration** — password reset and (recommended) login error messages must not reveal whether a given contact value is registered.
3. **OAuth/OIDC correctness:** PKCE for Google's authorization code flow, `state` parameter against CSRF on the callback, and (for Apple) proper ID-token signature/audience/issuer verification — not "decode and trust the JWT."
4. **Secrets never in either repository** — Google Client Secret, Apple private key, session-signing key: environment variables injected at deploy time only, matching the existing `.env`/`.env.example` discipline and the app's `scripts/check-no-secrets.mjs` CI gate.
5. **Token hashing at rest** for verification/reset tokens (§10–11), mirroring existing password-hash discipline.
6. **CSRF protection** on all state-changing, cookie-authenticated routes — verify `sameSite=lax` coverage remains sufficient once OAuth redirect-based flows (top-level GET callbacks) are added; every state-changing POST after that still needs its own check.
7. **Audit logging extended, not replaced** — add `user.email_verified`, `user.password_reset`, `user.identity_linked`, `user.identity_unlinked`, `user.login_locked_out` alongside the existing `user.registered`/`user.login`/`user.logout`/`user.profile_updated`.
8. **Least privilege for the OAuth apps themselves** — request only `openid email profile` scope from Google/Apple; no broader scope without a named, approved business reason.

## 15. Future AI/Customer Portal Expansion

- Per `AGENT_REGISTRY.md`'s governed-agent model, any future AI agent acting on a customer's behalf (e.g., checking booking status) goes through the same typed, permissioned API routes a human session would use — never a separate, looser "AI-only" data path, mirroring the principle already stated for content in `04_CONTENT_INTEGRATION_PLAN.md` §6.
- Any AI access to customer data is consent-gated through the existing `Consent` entity, not a new bypass — an agent reading booking history on a customer's behalf still needs that customer's session/authorization context, not a service-account "read everything" credential.
- The Owner/Admin role gap noted in §2 would need its own design pass before an Owner Dashboard (`CRM_AND_PORTALS.md`) could authenticate anyone — not assumed or designed here.
- This is a forward-looking note, not a design commitment — the actual AI/portal integration is future scope per `PROJECT_ROADMAP.md`/`CURRENT_PROJECT_STATUS.md` and gets its own bounded architecture step when actually started.

---

## Proposed Rollout Phasing (sequencing only — no phase is authorized to start by this document)

1. **Harden existing password auth:** rate limiting, email verification, password reset, move session/credential storage to Prisma/MySQL (local/CI only) — closes the biggest current gaps without adding any new provider or credential.
2. **Google OAuth:** requires the Owner to provision a Google Cloud OAuth app (`A4`) and approval of the new token-verification dependency, before any code is written.
3. **Apple Sign In:** requires an active Apple Developer Program membership and Services ID (`A4`), after Google is stable.
4. **Owner/Admin role and portal/AI integration deepening** (§2, §15) — only after the above are live and stable.

Each phase requires its own explicit Owner approval before implementation begins, per `AUTONOMY_AND_APPROVAL_MATRIX.md` and this task's rule not to add providers or credentials yet.

## What This Document Does Not Do

- Does not add any npm dependency, provider SDK, or OAuth library.
- Does not register an application with Google or Apple, or generate/store any client secret or private key.
- Does not create or modify `prisma/schema.prisma` — blocked on the `DATA_MODEL.md` amendment named above.
- Does not write any authentication route, component, or test.
- Does not authorize any phase above to begin.

---

## Related Documents

- `08_DIGITAL_SYSTEMS/DATA_MODEL.md`
- `99_STANDARDS/SECURITY_STANDARD.md`
- `08_DIGITAL_SYSTEMS/CRM_AND_PORTALS.md`
- `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`
- `00_GOVERNANCE/AGENT_REGISTRY.md`
- `01_APPLICATION_ARCHITECTURE.md`
- `06_DEPLOYMENT_PLAN.md`
- `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md`
