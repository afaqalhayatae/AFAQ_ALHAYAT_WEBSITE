# Website Architecture Decision Report

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — decision request only. No decision is made by this document; every item below awaits explicit Owner approval.
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Last Updated:** 2026-08-01
- **Package:** `00_GOVERNANCE/`
- **Based on:** `00_GOVERNANCE/WEBSITE_EXPERIENCE_ARCHITECTURE_AUDIT_REPORT.md` §6 (Missing Items or Conflicts) and §7 (Implementation Readiness).

## Purpose

This document restates the 7 open conflicts/decisions identified in the website architecture audit, structured for Owner decision. No file was edited, no code touched, no asset changed, and no decision was made or implied by anyone other than the Owner. Each item lists the current conflict as documented, the decision required, what Owner approval would need to cover, and the resulting implementation impact once decided — presented neutrally, without a recommended option.

---

## 1. Homepage Lifecycle Status

**Current conflict:** Three sibling documents in `07_WEBSITE/01_HOMEPAGE/`, all version 1.0, disagree on lifecycle status: `00_HOMEPAGE_ARCHITECTURE.md` states Status = "In Review / Not for Implementation," while `02_HOMEPAGE_UI_UX.md` and `03_HOMEPAGE_SEO_AI.md` both state Status = "Build Phase."

**Decision required:** Which status is currently accurate — is the homepage specification ready to build against, or still under review? Should all three documents carry the same status, or is a per-document status difference intentional (e.g., architecture still under review while UI/UX and SEO specs are considered stable)?

**Owner approval needed:** Confirmation of the homepage's actual current status, and whether the three documents should be reconciled to state the same value.

**Implementation impact:** Determines whether any agent or developer may treat the homepage specification as build-ready today. Building against a "Build Phase" spec that the Owner still considers "In Review" risks implementing content or structure not yet actually approved.

---

## 2. Authentication Canonical Source

**Current conflict:** `07_WEBSITE/IMPLEMENTATION/01_APPLICATION_ARCHITECTURE.md` §5 describes authentication as an entirely open Phase-3 decision with no provider chosen. `07_WEBSITE/IMPLEMENTATION/08_AUTHENTICATION_ARCHITECTURE.md` (v1.1, same prepared date, same folder) is materially more advanced — it documents password authentication as already implemented in code, and a detailed 15-section plan for Google/Apple OAuth expansion with a 4-phase rollout.

**Decision required:** Which document reflects the Owner's understanding of current authentication status? Should `01_APPLICATION_ARCHITECTURE.md` §5 be updated to reference `08_AUTHENTICATION_ARCHITECTURE.md` instead of describing auth as fully undecided? Is the 4-phase rollout sequence in `08_AUTHENTICATION_ARCHITECTURE.md` (harden password auth → Google OAuth → Apple Sign In → Owner/Admin role) approved as the intended order?

**Owner approval needed:** Confirmation that `08_AUTHENTICATION_ARCHITECTURE.md` is the authoritative, current-state authentication document, and approval (or rejection) of its proposed rollout phasing — each phase still requires its own separate `A4` approval per that document's own text, so this is about the sequence, not authorizing any specific phase to begin.

**Implementation impact:** Determines which document future agents/developers should consult for authentication status. Leaving both documents live and disagreeing risks an agent building against the wrong picture — e.g., treating auth as untouched when password auth already exists, or assuming OAuth is farther along than it is.

---

## 3. Service Roadmap Source of Truth

**Current conflict:** `07_WEBSITE/IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md` (dated 2026-07-28) predates and does not reference three later `DECISION_LOG.md` entries — Decision 37 (2026-07-31, Pest Control publication approval + Gecko Control confirmation), Decision 38 (2026-07-31, Maintenance/Cleaning content authored, Deep Cleaning unblocked, 4 new Cleaning services added), and Decision 39 (2026-07-31, 11 new Maintenance services added). The roadmap's per-service status table (e.g., "Deep Cleaning — Blocked pending owner scope") no longer matches the Decision Log's later, more current record.

