# Content Approval Conflict Resolution Report

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — read-only findings and recommendation; resolves nothing by itself
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning/recommendation only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Scope:** Read-only review. No source document was edited, no code was touched, no commit was made.

## Purpose

Before homepage content implementation begins, this report resolves — or, where it cannot be resolved by an agent, surfaces for Owner decision — the conflicts between the sources that describe service content and publication readiness across this repository.

---

## 1. Service Approval Source of Truth

### 1.1 Which document controls publication readiness?

Two documents jointly hold this authority, and neither is optional:

- **`04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`** — the catalog's own header states it is "the single source of truth for 'what services exist'" and their **object-level** knowledge-package status. It is the canonical index of which `SVC-<NAME>` IDs exist and their current stage.
- **`00_GOVERNANCE/DECISION_LOG.md`** — the record of the actual Owner approval events (decisions 37, 38, 39) that changed those statuses. The catalog states the current status; the log is the evidence for *why* and *when* it changed.
- **`00_GOVERNANCE/ENTERPRISE_PUBLICATION_GATE_MODEL.md` (EPGM)** is the governing *computation model* (Approved, v0.1) for how object-level status is derived from layer statuses, dependencies, and Hard Publication Blocks — it is the rule, not a source of facts itself.

This matches `CLAUDE.md`'s own fact-ownership table ("Service catalog & IDs → `SERVICE_CATALOG.md`"; "Per-service operational facts → `04_SERVICE_KNOWLEDGE/<NN_SERVICE>/*`").

### 1.2 Conflict found: the catalog and the per-service packages disagree with each other

This is the central conflict this report must surface rather than resolve silently.

| Source | What it says | Dated |
|---|---|---|
| `SERVICE_CATALOG.md` | 16 of 27 services "✅ Approved... Owner-approved, general-operational-knowledge content published on the website (`afaqalhayatae-app`)" | 2026-07-31 |
| `DECISION_LOG.md` #37–39 | Confirms the same 16 approved, sourced from **a separate application repository** (`afaqalhayatae-app`) and its own `docs/SERVICE_COMPLETION_MATRIX.md` / `docs/VISUAL_ASSET_MASTER_PLAN.md` — neither of which exists in this repository (confirmed: no `afaqalhayatae-app` path found anywhere on this filesystem) | 2026-07-31 |
| Every individual service package in **this** repository, e.g. `04_SERVICE_KNOWLEDGE/02_AC_MAINTENANCE/README.md`, `.../CONTENT_EN.md`, and 9 other services identically | "Structurally Complete Draft — Owner and Technical Evidence Required" / "Draft — Not Approved for Publication" | 2026-07-24 to 2026-07-28 (never updated) |
| `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/CONTENT_EN.md` and `README.md` | "Review Draft"/"Review Required — Not Approved for Publication or Field Execution" | 2026-07-28/29 |
| `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/CHANGELOG.md` header | "Document Status: **Approved**" (this is the changelog *document's* own review status, not the package's publication status — its own version-history entries, e.g. 1.18, explicitly say "none of this is Approved for Publication") | 2026-07-29 |
| `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md` | Explicitly defers: "Each service's own `README.md` Evidence Gate remains the governing status for that package" | 2026-07-29 |
| `07_WEBSITE/IMPLEMENTATION/04_CONTENT_INTEGRATION_PLAN.md` §3 and `.../14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` | Both key their publishability logic to a `SERVICE_CATALOG.md` status-column vocabulary ("Complete / Review-ready / Structurally complete draft / Blocked") that **no longer exists** in the catalog's current form (replaced 2026-07-31 by the ✅/⚠ scheme above); `14_...` also predates and omits all 15 services added 2026-07-31 (the 4 new Cleaning services and 11 Expansion services) | 2026-07-27/28 (not updated since) |
| `07_WEBSITE/NAVIGATION_ARCHITECTURE.md` | Consistent with the *current* `SERVICE_CATALOG.md` (16 of 27 approved/indexable, 11 `noindex`) | 2026-08-01 (most current, already committed) |

