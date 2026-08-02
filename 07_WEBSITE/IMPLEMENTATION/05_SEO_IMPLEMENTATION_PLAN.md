# SEO Implementation Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only, no SEO configuration implemented by this document
- **Version:** 1.0
- **Prepared:** 2026-07-27
- **Depends on:** `07_WEBSITE/01_HOMEPAGE/03_HOMEPAGE_SEO_AI.md`, `99_STANDARDS/SEO_STANDARD.md`, `10_MARKETING_AND_SEO/*`, `09_AI_KNOWLEDGE/*`, `04_CONTENT_INTEGRATION_PLAN.md`

## Note on scope

This document translates existing, already-approved SEO/GEO strategy documents into an implementation plan for the Next.js build. It does not invent new SEO strategy and does not configure any tool.

---

## 1. Technical SEO Foundation

| Requirement | Source | Implementation approach |
|---|---|---|
| Canonical URLs | `07_WEBSITE/01_HOMEPAGE/03_HOMEPAGE_SEO_AI.md` | Next.js `metadata.alternates.canonical` per page; apex-vs-`www` resolved once `06_DEPLOYMENT_PLAN.md`'s open DNS gate closes. |
| XML Sitemap | Same | Generated programmatically from the same content adapter (`04_CONTENT_INTEGRATION_PLAN.md`) that gates page publishability — a page never appears in the sitemap before it's publishable. |
| Robots.txt | Same | Environment-aware: staging disallows all; production allows per publishable route set. |
| HTTPS | `TECH_STACK.md` | Enforced at Hostinger/DNS level; verified during deployment (see `06_DEPLOYMENT_PLAN.md`). |
| Core Web Vitals / mobile-friendliness | `TECH_STACK.md`, `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §9 | Next/Image, code splitting, lazy loading, performance budget checks in CI. |
| Image optimization (WebP, alt text) | `LUXURY_DESIGN_DIRECTION.md` §4 | Next/Image with mandatory alt text sourced from each service's `MEDIA.md` entry — no image ships without one. |

---

## 2. Structured Data (schema.org)

Per `10_MARKETING_AND_SEO/SCHEMA_STRATEGY.md` and the Homepage SEO/AI strategy, implement:

- **Organization Schema** — sourced from `01_BUSINESS/COMPANY_PROFILE.md` + `02_BRAND/CONTACT_INFORMATION.md` (approved fields only).
- **LocalBusiness Schema** — sourced from `02_BRAND/LOCAL_SEO_PROFILE.md`; fields still `Pending` (address, GBP URL) are simply omitted from the schema object, never filled with a placeholder.
- **Service Schema** — one per publishable service page, generated from the same `services.ts` adapter output used to render the visible page — schema and visible content must never diverge.
- **FAQ Schema** — generated from each service's `FAQ.md` and paired 1:1 with the visible `<FaqAccordion />` content.
- **Breadcrumb Schema** — derived from the route hierarchy (`/services/[serviceId]`, `/locations/[areaId]`).
- **WebSite Schema** — homepage only, including sitelinks search box only if a working site search exists.

All schema generation is a projection of the content adapter's output, not a separately maintained data source — this avoids the exact "visible page says one thing, schema says another" failure mode `SYSTEM_ARCHITECTURE.md` §7 warns against.

---

## 3. Local SEO / GEO Implementation

- **NAP consistency:** Name/Address/Phone must render identically everywhere it appears (header, footer, contact page, schema) because all instances trace to the same `CONTACT_INFORMATION.md` adapter output — not independently typed per location.
- **Coverage claims:** Location pages state coverage strictly from `SERVICE_MATRIX.md` and `SERVICE_AREAS.md` — emirate-level claims only until a given area clears its own registry review checklist, per `04_CONTENT_INTEGRATION_PLAN.md` §5.
- **Google Business Profile integration:** Held until the GBP URL and address are confirmed (`LOCAL_SEO_PROFILE.md` — currently pending); the site should not embed a Maps/GBP widget referencing unconfirmed location data.
- **Target entities:** Reuse the entity list already defined in `07_WEBSITE/01_HOMEPAGE/03_HOMEPAGE_SEO_AI.md` (AFAQ Alhayat; Pest Control, Cleaning, Facility Management, Water Tank Cleaning, Disinfection; the seven emirates) as the initial entity set for on-page semantic markup — extended per-service as each package clears its own `SEO_AI.md`.

---

## 4. URL Structure and Internal Linking

- Apply `10_MARKETING_AND_SEO/URL_AND_INTERNAL_LINKING_STANDARD.md` for all route naming (lowercase, hyphenated, locale-prefixed, stable once published).
- Service and location pages cross-link to each other (a service page links to its available areas; an area page links to its available services) generated from `SERVICE_MATRIX.md`, not hand-authored per page — ensuring the link graph never drifts from the approved coverage data.
- Avoid orphan pages: every publishable page must be reachable from at least the relevant index page and the sitemap.

---

## 5. Bilingual SEO

- `hreflang` alternates (`ar`, `en`, and `x-default`) on every paired page, generated automatically from the locale-routing structure in `01_APPLICATION_ARCHITECTURE.md` §4 — not manually maintained per page.
- Separate sitemap entries per locale, both gated by the same publishability rules.
- Meta titles/descriptions authored per language (not machine-translated) per `PROJECT_MANIFEST.md`'s bilingual-equality principle.

---

## 6. AI / GEO Optimization

Per `07_WEBSITE/01_HOMEPAGE/03_HOMEPAGE_SEO_AI.md` and `99_STANDARDS/AI_GEO_STANDARD.md` / `09_AI_KNOWLEDGE/GEO_STRATEGY.md`:

- Semantic HTML with a single `<h1>` and correct heading hierarchy per page (already a `12_DESIGN_SYSTEM/TYPOGRAPHY.md` rule, reapplied here as an SEO/AI requirement, not duplicated as a separate rule).
- Content answers customer questions directly and factually — no keyword stuffing, no unverifiable claims — matching `09_AI_KNOWLEDGE/ANSWER_POLICY.md`'s own restraint requirements so the site and any AI answer surface stay consistent.
- Entity relationships (service ↔ area ↔ organization) expressed consistently between visible content, schema markup, and `09_AI_KNOWLEDGE/ENTITY_REGISTRY.md` / `ENTITY_RELATIONSHIPS.md`.

---

## 7. Analytics and Measurement

- Google Analytics, Search Console, and Tag Manager (per `TECH_STACK.md`) are wired in **test mode** during Phase 1/2, per `IMPLEMENTATION_READINESS_REPORT.md`'s prohibition on live external-channel connections without a confirmed gate.
- Success metrics tracked match `07_WEBSITE/01_HOMEPAGE/03_HOMEPAGE_SEO_AI.md`: organic traffic, local rankings, AI mentions (where measurable), conversion/booking rate, CTR, engagement time, Core Web Vitals.
- Event tracking must not capture more personal data than the `Consent` and `Interaction` entities in `08_DIGITAL_SYSTEMS/DATA_MODEL.md` already permit.

---

## 8. Pre-Publish SEO Gate

Before any page goes live, confirm (cross-referencing `LUXURY_DESIGN_DIRECTION.md` §11's Design Acceptance Gate, not duplicating a separate checklist):

- [ ] Page content and schema markup are generated from the same adapter output.
- [ ] No claim on the page exceeds its source document's approval status.
- [ ] Location pages exist only for registry-approved `area_id`s.
- [ ] hreflang and canonical tags are correct for both locales.
- [ ] Core Web Vitals budget met on mobile.
- [ ] Analytics events are test-mode until the live-tracking gate is approved.

---

## What This Document Does Not Do

- It does not configure Google Search Console, Analytics, or Tag Manager accounts.
- It does not generate a sitemap, robots.txt, or schema object.
- It does not approve any page for publication.

---

## Related Documents

- `04_CONTENT_INTEGRATION_PLAN.md`
- `00_GOVERNANCE/03_CONTENT_TO_WEBSITE_MAPPING.md`
- `10_MARKETING_AND_SEO/SCHEMA_STRATEGY.md`
- `09_AI_KNOWLEDGE/GEO_STRATEGY.md`
