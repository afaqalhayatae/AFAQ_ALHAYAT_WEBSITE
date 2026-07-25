# Service Relationships Draft — Preparatory

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — Preparatory, Owner-Reviewed (Complete)
- **Version:** 0.2
- **Prepared:** 2026-07-24
- **Updated:** 2026-07-25 (Phase C.2 WP2 — Alternative closed; Deep Cleaning publication limitation lifted)
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.1.b

## What This Is

A preparatory draft of ESMM Layer 3 (Service Relationships) covering all 12
catalog services, prepared under Phase C.1.b authorization. It is **not**
`SERVICE_RELATIONSHIPS.md` and creates no registry. It reshapes only
existing repository content — `06_CUSTOMER_AND_SALES/SALES/UPSELL_CROSSSELL_DRAFT.md`,
individual service `README.md` files, and `SERVICE_CATALOG.md` — into
candidate relationship edges between existing `SVC-` IDs. No relationship
is inferred from a service name or category alone.

Per Owner instruction, `09_AI_KNOWLEDGE/ENTITY_RELATIONSHIPS.md` was **not**
used as a source. It is treated as historical/non-canonical only: it is an
organization-level entity diagram (not a service-to-service relationship
graph), and it is independently stale (it still states "9 Services" and
"only Pest Control has a package," both superseded by the current
12-service catalog).

This draft has been reviewed by `AGT-QA` (two passes: one finding and
correcting a defect, one raising and resolving the rejected-candidate
retention question) and by the Business Owner (three resolution rounds,
recorded below). It is still not approved and not canonical, and must not
be cited elsewhere or used to inform publishing, AI answers, or
customer-facing material.

---

## 1. Relationship-Type Status Overview

ESMM Layer 3 requires seven relationship types. Their readiness differs
sharply and is stated honestly below rather than forced into uniform
coverage:

| Type | Status |
|---|---|
| Parent | **Dormant for all 12 services.** Per `DECISION_LOG.md` decision 27 and ESMM Layer 14's own note, `SERVICE_CATALOG.md` categories are classification labels only — no Parent Service Object exists yet. No parent edge is drafted. |
| Child | **Dormant for all 12 services**, same reason as Parent. |
| Related | Populated below from explicit, named scope-boundary text in service `README.md` files — not from shared catalog category (see § 4 for why category alone was not used). |
| Alternative | **Closed 2026-07-25 (Phase C.2 WP2).** No candidates identified — no repository source frames any two services as substitutable alternatives for the same customer need. Owner-confirmed: no Alternative relationships exist across the 12 services at this stage; re-evaluate only if new evidence appears. Not pending resolution. |
| Upsell | **No validated candidate.** One source example names a service pair ("Basic Cleaning" → "Deep Cleaning"), but "Basic Cleaning" does not match a catalog name. Closed 2026-07-25: "Basic Cleaning" is permanently unmapped as a historical source term — see § 5. This is not pending resolution. |
| Cross-sell | Six candidates (see § 2); **Owner-reviewed 2026-07-24 — original 3 confirmed. Owner-reviewed 2026-07-25 — 3 more confirmed, resolved from § 5 unresolved terms.** |
| Dependency | Four candidates found (see § 3); **Owner-reviewed 2026-07-24 — 2 confirmed (→ Plumbing, → Waterproofing), 2 rejected (→ AC Maintenance, → Water Tank Cleaning).** |

---

## 2. Upsell and Cross-sell Candidates

Source: `06_CUSTOMER_AND_SALES/SALES/UPSELL_CROSSSELL_DRAFT.md` §
Upselling, § Cross-Selling. This entire source document is `Status: Draft`,
`Publication: Blocked` — every candidate below is a **candidate for Owner
confirmation**, not a validated relationship.

