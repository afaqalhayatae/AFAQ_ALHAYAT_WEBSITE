# Changelog

## Purpose

This document records all changes made to the Pest Control Knowledge Package.

---

| Version | Date | Author | Description |
|---------|------|--------|-------------|
| 1.0 | Initial Release | Project Team | Initial Enterprise Knowledge Package created. |
| 1.1 | 2026-07-28 | AI Agent (planning) | Added `WEB_CONTENT_PRODUCTION_PLAN.md` — organizes existing package knowledge into a web-content shape (outlines, SEO title/meta, FAQ readiness map, internal linking, visual plan, location mapping). Planning only; does not change this package's Evidence Gate or Review-Required status. |
| 1.2 | 2026-07-28 | AI Agent (content fix) | Applied 4 content-readiness fixes: removed the non-existent "Disinfection" internal-link reference in `SEO_AI.md`; rewrote "Why Choose Us" in `CONTENT_EN.md`/`CONTENT_AR.md` as real customer-facing copy with no unsupported certification/guarantee/response-time claim; reworded the warranty FAQ answer to remove internal-note phrasing; added `FAQ_AR.md` (full Arabic FAQ). Evidence Gate, keyword framework, and SEO structure unchanged. |
| 1.3 | 2026-07-28 | AI Agent (planning) | Added `VISUAL_ASSET_BRIEF.md` — hero/service/process/trust/blog image concepts, illustrative-only AI prompt text, style rules, file naming, and alt text requirements for Pest Control. Planning only; no image generated; flags a missing pest-type icon set as a separate future task. |
| 1.4 | 2026-07-28 | AI Agent (planning) | Added `IMAGE_SEO_LIBRARY.md` — granular 16-row image asset inventory (IDs, filenames, AR/EN alt text, keyword candidates, status) operationalizing `VISUAL_ASSET_BRIEF.md`, plus filename/alt-text/AI-generation/performance rules and the image approval workflow. Planning only; no image generated; `PC-PROC-03` remains blocked pending `OPERATIONS.md` approval. |
| 1.5 | 2026-07-28 | AI Agent (planning) | Added `IMAGE_GENERATION_BRIEF.md` and extended `IMAGE_SEO_LIBRARY.md` to 18 rows (`PC-SVC-05`, `PC-PROC-05`). No image-generation tool is available in this environment, so the brief provides a complete, execution-ready spec (filenames, AR/EN alt text, prompts) per requested asset instead of generated files — explicitly labeled as not-yet-generated. |
| 1.6 | 2026-07-28 | AI Agent (planning) | Added `assets/{hero,service-cards,process,trust,blog}/` subfolders as part of an enterprise-wide image asset management structure created across all `04_SERVICE_KNOWLEDGE/` service folders. Folders only — no files added inside them, no images generated. `IMAGE_SEO_LIBRARY.md` and `IMAGE_GENERATION_BRIEF.md` in this package were not modified or overwritten. |
| 1.7 | 2026-07-28 | AI Agent (correction) | Confirmed during the folder-naming correction pass (see `07_WEBSITE/IMPLEMENTATION/IMAGE_LIBRARY_CREATION_REPORT.md`) that this package's folder number/name already matched the approved catalog — no move was needed here. Six sibling folders created in the same original pass were incorrectly numbered/named and have been moved/split/renamed into their correct catalog folders. |
| 1.8 | 2026-07-28 | AI Agent (rewrite) | Rewrote all 15 `IMAGE_GENERATION_BRIEF.md` generation prompts from illustration style to Owner-approved realistic professional photography (decision 36, `11_VISUAL_ASSET_STRATEGY.md` v2.0). Asset IDs, SEO filenames, image purposes/usage, keyword targets, and document structure unchanged. Flagged (not silently changed): 3 prompts (`PC-SVC-05`, `PC-BLOG-01`, `PC-BLOG-03`) were originally abstract/iconographic concepts, reinterpreted as realistic-photography equivalents; 2 alt texts still describe the old graphic concept and need revision once a real photograph exists. No image generated. |
| 1.9 | 2026-07-28 | AI Agent (asset intake) | Saved a delivered image file, `assets/hero/pest-control-hero-v1.png`, at the Owner's explicit request (filename kept exactly, no other structure changed). Logged as a new "Delivered Assets" entry in `IMAGE_SEO_LIBRARY.md` §6a rather than mapped onto `PC-HERO-01`/`PC-HERO-02`, because the filename/format don't match either row (`.png` vs. required `.webp`) and the image itself has embedded Arabic text, trust-badge icons, and a phone number baked in — the hero spec calls for a clean photograph with negative space for text overlay, not a finished composite. No row's Status changed; the file has not gone through Quality Review or Website Integration and is not wired into any page. |
| 1.10 | 2026-07-28 | AI Agent (asset intake) | Saved a second delivered image file, `assets/hero/pest-control-homepage-hero-v1.webp`, at the Owner's explicit request (filename kept exactly, no other structure changed). Filename and format match `PC-HERO-01` exactly and the style (realistic photo of technician/branded van against the Dubai skyline) fits the generation brief, but `IMAGE_SEO_LIBRARY.md` §6a flags an AI text-fidelity artifact (the van's tagline renders as "CLEANLIIESS") that needs a Quality Review pass before the Owner can consider approval — `PC-HERO-01`'s Status remains **Planned — not approved**; the file is not wired into any page. |
| 1.11 | 2026-07-28 | AI Agent (asset intake) | Saved a third delivered image file, `assets/service-cards/cockroach-control-service-card-v1.webp`, at the Owner's explicit request (filename/format kept exactly, no other structure changed). This asset doesn't map to any planned Image ID — no pest-type-specific service card exists in this library's 18-row inventory. More significantly, flagged in `IMAGE_SEO_LIBRARY.md` §6a as a content-accuracy issue, not just a style one: the image bakes in a "CERTIFIED SOLUTIONS" badge and a "24/7 SUPPORT" badge as settled visual claims, while `CONTENT_EN.html`'s own draft still lists competency evidence, product approvals, and response commitment as unconfirmed — per `CLAUDE.md`, certifications and response-time commitments must never be fabricated. The AR/EN support-hours badges also disagree with each other ("24/4" vs "24/7"). Recommend this asset stay unapproved until the claims are either evidenced or the image is regenerated without them. Not wired into any page; no Image ID Status changed. |
| 1.12 | 2026-07-28 | AI Agent (asset intake) | Saved `assets/service-cards/cockroach-control-service-card-v2.webp`, delivered by the Owner as an "approved" revision of v1.11's asset, with Owner-supplied Asset ID `PC-SVC-COCKROACH-01`, Purpose, SEO title, and Arabic alt text. Added `PC-SVC-COCKROACH-01` as a new row (19th) in `IMAGE_SEO_LIBRARY.md`'s main inventory table and a matching delivery record in §6a. v2 fixes v1's two worst problems — the explicit "CERTIFIED SOLUTIONS" badge and the mismatched-language "24/7 SUPPORT" badge are both gone, replaced with softer, Arabic-only wording. However, §6a still flags: a "safe for family/children/pets" badge that sits in tension with `SAFETY.md`'s Draft status and its "keep children and pets away" instruction; an "eco-friendly pesticides" claim with no approved-product-list source; and small text on the second badge that reads as "guaranteed results" (worth the Owner re-checking directly) — if accurate, a warranty-type claim outside this package's authority (`06_CUSTOMER_AND_SALES` owns warranty language, always `A4`-gated). Treating "approved" as Owner sign-off on creative direction/selection, not as the §7 Final Approval gate for those specific claims. Not wired into any page; no Image ID Status advanced to Final Approval. |
| 1.13 | 2026-07-28 | AI Agent (correction pass) | Ran a controlled correction pass on `pest-control-homepage-hero-v1.webp` and `cockroach-control-service-card-v2.webp` per Owner request; documented in full in `IMAGE_SEO_LIBRARY.md` §6b. **Format (A):** both files re-encoded in place, filenames unchanged, as true lossless WebP — verified via binary signature (`RIFF...WEBPVP8L`) and a pixel-for-pixel identity check against the pre-conversion file, so no content, branding, layout, or color could have changed in this step. **Content (B/C):** the requested text corrections (hero tagline typo, service-card claim removal, Arabic spelling fixes) were **not implemented** — flagged as a genuine capability gap rather than attempted and mis-reported. The hero typo sits on a perspective-skewed photographic surface with no inpainting tool available and image generation explicitly disallowed by the task; a programmatic patch would look visibly pasted-on. The service-card fixes are Arabic-text edits, and this environment's available text-rendering library lacks `libraqm` (confirmed via `PIL.features.check('raqm')` → `False`), so any programmatic Arabic redraw would risk producing new disconnected/malformed glyphs — an unacceptable risk on a document meant to catch exactly that error class. Independently (without touching the image), linguistically verified that "العائلة" is the correct spelling of "family" and "أم القيوين" is the canonical spelling per `03_MARKET/SERVICE_AREAS.md` — both confirm, not resolve, the prior QA flags. No Image ID Status changed; nothing wired into any page. |
| 1.14 | 2026-07-28 | AI Agent (pixel edit) | Performed an actual in-place pixel edit on `pest-control-homepage-hero-v1.webp` (hero only — the service card was out of scope for this request and is unchanged), documented in `IMAGE_SEO_LIBRARY.md` §6c. Fixed the van-door tagline typo ("CLEANLIIESS" → "CLEANLINESS") by rebuilding the local background and redrawing the line in a matched font/color at pixel region `x:508–845, y:605–637`; verified via an exact pixel diff that nothing outside that rectangle changed (logo, van, uniform, colors, phone number, composition all untouched), and re-saved as true lossless WebP (signature-verified). This took three attempts — the first two (a tiled-texture background and a non-uniform-squished font) produced visibly bad results and were discarded rather than shipped; the third (smooth gradient background + uniform-scaled condensed font) was the one applied. Three further instances of the same class of defect were newly found and catalogued but **not fixed**: curved gibberish "echo" text overlapping the wave graphic on the van door, an equivalent illegible line on the jacket back, and a curved-plus-straight pair on the spray tank (the straight one has its own apparent typo). All three were judged higher-risk than the one that was fixed and left disclosed rather than attempted. Also retracted a prior misread: the van door's Arabic line was re-checked at high zoom and is correct — no embedded Latin artifact exists there. `PC-HERO-01` Status unchanged (still Planned — not approved); nothing wired into any page. |
| 1.15 | 2026-07-28 | AI Agent (pixel edit) | Performed a targeted pixel edit on `cockroach-control-service-card-v2.webp` per Owner request, documented in `IMAGE_SEO_LIBRARY.md` §6d. **Claims removed (done, verified):** blanked Badge 1's absolute family/child/pet safety caption (both lines), Badge 2's guaranteed-results second line only (kept the neutral "long-lasting effectiveness" first line), and Badge 4's eco-friendly-pesticide caption (both lines) — all three by filling with the card's own sampled flat background color, since this is a flat graphic asset, not a photo. Icons kept in all three badges. Verified via exact pixel diff that only `x:65–1028, y:862–932` changed — photo, logo, headline, body copy, badges 3 and 5, footer, and phone number are all pixel-identical to before. Re-saved as true lossless WebP in place, filename unchanged, signature verified. **Arabic spelling fixes:** the "العائلة" correction is moot — its whole badge was removed above. The "أم الفيوين" → "أم القيوين" footer fix (this word is kept, since coverage text isn't a claim) was investigated via a glyph-splice from a real ق elsewhere in the same image (avoiding the `libraqm` problem from the prior pass by not synthesizing new Arabic) but **not applied** — the only available donor ق is shaped to join different neighboring letters than the target position needs, and splicing across that mismatch risked a worse-looking break in the word at this very small text size. "أم الفيوين" remains misspelled in the current file — the one open item from the original QA findings still unresolved. `PC-SVC-COCKROACH-01` Status unchanged (Planned — not approved); nothing wired into any page. |
| 1.16 | 2026-07-28 | AI Agent (pixel edit) | Resolved the "أم الفيوين" → "أم القيوين" footer fix left open in v1.15, documented in `IMAGE_SEO_LIBRARY.md` §6e. Installed `arabic-reshaper` + `python-bidi` to pre-shape the correct word into properly-joined presentation-form glyphs before rendering — this sidesteps the missing-`libraqm` limitation that blocked freehand Arabic rendering in earlier passes, since shaping now happens before Pillow draws the text rather than during it. Rendered in SF Arabic Bold, matched to the surrounding footer text's size/color, composited into `x:1263–1352, y:1068–1094` only (verified via exact pixel diff — nothing else in the file changed). Re-saved as true lossless WebP, filename unchanged, signature verified. Visually confirmed correct letter joining and consistent alignment with the row's other emirate names. **No known open text-accuracy issues remain on this asset** — both Arabic spelling errors and all three unsupported claims originally flagged are now resolved. `PC-SVC-COCKROACH-01` Status unchanged (Planned — not approved); nothing wired into any page. |
| 1.17 | 2026-07-28 | AI Agent (specification only — no image generated) | Owner requested a production batch of 6 new pest-type service cards (ant, bed bug, mosquito, fly, rodent, termite control), each with a specified filename under `assets/service-cards/`. **No image-generation tool is available in this environment** (confirmed via a fresh tool search before responding) — no file was created, copied, or renamed to stand in for any of the 6 requested filenames; none of them exist on disk. Rather than claim completion or fabricate placeholder assets, prepared a complete execution-ready specification instead, consistent with how this exact gap was already handled for the original 18-asset batch: added `IMAGE_GENERATION_BRIEF.md` §6 (6 filenames, bilingual alt text, generation prompts built on the two already-approved reference assets' identity, plus a batch-specific prompt suffix encoding every constraint from the request — no certifications, no guarantees, no "100%," no invented badges, no AI-fabricated text in either language) and extended `IMAGE_SEO_LIBRARY.md` with 6 matching rows (19 → 25), each explicitly marked "Planned — not approved, no image generated." No Image ID reached even the Generation stage of the §7 approval workflow; nothing wired into any page. |
| 1.18 | 2026-07-29 | AI Agent (data system build) | Added 6 new files (`01_SERVICE_PROFILE.md` through `06_PAGE_CONTENT.md`) as part of an enterprise-wide "service data system" request covering all 12 catalog services (this package was built first, as the template — see `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md` for the other 11's status). Every fact in all 6 files is sourced from this package's own existing documents (`BUSINESS.md`, `OPERATIONS.md`, `CUSTOMER_GUIDE.md`, `CONTENT_EN.md`/`CONTENT_AR.md`, `FAQ.md`/`FAQ_AR.md`, `SEO_AI.md`, `IMAGE_SEO_LIBRARY.md`) plus the three canonical cross-service registries (`SERVICE_CATALOG.md`, `SERVICE_MATRIX.md`, `03_MARKET/SERVICE_AREAS.md`) — no price, certification, warranty, or response-time claim was introduced, consistent with this package's Evidence Gate. `04_FAQ.md` extends the existing 8-question `FAQ.md`/`FAQ_AR.md` to 10 by adding 2 new questions (coverage, pre-visit preparation), each sourced from an existing document rather than invented. Same Evidence Gate as the rest of the package — none of this is Approved for Publication. |
| 1.19 | 2026-08-01 | AI Agent (sync execution) | Executed Owner-approved sync (`00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_PLAN.md`, `00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`): updated the Status field in `README.md`, `02_SEO_DATA.md`, `04_FAQ.md`, and `06_PAGE_CONTENT.md` to reflect `DECISION_LOG.md` #37's approval of general operational content. No claim was added, changed, or removed; certification, municipality-compliance, product-approval, safety-assurance, fast-response, and warranty claims remain unapproved. Per Owner instruction, only the three files `DECISION_LOG.md` #37 explicitly names were updated — `01_SERVICE_PROFILE.md`, `03_BOOKING_OPTIONS.md`, `05_IMAGE_METADATA.md`, and the legacy `CONTENT_EN.md`/`CONTENT_AR.md`/`FAQ.md`/`FAQ_AR.md`/`SEO_AI.md` set were not touched; nothing was merged or deleted. |

---

## Version History

### Version 1.6

- Added empty `assets/` subfolder structure (hero, service-cards, process, trust, blog) to match the new cross-service image asset management structure. No other files changed.

### Version 1.5

- Created IMAGE_GENERATION_BRIEF — full generation-ready spec for 15 requested assets; no image actually generated (no tool available). Extended IMAGE_SEO_LIBRARY with 2 new rows for concepts introduced by this request.

### Version 1.4

- Created IMAGE_SEO_LIBRARY — concrete per-image inventory with IDs, SEO filenames, and bilingual alt text; carries forward the same evidence gate as `VISUAL_ASSET_BRIEF.md`.

### Version 1.3

- Created VISUAL_ASSET_BRIEF — plans imagery gated the same way as written content (no specific treatment method depicted until `OPERATIONS.md` clears); flags missing pest-type icons as a future task.

### Version 1.2

- Fixed `SEO_AI.md` internal links (removed "Disinfection").
- Rewrote `CONTENT_EN.md`/`CONTENT_AR.md` "Why Choose Us" sections.
- Reworded `FAQ.md` warranty answer.
- Added `FAQ_AR.md`.

### Version 1.1

- Created WEB_CONTENT_PRODUCTION_PLAN — flags the "Why Choose Us" sections and one FAQ answer as not publish-ready as drafted, identifies a missing Arabic FAQ, and flags a stale "Disinfection" internal-link reference in SEO_AI.md.

### Version 1.0

- Created README
- Created BUSINESS
- Created OPERATIONS
- Created SAFETY
- Created CUSTOMER_GUIDE
- Created FAQ
- Created SEO_AI
- Created CONTENT_AR
- Created CONTENT_EN
- Created TRAINING
- Created MEDIA
- Created CHANGELOG

---

## Next Planned Updates

- Add Pricing Structure
- Add Municipality Compliance
- Add Service Forms
- Add Inspection Templates
- Add Warranty Policy
- Add Risk Assessment Forms
- Add Chemical Catalogue
- Add Photo Library

---

## Status

Current Version: **1.18**

Document Status: **Approved**

> Note: This "Document Status: Approved" refers to the changelog document
> itself, not the underlying service package — `README.md`'s Evidence Gate
> ("Review Required — Not Approved for Publication or Field Execution")
> remains the governing status for the package as a whole. This mismatch
> predates this update and is flagged here rather than silently resolved.