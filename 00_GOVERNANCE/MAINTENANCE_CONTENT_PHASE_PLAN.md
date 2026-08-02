# Maintenance Content Phase Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only; no content authored, no website file modified
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Authorizing decision:** `00_GOVERNANCE/HOMEPAGE_CONTENT_DECISION_APPLIED.md` §1, Decision 2 — "Create a dedicated Maintenance Content Phase before showing full maintenance content on homepage."
- **Scope:** Maintenance service content preparation only. Does not cover Cleaning, Pest Control, Drainage & Water Protection services, or any other homepage section.

## Purpose

Plan how the Maintenance category (AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman Services) gets real, approved, customer-facing content — the gap identified in `HOMEPAGE_CONTENT_DRAFT.md` §3 and `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`. This is a planning document only: it does not write any service content, does not touch website code, and does not add anything to the homepage.

---

## 1. Required Services

Per `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`'s "General Maintenance" category and `01_BUSINESS/COMPANY_PROFILE.md`'s Core Services list, this phase covers exactly these 5 services:

| Service | ID | Current in-repo content state |
|---|---|---|
| AC Maintenance | `SVC-AC-MAINTENANCE` | Empty content-gate template (`CONTENT_EN.md`, `CONTENT_AR.md`, `FAQ.md`, `SEO_AI.md`) |
| Plumbing | `SVC-PLUMBING` | Same |
| Electrical Maintenance | `SVC-ELECTRICAL-MAINTENANCE` | Same |
| Painting | `SVC-PAINTING` | Same |
| Handyman Services | `SVC-HANDYMAN` | Same |

