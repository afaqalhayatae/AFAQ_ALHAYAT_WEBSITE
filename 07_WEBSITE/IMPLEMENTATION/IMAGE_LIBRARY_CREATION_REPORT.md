# Image Library Creation Report

## Document Information

- Owner: AI Agent (planning)
- Status: Draft — Planning Only
- Version: 3.1 (complete, all briefs reconciled — see "Completion (v3.0)" and the prompt-reconciliation update below)
- Date: 2026-07-28

---

## Completion (v3.0) — 12/12 Catalog Coverage Reached

The 3 services flagged as "not yet covered" in v2.0 — Drain Unblocking,
Waterproofing, Water Leak Detection — now have a complete image library:
`IMAGE_SEO_LIBRARY.md`, `IMAGE_GENERATION_BRIEF.md`, and
`assets/{hero,service-cards,process,trust,blog}/` in each of
`10_DRAIN_UNBLOCKING/`, `11_WATERPROOFING/`, `12_WATER_LEAK_DETECTION/`.
`README.md` and `CHANGELOG.md` were updated in all 3. No images were
generated.

**Visual-direction reconciliation applied at the same time:** the Owner
approved realistic professional photography as the platform's image
direction on 2026-07-28 (`00_GOVERNANCE/DECISION_LOG.md` decision 36;
`11_VISUAL_ASSET_STRATEGY.md` v2.0), after v2.0 of this report was written.
The 8 briefs from the v2.0 correction pass (`02_AC_MAINTENANCE` through
`09_HANDYMAN`) still contained the older "needs owner sign-off" wording for
that exact question — each was updated in place to reflect that the style
question is now Owner-approved, while preserving the one sub-issue decision
36 does **not** resolve: `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §10's
absolute prohibition on AI-generated media presented as real company
evidence. All 12 briefs (including the new 3) now carry consistent language
on this point. **`01_PEST_CONTROL/IMAGE_GENERATION_BRIEF.md` was not
touched** — it is a substantially larger, pre-existing document with 15
fully-specified illustration-style generation prompts written before decision
36; reconciling it means rewriting each prompt individually, which is a
larger, separate task not requested here and flagged for a future pass
rather than done unprompted.

### Final Service → Image Library Mapping (12/12)

| Real Catalog Folder | Service ID | Image Library Status |
|---|---|---|
| `01_PEST_CONTROL/` | `SVC-PEST-CONTROL` | Complete (pre-existing, richer 18-row library; generation brief prompts still reflect the pre-decision-36 illustration style — not yet reconciled) |
| `02_AC_MAINTENANCE/` | `SVC-AC-MAINTENANCE` | Complete |
| `03_GENERAL_CLEANING/` | `SVC-GENERAL-CLEANING` | Complete |
| `04_DEEP_CLEANING/` | `SVC-DEEP-CLEANING` | Complete |
| `05_WATER_TANK_CLEANING/` | `SVC-WATER-TANK-CLEANING` | Complete |
| `06_PLUMBING/` | `SVC-PLUMBING` | Complete |
| `07_ELECTRICAL_MAINTENANCE/` | `SVC-ELECTRICAL-MAINTENANCE` | Complete |
| `08_PAINTING/` | `SVC-PAINTING` | Complete |
| `09_HANDYMAN/` | `SVC-HANDYMAN` | Complete |
| `10_DRAIN_UNBLOCKING/` | `SVC-DRAIN-UNBLOCKING` | Complete — added in v3.0 |
| `11_WATERPROOFING/` | `SVC-WATERPROOFING` | Complete — added in v3.0 |
| `12_WATER_LEAK_DETECTION/` | `SVC-WATER-LEAK-DETECTION` | Complete — added in v3.0 |

**12 of 12 real catalog services now have a complete image library
structure.** No images have been generated anywhere in the catalog. The only
remaining open item sitewide is the `LUXURY_DESIGN_DIRECTION.md` §10 vs.
AI-photorealism question that decision 36 explicitly left open (see below).

### Update — `01_PEST_CONTROL` prompt reconciliation closed (2026-07-28)

The one item left open at the end of v3.0 — `01_PEST_CONTROL/IMAGE_GENERATION_BRIEF.md` still using illustration-style prompts — has been resolved. All 15 generation prompts were rewritten to realistic professional photography per decision 36, without changing any Asset ID, SEO filename, image purpose/usage, keyword target, or document structure (`01_PEST_CONTROL/CHANGELOG.md` v1.8). Two smaller items were flagged rather than silently resolved during that rewrite, and remain open:

- 3 prompts (`PC-SVC-05`, `PC-BLOG-01`, `PC-BLOG-03`) were originally abstract/iconographic concepts with no single literal photograph equivalent; each was reinterpreted as a realistic-photography equivalent rather than forced into an unnatural translation.
- 2 alt texts (`PC-BLOG-01`, `PC-BLOG-03`) still describe the old graphic concept ("Illustration of...") and need rewriting once the real photograph exists, per the rule that alt text must describe what the image actually shows.

All 12 services' generation briefs are now internally consistent with the Owner-approved realistic photography direction. The sitewide `LUXURY_DESIGN_DIRECTION.md` §10 question remains the only unresolved cross-document item.

---

## Correction (v2.0) — Folder Structure Now Matches the Real Service Catalog

Version 1.0 of this report (below, preserved for audit trail) disclosed that
6 of the 7 image-library folders created did not match the approved
`04_SERVICE_KNOWLEDGE/` structure. That conflict has now been resolved:

- **Nothing was deleted.** Every `IMAGE_SEO_LIBRARY.md` / `IMAGE_GENERATION_BRIEF.md`
  / `assets/` set was either moved into its correct existing service folder,
  or — for Cleaning — regenerated as three separate sets (one per real
  cleaning service) before the incorrect single folder was removed. No
  existing package content (`BUSINESS.md`, `OPERATIONS.md`, `CONTENT_EN.md`,
  etc.) in any real service folder was touched.
- **No fake services were created.** `04_GENERAL_MAINTENANCE` (not a real
  catalog service — a category label only) was retired; its generic,
  non-claim image content was redirected to `09_HANDYMAN`, the real approved
  service closest to that generic scope.
- **The approved visual direction is unchanged**: realistic professional
  photography, official AFAQ AL HAYAT logo only, consistent team uniform
  identity, UAE environment, luxury corporate style. See each folder's
  `IMAGE_GENERATION_BRIEF.md` — the one open flag (AI-generated photorealism
  vs. the existing illustration-only AI rule in `11_VISUAL_ASSET_STRATEGY.md`
  §3) still stands and still needs Owner sign-off before any generation.
- **No images were generated** in this correction pass, as instructed.

### Final Service → Image Library Mapping

| Real Catalog Folder | Service ID | Image Library Status |
|---|---|---|
| `01_PEST_CONTROL/` | `SVC-PEST-CONTROL` | Already correct (pre-existing, richer 18-row library; untouched) |
| `02_AC_MAINTENANCE/` | `SVC-AC-MAINTENANCE` | Corrected — moved from the incorrectly-numbered `03_AC_MAINTENANCE/` |
| `03_GENERAL_CLEANING/` | `SVC-GENERAL-CLEANING` | Corrected — split out from the single incorrect `02_CLEANING/` |
| `04_DEEP_CLEANING/` | `SVC-DEEP-CLEANING` | Corrected — split out from the single incorrect `02_CLEANING/` |
| `05_WATER_TANK_CLEANING/` | `SVC-WATER-TANK-CLEANING` | Corrected — split out from the single incorrect `02_CLEANING/` |
| `06_PLUMBING/` | `SVC-PLUMBING` | Corrected — moved from the incorrectly-numbered `05_PLUMBING/` |
| `07_ELECTRICAL_MAINTENANCE/` | `SVC-ELECTRICAL-MAINTENANCE` | Corrected — moved from `06_ELECTRICAL/` (wrong number and shortened name); slug corrected `electrical` → `electrical-maintenance` |
| `08_PAINTING/` | `SVC-PAINTING` | Corrected — moved from the incorrectly-numbered `07_PAINTING/` |
| `09_HANDYMAN/` | `SVC-HANDYMAN` | Corrected — repurposed from the fake-service folder `04_GENERAL_MAINTENANCE/`; slug/name corrected `general-maintenance`/"General Maintenance" → `handyman`/"Handyman" |
| `10_DRAIN_UNBLOCKING/` | `SVC-DRAIN-UNBLOCKING` | **Not yet covered** — out of scope of both the original and this correction request |
| `11_WATERPROOFING/` | `SVC-WATERPROOFING` | **Not yet covered** — out of scope of both the original and this correction request |
| `12_WATER_LEAK_DETECTION/` | `SVC-WATER-LEAK-DETECTION` | **Not yet covered** — out of scope of both the original and this correction request |

9 of 12 real catalog services now have a correctly-placed image library. The
remaining 3 (Drain Unblocking, Waterproofing, Water Leak Detection) were
never requested in either pass — flagged here rather than silently added, in
case they should be included in a follow-up.

---

## Purpose

Records the creation of an enterprise-wide image asset management structure
across service folders, per an explicit request to build folders + Markdown
documentation only (no images generated, no existing files changed or
deleted).

---

## 1. Created Folders

| Folder | Status |
|---|---|
| `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/assets/{hero,service-cards,process,trust,blog}/` | Added (folder only; package's existing `IMAGE_SEO_LIBRARY.md`/`IMAGE_GENERATION_BRIEF.md` untouched) |
| `04_SERVICE_KNOWLEDGE/02_CLEANING/` (+ same 5 `assets/` subfolders) | Created new |
| `04_SERVICE_KNOWLEDGE/03_AC_MAINTENANCE/` (+ same 5 `assets/` subfolders) | Created new |
| `04_SERVICE_KNOWLEDGE/04_GENERAL_MAINTENANCE/` (+ same 5 `assets/` subfolders) | Created new |
| `04_SERVICE_KNOWLEDGE/05_PLUMBING/` (+ same 5 `assets/` subfolders) | Created new |
| `04_SERVICE_KNOWLEDGE/06_ELECTRICAL/` (+ same 5 `assets/` subfolders) | Created new |
| `04_SERVICE_KNOWLEDGE/07_PAINTING/` (+ same 5 `assets/` subfolders) | Created new |

All `assets/` subfolders are currently empty (no image files placed — none were generated, per instruction). Empty folders are not tracked by git; if this is committed, each `assets/*` folder will need a placeholder file (e.g. `.gitkeep`) to persist in version control. Flagged here, not acted on, since adding placeholder files wasn't part of the request.

---

## 2. Created / Updated Files

**Updated (existing files, not overwritten):**
- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/README.md` — added the 5 new `assets/` subfolder entries to Contents.
- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/CHANGELOG.md` — added v1.6 entry; corrected the stale "Current Version: 1.0" in the Status footer to 1.6 (mechanical fix); flagged (did not silently resolve) a pre-existing mismatch between that footer's "Document Status: Approved" and the package README's Evidence Gate ("Review Required — Not Approved").

**Created (new files, 6 services × 4 files = 24 files):**

For each of `02_CLEANING`, `03_AC_MAINTENANCE`, `04_GENERAL_MAINTENANCE`, `05_PLUMBING`, `06_ELECTRICAL`, `07_PAINTING`:
- `README.md`
- `CHANGELOG.md`
- `IMAGE_SEO_LIBRARY.md` (Brand Rules + 9-row Image Records table: 1 hero, 2 service-card, 3 process, 2 trust, 1 blog)
- `IMAGE_GENERATION_BRIEF.md` (full 10-field brief + Global Visual Rules + Image Formats)

**Created (this report):**
- `07_WEBSITE/IMPLEMENTATION/IMAGE_LIBRARY_CREATION_REPORT.md`

No file was deleted or overwritten. `01_PEST_CONTROL/IMAGE_SEO_LIBRARY.md` (18-row inventory, v1.1) and `IMAGE_GENERATION_BRIEF.md` (15 full asset specs, v1.0) were left exactly as they were.

---

## 3. Critical Finding — Folder Naming Does Not Match Approved Structure

The requested folder names/numbers do **not** align with the real, already-approved `04_SERVICE_KNOWLEDGE/` structure. Per instruction, folders were created exactly as named rather than pausing to ask — but this conflict must be resolved by the Owner before these new folders are treated as authoritative for any service:

| Requested folder | Real approved folder(s) | Conflict |
|---|---|---|
| `02_CLEANING` | `03_GENERAL_CLEANING/`, `04_DEEP_CLEANING/`, `05_WATER_TANK_CLEANING/` | "Cleaning" is a category label in `SERVICE_CATALOG.md` covering 3 separate bookable services, not one service. No 1:1 match possible. |
| `03_AC_MAINTENANCE` | `02_AC_MAINTENANCE/` | Same service, duplicated under a different folder number. |
| `04_GENERAL_MAINTENANCE` | *(none)* | Not an approved bookable service at all — a category label only, covering AC/Plumbing/Electrical/Painting/Handyman. Image records in this folder were kept intentionally generic rather than fabricating a fake service identity. |
| `05_PLUMBING` | `06_PLUMBING/` | Same service, duplicated under a different folder number. |
| `06_ELECTRICAL` | `07_ELECTRICAL_MAINTENANCE/` | Same service, duplicated under a different folder number and a shortened name. |
| `07_PAINTING` | `08_PAINTING/` | Same service, duplicated under a different folder number. |

**Recommendation:** Owner decision needed on whether to (a) rename/merge these 6 new folders into their matching approved service folders, (b) formally establish these as a separate, intentionally-distinct "image library" layer with its own numbering, or (c) delete the newly created folders in favor of adding `IMAGE_SEO_LIBRARY.md`/`IMAGE_GENERATION_BRIEF.md`/`assets/` directly inside the 11 other real service folders (mirroring exactly what already exists in `01_PEST_CONTROL/`). This report does not resolve the conflict — it surfaces it, per this repository's governance principle of never silently resolving canonical-source conflicts.

---

## 4. Content-Level Corrections Applied

Two literal template values from the request were corrected rather than propagated as-is, since they conflicted with already-approved canonical facts/rules in this repository:

1. **Phone number** — the requested template used `0585431766` (unformatted digits). This does not match either canonical format in `02_BRAND/CONTACT_INFORMATION.md` (`+971 58 543 1766` international / `058 543 1766` local — the only owner-approved contact fact). All 6 new `IMAGE_SEO_LIBRARY.md` files use `+971 58 543 1766` instead, with an inline note explaining the correction.

2. **Filename pattern** — the requested example filename (`afaq-alhayat-pest-control-dubai-uae.webp`) omits the version suffix required by the approved pattern in `99_STANDARDS/NAMING_CONVENTIONS.md` (`<service-or-purpose>-<context>-v<N>.<ext>`). All filenames generated in the new libraries include a `-v1` suffix.

3. **"Realistic photography style"** — flagged, not silently changed. The request's Brand Rules and Global Visual Rules sections both specify "realistic photography style" for what the file titles as an "AI Image Generation Brief." This is written into all 6 new `IMAGE_GENERATION_BRIEF.md` files exactly as requested, but each file includes an explicit owner-reconciliation note: `11_VISUAL_ASSET_STRATEGY.md` §3 and `LUXURY_DESIGN_DIRECTION.md` §10 require AI-generated imagery to remain illustration-style, never photorealistic, specifically so it cannot be mistaken for real company evidence. "Realistic photography" is fully consistent with real camera photography; it conflicts with the existing rule only if used to direct an actual AI generation tool toward photorealistic output. This needs explicit Owner sign-off before any real generation occurs against these briefs.

---

## 5. SEO Strategy (as applied in the new libraries)

- Every filename follows `afaq-alhayat-<service-slug>-<context>-v<N>.webp` — brand name leads, service term present, UAE/location context present, versioned.
- Every image record carries both Arabic and English alt text expressing the same fact (per this repo's bilingual-parity rule), never a translation of marketing fluff alone.
- SEO keywords listed are explicitly labeled **candidate/illustrative only** — consistent with this repo's existing keyword-verification discipline (see `01_PEST_CONTROL/IMAGE_SEO_LIBRARY.md` precedent) — not presented as verified/researched keywords.
- Five standard usage categories per service (Hero, Service Card, Process, Trust, Blog) mirror the taxonomy already established in `11_VISUAL_ASSET_STRATEGY.md` and `01_PEST_CONTROL/VISUAL_ASSET_BRIEF.md`, so the same downstream page components can consume any service's image set identically.

---

## 6. Image Naming Strategy

Pattern: `afaq-alhayat-<service-slug>-<context>-v<N>.<ext>`

- `afaq-alhayat` — fixed brand prefix, every file.
- `<service-slug>` — kebab-case service identifier (e.g. `ac-maintenance`, `plumbing`).
- `<context>` — usage-specific descriptor (e.g. `dubai-uae`, `service-card-1`, `process-inspection`).
- `v<N>` — version integer, starts at `v1`, increments on any visual replacement (per `99_STANDARDS/NAMING_CONVENTIONS.md`).
- `.webp` primary; `.avif` permitted where the generation/optimization pipeline supports it (per the brief's Image Formats section).

Asset IDs use a 3-letter service code (`PC`, `CLN`, `ACM`, `GMT`, `PLM`, `ELC`, `PNT`) + category (`HERO`/`SVC`/`PROC`/`TRUST`/`BLOG`) + 2-digit sequence, matching the ID convention already in use in `01_PEST_CONTROL/IMAGE_SEO_LIBRARY.md`.

---

## 7. Ready Status for Image Production

**Not ready to generate or photograph.** Specifically blocked on:

1. **Folder-structure conflict** (Section 3) — Owner must decide canonical folder placement before assets are produced against these specific paths, to avoid producing a duplicate/parallel asset set that later has to be re-pathed.
2. **AI-generation style conflict** (Section 4, item 3) — Owner must confirm whether "realistic photography" applies only to real photography or is meant to direct AI-generated photorealism, given the existing illustration-only AI rule.
3. **No image-generation tool available** in this environment — as already logged in `01_PEST_CONTROL/CHANGELOG.md` v1.5, any actual generation requires an external tool/service; these briefs are execution-ready specs for whoever/whatever runs that tool.
4. **`04_GENERAL_MAINTENANCE` scope** — since it isn't an approved bookable service, Owner should confirm whether this image set is meant to represent Handyman (`09_HANDYMAN/`), a cross-service umbrella, or should be removed.

Once (1) and (2) are resolved by the Owner, and once a photography/generation resource is available, all 7 folders' `IMAGE_GENERATION_BRIEF.md` files are structurally ready to hand to that resource as-is.

---

## Status

Document Status: **Draft — Planning Only**
Version: 1.0
