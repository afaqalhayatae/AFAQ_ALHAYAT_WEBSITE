# Local SEO Execution Map

## Document Information

- **Status:** Draft — execution checklist only, not itself an approval to build any page
- **Prepared:** 2026-08-02
- **Relationship to existing documents:** `LOCAL_SEO_MASTER_PLAN.md` (this session, prior turn) already defines the full architecture — page hierarchy, seven mandatory per-page elements, and the Pest-Type + City open decision. **This document does not restate that architecture.** It is a leaner execution checklist: exactly which Service+City and Pest-Type+City combinations are ready to build first, given current content readiness, and which are blocked and why.

---

## 1. UAE Emirates (per `03_MARKET/SERVICE_AREAS.md` — unchanged, not re-approved here)

Dubai · Abu Dhabi · Sharjah · Ajman · Umm Al Quwain · Ras Al Khaimah · Fujairah — all 7 approved at emirate level since 2026-07-23. Only Dubai has a live emirate page today.

## 2. Service + City — Execution Readiness

Per `SERVICE_MASTER_MATRIX.md`, only content-complete services are eligible for a City page (`LOCAL_SEO_MASTER_PLAN.md` §1's no-shallow-pages rule). Readiness by service:

| Service | Content status | City-page eligible? |
|---|---|---|
| AC Maintenance, Plumbing, Electrical Maintenance, Painting | Complete, approved (5-stage trail) | **Yes** |
| Handyman | Complete, approved | **Yes** — page itself stays grid-excluded (image gap) but a dedicated City page is not blocked by that, since it doesn't depend on the homepage grid |
| General Cleaning, Deep Cleaning, Pest Control, Water Tank Cleaning, Drain Unblocking, Water Leak Detection, Villa/Office/Post-Construction/Carpet-Upholstery Cleaning | Content live | **Yes** |
| Waterproofing | Content live | **Yes** (same grid-exclusion note as Handyman) |
| 11 Service-Expansion-Phase services (CCTV Installation, etc.) | No content | **No** — blocked until base service content exists |

**Worked examples from this directive's instruction, checked against the table above:**
- AC Maintenance Dubai — **eligible**
- Plumbing Sharjah — **eligible**
- Cleaning Dubai — **eligible**, but "Cleaning" must resolve to one specific service (e.g., General Cleaning Dubai), not a generic combined page, per the no-shallow-pages rule

## 3. Pest Type + City — Execution Readiness

Per `LOCAL_SEO_MASTER_PLAN.md` §6, this remains **blocked on an Owner decision** (Option A: content variant under `SVC-PEST-CONTROL`; Option B: new catalog IDs) before any such page is built. This execution map does not resolve that decision. Once resolved:

| Pest type | Source content depth | Notes |
|---|---|---|
| Cockroach Control | Draft `subServices` entry (SEO fields, short description) + parent Pest Control content | Not yet Evidence-Gated |
| Ant Control | Draft `subServices` entry + parent content | Not yet Evidence-Gated |
| Termite Control | Draft `subServices` entry + parent content | Not yet Evidence-Gated |
| Bed Bug Control | Parent Pest Control content only (no dedicated subService entry exists) | Thinnest source material of the four |

Worked examples (Cockroach Control Sharjah, Bed Bug Control Dubai, etc.) remain **not built** — architecture and source-content readiness are mapped here for when the Owner decision clears, not executed now.

## 4. Sequencing (unchanged from `LOCAL_SEO_MASTER_PLAN.md` §7)

1. Build the six missing emirate pages first.
2. Build Service+City pages for the already-eligible services (§2), Dubai first.
3. Resolve the Pest-Type+City decision before building any pest-type page (§3).
4. Do not build any page for the 11 structural-only services.

---

## What This Document Does Not Do

- Does not create any page, route, or content.
- Does not resolve the Pest-Type+City Owner decision.
- Does not modify `LOCAL_SEO_MASTER_PLAN.md`, `SERVICE_AREAS.md`, or `SERVICE_CATALOG.md`.

## Related Documents

- `10_MARKETING_AND_SEO/LOCAL_SEO_MASTER_PLAN.md` — full architecture (not duplicated here)
- `00_GOVERNANCE/SERVICE_MASTER_MATRIX.md`
- `03_MARKET/SERVICE_AREAS.md`
