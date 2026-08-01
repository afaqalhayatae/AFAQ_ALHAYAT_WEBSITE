# Website Architecture Decision Update

## Document Information

- **Owner:** Business Owner
- **Status:** Approved — decisions recorded here are effective immediately upon this document's creation. Not yet applied to the underlying website/application files (see "Not Yet Done" under each item).
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Last Updated:** 2026-08-01
- **Package:** `00_GOVERNANCE/`
- **Resolves:** All 7 decision points from `00_GOVERNANCE/WEBSITE_ARCHITECTURE_DECISION_REPORT.md`.

## Purpose

Following the Owner's review of `WEBSITE_ARCHITECTURE_DECISION_REPORT.md`, this document records the Owner's decisions on all 7 open points. These decisions are effective immediately as governance record. **No website file, application file, or code was edited to implement them** — this is documentation only, per this task's explicit instruction. Applying these decisions to the underlying documents/code is separate, not-yet-executed follow-up work, itself still subject to normal approval gates where applicable (see §2 and §6 below in particular).

---

## 1. Homepage Lifecycle Status

**Decision:** Status = **Build Phase**. All three homepage documents (`00_HOMEPAGE_ARCHITECTURE.md`, `02_HOMEPAGE_UI_UX.md`, `03_HOMEPAGE_SEO_AI.md`) should be reconciled to state this same lifecycle status.

**Resolves:** `WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §1 — the conflict between `00_HOMEPAGE_ARCHITECTURE.md`'s "In Review / Not for Implementation" and the other two documents' "Build Phase."

**Not yet done:** `00_HOMEPAGE_ARCHITECTURE.md` still reads "In Review / Not for Implementation" — its Document Information block has not been edited to say "Build Phase." That edit is separate, not-yet-executed follow-up work.

---

## 2. Authentication Canonical Source

**Decision:** `07_WEBSITE/IMPLEMENTATION/08_AUTHENTICATION_ARCHITECTURE.md` is the canonical authentication document. `01_APPLICATION_ARCHITECTURE.md` should reference it rather than independently describing authentication status.

**Approved OAuth rollout sequence:** Password hardening → Google OAuth → Apple Sign In → Owner/Admin Role.

**No implementation starts from this document.** This decision approves the *documentation hierarchy and sequencing order only* — it does not authorize beginning any phase. Each phase named above still requires its own separate `A4` Owner approval before any code, dependency, provider registration, or credential is added, exactly as `08_AUTHENTICATION_ARCHITECTURE.md` itself already states.

**Resolves:** `WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §2.

**Not yet done:** `01_APPLICATION_ARCHITECTURE.md` §5 still describes authentication as an entirely open, provider-undecided question — it has not been edited to reference `08_AUTHENTICATION_ARCHITECTURE.md` or reflect its more advanced state. That edit is separate, not-yet-executed follow-up work.

---

## 3. Services

**Decision:** `00_GOVERNANCE/DECISION_LOG.md` is the current source of truth for service-catalog and per-service publication status. `07_WEBSITE/IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md` is historical and requires a future update to incorporate Decisions 37, 38, and 39.

**Resolves:** `WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §3.

**Not yet done:** `12_SERVICE_EXPANSION_ROADMAP.md` has not been revised to incorporate Decisions 37–39 or the 15 services they added. That revision is separate, not-yet-scheduled follow-up work.

---

## 4. Locations

**Decision:** The seven-Emirates location architecture is approved, in the following priority order:

1. Dubai
2. Abu Dhabi
3. Sharjah
4. Ajman
5. Ras Al Khaimah
6. Fujairah
7. Umm Al Quwain

**Publishing constraint carried forward, unchanged:** each page still requires genuine local content before publishing, per `LUXURY_DESIGN_DIRECTION.md` §6 and `13_LOCATION_EXPANSION_ROADMAP.md` §2 — this decision approves the build sequence, it does not waive the content-quality gate. A page with no genuinely unique local content beyond a name swap still must not publish.

**Resolves:** `WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §4.

**Not yet done:** Dubai remains the only emirate with a live page. Abu Dhabi, Sharjah, Ajman, Ras Al Khaimah, Fujairah, and Umm Al Quwain (in the approved order above) are not yet built — that build work, and the genuine-local-content sourcing it depends on per emirate, is separate, not-yet-started follow-up work.

---

## 5. Navigation