| Type | From | To | Source | Owner Decision (2026-07-24) |
|---|---|---|---|---|
| Cross-sell | `SVC-PLUMBING` | `SVC-WATER-TANK-CLEANING` | "After Plumbing: Water Tank Cleaning" | **Confirmed** |
| Cross-sell | `SVC-PEST-CONTROL` | `SVC-DEEP-CLEANING` | "After Pest Control: Deep Cleaning" | **Confirmed — structural only, not publication-ready. See note below.** |
| Cross-sell | `SVC-PAINTING` | `SVC-HANDYMAN` | "After Painting: Handyman Services" | **Confirmed** |
| Cross-sell | `SVC-PLUMBING` | `SVC-DEEP-CLEANING` | "After Plumbing: ... Bathroom Deep Cleaning" — Owner-confirmed 2026-07-25 as a sub-scope of `SVC-DEEP-CLEANING`; no new service created. | **Confirmed — structural only, not publication-ready. See note below.** |
| Cross-sell | `SVC-AC-MAINTENANCE` | `SVC-ELECTRICAL-MAINTENANCE` | "After AC Maintenance: ... Electrical Inspection" — Owner-confirmed 2026-07-25 as a sub-scope of `SVC-ELECTRICAL-MAINTENANCE`; no new service created. | **Confirmed** |
| Cross-sell | `SVC-PAINTING` | `SVC-ELECTRICAL-MAINTENANCE` | "After Painting: ... Electrical Inspection" — same resolution, Owner-confirmed 2026-07-25. | **Confirmed** |