**Reading of this conflict, not a resolution of it:** `SERVICE_CATALOG.md` and `DECISION_LOG.md` are the more recent and more authoritative pair — they record an actual Owner decision. `NAVIGATION_ARCHITECTURE.md` was written consistently with them one day later. But:

1. The approval those two decisions describe was granted to content that lives **in a repository this knowledge base cannot see or verify** (`afaqalhayatae-app`). This repository has no way to confirm that content still matches the no-fabrication rules today, only that it was represented as compliant at approval time.
2. This repository's own canonical per-service packages — which `CLAUDE.md` names as the owning source for per-service operational facts — were **never updated** to reflect that approval. They still self-report Draft/Not-Approved. Per `ENTERPRISE_PUBLICATION_GATE_MODEL.md` §3 ("a file's own status carries no authority over the layer or object it feeds") this is not fatal to the catalog's authority, but it is a real documentation-parity gap, already acknowledged in `DECISION_LOG.md` #38/#39 itself ("a documentation-parity gap tracked in `docs/SERVICE_COMPLETION_MATRIX.md`, not resolved by this entry").
3. Two of this repository's own website-planning documents (`04_CONTENT_INTEGRATION_PLAN.md`, `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`) describe an adapter/gating mechanism keyed to a schema that has since changed shape and a service list that is now 15 services short. If homepage implementation follows those two documents literally, it will gate on the wrong field values and omit newly-approved services.

**This is a Detect → Record → Stop → Escalate situation per `ENTERPRISE_PUBLICATION_GATE_MODEL.md` §15** ("an unresolved conflict forces the affected layer... to Blocked... no agent picking 'the more recent' or 'the more complete' source on its own authority"). This report records the conflict; it does not pick a winner. See §4 for the specific Owner decisions this leaves open.

### 1.3 Which services are approved for homepage display?

