# Existing Application Integration Audit

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — read-only audit findings, requires Owner review
- **Version:** 1.0
- **Prepared:** 2026-07-27
- **Audited target:** `~/Documents/GitHub/afaqalhayatae-app` (local path, outside both repositories referenced by this document)
- **Method:** Read-only inspection of git history, source tree, and configuration. No code was modified, staged, or committed in either repository during this audit.

## Why this document exists

`00_PHASE1_APPROVAL.md` and `DECISION_LOG.md` decision 35 were written on the premise — inherited from `DECISION_LOG.md` decision 34 and `CURRENT_PROJECT_STATUS.md` — that website implementation had not started. That premise is false. A working application already exists, git-initialized, with 20 commits progressing through milestones **M0 → M4.6** (identified by commit messages using job-ID prefix `JOB-AGT-WEB-20260726-*`), built by a prior agent session working from this same knowledge repository. This document records what that application actually contains, so `00_GOVERNANCE/IMPLEMENTATION_STATUS_CORRECTION.md` can correct the governance record against reality instead of the other way around.

---

## 1. Git History

20 commits, all dated 2026-07-26, on branch `main`:

| Commit | Milestone | Summary |
|---|---|---|
| `92918d9`→`1166ce3` | M0 / M0.1 | Testing foundation, CI pipeline, secret-scan script, in-memory adapters, foundation hardening |
| `8ab3e3d` | M1 | Provisional domain foundation and Prisma schema |
| `8787a1a` | M1 | Provisional application service layer and domain rules |
| `42512df` | M1.2 | Align domain model with approved `DATA_MODEL.md` v0.2 |
| `e581d82` | M1.3 | API boundary layer over application services |
| `690d2c1` | M2 | Website experience layer (header, footer, home, services, contact) |
| `beeeb27` | M2.1 | Identity layer foundation (login/register, session, password auth) |
| `2fd2c6c` | M2.2/M2.3 | Customer dashboard and ownership linkage |
| `d795e3a` | M2.4 | Wire customer dashboard bookings and quotes |
| `345ac14`, `12a3c44` | M3, M3.1 | Premium brand & visual experience, brand scene illustrations |
| `478bc87` | M4.1 | SEO services and locations architecture (sitemap, hreflang, catalog) |
| `97bb2c1` | M4.2 | Content and conversion foundation |
| `7399a14` | M4.3 | Blog and SEO content engine |
| `673d2d1` | M4.4 | Legal and trust foundation (privacy/terms/cookies, reviews) |
| `610ea58` | M4.5 | Premium visual media system and demo assets |
| `d3bd62a` | M4.6 | Marketing email and Google ecosystem foundation |

**Working tree at audit time:** 13 files modified, not committed (docs, tests, i18n messages, `reviews-section.tsx`, `catalog/blog.ts`, `media/demo-visuals.ts`). A real `.env` exists locally (gitignored, not committed; contents were not read by this audit).

Commit messages consistently cite this knowledge repository's canonical documents (`DATA_MODEL.md` v0.2/v0.3, `AUTONOMY_AND_APPROVAL_MATRIX.md`) as their authority, and the repo's own `docs/hostinger-migration-runbook.md` explicitly defers every credential/DNS/deletion action to the Owner. This is a governed continuation of this project, not an unrelated or rogue codebase.

---

## 2. Current Architecture