No Upsell candidate is included in this table. The source's Upselling
examples ("Upgrade to an Annual Maintenance Contract," "Upgrade to a
Premium Service Package," "Add Emergency Priority Support") describe
commercial packaging concepts, not a relationship between two existing
`SVC-` IDs, so they do not fit this registry's service-to-service scope.
The one example naming a service pair ("Upgrade from Basic Cleaning to
Deep Cleaning") is listed in § 5 as unresolved, because "Basic Cleaning" is
not a catalog name.

**Deep Cleaning publication limitation — lifted 2026-07-25 (Phase C.2 WP2
B3).** The two Cross-sell candidates targeting `SVC-DEEP-CLEANING` (Pest
Control → Deep Cleaning, Plumbing → Deep Cleaning) are confirmed as valid
**structural** service relationships. The scope-differentiation-from-
General-Cleaning blocker this limitation was tied to is resolved —
`SERVICE_DNA_DRAFT_DEEP_CLEANING.md` Rounds 3–4 confirmed Deep Cleaning
as a separate catalog service from General Cleaning, with Task Scope as
the differentiation basis, and recorded scope, exclusions, and boundary.
This limitation is therefore lifted; these two candidates now carry the
same status as every other confirmed relationship in this file — a
confirmed structural candidate in a Draft, non-canonical registry, not
yet an approved relationship or publication authorization.

## 3. Dependency Candidates

Source: individual service `README.md` files, § Scope Requiring
Confirmation — a section whose own heading states its contents require
confirmation, not that they are settled.

| Type | From | To | Source | Owner Decision (2026-07-24) |
|---|---|---|---|---|
| Dependency | `SVC-WATER-LEAK-DETECTION` | `SVC-PLUMBING` | `12_WATER_LEAK_DETECTION/README.md` § Scope Requiring Confirmation: "Escalation to plumbing, waterproofing, AC, tank, structural, or authority specialists." | **Confirmed** |
| Dependency | `SVC-WATER-LEAK-DETECTION` | `SVC-WATERPROOFING` | Same source. | **Confirmed** |
| Dependency | `SVC-WATER-LEAK-DETECTION` | `SVC-AC-MAINTENANCE` | Same source ("AC"). | **Rejected** |
| Dependency | `SVC-WATER-LEAK-DETECTION` | `SVC-WATER-TANK-CLEANING` | Same source ("tank"). | **Rejected** |

"Structural" and "authority specialists" from the same sentence are not
AFAQ Alhayat catalog services and are excluded, not silently mapped to
anything.

## 4. Related Candidates (Explicit Scope-Boundary Distinctions)

Source: named exclusions in service `README.md` § Boundary / § Scope
Requiring Confirmation sections — two services are marked Related here
only where one service's own documentation explicitly names the other as
an adjacent-but-separate scope, not because they share a catalog category.

| Type | Between | Source | Owner Decision (2026-07-24) |
|---|---|---|---|
| Related (boundary distinction) | `SVC-GENERAL-CLEANING` ↔ `SVC-DEEP-CLEANING` | `03_GENERAL_CLEANING/README.md` § Boundary: "Deep cleaning... are separate scopes unless explicitly approved." | **Confirmed** |
| Related (boundary distinction) | `SVC-GENERAL-CLEANING` ↔ `SVC-PEST-CONTROL` | Same source: "...pest control... are separate scopes unless explicitly approved." | **Confirmed** |
| Related (boundary distinction) | `SVC-DRAIN-UNBLOCKING` ↔ `SVC-PLUMBING` | `10_DRAIN_UNBLOCKING/README.md` § Scope Requiring Confirmation: "Boundaries between drain unblocking, plumbing repair, sewer-line work, and external authority responsibilities." | **Confirmed** |

**Why shared `SERVICE_CATALOG.md` category was not used as a Related
source:** `DECISION_LOG.md` decision 27 cautions that catalog categories
are classification labels only. Treating every same-category pair (e.g.,
all five General Maintenance services) as automatically "Related" would
read a structural relationship into a label the repository has explicitly
said not to over-interpret. Only relationships named in a service's own
text are included.

"Post-construction work," "specialist fabric cleaning," "hazardous
materials," "work at height," and "licensed maintenance" (also named in
General Cleaning's Boundary section) and "sewer-line work" and "external
authority responsibilities" (Drain Unblocking) are not distinct catalog
services and are excluded rather than mapped to anything.

---

## 5. Unresolved Source References (Not Validated)

Terms appearing in source documents that do not exactly match a
`SERVICE_CATALOG.md` name. One term is closed as a permanent unresolved
historical reference; two were resolved 2026-07-25 and moved to § 2 (kept
below for the audit trail, marked accordingly); two were dropped
2026-07-25 and retained here only as historical references, per the
standing rejected/dropped-candidate retention policy.

| Term used in source | Where | Possible match | Status |
|---|---|---|---|
| "Basic Cleaning" | `UPSELL_CROSSSELL_DRAFT.md` § Upselling | Not mapped | **Closed 2026-07-25 — remains an unresolved historical source reference.** Owner-decided: not `SVC-GENERAL-CLEANING`, not `SVC-DEEP-CLEANING`, and no new service is created for it. This is a final decision, not a pending item — no further resolution is expected. |
| "Bathroom Deep Cleaning" | `UPSELL_CROSSSELL_DRAFT.md` § Cross-Selling (after Plumbing) | `SVC-DEEP-CLEANING` | **Resolved 2026-07-25** — Owner-confirmed as a sub-scope of `SVC-DEEP-CLEANING`; recorded as a Cross-sell candidate in § 2. No new service created. |
| "Electrical Inspection" | Same document (after AC Maintenance; after Painting) | `SVC-ELECTRICAL-MAINTENANCE` | **Resolved 2026-07-25** — Owner-confirmed as a sub-scope of `SVC-ELECTRICAL-MAINTENANCE` for both occurrences; recorded as two Cross-sell candidates in § 2. No new service created. |
| "Air Duct Cleaning" | Same document (after AC Maintenance) | None | **Dropped 2026-07-25** — Owner-confirmed not to map to any existing catalog service. Historical reference only, per rejected/dropped-candidate retention policy. |
| "Preventive Maintenance" | Same document (after Pest Control) | None | **Dropped 2026-07-25** — Owner-confirmed as a possible commercial maintenance concept, not a catalog service. Historical reference only, per rejected/dropped-candidate retention policy. |

---

## 6. Coverage Summary

**Updated 2026-07-25 — zero-coverage gap resolved.** On 2026-07-24, after
the Owner rejected the `SVC-WATER-LEAK-DETECTION` → `SVC-AC-MAINTENANCE`
dependency candidate, `SVC-AC-MAINTENANCE` had zero confirmed relationship
candidates, alongside `SVC-ELECTRICAL-MAINTENANCE`. On 2026-07-25, the
Owner resolved the "Electrical Inspection" source term as a sub-scope of
`SVC-ELECTRICAL-MAINTENANCE`, which validated two new Cross-sell
candidates: `SVC-AC-MAINTENANCE` → `SVC-ELECTRICAL-MAINTENANCE` and
`SVC-PAINTING` → `SVC-ELECTRICAL-MAINTENANCE`. Both formerly zero-coverage
services now have at least one confirmed candidate edge — `SVC-AC-MAINTENANCE`
as the source of a confirmed Cross-sell, `SVC-ELECTRICAL-MAINTENANCE` as
its target from two sources.

`SVC-WATER-TANK-CLEANING` retains coverage despite its dependency
candidate being rejected, because its Cross-sell candidate (from
`SVC-PLUMBING`) was separately confirmed. `SVC-WATERPROOFING` retains
coverage because its dependency candidate was confirmed. Every one of the
12 catalog services now has at least one confirmed candidate edge.

---

## Owner Review Resolution (2026-07-24)

1. **Cross-sell (§ 2):** all 3 candidates confirmed — Plumbing → Water
   Tank Cleaning, Pest Control → Deep Cleaning, Painting → Handyman.
2. **Dependency (§ 3):** 2 of 4 confirmed (Water Leak Detection →
   Plumbing, Water Leak Detection → Waterproofing); 2 of 4 rejected (Water
   Leak Detection → AC Maintenance, Water Leak Detection → Water Tank
   Cleaning). Rejected rows are kept in § 3, marked Rejected, rather than
   deleted, to preserve the review record.
3. **Related (§ 4):** all 3 candidates confirmed — General Cleaning ↔
   Deep Cleaning, General Cleaning ↔ Pest Control, Drain Unblocking ↔
   Plumbing.
4. **Unresolved source terms (§ 5):** left open. The Owner did not
   resolve "Basic Cleaning," "Bathroom Deep Cleaning," "Electrical
   Inspection" (both occurrences), "Air Duct Cleaning," or "Preventive
   Maintenance" in this review; all five remain Pending Owner Input.
5. **`SVC-ELECTRICAL-MAINTENANCE` / `SVC-AC-MAINTENANCE` zero-coverage
   question:** left open. The Owner did not decide whether either service
   should remain without a confirmed relationship; both remain
   zero-coverage pending further input (see § 6).

This resolution confirms or rejects only the 10 originally drafted
candidates. It does not resolve the 5 unresolved terms or the
zero-coverage question, does not create any new candidate, and does not
create `SERVICE_RELATIONSHIPS.md`.

## Owner Review Resolution — Round 2 (2026-07-25)

Recorded under Program C Phase C.2, Work Package 2:

1. **"Bathroom Deep Cleaning"** confirmed as a sub-scope of
   `SVC-DEEP-CLEANING`; no new service created; recorded as a Cross-sell
   candidate (§ 2), Confirmed.
2. **"Electrical Inspection"** confirmed as a sub-scope of
   `SVC-ELECTRICAL-MAINTENANCE` for both occurrences; no new service
   created; recorded as two Cross-sell candidates (§ 2), Confirmed.
3. **"Air Duct Cleaning"** dropped — does not map to any existing
   service. Retained in § 5 as a historical reference only, per the
   standing rejected/dropped-candidate retention policy.
4. **"Preventive Maintenance"** dropped — treated as a possible
   commercial maintenance concept, not a catalog service. Retained in § 5
   as a historical reference only, same policy.
5. **`SVC-AC-MAINTENANCE` zero-coverage** resolved by adding `SVC-AC-MAINTENANCE`
   → `SVC-ELECTRICAL-MAINTENANCE` (Cross-sell), per decision 2 above.
6. **`SVC-ELECTRICAL-MAINTENANCE` zero-coverage** resolved by confirming
   both `SVC-AC-MAINTENANCE` → `SVC-ELECTRICAL-MAINTENANCE` and
   `SVC-PAINTING` → `SVC-ELECTRICAL-MAINTENANCE` (Cross-sell), per
   decision 2 above.

**Not addressed this round: "Basic Cleaning."** No decision was given for
this term. It remains in § 5, unresolved, exactly as before — not dropped,
not mapped, not silently resolved.

This resolution creates no new service, does not create
`SERVICE_RELATIONSHIPS.md`, and does not touch ESMM, EPGM, Service DNA
drafts, or the Customer Intent Model draft.

## Owner Review Resolution — Round 3 (2026-07-25)

Recorded under Program C Phase C.2, Deep Cleaning cross-artifact tension
resolution (raised by the Consolidated Readiness Review):

1. **Pest Control → Deep Cleaning** and **Plumbing → Deep Cleaning**
   remain confirmed as valid structural Cross-sell relationships (§ 2).
2. **Limitation attached:** these two relationships do not indicate Deep
   Cleaning is publication-ready. They must not be used for AI answers,
   publishing, or customer-facing material until `SERVICE_DNA_DRAFT_DEEP_CLEANING.md`'s
   scope-differentiation blocker (Deep Cleaning vs. General Cleaning) is
   resolved.
3. No other confirmed relationship in this file is affected.

This resolution creates no new candidate, does not create
`SERVICE_RELATIONSHIPS.md`, and does not touch ESMM, EPGM, or any Service
DNA draft.

## Owner Review Resolution — Round 4 (2026-07-25, Phase C.2 Work Package 2)

Recorded under Program C Phase C.2, Work Package 2 (Consolidated QA
Resolution — B2, B3):

1. **Alternative (§1):** confirmed closed — no Alternative relationships
   exist across the 12 catalog services at this stage. No candidates
   identified; not pending resolution; re-evaluate only if new evidence
   appears. §1's Alternative row is updated accordingly.
2. **Deep Cleaning limitation (§2):** confirmed lifted. The
   scope-differentiation-from-General-Cleaning blocker that Round 3's
   limitation was tied to is resolved by `SERVICE_DNA_DRAFT_DEEP_CLEANING.md`
   Rounds 3–4 (Deep Cleaning confirmed as a separate catalog service from
   General Cleaning, Task Scope as the differentiation basis, with scope,
   exclusions, and boundary now recorded). The Pest Control → Deep
   Cleaning and Plumbing → Deep Cleaning Cross-sell candidates now carry
   the same status as every other confirmed relationship in this file.
3. No new candidate is created by this round. `SERVICE_RELATIONSHIPS.md`
   is not created. ESMM and EPGM are not touched. No Service DNA draft is
   modified by this round.

## Validation Performed

- Every candidate's both ends were checked against `SERVICE_CATALOG.md`'s
  12 approved `SVC-` IDs; any source term that did not resolve to an exact
  catalog name was excluded and listed separately in § 5, not mapped by
  assumption.
- No cycle exists among the drafted edges, including the three added
  2026-07-25 (checked by inspection: all Cross-sell and Dependency edges
  are one-directional and do not loop; Related edges are explicitly
  bidirectional boundary pairs, not chains).
- No relationship was inferred from a service name or shared category —
  every populated candidate traces to an explicit textual mention in a
  cited source.
- Parent and Child are left dormant, not populated with any invented
  pair, consistent with decision 27.
- No commercial claim (discount, saving, urgency, availability, price) was
  introduced — the source document's own instruction ("Recommendations
  must never imply that an unapproved service, package, discount, saving,
  urgency, or availability exists") is respected by omission.
- `09_AI_KNOWLEDGE/ENTITY_RELATIONSHIPS.md` was read for awareness only,
  per Owner instruction, and contributed no content to this draft.
- This file does not modify `ENTERPRISE_SERVICE_META_MODEL.md`,
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`, `09_AI_KNOWLEDGE/ENTITY_RELATIONSHIPS.md`,
  or any file under `04_SERVICE_KNOWLEDGE/` or `06_CUSTOMER_AND_SALES/`.
- No `SERVICE_RELATIONSHIPS` registry file was created.

## Status

Draft — Preparatory, Owner-Reviewed (Complete). The Business Owner has
resolved every item raised during Phase C.2 Work Package 2: all 10
originally drafted candidates (2026-07-24); "Bathroom Deep Cleaning,"
"Electrical Inspection" (both occurrences), "Air Duct Cleaning,"
"Preventive Maintenance," both zero-coverage services, and "Basic
Cleaning" (closed 2026-07-25 as a permanent unresolved historical
reference, not mapped to any service); and, per the AGT-QA consolidated
review, the Alternative relationship type (closed 2026-07-25 — no
candidates identified across the 12 services) and the Deep Cleaning
publication limitation (lifted 2026-07-25 — its underlying scope blocker
is resolved). No item remains pending Owner decision. This draft
reflects its first independent AGT-QA consolidated review (Phase C.2
Work Package 2) against its final candidate set (6 Cross-sell, 2
Dependency, 3 Related — 11 confirmed candidates total) and is not
canonical — even confirmed candidates are not approved relationships
until the underlying source facts (all currently Draft, Blocked, or
"Requiring Confirmation") are separately confirmed, and until
`SERVICE_RELATIONSHIPS.md` is created through a later, separate
authorization.