**Decision:** Creation of a dedicated navigation-architecture document is approved.

**Resolves:** `WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §5.

**Not yet done:** No navigation-architecture document has been created by this task — only its creation is approved here. The actual menu hierarchy, item labels, and grouping logic still need to be authored as separate, not-yet-started follow-up work.

---

## 6. Chatbot

**Decision:** Planning documentation only is approved, built on the foundation of `09_AI_KNOWLEDGE/CONVERSATIONAL_ASSISTANT_STANDARD.md`.

**No Phase 1 implementation.** This decision authorizes documentation/planning work only. It does not lift, and is explicitly bound by, `00_PHASE1_APPROVAL.md`'s existing exclusion of live chatbot integration from Phase 1.

**Resolves:** `WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §6.

**Not yet done:** No chatbot-architecture document has been created by this task — only its planning is approved here. Authoring that document referencing `CONVERSATIONAL_ASSISTANT_STANDARD.md` is separate, not-yet-started follow-up work.

---

## 7. Contact Information

**Decision:** All public contact values (WhatsApp number/link, email, physical address, working hours, and all eight social profile links) **remain Pending until Owner verification.** No unverified contact data should be published.

**This decision changes no canonical status** — `02_BRAND/CONTACT_INFORMATION.md` and `02_BRAND/LOCAL_SEO_PROFILE.md` already mark these values `Pending`/`Owner Input Required`; this confirms that status stands and is not being converted to `Approved` by implication or by the live app's current rendering of them.

**Resolves:** `WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §7 — specifically resolves the *decision* (keep Pending, do not approve) without resolving the *underlying conflict*, which remains open below.

**Not yet done — and this is the load-bearing gap:** per `07_EXISTING_APP_INTEGRATION_AUDIT.md` §11, the live application already hardcodes and publicly renders every one of these Pending values today (WhatsApp, `Info@afaqalhayatae.com`, the Oud Metha address, the stated working hours, and all eight social links), on every page via the shared header/footer. This decision confirms those values must **not** be treated as approved — which means the live application's current behavior (rendering them publicly) is now in explicit conflict with this decision, not merely with the canonical documents' pre-existing status. Removing or blocking these values in the application is separate, not-yet-executed follow-up work, and per the source audit this is described as blocking any public deployment until resolved.

---

## Summary Table

| # | Decision Point | Decision | Applied to files yet? |
|---|---|---|---|
| 1 | Homepage lifecycle | Status = Build Phase, reconcile all 3 docs | No |
| 2 | Authentication canonical source | `08_AUTHENTICATION_ARCHITECTURE.md` canonical; rollout sequence approved; no implementation authorized | No |
| 3 | Services source of truth | `DECISION_LOG.md` current; roadmap historical | No |
| 4 | Locations | 7-Emirate architecture approved, priority order set | No — Dubai only live |
| 5 | Navigation | Creation of nav-architecture doc approved | No — not yet created |
| 6 | Chatbot | Planning-only approved, `CONVERSATIONAL_ASSISTANT_STANDARD.md` foundation; no Phase 1 implementation | No — not yet created |
| 7 | Contact information | Remain Pending; no unverified data published | N/A — confirms existing status; live app still conflicts with it |

---

## Related Documents

- `00_GOVERNANCE/WEBSITE_ARCHITECTURE_DECISION_REPORT.md` — the decision points this document resolves.
- `00_GOVERNANCE/WEBSITE_EXPERIENCE_ARCHITECTURE_AUDIT_REPORT.md` — original source audit.
- `00_GOVERNANCE/DECISION_LOG.md` — Decisions 37, 38, 39 (item 3); a future entry would record this update once cross-referenced there if the Owner wants it consolidated.
- `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md` — source of item 7's live-app conflict.
- `02_BRAND/CONTACT_INFORMATION.md`, `02_BRAND/LOCAL_SEO_PROFILE.md` — canonical sources item 7 confirms remain Pending.

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-08-01 | Initial recording of 7 Owner decisions resolving `WEBSITE_ARCHITECTURE_DECISION_REPORT.md`: homepage status (Build Phase), authentication canonical source + approved-but-not-started OAuth sequence, services source of truth (DECISION_LOG.md), 7-Emirate location priority order, navigation-documentation approval, chatbot planning-only approval, and contact information kept Pending. No website file, application file, or code modified. |