**Decision required:** Should `DECISION_LOG.md` be treated as the authoritative, current source for service-catalog and per-service publication status, with `12_SERVICE_EXPANSION_ROADMAP.md` understood as a historical snapshot? Or should the roadmap document itself be revised to incorporate the three later decisions and resume being the operational reference?

**Owner approval needed:** Confirmation of which document governs day-to-day service-status questions going forward, and — if the roadmap is to be kept current — approval to schedule that revision as separate work.

**Implementation impact:** Determines which document an agent should consult before doing any service-page content or imagery work. Using the stale roadmap as-is risks re-blocking already-unblocked work (e.g., treating Deep Cleaning as blocked when Decision 38 already resolved that) or omitting the 15 services added since the roadmap was written.

---

## 4. Location Architecture for Seven Emirates

**Current conflict:** All seven emirates are `Active` with "All catalog services" coverage in `03_MARKET/SERVICE_AREAS.md`'s Approved Registry, but only Dubai (`LOC-AE-DU`) has a generated location page today. The other six (Abu Dhabi, Sharjah, Ajman, Umm Al Quwain, Ras Al Khaimah, Fujairah) are registry-approved but have no page — confirmed independently by both `13_LOCATION_EXPANSION_ROADMAP.md` and `07_EXISTING_APP_INTEGRATION_AUDIT.md`. The latter document's own §12 already poses this as an open question to the Owner: "Should the remaining six emirate location pages be built next, or is Dubai-only intentional for a longer period?"

**Decision required:** Should the six remaining emirate pages be built next, and if so, in what priority order? What "genuine local content" (per `LUXURY_DESIGN_DIRECTION.md` §6 and `13_LOCATION_EXPANSION_ROADMAP.md` §2 — verifiable emirate-specific facts, locally relevant FAQs, or real cross-links) actually exists for each emirate to support publishing it?

**Owner approval needed:** A go/no-go on building the six pages, a priority order if approved, and per-emirate confirmation of what genuine local content is available (the roadmap explicitly states a page must not publish as a thin, name-swapped duplicate).

**Implementation impact:** Directly unblocks (or deliberately holds) the location-expansion content and SEO work. Without this decision, the six pages stay unbuilt indefinitely by default, and any Local SEO strategy premised on seven-emirate coverage remains only partially realized.

---

## 5. Navigation Structure Requirements

**Current conflict:** No dedicated navigation-structure document exists in `07_WEBSITE/`. "Main Navigation" appears only as an unelaborated sub-component label inside the Header component (`00_HOMEPAGE_ARCHITECTURE.md` §02, `04_HOMEPAGE_COMPONENTS.md` `CMP-002`) — no document lists the actual menu items, dropdown/submenu structure, or mobile-menu behavior.

**Decision required:** Should a dedicated navigation-structure document be created? What should the top-level navigation actually contain — which pages/services/locations appear directly, which are grouped under a dropdown, and how does the mobile menu differ (if at all)?

**Owner approval needed:** Approval to commission a navigation-structure specification, and the actual content decisions it would need (menu hierarchy, item labels, grouping logic).

**Implementation impact:** The Header component's Main Navigation element cannot be built completely or correctly today — only its existence as a labeled component is documented, not its content. This blocks a full, accurate Header implementation regardless of how many other homepage sections are ready.

---

## 6. Chatbot Architecture Requirements

**Current conflict:** No chatbot placement, UI position, or trigger-behavior documentation exists anywhere in `07_WEBSITE/`. The only reference within this domain is `07_WEBSITE/IMPLEMENTATION/00_PHASE1_APPROVAL.md`, which lists "chatbot" among live third-party integrations explicitly out of scope for Phase 1. A substantive conversational-assistant standard exists at `09_AI_KNOWLEDGE/CONVERSATIONAL_ASSISTANT_STANDARD.md`, but it is outside the website-architecture domain and does not itself specify website placement.

**Decision required:** Should chatbot placement/architecture now be planned within `07_WEBSITE/` (even if actual implementation stays deferred beyond Phase 1), or should it remain entirely out of scope until a later phase is explicitly opened? If planning is approved, should it be built on top of `09_AI_KNOWLEDGE/CONVERSATIONAL_ASSISTANT_STANDARD.md` as its foundation?