Based on the two most current, mutually-consistent sources (`SERVICE_CATALOG.md` and `NAVIGATION_ARCHITECTURE.md`, both reflecting `DECISION_LOG.md` #37–39):

**Approved, indexable, linkable from primary navigation and (by extension) eligible for homepage service listings — 16 of 27:**

| # | Service | Note |
|---|---|---|
| 1 | Pest Control (`SVC-PEST-CONTROL`) | Full content approved 2026-07-31 |
| 2 | AC Maintenance (`SVC-AC-MAINTENANCE`) | General-operational content, decision #38 |
| 3 | General Cleaning (`SVC-GENERAL-CLEANING`) | Same |
| 4 | Deep Cleaning (`SVC-DEEP-CLEANING`) | Same — previously blocked, unblocked by decision #38 |
| 5 | Water Tank Cleaning (`SVC-WATER-TANK-CLEANING`) | Same |
| 6 | Plumbing (`SVC-PLUMBING`) | Same |
| 7 | Electrical Maintenance (`SVC-ELECTRICAL-MAINTENANCE`) | Same |
| 8 | Painting (`SVC-PAINTING`) | Same |
| 9 | Handyman Services (`SVC-HANDYMAN`) | Content approved; **no real card image** — excluded from card grids, not from text nav/homepage links |
| 10 | Drain Unblocking (`SVC-DRAIN-UNBLOCKING`) | Same as #2–8 |
| 11 | Waterproofing (`SVC-WATERPROOFING`) | Content approved; card image **pulled** (AI-rendering defect) — same grid exclusion as Handyman |
| 12 | Water Leak Detection (`SVC-WATER-LEAK-DETECTION`) | Same as #2–8 |
| 13 | Villa Cleaning (`SVC-VILLA-CLEANING`) | Approved; **no `04_SERVICE_KNOWLEDGE/` folder exists** in this repo (documentation-parity gap) |
| 14 | Office Cleaning (`SVC-OFFICE-CLEANING`) | Same gap |
| 15 | Post-Construction Cleaning (`SVC-POST-CONSTRUCTION-CLEANING`) | Same gap |
| 16 | Carpet & Upholstery Cleaning (`SVC-CARPET-UPHOLSTERY-CLEANING`) | Same gap |

**Remain Draft/Review/structural-only — not approved for homepage display, must stay `noindex` and out of primary navigation and homepage listings — 11 of 27:**

CCTV Installation, Smart Home Installation, Swimming Pool Maintenance, Kitchen Installation, Interior Decoration, Interlock Installation, Lighting Maintenance, Wood Alternative Installation, Wallpaper Installation, Thermal Insulation, Rooftop Space Utilization — all "structural entry only" (catalog ID/SEO/i18n in place, no page content), per `SERVICE_CATALOG.md` and `DECISION_LOG.md` #39.

---

## 2. Homepage Content Allowed Now

### A) Approved content that can be implemented immediately

- A homepage services section/grid listing the **16 approved services** (§1.3 list above) by name, category, and short description consistent with each service's approved general-operational content — provided that content is sourced from the same approved material `DECISION_LOG.md` #37/#38 references, not re-authored from scratch by this or any agent.
- Card images for the 14 of 16 that have an Owner-approved real photo; Handyman and Waterproofing must render **without** a card image (or excluded from image-based grids) rather than a placeholder, per the existing no-placeholder rule (`DECISION_LOG.md` #37).
- Bilingual (EN/AR) rendering of the above, since `DECISION_LOG.md` #38 explicitly required no divergence in facts between languages for the authored content.
- Links from the homepage into each of the 16 approved services' pages, and into the approved emirate-level coverage (`03_MARKET/SERVICE_AREAS.md`'s Approved Registry) — consistent with `NAVIGATION_ARCHITECTURE.md`.
- General trust/company-identity homepage content already governed elsewhere (company profile, brand, approved contact fields) — subject to the existing rule that only fields marked `Approved` in `02_BRAND/CONTACT_INFORMATION.md` render at all.

### B) Content requiring owner approval before implementation

- Any homepage content for the **11 structural-only services** — these must not appear in any homepage grid, "our services" list, or internal link, per their `noindex` status and `NAVIGATION_ARCHITECTURE.md`'s explicit exclusion rationale.
- Any homepage claim involving price, discount, package, warranty, guarantee, license, certification, or a specific response-time/emergency commitment for **any** service, approved or not — these categories remain open (`A4`-gated) regardless of a service's general-content approval status (`DECISION_LOG.md` #38's own guardrail; `AUTONOMY_AND_APPROVAL_MATRIX.md` line "Quote a price or warranty → A4").
- Any homepage testimonial, review, "as seen in," or trust badge not backed by real, verifiable evidence — no such evidence exists in this repository today.
- Reconciling `04_CONTENT_INTEGRATION_PLAN.md` §3's adapter design and `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` against the current `SERVICE_CATALOG.md` schema and the 27-service list — an engineering/planning update, not a content decision, but it blocks a correct automated "publishable" flag if built from the stale documents as-is.
- Creating the missing `04_SERVICE_KNOWLEDGE/` folders for the 4 approved Cleaning services (Villa, Office, Post-Construction, Carpet & Upholstery) so this knowledge repository's own per-service ownership rule is satisfied for content already live — currently an open, Owner-acknowledged gap, not silently closed here.
- Deciding whether homepage implementation may proceed by trusting `SERVICE_CATALOG.md`'s "Approved" status directly, or must wait until each service's own package inside this repository is updated to match (see §4).

---

## 3. Business Facts Restrictions — Confirmed

Reviewed against `CLAUDE.md`, `README.md` Authority Rules, `CURRENT_PROJECT_STATUS.md` Hard Publication Blocks, and `AUTONOMY_AND_APPROVAL_MATRIX.md`:

