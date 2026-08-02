# Service Expansion Roadmap

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only. No page, content, or image is created by this document.
- **Version:** 1.0
- **Prepared:** 2026-07-28
- **Scope:** All 12 catalog services, mapped to page/SEO/image/content requirements.
- **Depends on:** `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`, `05_SEO_IMPLEMENTATION_PLAN.md`, `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md`.

## Note on scope and grouping

This document groups the catalog's 12 services into the three groups requested (Maintenance, Cleaning, Pest Control) rather than the catalog's own three category labels (General Maintenance / Cleaning & Pest Control / Drainage & Water Protection), since those don't map 1:1. The mapping is stated explicitly below so nothing is silently reclassified: **Maintenance** here = catalog's "General Maintenance" + "Drainage & Water Protection" (8 services); **Cleaning** = catalog's "Cleaning & Pest Control" minus Pest Control itself (3 services); **Pest Control** = the single Pest Control service. No new category is created in `SERVICE_CATALOG.md` by this document.

No SEO keyword volumes, rankings, or search-demand figures are asserted anywhere below — "SEO intent" describes the *type* of customer search the page should satisfy, not invented research data.

---

## 0. Current App State (verified, not assumed)

Per the existing app audit, `src/app/[locale]/services/[slug]/page.tsx` already generates a route for every catalog service dynamically — the route/page-requirement question is already structurally solved app-wide. What varies per service is **content depth and image readiness**, which is gated by each service's own canonical package maturity in `SERVICE_CATALOG.md`, not by missing code.

---

## 1. Maintenance Services (8)

| Service | Page requirement | SEO intent | Required images (per §7/§9 of `11_VISUAL_ASSET_STRATEGY.md`) | Content requirements |
|---|---|---|---|---|
| AC Maintenance (`SVC-AC-MAINTENANCE`) | Route exists; content depth gated by package (Structurally complete draft) | Routine/emergency AC servicing intent | Hero (technician at AC unit), detail (condenser/filter), before/after only if verified | `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `CUSTOMER_GUIDE.md`, `FAQ.md`, `SEO_AI.md`, `CONTENT_AR/EN.md`, `MEDIA.md` — package needs owner/technical evidence review before real imagery ships |
| Plumbing (`SVC-PLUMBING`) | Route exists; Structurally complete draft | Leak/blockage/fixture-repair intent | Hero (technician with tools at fixture), detail (pipe/fitting work) | Same file set; same review gate |
| Electrical Maintenance (`SVC-ELECTRICAL-MAINTENANCE`) | Route exists; Structurally complete draft | Wiring/fixture/safety-inspection intent | Hero (technician at panel/fixture, visible PPE), detail (tools) | Same file set; same review gate |
| Painting (`SVC-PAINTING`) | Route exists; Structurally complete draft | Interior/exterior repaint intent | Hero (in-progress painting), before/after only if verified, color/finish detail shots | Same file set; same review gate |
| Handyman Services (`SVC-HANDYMAN`) | Route exists; Structurally complete draft | General small-repair/multi-task intent | Hero (technician with varied tools), detail per common task type | Same file set; same review gate |
| Drain Unblocking (`SVC-DRAIN-UNBLOCKING`) | Route exists; Structurally complete draft; scope owner-confirmed but technical detail pending | Blocked-drain/emergency intent | Hero (technician with drain equipment), equipment detail | Same file set; scope/technical detail approval per `SERVICE_CATALOG.md` still pending |
| Waterproofing (`SVC-WATERPROOFING`) | Route exists; Structurally complete draft; scope owner-confirmed but technical detail pending | Water-ingress-protection intent (thermal insulation excluded unless separately confirmed, per `DECISION_LOG.md` decision 19) | Hero (application/membrane work), before/after only if verified | Same file set; same pending-approval note |
| Water Leak Detection (`SVC-WATER-LEAK-DETECTION`) | Route exists; Structurally complete draft; scope owner-confirmed but technical detail pending | Hidden-leak-detection intent | Hero (technician with detection equipment), equipment detail | Same file set; same pending-approval note |

## 2. Cleaning Services (3)

| Service | Page requirement | SEO intent | Required images | Content requirements |
|---|---|---|---|---|
| General Cleaning (`SVC-GENERAL-CLEANING`) | Route exists; **Review-ready package** — closest to publishable of this group | Routine home/office cleaning intent | Hero (cleaning in progress, real equipment), detail (equipment/products used) | File set as above; package already review-ready — prioritize this one first for real imagery |
| Deep Cleaning (`SVC-DEEP-CLEANING`) | Route exists; **Blocked pending owner scope** — no source draft exists | Intensive/move-in-move-out cleaning intent | None commissioned until scope is approved — do not photograph an undefined service | Owner must define scope before any content or image work proceeds |
| Water Tank Cleaning (`SVC-WATER-TANK-CLEANING`) | Route exists; **Review-ready package** | Tank hygiene/inspection intent | Hero (technician at tank access point, PPE visible), before/after only if verified | File set as above; second-priority for real imagery alongside General Cleaning |

## 3. Pest Control Services (1)

| Service | Page requirement | SEO intent | Required images | Content requirements |
|---|---|---|---|---|
| Pest Control (`SVC-PEST-CONTROL`) | Route exists; **Knowledge package marked Complete** — most mature of all 12 | Preventive/treatment/emergency pest intent | Hero (technician applying approved treatment, PPE visible), equipment detail, before/after only if verified — per `BRAND_IMAGES.md`'s explicit warning against "fear-based pest imagery used excessively," lead with professionalism, not shock | File set complete per catalog; still requires the same evidence review as any other package before real photography replaces the current illustration |

---

## 4. Sequencing Recommendation (not an authorization to proceed)

1. **Pest Control and General Cleaning / Water Tank Cleaning** — most content-mature; real imagery here has the least content risk.
2. **The remaining General Maintenance services** (AC, Plumbing, Electrical, Painting, Handyman) — structurally complete drafts; imagery follows once each clears its own evidence review.
3. **Drain Unblocking, Waterproofing, Water Leak Detection** — technical scope still pending per `SERVICE_CATALOG.md`; no imagery or expanded content until that clears.
4. **Deep Cleaning** — blocked entirely pending Owner scope definition; not sequenced until that happens.

---

## What This Document Does Not Do

- Does not create, edit, or reclassify any file in `04_SERVICE_KNOWLEDGE/`.
- Does not commission, generate, or approve any image.
- Does not assert any keyword-volume or ranking data.
- Does not change any service's maturity status in `SERVICE_CATALOG.md`.

---

## Related Documents

- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`
- `05_SEO_IMPLEMENTATION_PLAN.md`
- `07_WEBSITE/IMPLEMENTATION/13_LOCATION_EXPANSION_ROADMAP.md`