**Owner approval needed:** Confirmation of whether chatbot planning work should begin now, and if so, approval to commission a chatbot-architecture document referencing the existing conversational-assistant standard.

**Implementation impact:** Without this decision, no chatbot placement or UI decision — even at a documentation/planning level — can proceed. This is purely a scoping decision; it does not authorize any live chatbot integration, which remains separately gated by Phase 1's existing exclusion regardless of the outcome here.

---

## 7. Public Contact Information Approval Rules

**Current conflict:** Per `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md` §11 (restated, not re-verified, in the architecture audit's §6 item 9), the live application hardcodes and publicly renders on every page: a WhatsApp number/link, an `Info@afaqalhayatae.com` email, a physical address ("Dubai - Oud Metha, Um Hurair Street - Al Makhawi Center"), working hours ("Saturday–Thursday, 9:00–19:00"), and eight social profile links (Facebook, Instagram, TikTok, LinkedIn, X, Pinterest, Threads, YouTube). Every one of these values is marked `Pending`/`Owner Input Required` in the canonical sources (`02_BRAND/CONTACT_INFORMATION.md`, `02_BRAND/LOCAL_SEO_PROFILE.md`), not `Approved`. This directly conflicts with `CURRENT_PROJECT_STATUS.md`'s Hard Publication Block on "unverified contact or account details."

**Decision required, value by value:**
- Is the WhatsApp number/link accurate and approved?
- Is `Info@afaqalhayatae.com` the confirmed official email?
- Is the stated Oud Metha address accurate and approved for public display?
- Are the stated working hours (Saturday–Thursday, 9:00–19:00) confirmed?
- Which, if any, of the eight social profile links are real, owned, verified company accounts?

**Owner approval needed:** For each value above — either (a) confirm it is accurate, so `CONTACT_INFORMATION.md` and `LOCAL_SEO_PROFILE.md` can be updated to `Approved` to match what the app already renders, or (b) instruct that it be removed or blocked in the application until a confirmed value exists.

**Implementation impact:** Per the source audit, this is described as blocking any public deployment as-is — every page violates the Hard Publication Block simultaneously via the shared header/footer. Resolving this either (a) unblocks public deployment once canonical documents are brought into agreement with confirmed-accurate values, or (b) requires an application code change to strip/block each unconfirmed value before the site can be considered safe to publish.

---

## Summary Table

| # | Decision Point | Owner Approval Needed | Status |
|---|---|---|---|
| 1 | Homepage lifecycle status | Confirm current status; reconcile 3 documents | Awaiting decision |
| 2 | Authentication canonical source | Confirm authoritative document; approve/reject rollout phasing | Awaiting decision |
| 3 | Service roadmap source of truth | Confirm DECISION_LOG.md vs. roadmap as operational reference | Awaiting decision |
| 4 | Location architecture (7 Emirates) | Go/no-go + priority order + per-emirate content confirmation | Awaiting decision |
| 5 | Navigation structure requirements | Approve commissioning a nav-structure spec; provide menu content | Awaiting decision |
| 6 | Chatbot architecture requirements | Confirm whether planning should begin now | Awaiting decision |
| 7 | Public contact information approval rules | Confirm or reject each of 5 value categories | Awaiting decision |

No item above has been decided by this document. No file, code, or asset was modified to produce it.

---

## Related Documents

- `00_GOVERNANCE/WEBSITE_EXPERIENCE_ARCHITECTURE_AUDIT_REPORT.md` — source audit this report is based on.
- `00_GOVERNANCE/DECISION_LOG.md` — decisions 37, 38, 39 (item 3); future decision entries would record any resolution of the items above.
- `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md` — original source of item 7's finding.
- `02_BRAND/CONTACT_INFORMATION.md`, `02_BRAND/LOCAL_SEO_PROFILE.md` — canonical sources referenced in item 7.

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-08-01 | Initial decision report restating the 7 open conflicts from `WEBSITE_EXPERIENCE_ARCHITECTURE_AUDIT_REPORT.md` for Owner decision. No decision made, no file modified. |