- **No invented numbers** — confirmed as a standing rule; no price, discount, or response-time figure exists approved for any service, and `DECISION_LOG.md` #38 explicitly excluded these when authoring the 16 approved services' content.
- **No invented certifications** — confirmed; every service package's own Evidence Gate (e.g. `02_AC_MAINTENANCE/README.md`) explicitly withholds licensing/certification claims pending evidence, and no certification exists in any approved-content decision.
- **No invented reviews** — confirmed; `CURRENT_PROJECT_STATUS.md`'s Hard Publication Blocks explicitly prohibit "fake branches, virtual offices, reviews, identities, or human employees," and no review/testimonial content exists anywhere in this repository.
- **No invented claims generally** — confirmed; every approval decision reviewed (`DECISION_LOG.md` #37, #38, #39) explicitly carries forward the same exclusion language for price/warranty/license/certification/response-time, with no exception found.

No violation of these four restrictions was found in any homepage-relevant source reviewed. The risk identified in §1–2 is a **staleness/parity** problem (documents disagreeing about what stage something has reached), not a fabrication problem.

---

## 4. Final Recommendation

### Safe next implementation scope

Build the homepage services section against the **16-service approved list in §1.3**, using only the general-operational content already Owner-approved per `DECISION_LOG.md` #37/#38, sourced from wherever that approved content actually lives (the `afaqalhayatae-app` repository, per the decision log) — not re-derived independently in this repository. Bilingual parity and the existing no-image-placeholder rule (Handyman, Waterproofing) apply. Exclude all 11 structural-only services entirely from any homepage surface.

### Blocked items

- Any commercial claim (price/warranty/license/certification/response-time) on the homepage for any service.
- Any homepage surface for the 11 structural-only services.
- Any automated "publishable" logic built from `04_CONTENT_INTEGRATION_PLAN.md` §3 or `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` as currently written, until they are reconciled with the current `SERVICE_CATALOG.md`.
- Full content-package completion for the 4 new Cleaning services and 11 Expansion services inside this knowledge repository (documentation-parity gap, not resolved here).

### Required Owner decisions

1. **Authority precedence:** when `SERVICE_CATALOG.md`/`DECISION_LOG.md` (approved, but evidenced only in an external repository) and this repository's own per-service packages (still self-reporting Draft) disagree, which governs homepage implementation — and should the per-service packages be updated to match, retired in favor of the external repo, or kept as a distinct, slower-moving evidence layer?
2. **Repository boundary:** should `afaqalhayatae-app` (referenced repeatedly in `DECISION_LOG.md` but absent from this workspace) be linked, mirrored, or otherwise made inspectable from this knowledge repository, so future governance review can verify rather than take on faith what was approved there?
3. **Documentation-parity backfill:** authorize (or explicitly defer) creating `04_SERVICE_KNOWLEDGE/` folders for the 4 approved Cleaning services, and updating the 11 pre-existing service packages' own status fields to reflect their 2026-07-31 approval, so a reader of any single per-service package is not misled by a stale "Not Approved for Publication" line.
4. **Planning-document refresh:** authorize an update pass on `04_CONTENT_INTEGRATION_PLAN.md` §3 and `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` to match the current `SERVICE_CATALOG.md` schema and full 27-service list before either is used to drive actual homepage engineering.

---

## Related Documents

- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `00_GOVERNANCE/DECISION_LOG.md`
- `00_GOVERNANCE/ENTERPRISE_PUBLICATION_GATE_MODEL.md`
- `00_GOVERNANCE/CURRENT_PROJECT_STATUS.md`
- `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`
- `07_WEBSITE/NAVIGATION_ARCHITECTURE.md`
- `07_WEBSITE/IMPLEMENTATION/04_CONTENT_INTEGRATION_PLAN.md`
- `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md`
- `04_SERVICE_KNOWLEDGE/BOOKING_SERVICE_CATALOG.md`
