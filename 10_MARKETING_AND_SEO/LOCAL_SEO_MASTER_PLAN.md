# Local SEO Master Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — architecture only. No page, content, FAQ, or schema is created by this document; no keyword volume, ranking, or search-demand figure is asserted (none exists in this repository).
- **Version:** 1.0
- **Prepared:** 2026-08-02
- **Depends on:** `03_MARKET/SERVICE_AREAS.md` (approved emirate + Tier-1 community coverage), `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `00_GOVERNANCE/SERVICE_MASTER_MATRIX.md` (current per-service readiness), `10_MARKETING_AND_SEO/LOCAL_SEO.md` (existing local-SEO rules/release checklist — not restated here, only extended), `URL_AND_INTERNAL_LINKING_STANDARD.md`, `SCHEMA_STRATEGY.md`, `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` (existing 10-category keyword framework — reused, not duplicated).
- **Relationship to existing documents:** `LOCAL_SEO.md` already sets the governing rules (no branch fabrication, no thin swapped-city-name pages, NAP consistency, release checklist). This document does not restate those rules — it builds the **structural architecture** (URL pattern, page hierarchy, per-page-type requirement set) that `LOCAL_SEO.md`'s rules apply to, scaled to the current 27-service catalog and all 7 emirates.

---

## 1. Governing Constraint — No Shallow Pages

Per `LOCAL_SEO.md` and `CURRENT_PROJECT_STATUS.md`'s hard publication blocks, a Service + City page is **not** permitted to exist merely by substituting a city name into duplicated copy. Every page type defined in §5 requires unique local content, and **no page may be created for a service that is not itself content-complete** (see `SERVICE_MASTER_MATRIX.md` — 11 of 27 services have no content yet; those services get no city page of any kind until their base content is approved). This document defines architecture only; it authorizes no page creation.

---

## 2. Current Foundation (verified, not assumed)

- **Emirate-level coverage is already approved** for all 7 emirates, all 27 catalog services, since 2026-07-23 (`SERVICE_AREAS.md` Approved Registry). This plan does not seek new coverage approval.
- **Only Dubai has a live emirate page today** (`13_LOCATION_EXPANSION_ROADMAP.md`'s verified current-state note); the other six are approved but unbuilt.
- **Tier-1 priority communities are already registered** per emirate in `SERVICE_AREAS.md` (e.g., Palm Jumeirah, Emirates Hills, Dubai Hills Estate for Dubai; equivalents recorded for Abu Dhabi, Sharjah, Ajman/Ras Al Khaimah, Fujairah/Umm Al Quwain) — these are **service-area and marketing-priority markers, not branch addresses**, and city/community-level pages remain entirely unbuilt for every emirate.
- **`14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` already defines a 10-category mandatory keyword framework** (primary, secondary, long-tail, search-intent, local, Arabic, English, plus three more) for the original 12 services. This plan extends that same framework's *local* category to the full 27-service, 7-emirate matrix rather than defining a new one.

---

## 3. Page Hierarchy

```
/{locale}/services/{service-slug}                          — service page (exists for all 27, content gated per SERVICE_MASTER_MATRIX.md)
/{locale}/locations/{emirate-slug}                          — emirate page (exists for Dubai only today)
/{locale}/services/{service-slug}/{emirate-slug}            — Service + City page (none exist yet — this plan's subject)
/{locale}/services/{service-slug}/{emirate-slug}/{pest-type} — Pest-type + City page (Pest Control only — see §6, requires an Owner decision before any exists)
```

URL slugs follow the already-approved rules in `URL_AND_INTERNAL_LINKING_STANDARD.md` (lowercase ASCII, hyphenated, no tracking codes, no invented district/branch terms) — not restated here.

---

## 4. Service + City Matrix — Scope

| Category | Services | Emirates | Maximum page count if fully built |
|---|---|---|---|
| Maintenance | 19 (per `SERVICE_MASTER_MATRIX.md`) | 7 | 133 |
| Cleaning | 7 | 7 | 49 |
| Pest Control | 1 service, pest-type sub-pattern TBD (§6) | 7 | 7 (service-level) + pest-type expansion, TBD |

**This is a maximum theoretical count, not a build target.** Per §1, only content-complete services are eligible, and even then, pages are sequenced (§7) — this plan does not authorize building all 133+49 pages at once, nor does `LOCAL_SEO.md`'s "unique, useful content" rule permit doing so mechanically.

### Illustrative examples (pattern, not a build list)

**Maintenance:** AC Maintenance Dubai · Plumbing Sharjah · Electrical Maintenance Abu Dhabi · Painting Ajman · Handyman Services Fujairah (content-complete but stays grid-excluded per its image gap — see `SERVICE_MASTER_MATRIX.md`)

**Cleaning:** Deep Cleaning Dubai · Villa Cleaning Sharjah · General Cleaning Ras Al Khaimah · Water Tank Cleaning Umm Al Quwain

**Pest Control (pattern only, see §6):** Cockroach Control Sharjah · Ant Control Dubai · Bed Bug Control Abu Dhabi · Termite Control Ajman

---

## 5. Required Elements Per Page (mandatory, no exceptions)

Every future Service + City (or Pest-Type + City) page must define all seven before content production begins:

| # | Element | Rule |
|---|---|---|
| 1 | **SEO Title** | Pattern `[Service] in [City] \| AFAQ AL HAYAT`, following the exact title convention already used on the 16 live service pages (`SERVICE_DATABASE.json` `seoTitle` fields) — not invented per page. |
| 2 | **Meta Description** | Localized restatement of the service's already-approved `metaDescription`, naming the specific emirate — never a copy-paste of the base service page's description with only the city swapped, per `LOCAL_SEO.md`'s explicit prohibition. |
| 3 | **Local intent keywords** | Reuses `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`'s Category 5 (Local SEO keywords) framework: `[service] + [emirate]` generated systematically from `SERVICE_MATRIX.md`/`SERVICE_AREAS.md`, never hand-invented per page. Both English and Arabic required (Categories 6–7 of the same framework). |
| 4 | **Unique content** | At minimum: emirate-specific coverage note (from `SERVICE_AREAS.md`), any Tier-1 community context relevant to that emirate, and locally-relevant framing of the service's already-approved scope/common-problems content — not a template with the city name substituted. This is the specific requirement `LOCAL_SEO.md`'s Release Checklist gates on ("unique, useful location context"). |
| 5 | **FAQ** | Minimum one locally-relevant Q&A in addition to the base service FAQ (e.g., coverage confirmation for that emirate) — reusing the base service's existing FAQ content is permitted for the remainder, but the page may not consist of *only* re-served base-service FAQ content with no local question. |
| 6 | **Internal linking plan** | Bidirectional: emirate page → every content-complete service's City page for that emirate; service page → every emirate where that service has a City page built. No orphan pages. Follows `URL_AND_INTERNAL_LINKING_STANDARD.md`'s existing internal-linking rules — not a new linking policy. |
| 7 | **Schema requirements** | `Service` schema (per `SCHEMA_STRATEGY.md`'s supported types) with `areaServed` set to the specific emirate from `SERVICE_AREAS.md`'s approved Area IDs; `FAQPage` schema only if the page's FAQ is genuinely visible on-page; **no `LocalBusiness` schema** unless/until an eligible, verified branch location exists — per `SCHEMA_STRATEGY.md`'s existing restriction, reused unchanged here. |

---

## 6. Pest Control — Pest-Type + City (open item, not resolved by this plan)

The pest-type + city pattern requested in this directive (Cockroach Control Sharjah, Ant Control Dubai, Bed Bug Control Abu Dhabi, Termite Control Ajman) is **architecturally straightforward** (same seven-element requirement as §5, with `{pest-type}` as an additional URL segment) but has one open precondition: **no separate catalog service ID exists per pest type today** (`SERVICE_MASTER_MATRIX.md` §"Pest Control" note). The current Pest Control content addresses pest types only as an internal `commonProblems` list within one service record, not as independently addressable service entities.

Before any Pest-Type + City page is built, the Owner must decide:

- **Option A:** Keep pest types as sub-sections of the single `SVC-PEST-CONTROL` page and build pest-type + city pages as *content variants* of that one service (no new catalog ID, `service-slug` stays `pest-control`, `{pest-type}` becomes a URL/content parameter only).
- **Option B:** Create distinct catalog IDs per pest type (e.g., `SVC-COCKROACH-CONTROL`), each with its own content/SEO/FAQ package — a larger content-authoring commitment, consistent with how the 11 Service-Expansion-Phase services were structurally onboarded.

This plan does not select an option. No pest-type page of either kind is created or authorized by this document.

---

## 7. Sequencing (recommended, not decided)

Building on `PROJECT_EXECUTION_STATUS_REPORT.md` §5:

1. Build the six missing emirate-level pages (Abu Dhabi, Sharjah, Ajman, Umm Al Quwain, Ras Al Khaimah, Fujairah) — prerequisite for any Service + City page, since the City page architecture nests under the emirate.
2. For the 16 already content-complete services, build Service + City pages for Dubai first (existing emirate page, fastest to pair), then the other six as their emirate pages come online.
3. Do not build any Service + City page for the 11 structural-only Maintenance-expansion services until their base service content is approved (§1's hard constraint).
4. Resolve the Pest-Type + City decision (§6) before building any pest-type page.
5. Community/Tier-1-level pages (Palm Jumeirah, etc.) are a distinct, later tier per `SERVICE_AREAS.md` — out of scope for this emirate-level City-page plan.

---

## What This Document Does Not Do

- Does not create any page, URL route, content string, FAQ, or schema markup.
- Does not create any new catalog service ID (including any pest-type ID).
- Does not modify `SERVICE_AREAS.md`, `SERVICE_CATALOG.md`, `LOCAL_SEO.md`, or any website file.
- Does not assert any keyword-volume, ranking, or search-demand data — none exists in this repository.
- Does not stage, commit, or push anything.

---

## Related Documents

- `10_MARKETING_AND_SEO/LOCAL_SEO.md` — governing rules and release checklist (extended, not duplicated, by this plan)
- `10_MARKETING_AND_SEO/URL_AND_INTERNAL_LINKING_STANDARD.md`, `SCHEMA_STRATEGY.md`
- `07_WEBSITE/IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md`, `13_LOCATION_EXPANSION_ROADMAP.md`, `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`
- `03_MARKET/SERVICE_AREAS.md` — approved emirate + Tier-1 community registry
- `00_GOVERNANCE/SERVICE_MASTER_MATRIX.md`, `PROJECT_EXECUTION_STATUS_REPORT.md`
