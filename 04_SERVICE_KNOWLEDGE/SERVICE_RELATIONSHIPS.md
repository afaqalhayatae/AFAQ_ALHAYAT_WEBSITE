# Service Relationships

## Document Information

- **Owner:** Business Owner
- **Status:** Draft
- **Version:** 0.1
- **Prepared:** 2026-07-25
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.2 Work Package 4

## What This Is

The canonical Enterprise Service Meta-Model (ESMM) Layer 3 (Service
Relationships) registry, per `DECISION_LOG.md` decision 25 and
`ENTERPRISE_SERVICE_META_MODEL.md` §3. It states the current, resolved
status of every relationship candidate among the twelve catalog
services, reshaped from `00_GOVERNANCE/ESF/SERVICE_RELATIONSHIPS_DRAFT.md`
— Owner-reviewed across four resolution rounds and independently
reviewed by `AGT-QA` — under Program C Phase C.2 Work Package 4. No new
relationship candidate is introduced here; no candidate confirmed,
rejected, or closed in the source draft is altered. This file does not
modify `ENTERPRISE_SERVICE_META_MODEL.md`, `ENTERPRISE_PUBLICATION_GATE_MODEL.md`,
`SERVICE_CATALOG.md`, or `SERVICE_DNA_REGISTRY.md`.

The source draft's full drafting history — every resolution round, the
reasoning behind each Owner decision, and the two `AGT-QA` review passes
— remains the historical audit trail and is not duplicated here.

**Status caveats carried forward, not resolved by this registry:**

- **Rejected and dropped candidates are retained below**, marked
  `Rejected` or `Dropped`, not removed — per the Business Owner's
  standing retention policy (Phase C.1.b): a rejected or dropped entry
  is a historical decision record only, not a valid relationship, and
  must not be used for AI, automation, publishing, or any downstream
  consumption.
- **A `Confirmed` status below means the relationship candidate itself
  is validated — not that it is an approved, publication-ready fact.**
  Several candidates' underlying source documents (`06_CUSTOMER_AND_SALES/SALES/UPSELL_CROSSSELL_DRAFT.md`,
  individual service `README.md` files) remain themselves `Draft` or
  `Publication: Blocked`. This registry does not resolve that.
- **Parent and Child are Dormant for all 12 services**, per
  `DECISION_LOG.md` decision 27 — `SERVICE_CATALOG.md` categories remain
  classification labels only; no Parent Service Object exists yet. No
  parent or child edge is recorded.
- Per ESMM Layer 3's own validation rule, both ends of every recorded
  edge resolve to an existing `SVC-` ID in `SERVICE_CATALOG.md`, and no
  cycle exists among the recorded edges.

This registry's own status is **Draft**, not Approved — capped by the
same dependency-status rule as `SERVICE_DNA_REGISTRY.md`
(`ENTERPRISE_PUBLICATION_GATE_MODEL.md` §7), given the still-Draft/Blocked
status of the underlying source documents behind several candidates.

---

## 1. Relationship-Type Status Overview

| Type | Status |
|---|---|
| Parent | **Dormant for all 12 services.** No Parent Service Object exists yet (decision 27). No parent edge is recorded. |
| Child | **Dormant for all 12 services**, same reason as Parent. |
| Related | Populated from explicit, named scope-boundary text in service `README.md` files — 3 confirmed (§4). Not inferred from shared catalog category. |
| Alternative | **Closed — no candidates identified.** No repository source frames any two services as substitutable alternatives for the same customer need. Owner-confirmed: no Alternative relationships exist across the 12 services at this stage; not pending resolution; re-evaluate only if new evidence appears. |
| Upsell | **No validated candidate.** The source document's Upselling examples describe commercial packaging concepts (e.g., "Upgrade to an Annual Maintenance Contract"), not a relationship between two existing `SVC-` IDs. The one example naming a service pair ("Upgrade from Basic Cleaning to Deep Cleaning") is closed as a permanent unresolved historical reference (§5) — "Basic Cleaning" does not match a catalog name. Not pending resolution. |
| Cross-sell | **6 confirmed candidates** (§2). |
| Dependency | **4 candidates found — 2 confirmed, 2 rejected** (§3). |

---

## 2. Cross-sell Candidates

| From | To | Status | Source |
|---|---|---|---|
| `SVC-PLUMBING` | `SVC-WATER-TANK-CLEANING` | **Confirmed** | `UPSELL_CROSSSELL_DRAFT.md` § Cross-Selling: "After Plumbing: Water Tank Cleaning." |
| `SVC-PEST-CONTROL` | `SVC-DEEP-CLEANING` | **Confirmed** | Same document: "After Pest Control: Deep Cleaning." |
| `SVC-PAINTING` | `SVC-HANDYMAN` | **Confirmed** | Same document: "After Painting: Handyman Services." |
| `SVC-PLUMBING` | `SVC-DEEP-CLEANING` | **Confirmed** | Same document, "Bathroom Deep Cleaning" reference — Owner-confirmed as a sub-scope of `SVC-DEEP-CLEANING`; no new service created (§5). |
| `SVC-AC-MAINTENANCE` | `SVC-ELECTRICAL-MAINTENANCE` | **Confirmed** | Same document, "Electrical Inspection" reference — Owner-confirmed as a sub-scope of `SVC-ELECTRICAL-MAINTENANCE`; no new service created (§5). |
| `SVC-PAINTING` | `SVC-ELECTRICAL-MAINTENANCE` | **Confirmed** | Same document, second "Electrical Inspection" occurrence — same resolution. |

