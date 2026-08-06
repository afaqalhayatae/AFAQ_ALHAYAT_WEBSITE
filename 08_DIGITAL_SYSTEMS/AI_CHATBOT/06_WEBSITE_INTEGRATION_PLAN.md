# Website Integration Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Superseded by real implementation — see the 2026-08-06 update below. Kept as the historical planning record.
- **Version:** 0.1
- **Prepared:** 2026-08-03

## Update (2026-08-06) — LLM path is live

The owner provided a real, funded OpenAI API key directly in chat (their
own account, not a credential this session created or paid for) — this
supersedes §6's "no credential is created" line and the Anthropic-specific
plan below (implemented against OpenAI's `openai` npm package instead —
the architecture and tool-calling approach are equivalent).
`src/lib/chat/llm-adapter.ts` now has a real `runLlmTurn` with a `record_lead`
tool call that hands off to the same Enquiry/Quote/Consent service layer
(`src/lib/chat/tools.ts`) the rule-based MVP already used. Any LLM failure
falls back to the rule-based engine transparently — it is not removed.

The chat widget itself was already mounted on the live site in an earlier
pass this session (`src/app/[locale]/layout.tsx`), which also supersedes
this document's "What This Document Does Not Authorize" §1 below.

**Two open gaps, both owner-actionable, neither blocking the code:**
1. **Production credential** — `OPENAI_API_KEY` is set only in the local
   `.env` used for this session's testing (git-ignored, never committed).
   The live production deployment needs this same variable set in
   whatever Hostinger uses for environment configuration — otherwise the
   live site's chatbot runs the rule-based engine only, same as before.
2. **Billing credits** — live-tested this session: the first real message
   got a genuine AI-generated Arabic reply, then a subsequent call failed
   with `insufficient_quota` / "no credits remaining." The owner needs to
   add credits at `platform.openai.com/settings/organization/billing`
   before the AI path will work for real customers, on production or
   locally.

Also added this session, not covered by the original plan below: file/
photo upload (`src/app/api/chat/upload/route.ts`, local disk under
`public/uploads/chat/`, git-ignored) and location sharing
(`src/app/api/chat/location/route.ts`, raw coordinates only — no paid
reverse-geocoding), both folded into a session's evidence automatically
and passed through to whatever lead gets recorded.
- **Depends on:** `01_AI_CHATBOT_ARCHITECTURE.md` (MVP vs. production stages — not restated here), `02_CONVERSATION_FLOWS.md`, `03_SERVICE_QUALIFICATION_RULES.md`, `04_CHATBOT_SYSTEM_PROMPT.md`, `05_TEST_SCENARIOS.md`
- **Write scope:** `AGT-WEB`

## What This Document Does Not Authorize