- **Stack as built:** Next.js `16.2.12` (App Router), React `19.2.4`, TypeScript, Tailwind CSS v4 (`@theme` tokens, not a `tailwind.config.ts`), Prisma `7.9.0` with `provider = "mysql"`, Vitest for tests, ESLint 9 flat config. No Prettier config found (not a stated requirement in this repo's own `TECH_STACK.md`).
- **Locale routing:** `src/middleware.ts` redirects unprefixed paths to `defaultLocale = "ar"`; `src/i18n/config.ts` declares `ar` (rtl) and `en` (ltr) — matches `01_APPLICATION_ARCHITECTURE.md` §4.
- **Layering:** `src/lib/services/*` (domain logic) → `src/lib/adapters/*` (repository interfaces + **in-memory implementations only**, no Prisma-backed adapter exists yet) → `src/app/api/*` (thin route handlers) → `src/app/[locale]/*` (pages). This is a clean hexagonal/ports-and-adapters shape, not the flatter structure `02_FOLDER_STRUCTURE.md` sketched — a reasonable evolution, not a defect, but the two documents now disagree on layout and should be reconciled.
- **Persistence reality:** `prisma/schema.prisma` mirrors `DATA_MODEL.md` v0.2/v0.3 field-for-field (see its own header comment: "schema-only, validated with `npx prisma validate` and nothing else"). Every repository actually wired into the services (`src/lib/adapters/in-memory/*`) is in-memory. **Nothing persists across a server restart today** — there is no live MySQL connection anywhere in the runtime path, only the schema definition.
- **Auth:** Node `crypto.scrypt` password hashing with per-user salt and `timingSafeEqual` comparison (`src/lib/adapters/password/password-provider.ts`); session id in an `httpOnly`, `sameSite=lax` cookie, `secure` gated on `NODE_ENV === "production"` (`src/app/api/auth/_lib/session-cookie.ts`). Session/user/credential storage is also in-memory only.

---

## 3. Implemented Features

- Public marketing pages: home, services index + `[slug]` + `[slug]/[location]`, locations index + `[slug]`, about, contact, FAQ, blog index + `[slug]`.
- Legal pages: privacy policy, terms and conditions, cookie policy (with a cookie-consent banner and cookie helper).
- Identity: register, login, logout, session endpoint, password hashing — in-memory only.
- Customer portal: account overview, profile, bookings, quotes, requests — pages plus matching `api/account/*` routes, gated by session ownership.
- Commercial-adjacent write paths: `api/bookings`, `api/quotes`, `api/enquiries`, `api/consents`, `api/approvals` (including a decision sub-route) — all backed by in-memory repositories, all modeled directly on `DATA_MODEL.md` entities.
- SEO: per-page `hreflang`/canonical generation (`src/lib/seo/metadata.ts`), a locale- and content-aware `sitemap.ts` that excludes non-indexable locations and `isDemo` blog posts, and JSON-LD/structured data present in the FAQ page, blog article page, reviews section (`AggregateRating`), and service content sections.
- Design tokens: `src/styles/tokens.css` transcribes `12_DESIGN_SYSTEM/{COLORS,TYPOGRAPHY,SPACING,GRID}.md` values verbatim, with a header comment instructing future editors not to hand-edit without updating the source doc first.
- Analytics/marketing scaffolding: Google Tag Manager loader and a consent banner, both inert until real `NEXT_PUBLIC_GTM_CONTAINER_ID`/`GOOGLE_SITE_VERIFICATION` values are supplied (currently unset).
- CI: GitHub Actions workflow runs lint, typecheck, test, a custom no-secrets scan (`scripts/check-no-secrets.mjs`), a non-blocking `npm audit`, and a production build on every push/PR to `main`.

---

## 4. Missing Features / Gaps

- **No live database.** Prisma schema exists and validates; no adapter actually calls `@prisma/client` anywhere in `src/`. Wiring a real MySQL-backed adapter set (still local/CI only, per the just-approved Phase 1 scope) is the largest remaining foundation gap.
- **6 of 7 approved emirates are missing.** `src/lib/catalog/locations.ts` contains only `LOC-AE-DU` (Dubai); `03_MARKET/SERVICE_AREAS.md` lists all seven emirates as `Active` with "All catalog services." Abu Dhabi, Sharjah, Ajman, Umm Al Quwain, Ras Al Khaimah, and Fujairah have no generated pages yet.
- **No environment-aware `robots.ts`/`robots.txt`.** `05_SEO_IMPLEMENTATION_PLAN.md` §1 calls for staging to disallow all crawling and production to allow the publishable set; no such file exists in this repo yet — only the sitemap's own content gating exists today.
- **No production credentials or deployment target confirmed** — consistent with, not a gap against, current governance (Hostinger deployment method, staging capability, and DNS/canonical-host configuration all remain open per `06_DEPLOYMENT_PLAN.md` and this repo's own `docs/hostinger-migration-runbook.md`).
- **No booking/quote commercial data** (pricing, packages, warranty) is modeled or rendered — correctly deferred, matching `04_CONTENT_INTEGRATION_PLAN.md` §3's Phase 1/2 hard block on commercial content.
- **Prettier** is not configured, despite being named in the Phase 1 requirements under discussion.

---

## 5. Alignment with `12_DESIGN_SYSTEM/*`

Strong alignment, and already consistent with `00_PHASE1_APPROVAL.md` decision 1 (before that decision existed): `src/styles/tokens.css` uses `12_DESIGN_SYSTEM/COLORS.md` values exactly (`#0f4c81`, `#16a34a`, `#f59e0b`, `#dc2626`, `#0ea5e9`, `#25d366`, `#f8fafc`, etc.) — **not** `02_BRAND/BRAND_COLORS.md`'s diverging values (no Gold `#D4AF37` accent token, no `#22c55e`/`#2563eb`/`#f5f7fa` alternates appear anywhere). Typography (`Noto Kufi Arabic` / Inter via `next/font`, `clamp()`-based scale), spacing (8px-multiple scale, custom-named to avoid colliding with Tailwind defaults), and grid breakpoints (768/1200/1440px) all match their respective source documents. No independent verification of every component against `12_DESIGN_SYSTEM/COMPONENTS.md`'s full inventory was performed in this pass.

---

## 6. Alignment with `04_SERVICE_KNOWLEDGE/*`

`src/lib/catalog/services.ts` lists exactly the 12 approved `SVC-` IDs from `SERVICE_CATALOG.md`, correctly structural-only (id/slug/category, no facts duplicated) with bilingual display strings deferred to i18n messages. Per-service content depth (methods, safety, FAQ) was not verified page-by-page in this pass — flagged as a follow-up, not asserted as complete or incomplete here.

---

## 7. SEO Implementation

`hreflang` + canonical generation, locale-aware sitemap with content-gating (`indexable` flag on locations, `isDemo` exclusion on blog posts), and JSON-LD on FAQ/blog/reviews/service-content pages are implemented and appear to follow `05_SEO_IMPLEMENTATION_PLAN.md`'s intent. Gaps: no `robots.ts`, and Organization/LocalBusiness schema (which per §2 of that plan should source from `COMPANY_PROFILE.md` + `CONTACT_INFORMATION.md`'s **approved fields only**) was not located in this pass — if it exists elsewhere it was not found by this audit's search; if it doesn't exist yet, it must not be added using the unverified contact facts flagged in Section 11 below.

---

## 8. Bilingual Support

`ar` (default, RTL) and `en` (LTR) are both routed and rendered; `src/i18n/messages/{ar,en}.json` are line-count-equal (631 lines each) as a structural signal of parity, though full semantic parity (same facts, not just same key count) was not independently re-verified here. RTL/LTR direction is applied per-locale via `:lang()` selectors in `tokens.css` and locale-prefixed routing throughout.

---

## 9. Booking / Customer Features

Full request/response plumbing exists for bookings, quotes, and enquiries, gated by session ownership on the customer-portal side and modeled on `DATA_MODEL.md` entities including `Approval` (with `targetType`/`targetId` binding per that document's rule against generic approvals). All of it currently runs against in-memory repositories only — no request submitted today would survive a server restart, and none reaches a real database, consistent with "no production credentials" but meaning this feature set is not yet usable beyond local development/testing.

---

## 10. Security Status

- `.env` is gitignored and not tracked; `.env.example` contains placeholders only with an explicit "never commit a real value" comment.
- `scripts/check-no-secrets.mjs` scans all git-tracked files for AWS keys, private-key headers, bearer tokens, and credentialed connection strings, and runs in CI on every push/PR.
- Session cookie is `httpOnly`, `sameSite=lax`, `secure` in production — not readable by client-side JavaScript.
- Passwords are hashed with `scrypt` (salted, per-user) and compared with `timingSafeEqual` — no plaintext or reversible storage.
- `npm audit` runs in CI but is explicitly non-blocking, with a dated comment explaining the 16 open advisories are only fixable via a `next`/`prisma` downgrade and are tracked for Owner-approved resolution rather than silently ignored or silently forced.
- No credential, DNS, or hosting action has been taken — `docs/hostinger-migration-runbook.md` is a checklist for the Owner, explicitly stating the agent that wrote it has no account access.

No hardcoded secret, API key, or production credential was found in any tracked file during this audit.

---

## 11. Critical Finding: Unverified Contact Facts Are Hardcoded and Publicly Rendered

This is the most significant finding in this audit and should be treated as **blocking any public deployment** until resolved by the Owner.

`src/lib/brand/links.ts` is labeled *"Owner-approved source of truth"* and hardcodes values that `02_BRAND/CONTACT_INFORMATION.md` and `02_BRAND/LOCAL_SEO_PROFILE.md` — this repository's own canonical sources — mark as **Pending / Owner Input Required**, not approved. These values are wired into `Header` and `Footer`, which render on every public page:

| Value | Rendered in app | Canonical source status |
|---|---|---|
| WhatsApp number/link | `WHATSAPP_URL` (`wa.me/...`), shown in header + footer, and `contact.info.whatsapp` i18n string set equal to the approved phone number | `CONTACT_INFORMATION.md`: *"Owner Confirmation Required. Do not assume that the approved phone number is also the official WhatsApp number."* — the app currently makes exactly that assumption. |
| Email | `contact.info.email` = `Info@afaqalhayatae.com`, rendered as a live `mailto:` link in the footer | `CONTACT_INFORMATION.md`: *"No official email address has been confirmed. Do not derive an email address from the approved domain."* — the value present is an `info@`-style address derived from the approved domain, which is the exact pattern the source document prohibits. |
| Physical address | `footer.address` = "Dubai - Oud Metha, Um Hurair Street - Al Makhawi Center" (ar/en), plus a `GOOGLE_MAPS_URL` link, rendered in the footer on every page | `LOCAL_SEO_PROFILE.md`: *"Address: Owner Input Required. No verified street address exists... Branch IDs: Owner Input Required. No branch structure has been defined yet."* |
| Working hours | `contact.info.hours` = "Saturday–Thursday, 9:00–19:00", rendered on the contact page | `CONTACT_INFORMATION.md`: *"Owner Input Required. Hours have not been verified."* |
| Social profile links | 8 platform URLs (Facebook, Instagram, TikTok, LinkedIn, X, Pinterest, Threads, YouTube) in `SOCIAL_LINKS`, rendered in the footer on every page | `CONTACT_INFORMATION.md`: *"Owner Input Required. Add only verified profile URLs."* |

This directly conflicts with `CURRENT_PROJECT_STATUS.md`'s **Hard Publication Blocks**, the first of which is *"Unverified contact or account details."* If this application were deployed to production as-is, every page would violate that block simultaneously via the shared header/footer.

**This audit takes no position on whether these values are real** (the Owner may already know the WhatsApp number, email, address, and social accounts are accurate and simply never updated `CONTACT_INFORMATION.md`/`LOCAL_SEO_PROFILE.md` to `Approved`) **or fabricated** by whatever process produced them. Per this repository's rule that conflicting or unverified canonical facts must be surfaced, not silently resolved in either direction, this is recorded as an open conflict for the Owner to close — either by confirming these exact values so the canonical documents can be updated to `Approved`, or by instructing that they be removed/blocked in the application until they are.

---

## 12. Open Questions for the Owner

1. Are the WhatsApp number, `Info@afaqalhayatae.com`, the Oud Metha address, the stated working hours, and the eight social profile URLs in `src/lib/brand/links.ts` and the i18n messages **real and confirmed**? If yes, `CONTACT_INFORMATION.md` and `LOCAL_SEO_PROFILE.md` should be updated to `Approved` to match. If no, they must be removed or blocked in the application before any further public-facing work continues.
2. Should `02_FOLDER_STRUCTURE.md` be revised to reflect the layered `services → adapters → api routes` architecture actually built, or should the existing app be restructured to match the earlier plan?
3. Is the existing in-memory-only persistence layer acceptable to continue building on for the remainder of Phase 1, with real MySQL wiring as the next bounded job — consistent with `00_PHASE1_APPROVAL.md` §2?
4. Should the remaining six emirate location pages be built next, or is Dubai-only intentional for a longer period?

---

## Related Documents

- `00_GOVERNANCE/IMPLEMENTATION_STATUS_CORRECTION.md`
- `00_PHASE1_APPROVAL.md`
- `01_APPLICATION_ARCHITECTURE.md`
- `02_FOLDER_STRUCTURE.md`
- `02_BRAND/CONTACT_INFORMATION.md`
- `02_BRAND/LOCAL_SEO_PROFILE.md`
- `08_DIGITAL_SYSTEMS/DATA_MODEL.md`
