# Google Ads Landing Pages

## Document Information

- **Owner:** Business Owner / Marketing
- **Status:** Published — all 10 landing pages are live in `afaqalhayatae-app` (commits `9f7727f`, `5016c8d`), documented here for governance/reference.
- **Prepared:** 2026-08-06

## What this folder is

Conversion-focused landing pages built specifically for **paid Google Ads traffic**, one per service, at `afaqalhayatae.com/{locale}/lp/{slug}`. Each is built from a shared `GoogleAdsLandingPage` component (`afaqalhayatae-app/src/components/google-ads-landing-page.tsx`) reading from a single data source (`afaqalhayatae-app/src/lib/catalog/landing-pages.ts`) — not 10 separately designed pages.

**Not to be confused with** `07_WEBSITE/LANDING_PAGE_SYSTEM/`, which documents the informational `/services/{section}/{slug}` pages (organic/navigational traffic, different structure, different purpose). Both follow the shared general principles in `10_MARKETING_AND_SEO/LANDING_PAGE_STANDARD.md`.

## Services covered

| Folder | Live URL slug | Real catalog service |
|---|---|---|
| `PEST_CONTROL/` | `pest-control` | `pest-control` |
| `DEEP_CLEANING/` | `deep-cleaning` | `deep-cleaning` |
| `HOME_CLEANING/` | `home-cleaning` | `general-cleaning` |
| `AC_MAINTENANCE/` | `ac-maintenance` | `ac-maintenance` |
| `HOME_MAINTENANCE/` | `home-maintenance` | `handyman` |
| `PLUMBING/` | `plumbing` | `plumbing` |
| `ELECTRICAL/` | `electrical` | `electrical-maintenance` |
| `WATER_TANK_CLEANING/` | `water-tank-cleaning` | `water-tank-cleaning` |
| `VILLA_CLEANING/` | `villa-cleaning` | `villa-cleaning` |
| `EMERGENCY_HOME_SERVICES/` | `emergency-home-services` | (multi-trade bundle — no single service, books to `/book` without a `?service=` prefill) |

## Per-service files

- **CONTENT.md** — the page copy (hero, problem, why-us, service details, process, standard-of-work, pricing, FAQ, final CTA), bilingual. Mirrors the live app data; the app source is authoritative.
- **SEO.md** — title/description/keywords, canonical/indexing notes.
- **ADS_KEYWORDS.md** — the one genuinely new deliverable: primary/negative keywords, suggested ad groups, headlines, descriptions, CTA variations, message-match note. **Draft status** — no campaign has been created or funded; that remains an owner decision.
- **IMAGE_PLAN.md** — which real, already-approved photo is used and why (no AI-generated or fabricated imagery).
- **PAGE_STRUCTURE.md** — the fixed 11-section render order, with this service's section titles filled in.

## Claim-Safety notes specific to this system

- **Pricing:** every page says "Get a Free Quote," never a fixed AED figure.
- **Reviews:** an honest placeholder ("Customer reviews will appear here as they come in.") — no invented testimonials, per `10_MARKETING_AND_SEO/CONTENT_STRATEGY.md`.
- **"Standard of Work" section:** a single real photo, not a fabricated before/after comparison (no true before/after photo pairs exist in the approved library).