*(Confirmed by direct file inspection during `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`'s execution — each file contains only a "Content Gate," a "Content Pending Approval" checklist of items not yet written, and an unanswered "Approved Question Backlog," not actual customer-facing copy.)*

**Not in scope for this phase:** Deep Cleaning, Drain Unblocking, Waterproofing, Water Leak Detection, or any of the 4 folder-less Cleaning services or 11 structural-only Expansion services — each has its own separate status and is not part of the "Maintenance" homepage category.

---

## 2. Missing Information

For each of the 5 services, the following is currently absent and needed before real content can be written — grouped by what this phase may safely produce versus what stays permanently out of scope for a *content* phase:

### In scope for this phase (general, non-commercial, non-safety-specific facts)

- Customer-facing service description and general scope (what the service covers, in plain terms).
- Typical customer problems the service addresses (e.g., "AC not cooling," "blocked drain," matching the pattern already used safely in `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`'s problem-based keyword examples).
- General process/journey description (booking → assessment → work → completion), without operational SOP detail.
- Safe, non-numeric trust/benefit language, following the same pattern already approved for Cleaning and Pest Control.
- General FAQ content that does not require a commercial or safety-specific answer.

### Explicitly out of scope for this phase, same as every other service package

- Price, discounts, packages.
- Warranty or guarantee terms.
- Certification, licensing, or regulatory-compliance claims.
- Exact response-time or emergency-service commitments.
- Specific tools, products, or methods not already confirmed.

*(This mirrors the same boundary `DECISION_LOG.md` #38 already drew for the other 11 services it approved — general operational content only, with these five categories permanently excluded regardless of phase.)*

### Open sourcing question (must be resolved before drafting starts)

`DECISION_LOG.md` #38 describes general-operational content for these same 5 services as already "authored directly from general operational/industry knowledge" and "published on the website" (`afaqalhayatae-app`) — but, per `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`'s direct file inspection, none of that content was ever mirrored into this repository. Before drafting begins, the Owner should confirm which sourcing path this phase follows:

- **(a) Import** — copy the actual approved content that already exists in `afaqalhayatae-app`, if it can be made accessible to this repository.
- **(b) Author fresh** — write new general-operational content directly in this repository, following the same no-fabrication boundary as (2) above, independent of whatever exists in the external repository.

This plan does not choose between (a) and (b) — it is an Owner sourcing decision, not a content decision.

---

## 3. Content Structure

Proposed structure per service, following the pattern already successfully used for General Cleaning and Water Tank Cleaning (the two services with real approved content today), rather than inventing a new structure:

| File | Purpose | Model to follow |
|---|---|---|
| `CONTENT_EN.md` / `CONTENT_AR.md` | Service title, short description, customer-facing overview, process summary, CTA | `03_GENERAL_CLEANING/CONTENT_EN.md`/`CONTENT_AR.md` |
| `FAQ.md` | Real, answered questions limited to the safe categories in §2 | `03_GENERAL_CLEANING/FAQ.md` (Q&A directly, no unanswered backlog) |
| `SEO_AI.md` | Entity name/ID, category, search-intent groups, AI answer guardrails | `03_GENERAL_CLEANING/SEO_AI.md` |
| `README.md` | Status line update once content is drafted and reviewed | Same pattern as the sync already applied to General Cleaning/Water Tank Cleaning |

**Not proposed for this phase:** replicating Pest Control's fuller numbered `01`–`06` file set (`01_SERVICE_PROFILE.md` through `06_PAGE_CONTENT.md`). That structure was built as a page-assembly aid for the most content-mature service in the catalog; adopting it for 5 services at once is a larger scope decision the Owner has not asked for here. The simpler General-Cleaning-style structure is proposed as the faster, proven path; expanding to the fuller structure later remains an option.

---

## 4. SEO Requirements

Consistent with `HOMEPAGE_CONTENT_DECISION_APPLIED.md` §1, Decision 4 ("do not finalize keyword targeting yet"):

- Each service's `SEO_AI.md` may define its entity name, ID, category, and safe search-intent groups (informational, not keyword-target, framing) — the same non-committal structure `03_GENERAL_CLEANING/SEO_AI.md` already uses.
- **No keyword list, title, or meta description produced in this phase may be treated as a finalized target.** Any keyword content drafted here carries the same "illustrative, unresearched candidate" caveat already standard across this repository (`07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`).
- Real keyword-volume, competitor, and ranking research remains a separate, not-yet-scoped phase per `HOMEPAGE_CONTENT_DECISION_APPLIED.md` — this plan does not schedule or scope that research.

---

## 5. FAQ Requirements

- Each service's `FAQ.md` should carry only real question/answer pairs answerable from approved, general information — no unanswered "backlog" list should ship as customer-facing content (the current AC Maintenance-style backlog format is a planning artifact, not publishable content).
- Safe candidate question types, by analogy to what already works for Pest Control/General Cleaning: what the service generally covers, what happens during a typical visit, whether an inspection/quotation happens before work begins (already an approved general fact, `06_CUSTOMER_AND_SALES/CUSTOMER_SUPPORT/GENERAL_SERVICE_FAQ_DRAFT.md` Q7), which emirates are covered (already approved, `03_MARKET/SERVICE_AREAS.md`).
- Any question requiring a price, warranty, certification, or response-time answer stays unanswered/excluded from the customer-facing FAQ, exactly as `HOMEPAGE_CONTENT_DRAFT.md` §8 already treats the general-company FAQ.

---

## 6. Approval Checkpoints

Following the same evidence and review discipline already used for the rest of this repository (`00_GOVERNANCE/ENTERPRISE_PUBLICATION_GATE_MODEL.md` §10 — "a layer cannot reach Approved without independent `AGT-QA` review; a producing role cannot self-approve"):

1. **Owner sourcing decision** — resolve §2's "Open sourcing question" (import vs. author fresh) before any drafting starts.
2. **Draft content pass** — write `CONTENT_EN.md`/`CONTENT_AR.md`, `FAQ.md`, and `SEO_AI.md` per §3–5, strictly within the §2 boundary (no price/warranty/certification/license/response-time claim).
3. **Independent review** — a reviewing role distinct from whoever drafted the content checks every file against the no-fabrication boundary before any status changes.
4. **Owner sign-off** — the Owner reviews and approves the drafted content itself (not just the plan).
5. **Status sync** — once approved, update each service's `README.md`/`CONTENT_EN.md`/`CONTENT_AR.md`/`FAQ.md`/`SEO_AI.md` status banners, following the same pattern already used in `SERVICE_KNOWLEDGE_SYNC_PLAN.md`/`SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md` — status banner and decision citation only, no content rewrite bundled into that step.
6. **Homepage eligibility** — only after step 5 completes for all 5 services (or a partial subset the Owner explicitly accepts) does the Maintenance category become eligible for full homepage content, per `HOMEPAGE_CONTENT_DECISION_APPLIED.md`.

No step above is executed by this document — it is the checklist for a future, separately authorized phase.

---

## What This Document Does Not Do

- Does not author any service content, English or Arabic.
- Does not modify any website code, page, or component.
- Does not add anything to the homepage draft.
- Does not invent any business claim, price, warranty, certification, or response-time commitment.
- Does not resolve the import-vs-author-fresh sourcing question — surfaces it for Owner decision.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/HOMEPAGE_CONTENT_DECISION_APPLIED.md`
- `00_GOVERNANCE/HOMEPAGE_CONTENT_DRAFT.md`
- `00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_PLAN.md`, `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `04_SERVICE_KNOWLEDGE/02_AC_MAINTENANCE/`, `06_PLUMBING/`, `07_ELECTRICAL_MAINTENANCE/`, `08_PAINTING/`, `09_HANDYMAN/`
- `04_SERVICE_KNOWLEDGE/03_GENERAL_CLEANING/` — structural model for this phase
- `99_STANDARDS/SERVICE_TEMPLATE.md`
- `00_GOVERNANCE/DECISION_LOG.md` #38
