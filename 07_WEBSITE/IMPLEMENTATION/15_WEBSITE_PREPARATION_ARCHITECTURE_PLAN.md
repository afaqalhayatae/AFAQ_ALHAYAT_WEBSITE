# Website Preparation Architecture Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — architecture/requirements only. No code, component, route, or website file is created or modified by this document.
- **Version:** 1.0
- **Prepared:** 2026-08-02
- **Relationship to existing documents:** This is a synthesis and gap-fill document, not a replacement. `NAVIGATION_ARCHITECTURE.md`, `12_SERVICE_EXPANSION_ROADMAP.md`, `13_LOCATION_EXPANSION_ROADMAP.md`, `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`, and `10_MARKETING_AND_SEO/URL_AND_INTERNAL_LINKING_STANDARD.md` already cover most of what's requested — each section below states what already exists, what's stale, and what's genuinely new (mainly §5–§6).
- **Depends on:** `00_GOVERNANCE/SERVICE_MASTER_MATRIX.md`, `PROJECT_EXECUTION_STATUS_REPORT.md`, `10_MARKETING_AND_SEO/LOCAL_SEO_MASTER_PLAN.md`, `06_CUSTOMER_AND_SALES/BOOKING/`, `09_AI_KNOWLEDGE/CONVERSATIONAL_ASSISTANT_STANDARD.md`.

---

## 1. Service Architecture

**Already solved at the code level:** per `12_SERVICE_EXPANSION_ROADMAP.md` §0 (verified, not stale on this point), `src/app/[locale]/services/[slug]/page.tsx` already generates a route for every catalog service dynamically. Adding a service to `SERVICE_DATABASE.json` does not require a new route.

**What's actually gating readiness is content, not architecture** — confirmed by `SERVICE_MASTER_MATRIX.md`: 16 of 27 services are content-complete and live; 11 are structural-only (`noindex`) purely because page content doesn't exist yet, not because of any code gap.

**Stale reference flagged:** `12_SERVICE_EXPANSION_ROADMAP.md` and `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` were written for the original 12-service catalog (2026-07-28) and group services as Maintenance(8)/Cleaning(3)/Pest Control(1). `SERVICE_MASTER_MATRIX.md` (this session) has the current 19/7/1 = 27 grouping. Both documents' *frameworks* (keyword categories, image requirements, page-requirement pattern) remain valid and reusable — only their service *counts and rows* need extending, which is an Owner-authorized documentation update, not performed here.

---

## 2. Location Architecture

**Already approved, partially built:** all 7 emirates are approved at emirate level (`SERVICE_AREAS.md`); only Dubai has a live page (`13_LOCATION_EXPANSION_ROADMAP.md`'s own verified current-state note, still accurate). Per that same document, adding each remaining emirate is architecturally trivial (dynamic `[slug]` route already exists; the app's own code comment calls it "a one-line addition, no route changes required").

**New in this session:** `LOCAL_SEO_MASTER_PLAN.md` defines the Service+City page tier that sits *below* the emirate page — this did not exist as an architecture before this directive. See that document for the full page-hierarchy, required-elements, and sequencing detail; not repeated here.

---

## 3. Internal Linking Structure

`URL_AND_INTERNAL_LINKING_STANDARD.md` already sets the governing rules (stable slugs, no invented terms, one trailing-slash policy). `04_CONTENT_INTEGRATION_PLAN.md` §5 (referenced by `NAVIGATION_ARCHITECTURE.md`) already defines the service↔location internal-linking pattern.

**Extension needed, not a new policy:** `LOCAL_SEO_MASTER_PLAN.md` §5 element 6 restates the same linking rule scaled to the current 27-service/7-emirate matrix (bidirectional emirate↔service↔city links, no orphan pages). No new linking rule is introduced here — this section exists only to confirm the existing standard already covers the expanded catalog without modification.

---

## 4. Navigation Requirements