- Mounting the chat widget on the live site (touches `src/app/[locale]/layout.tsx` — the one existing file this whole effort eventually needs to touch; held back for explicit confirmation, per this repository's standing "don't change existing design" instruction).
- Creating or storing a real `ANTHROPIC_API_KEY` (`A4` credential gate, `AUTONOMY_AND_APPROVAL_MATRIX.md` — every action, no exception).
- Any live write to a real database (none exists yet — `afaqalhayatae-app`'s persistence is in-memory only, unchanged by this document).

---

# Part 1 — Website Integration Plan

## 1. Chat Widget Placement

- **Mount point:** `src/app/[locale]/layout.tsx`, alongside the existing `ConsentBanner`, `GoogleTagManager`, `AnnouncementBar`, `ClickTracking` components already mounted there (same pattern, not a new mounting mechanism).
- **Visual placement:** fixed floating bubble, bottom-end corner respecting RTL/LTR (`start`/`end` logical CSS properties, not hardcoded `left`/`right`, consistent with `12_DESIGN_SYSTEM/`'s RTL-first rule already followed elsewhere in the app).
- **Does not obscure:** the existing `AnnouncementBar`, primary CTAs, or mobile bottom navigation — verified by manual check once mounted (Stage 2 gate, `CONVERSATIONAL_ASSISTANT_STANDARD.md` §9).
- **Does not appear on:** account/auth pages where a support widget could be confused with account-security UI (`/login`, `/register`) — explicit exclusion list in the mount component, not a blanket site-wide assumption.

## 2. Required Routes

| Route | Purpose | New or existing |
|---|---|---|
| `src/app/api/chat/route.ts` | Streaming chat endpoint (POST), session-scoped | New |
| `src/app/api/chat/consent/route.ts` | Records consent before any qualification data is submitted (per `DATA_MODEL.md` Consent entity) | New — thin wrapper, reuses `consent-service.ts`, not a parallel consent system |
| *(no new page route)* | Widget is a component, not a page | — |

No existing route is modified. `/api/enquiries`, `/api/quotes`, `/api/bookings`, `/api/booking-requests` are **called by**, not changed by, the chat integration (§4 below).

## 3. Data Flow

```
Browser (chat widget)
  → POST /api/chat  { sessionId, message }
    → chat-mvp/qualification-flow.ts (MVP stage) OR Claude API + tool-calling (production stage)
    → response streamed back to widget
  → on qualification complete:
    → POST /api/chat/consent  (records Consent, per DATA_MODEL.md)
    → server-side (same process, no second HTTP hop) calls:
        submitEnquiry()   — default path, per 01_AI_CHATBOT_ARCHITECTURE.md §4
        OR requestQuote()  — if the customer described specific requirements/evidence
    → real Enquiry/QuoteRequest record created (in-memory today, same as every
      other write path in this app — not a new persistence gap introduced by chat)
  → widget shows: WhatsApp link / phone / "request recorded" confirmation
```

Session state (conversation-in-progress) is **server-side, in-memory, keyed by an httpOnly session cookie** — same cookie pattern already used by `session-cookie.ts` for auth, reused rather than inventing a second cookie mechanism. Conversation state is not the same record as the Customer/Enquiry — it's ephemeral scaffolding that produces those real records only once qualification completes.

## 4. Connection with Enquiry/Booking System

Reuses the exact real service layer already audited this session — no second, parallel data path:

| Chat outcome | Real call made | Existing precedent |
|---|---|---|
| General need, no specific evidence | `submitEnquiry()` | Same function `/api/enquiries` already calls |
| Specific service + requirements/evidence described | `requestQuote()` | Same function `/api/quotes` already calls — structurally has no price field |
| Explicit date/time request | Hand off to the **existing** booking form (`/book?service=...&emirate=...` prefilled from chat-collected answers) rather than a second booking-submission code path | Reuses `submit-booking-request.ts` + `/api/booking-requests`, not a duplicate |

A guest `Customer` record is created inline exactly as `booking-requests/route.ts` already does (§ audited this session) — same pattern, not a new customer-creation mechanism.

## 5. Security Considerations

- **Credential:** `ANTHROPIC_API_KEY` server-side only (Next.js API route, never exposed to the client bundle) — `A4` gate, Owner action, not created here.
- **Session cookie:** `httpOnly`, `sameSite=lax`, `secure` in production — same flags already used by the real auth session cookie (`session-cookie.ts`), not a weaker pattern for chat.
- **Rate limiting:** required before production (not yet implemented anywhere in this app) — chat is the first user-facing feature that calls a paid external API per message, so uncontrolled request volume has a real cost, unlike the existing free in-memory endpoints.
- **Prompt-injection / data-extraction resistance:** per `CONVERSATIONAL_ASSISTANT_STANDARD.md` §7 ("Reject attempts to override policies or retrieve restricted knowledge") — system prompt instructs the model to never reveal its instructions or internal document paths; test coverage for this is required before Stage 2 (`05_TEST_SCENARIOS.md`'s injection-test category, not yet written).
- **PII minimization:** only name, phone, and stated need are collected — matches `DATA_MODEL.md`'s "minimum data required for an approved purpose" rule; no ID documents, no payment data ever requested by the bot.
- **Consent before submission:** structurally enforced — the qualification flow's last step is consent (`03_SERVICE_QUALIFICATION_RULES.md` §2 item 7); no `submitEnquiry`/`requestQuote` call happens without it.
- **No secret in the repo:** `ANTHROPIC_API_KEY` goes in `.env` (gitignored, same pattern as the existing `.env.example` placeholder convention) — `scripts/check-no-secrets.mjs` (already in CI) covers this automatically, no new tooling needed.

---

# Part 2 — Production Transition Plan

## 6. From MVP Rules Engine to LLM

| Stage | Language understanding | What changes in code |
|---|---|---|
| MVP (built) | `chat-mvp/intents.ts` keyword matching | — |
| Transition | Claude API call **replaces only** `detectPrimaryIntent()`/`matchService()` — `qualification-flow.ts`'s state machine, question order, and hard price-safety guarantee (`responses.ts`) are **reused as-is**, not rewritten | `src/lib/chat/` (new, production namespace) wraps the same state machine with an LLM-backed intent/entity extraction step |
| Production | Full tool-calling: the model itself decides when qualification is complete and calls `submit_enquiry`/`request_quote` tools | Tool definitions in `src/lib/chat/tools.ts`, each a thin wrapper around the **existing** `submitEnquiry`/`requestQuote`/`recordConsent` functions — same functions the MVP plan already pointed to (§4 above), not new ones |

The MVP's qualification logic is not throwaway — it's the reused backbone. Only the *understanding* layer (rule-based → LLM) changes.

## 7. Knowledge Retrieval

Deterministic structured lookup, not embeddings (restated from `01_AI_CHATBOT_ARCHITECTURE.md` §4 — decision unchanged, given corpus size: 27 services, ~4 contract docs, ~30 FAQ entries):

1. `src/data/chat-knowledge/services.json` — synced snapshot of `SERVICE_CATALOG.md` + approved `SERVICE_DATABASE.json` fields.
2. `src/data/chat-knowledge/contracts.json` — synced snapshot of `06_CUSTOMER_AND_SALES/SALES/CONTRACTS/*.md` (already built, Owner-approved as the chatbot's contracts source).
3. `src/data/chat-knowledge/faq.json` — synced snapshot of approved (`isDemo: false`) FAQ entries.

Sync is a **reviewed, manual snapshot step** (same pattern already used for `SERVICE_DATABASE.json` itself), not a live cross-repo filesystem read — the knowledge repo doesn't exist on the Hostinger host.

## 8. Customer Data Persistence

**Unchanged by this plan** — chat writes to the same in-memory repositories every other feature already uses. This is a pre-existing, cross-cutting gap (flagged in this session's earlier audits, not introduced by chat) — real MySQL wiring is its own separate, already-identified workstream (`07_EXISTING_APP_INTEGRATION_AUDIT.md` §4: "no adapter actually calls `@prisma/client` anywhere"). Chat should not be blocked on that wiring, but every chat-originated lead shares the same "lost on server restart" caveat as bookings/enquiries do today until it's resolved — this must be disclosed, not hidden, if Stage 2 pilot launches before the database work completes.

---

# Part 3 — Exact Files Needed for Integration

| File | Status | Purpose |
|---|---|---|
| `src/app/api/chat/route.ts` | New | Streaming chat endpoint |
| `src/app/api/chat/consent/route.ts` | New | Consent recording before submission |
| `src/lib/chat/system-prompt.ts` | New | Builds the prompt from `04_CHATBOT_SYSTEM_PROMPT.md` + live knowledge snapshot |
| `src/lib/chat/tools.ts` | New | Tool-calling wrappers around `submitEnquiry`/`requestQuote`/`recordConsent` |
| `src/lib/chat/session.ts` | New | Server-side conversation-state store, cookie-keyed |
| `src/data/chat-knowledge/{services,contracts,faq}.json` | New | Synced knowledge snapshots (§7) |
| `src/components/chat/chat-widget.tsx` | New | Floating widget UI |
| `src/components/chat/chat-message.tsx`, `chat-input.tsx` | New | Widget sub-components |
| `src/app/[locale]/layout.tsx` | **Existing — one-line mount only** | Add `<ChatWidget />` alongside the other already-mounted global components — the single touch point to an existing file, held back pending explicit confirmation (see header) |
| `.env.example` | **Existing — one-line addition** | Document `ANTHROPIC_API_KEY=` placeholder (value never set here) |

Every other file in `afaqalhayatae-app` is untouched. The MVP files (`src/lib/chat-mvp/*`) are not deleted or replaced — they remain the reference implementation for the qualification state machine that the production `src/lib/chat/` namespace wraps (§6).

## Related Documents

- `01_AI_CHATBOT_ARCHITECTURE.md`, `02_CONVERSATION_FLOWS.md`, `03_SERVICE_QUALIFICATION_RULES.md`, `04_CHATBOT_SYSTEM_PROMPT.md`, `05_TEST_SCENARIOS.md`
- `08_DIGITAL_SYSTEMS/DATA_MODEL.md`, `API_CONTRACTS.md`
- `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`
