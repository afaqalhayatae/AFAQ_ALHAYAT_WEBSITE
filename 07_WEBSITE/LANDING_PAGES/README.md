# Google Ads Landing Pages

## Document Information

- **Owner:** Business Owner / Marketing
- **Status:** Published — all 12 landing pages are live in `afaqalhayatae-app` (commits `9f7727f`, `5016c8d`, the Painting page added 2026-08-07, and Interior Decoration added 2026-08-07 — see below).
- **Prepared:** 2026-08-06
- **Updated:** 2026-08-07 — added `PAINTING/` (Owner-prioritized, "عايزك تركز لي علي الصبغ والديكوات"); `INTERIOR_DECORATION/` was prepared but initially held back pending an explicit Owner activation decision (the Phase 3a sequencing gate below) — the Owner reviewed the summary and gave that approval directly in chat the same day ("انشر"), so it was merged and published too. `afaqalhayatae-app/src/lib/catalog/booking-options.ts`'s cross-cutting gap (no `interior-decoration` entry, so `/book?service=interior-decoration` couldn't pre-select a category) was fixed at the same time.

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
| `PAINTING/` | `painting` | `painting` |
| `INTERIOR_DECORATION/` | `interior-decoration` | `interior-decoration` |

## Interior Decoration — publication note

This was the first of the 11 "Service Expansion Phase" services (`00_GOVERNANCE/11_SERVICE_ACTIVATION_REVIEW.md`) to go live, ahead of that review's recommended Phase 3a sequencing ("activate after Phase 1 signal is clean" — Phase 1 hasn't shipped yet). It was held back for exactly that reason when first prepared on 2026-08-07, pending an explicit Owner activation decision. The Owner reviewed the hold-back reasoning in chat the same day and approved publishing directly ("انشر") — the content itself was never the blocker (`SERVICE_DATABASE.json`'s `interior-decoration` entry is real and Owner-sourced, unchanged from the prepared draft). This is a lighter-weight approval than Painting's formal `DECISION_LOG.md` #38 / `PAINTING_CONTENT_APPROVAL_DECISION.md` sign-off — if a written decision record is wanted for this one too, that's still open.

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