No Upsell candidate is recorded — see §1 and §5.

---

## 3. Dependency Candidates

| From | To | Status | Source |
|---|---|---|---|
| `SVC-WATER-LEAK-DETECTION` | `SVC-PLUMBING` | **Confirmed** | `12_WATER_LEAK_DETECTION/README.md` § Scope Requiring Confirmation: "Escalation to plumbing, waterproofing, AC, tank, structural, or authority specialists." |
| `SVC-WATER-LEAK-DETECTION` | `SVC-WATERPROOFING` | **Confirmed** | Same source. |
| `SVC-WATER-LEAK-DETECTION` | `SVC-AC-MAINTENANCE` | **Rejected** | Same source ("AC"). Retained as a historical decision record. |
| `SVC-WATER-LEAK-DETECTION` | `SVC-WATER-TANK-CLEANING` | **Rejected** | Same source ("tank"). Retained as a historical decision record. |

---

## 4. Related Candidates (Explicit Scope-Boundary Distinctions)

| Between | Status | Source |
|---|---|---|
| `SVC-GENERAL-CLEANING` ↔ `SVC-DEEP-CLEANING` | **Confirmed** | `03_GENERAL_CLEANING/README.md` § Boundary: "Deep cleaning... are separate scopes unless explicitly approved." |
| `SVC-GENERAL-CLEANING` ↔ `SVC-PEST-CONTROL` | **Confirmed** | Same source: "...pest control... are separate scopes unless explicitly approved." |
| `SVC-DRAIN-UNBLOCKING` ↔ `SVC-PLUMBING` | **Confirmed** | `10_DRAIN_UNBLOCKING/README.md` § Scope Requiring Confirmation: "Boundaries between drain unblocking, plumbing repair, sewer-line work, and external authority responsibilities." |

Related candidates are populated only from explicit textual mentions in a
service's own documentation — shared `SERVICE_CATALOG.md` category alone
is never used as a source, per decision 27.

---

## 5. Unresolved / Historical Source References

Terms from source documents that required resolution against
`SERVICE_CATALOG.md`'s 12 approved names. All five are closed; none is
pending.

| Term | Where | Resolution |
|---|---|---|
| "Basic Cleaning" | `UPSELL_CROSSSELL_DRAFT.md` § Upselling | **Closed — permanent unresolved historical reference.** Owner-decided: not `SVC-GENERAL-CLEANING`, not `SVC-DEEP-CLEANING`; no new service created. Not mapped to any candidate. |
| "Bathroom Deep Cleaning" | Same document § Cross-Selling (after Plumbing) | **Resolved** — sub-scope of `SVC-DEEP-CLEANING`; recorded as a Cross-sell candidate (§2). |
| "Electrical Inspection" | Same document (after AC Maintenance; after Painting) | **Resolved** — sub-scope of `SVC-ELECTRICAL-MAINTENANCE` for both occurrences; recorded as two Cross-sell candidates (§2). |
| "Air Duct Cleaning" | Same document (after AC Maintenance) | **Dropped** — does not map to any existing catalog service. Retained as a historical reference only. |
| "Preventive Maintenance" | Same document (after Pest Control) | **Dropped** — a possible commercial maintenance concept, not a catalog service. Retained as a historical reference only. |

---

## 6. Coverage Summary

Every one of the 12 catalog services has at least one confirmed
relationship candidate edge (Related, Cross-sell, or Dependency).
`SVC-AC-MAINTENANCE` and `SVC-ELECTRICAL-MAINTENANCE` — the two services
with zero confirmed candidates as of the initial 2026-07-24 review — are
each covered via the "Electrical Inspection" resolution (§2, §5).

---

## Validation Performed

- Both ends of every recorded edge validated against `SERVICE_CATALOG.md`'s
  12 approved `SVC-` IDs — no term that failed to resolve to an exact
  catalog name is mapped by assumption; unresolved terms are listed
  separately in §5.
- No cycle exists among the recorded edges — Cross-sell and Dependency
  edges are one-directional and do not loop; Related edges are explicit
  bidirectional boundary pairs, not chains.
- No relationship is inferred from a service name or shared category —
  every populated candidate traces to an explicit textual mention in a
  cited source, or to a direct Owner decision (Alternative closure).
- Parent and Child are left dormant, consistent with decision 27 — no
  invented pair.
- No commercial claim (discount, saving, urgency, availability, price)
  is introduced.
- Rejected and dropped candidates are retained, not removed, per the
  Owner's standing retention policy.
- This file does not modify `ENTERPRISE_SERVICE_META_MODEL.md`,
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`, `SERVICE_CATALOG.md`,
  `SERVICE_DNA_REGISTRY.md`, or `SERVICE_RELATIONSHIPS_DRAFT.md`.

## Status

Draft. Content-complete — every relationship type addressed (populated,
confirmed-closed, or correctly dormant); no item pending. Not Approved —
capped below Approved by the still-Draft/Blocked status of several
candidates' underlying source documents, per
`ENTERPRISE_PUBLICATION_GATE_MODEL.md` §7. Created under Program C Phase
C.2 Work Package 4, pending independent `AGT-QA` review.
