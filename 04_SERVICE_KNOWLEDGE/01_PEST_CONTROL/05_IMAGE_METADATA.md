# Image Metadata — Pest Control

## Document Information

- **Service ID:** `SVC-PEST-CONTROL`
- **Status:** Draft — records the actual state of the two real image files that exist for this service as of 2026-07-29. Does not duplicate `IMAGE_SEO_LIBRARY.md`, which remains the authoritative per-image tracking document (§6a–§6e for full delivery/correction history) — this file is a structured-data view of the same two assets for booking/SEO/schema consumers.
- **Prepared:** 2026-07-29

---

## Image 1 — Homepage Hero

- **File Name:** `pest-control-homepage-hero-v1.webp`
- **Current Location:** `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/assets/hero/pest-control-homepage-hero-v1.webp`
- **Service Name:** Pest Control (`SVC-PEST-CONTROL`)
- **Category:** Cleaning & Pest Control
- **Recommended Website Section:** Homepage — Hero
- **Recommended Page:** `/` (homepage)
- **SEO Alt Text (EN):** Technician inspecting a UAE home for pest activity
- **SEO Alt Text (AR):** فني يفحص منزلاً في الإمارات بحثًا عن الآفات
- **SEO Caption:** AFAQ AL HAYAT pest control technician and branded service van, Dubai
- **Recommended Schema Type:** `Service` (as the primary `image` property of the Pest Control `Service` entity) — see `12_WATER_LEAK_DETECTION`-style pattern is not applicable; use `LocalBusiness.image` only if this same asset is reused as the organization's general representative photo.
- **Format:** True WebP, verified (`RIFF....WEBPVP8L`)
- **Current known issues (per `IMAGE_SEO_LIBRARY.md` §6c):** van-door tagline typo fixed; three smaller garbled-text instances (van wave overlay, jacket back, spray tank) remain unfixed. Not yet through Quality Review or Final Approval.

## Image 2 — Cockroach Control Service Card

- **File Name:** `cockroach-control-service-card-v2.webp`
- **Current Location:** `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/assets/service-cards/cockroach-control-service-card-v2.webp`
- **Service Name:** Pest Control — Cockroach Control (`PC-SVC-COCKROACH-01`)
- **Category:** Cleaning & Pest Control
- **Recommended Website Section:** Services overview — pest-type card grid
- **Recommended Page:** `/services/pest-control`
- **SEO Alt Text (AR):** فني مكافحة حشرات من آفاق الحياة يستخدم معدات احترافية لمكافحة الصراصير داخل منزل حديث في الإمارات مع هوية الشركة الرسمية
- **SEO Alt Text (EN):** *Not yet supplied* — flagged as an open gap in `IMAGE_SEO_LIBRARY.md`; do not invent one here without Owner sign-off, since the Arabic version was Owner-supplied specifically and an English version wasn't.
- **SEO Caption:** Cockroach control service — AFAQ AL HAYAT, all 7 UAE emirates
- **Recommended Schema Type:** `Service` (as an `image` on a Cockroach Control sub-service entity, if one is modeled separately from the general Pest Control `Service`)
- **Format:** True WebP, verified (`RIFF....WEBPVP8L`)
- **Current known issues:** none open as of the last correction pass (`IMAGE_SEO_LIBRARY.md` §6e) — both Arabic spelling errors and all three unsupported claims originally found have been resolved. Still not through Quality Review or Final Approval per the §7 workflow.

---

## Planned but not yet produced (no file exists)

Six additional pest-type service cards were specified (filenames, alt text, generation prompts) but **not generated** — no image-generation tool is available in this environment. See `IMAGE_GENERATION_BRIEF.md` §6 for the full spec and `IMAGE_SEO_LIBRARY.md`'s 25-row inventory (`PC-SVC-ANT-01` through `PC-SVC-TERMITE-01`). None of these six should appear in any "existing images" report until they actually exist on disk.

---

## Related Documents

- `01_PEST_CONTROL/IMAGE_SEO_LIBRARY.md` (authoritative per-image tracking and approval workflow)
- `01_PEST_CONTROL/IMAGE_GENERATION_BRIEF.md` (specs for not-yet-produced assets)
- `01_PEST_CONTROL/VISUAL_ASSET_BRIEF.md`