`NAVIGATION_ARCHITECTURE.md` (prepared 2026-08-01, i.e., *after* `DECISION_LOG` #38/#39) is **not stale** — it explicitly draws menu content dynamically from `SERVICE_CATALOG.md` and `SERVICE_AREAS.md` rather than hardcoding a service count, and explicitly excludes any catalog entry "not yet ready for public linking." No change to that document is needed or made here. Confirmed by direct re-read this session.

---

## 5. Booking Integration Requirements (new ground)

`06_CUSTOMER_AND_SALES/BOOKING/BOOKING_PROCESS_DRAFT.md` defines the **customer-facing process** (channels, no availability/price/response-time promise). No document yet defines what the **website needs to send/receive** to support that process. This section is architecture-level requirements only — no booking system is built or selected here.

| Requirement | Detail | Depends on |
|---|---|---|
| Service + emirate selection | Booking form must read from `SERVICE_CATALOG.md` (only content-complete, live services selectable) and `SERVICE_AREAS.md` (only approved emirates) — never a hardcoded list that could drift from either registry | `SERVICE_MASTER_MATRIX.md` for current eligibility |
| No availability promise on the website itself | Per `BOOKING_PROCESS_DRAFT.md`'s explicit constraint, the booking UI must not display or imply confirmed date/time availability until an operator/CRM confirms it — a form submission, not an instant-booking widget, until a real scheduling backend exists | `08_DIGITAL_SYSTEMS/README.md`'s `CRM/` (planned, not yet populated) |
| Data captured | Service ID, emirate/location ID, contact method, task description — no price, discount, or commercial-term field until `06_CUSTOMER_AND_SALES/PRICING/` is approved for publication | `PRICING/`, `POLICIES/` (both gated) |
| Routing | Submitted requests route to `sales@afaqalhayatae.com` (per `08_DIGITAL_SYSTEMS/INTEGRATIONS/EMAIL_SYSTEM_FOUNDATION.md`, this session) until a CRM inbox exists | `EMAIL_SYSTEM_FOUNDATION.md` |
| Consent | Any follow-up marketing use of a booking-form contact requires the same consent capture `EMAIL_MARKETING.md` already mandates — a booking submission is not itself marketing consent | `EMAIL_MARKETING.md` |

**Not resolved by this document:** which booking/scheduling backend is used, real-time calendar integration, and payment collection — all depend on technology decisions not yet made (`TECH_STACK.md`), consistent with why `08_DIGITAL_SYSTEMS/` is mostly still a planned structure.

---

## 6. Chatbot Requirements (new ground)

`09_AI_KNOWLEDGE/CONVERSATIONAL_ASSISTANT_STANDARD.md` already defines the assistant's **product behavior** (bilingual, must disclose it's AI, must escalate to a human-review path, capability boundaries). This section adds the **website-integration-specific** requirements that standard doesn't cover:

| Requirement | Detail |
|---|---|
| Mount point | Persistent widget, available site-wide (not just on service pages), consistent with the "clear route to submit a request for owner review" requirement already in `CONVERSATIONAL_ASSISTANT_STANDARD.md` §1 |
| Data scope | May read only `Approved`/live content — the same 16 content-complete services, current `SERVICE_AREAS.md` coverage, and each service's own approved FAQ. Must not surface the 11 structural-only services as available, and must not answer from `SOURCE_DRAFT.md` or any Draft-status file, per `ANSWER_POLICY.md`'s existing rule (not restated in full here) |
| Escalation | Any question outside approved content (price, warranty, licensing, exact response time) routes to the same human-review path as `CONVERSATIONAL_ASSISTANT_STANDARD.md` §1 already requires — not answered, not guessed |
| Relationship to future agents | This is the production surface the future **Customer Support Agent** (`08_DIGITAL_SYSTEMS/AUTOMATION/AI_AGENT_FUTURE_SYSTEM.md`, this session) would eventually operate through — that agent does not exist yet; the chatbot described here is the standard's already-approved architecture, implementation pending |
| Booking handoff | Chatbot may direct a user into the booking flow (§5) but must not itself confirm availability or price, for the same reason the booking UI can't (§5 row 2) |

---

## 7. Summary of What's Genuinely New vs. Already Covered

| Area | Status |
|---|---|
| Service architecture | Already solved (code); content is the gap, not architecture. No new document needed beyond flagging staleness in row counts. |
| Location architecture | Already approved/partially built; this session's `LOCAL_SEO_MASTER_PLAN.md` adds the missing City-page tier. |
| Internal linking | Already governed; scaled, not changed. |
| Navigation | Already current — no gap found. |
| Booking integration requirements | **New** — first time these are stated as website-integration requirements rather than customer-facing process only. |
| Chatbot requirements | **New** — first time website-integration specifics are stated beyond the existing product standard. |

---

## What This Document Does Not Do

- Does not create, modify, or scaffold any application code, route, or component.
- Does not modify `NAVIGATION_ARCHITECTURE.md`, `BOOKING_PROCESS_DRAFT.md`, `CONVERSATIONAL_ASSISTANT_STANDARD.md`, or any other existing file.
- Does not select a booking backend, CRM, or chatbot vendor/technology.
- Does not stage, commit, or push anything.

---

## Related Documents

- `07_WEBSITE/NAVIGATION_ARCHITECTURE.md`, `IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md`, `13_LOCATION_EXPANSION_ROADMAP.md`, `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`, `04_CONTENT_INTEGRATION_PLAN.md`
- `10_MARKETING_AND_SEO/URL_AND_INTERNAL_LINKING_STANDARD.md`, `LOCAL_SEO_MASTER_PLAN.md`
- `06_CUSTOMER_AND_SALES/BOOKING/BOOKING_PROCESS_DRAFT.md`
- `09_AI_KNOWLEDGE/CONVERSATIONAL_ASSISTANT_STANDARD.md`, `ANSWER_POLICY.md`
- `08_DIGITAL_SYSTEMS/INTEGRATIONS/EMAIL_SYSTEM_FOUNDATION.md`, `AUTOMATION/AI_AGENT_FUTURE_SYSTEM.md`
- `00_GOVERNANCE/SERVICE_MASTER_MATRIX.md`, `PROJECT_EXECUTION_STATUS_REPORT.md`
