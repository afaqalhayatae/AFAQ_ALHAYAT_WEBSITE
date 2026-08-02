# Design System – Asset Alignment Report

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — review only, no file modified. Contains findings requiring Owner decision.
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Last Updated:** 2026-08-01
- **Package:** `00_GOVERNANCE/`
- **Scope reviewed:** `12_DESIGN_SYSTEM/` against `public/brand/icons/` and `public/brand/images/`. Read-only — no code, design, or file was modified, moved, or renamed.

---

## 1. Icon Usage Review

### 1.1 Is the icon system clear?

**No — two separate icon systems exist, and no document declares how they relate to each other.**

| System | Defined in | Library | Style |
|---|---|---|---|
| UI Icons | `12_DESIGN_SYSTEM/ICONS.md` (v1.0), `02_BRAND/ICONOGRAPHY.md` | **Lucide Icons** (code-based, imported in the application) | Line icons, uniform stroke weight, no extra detail — sizes 16/24/32–48px |
| Brand Icons | `public/brand/icons/` (this repo's asset library) | 172 custom SVG files across `maintenance/`, `cleaning/`, `pest-control/`, `master-library/` | Detailed, multi-color illustrated icons — average file size 205 KB, up to 2.4 MB, viewBox up to 512×512 |

`public/brand/icons/` is not mentioned in either `12_DESIGN_SYSTEM/ICONS.md` or `02_BRAND/ICONOGRAPHY.md` as an approved source. Neither document was updated when this custom library was ingested (Decision Log has no entry for it beyond the Design Freeze).

### 1.2 Difference between Brand Icons and UI Icons

- **UI Icons (Lucide):** interface-chrome icons — navigation, booking, phone, WhatsApp, payment, settings — per `12_DESIGN_SYSTEM/ICONS.md` §"أيقونات الإجراءات." Meant to be simple line icons at small/medium sizes (16–48px), rendered from code, colored from the design-system palette (`#0F4C81`, `#16A34A`, `#6B7280`).
- **Brand Icons (`public/brand/icons/`):** service/marketing icons — one detailed illustration per service (e.g. `icon-pest-cockroach.svg`, `icon-maintenance-plumbing.svg`) and per-location icons (`Dubai.svg`, `Abu Dhabi.svg`, etc. in `master-library/`). These are static image assets, not code-rendered, and visually nothing like the "simple line icon" spec in `12_DESIGN_SYSTEM/ICONS.md`.

These appear to serve genuinely different purposes (interface chrome vs. marketing/service visuals), which is a reasonable two-track design — but this is inferred, not documented anywhere as an intentional decision.

### 1.3 Conflicts found

1. **Style mismatch:** `12_DESIGN_SYSTEM/ICONS.md` mandates simple, uniform-stroke line icons for the platform's icon system. `public/brand/icons/` is a detailed illustration set. If any Brand Icon were ever used as a UI Icon (or vice versa), it would visibly break the stated style rule.
2. **Undocumented library:** `public/brand/icons/` has no owning design-system or brand document declaring it approved, its intended usage (service cards? blog? location pages?), or its relationship to the Lucide-based UI icon system.
3. **Confirmed AI-generation, unaddressed by governance:** every one of the 172 SVG files carries an embedded C2PA content-credentials manifest identifying `softwareAgent: "Canva AI"` and `digitalSourceType: compositeWithTrainedAlgorithmicMedia` (verified by decoding the embedded manifest in all 172 files, not inferred). No brand or design-system document currently states a policy on AI-generated brand icons specifically — this is distinct from, and additional to, the photography-AI question already open in Decision 36 (§3 below).

---

## 2. Image Review

### 2.1 Organization of service images

`public/brand/images/services/` is correctly organized: `maintenance/` (5 files), `cleaning/` (3 files), `pest-control/` (1 file), each file in its correct category folder, no duplicates, no naming conflicts (confirmed by checksum and filename scan in the prior `IMAGE_LIBRARY_REVIEW_REPORT.md`, unchanged since).

### 2.2 Readiness for cards and pages

| Check | Result |
|---|---|
| Format | True WEBP (converted and verified in the prior optimization step) |
| Dimensions | 1254×1254 to 1536×1024 (near-square to slightly landscape) |
| `02_BRAND/BRAND_IMAGES.md` "Minimum Resolution: 1920 × 1080 px" | **Not met by any of the 9 images** — the widest is 1536 px, below the stated 1920 px minimum width. |
| No text/watermark/logo-exaggeration | Confirmed clean in prior review |
| File size | 260–478 KB each — reasonable for web delivery |

The images are technically suitable for **service-card use** (card layouts typically use smaller crops than 1920×1080), but do not meet the brand guideline's stated minimum resolution as written, which more plausibly targets hero/full-bleed placements. This is a literal-compliance gap worth the Owner's attention if these images are ever used in a hero or full-width context.

### 2.3 Missing images

- `service-pest-control.webp` — not produced (no image-generation tool available; spec exists at `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/IMAGE_GENERATION_BRIEF.md` §7).
- `service-cockroach-control.webp` — not produced, same reason.

### 2.4 Confirmed AI-generation — all 9 approved images

Verified by decoding each file's embedded C2PA content-credentials manifest (checked against the pre-conversion backups, since the manifest predates the WEBP re-encoding step): all 9 images — `service-ac-maintenance`, `service-electrical-maintenance`, `service-painting-maintenance`, `service-plumbing-maintenance`, `service-waterproofing`, `service-deep-cleaning`, `service-home-cleaning`, `service-office-cleaning`, `service-termite-control` — carry an identical manifest declaring:

- `softwareAgent`: `gpt-image`, version `2.0`
- `digitalSourceType`: `http://cv.iptc.org/newscodes/digitalsourcetype/trainedAlgorithmicMedia`

This is a **confirmed fact**, not a suspicion — every image currently in the approved service-image library depicting an "AFAQ Al Hayat technician" was generated by an AI image model, not photographed. See §3 below for why this matters.

---

## 3. Identity Review

### 3.1 Colors

Already an open item (Decision 35, `DECISION_LOG.md`, 2026-07-27): `12_DESIGN_SYSTEM/COLORS.md` is the canonical implementation source; `02_BRAND/BRAND_COLORS.md` remains brand/print reference only. Not re-decided here — carried forward as still unreconciled into one document.

### 3.2 Fonts — new conflict found

`02_BRAND/TYPOGRAPHY.md` (brand reference) and `12_DESIGN_SYSTEM/TYPOGRAPHY.md` v2.0 ("Approved Design Standard") **name different Arabic fonts**:

| Document | Arabic font | English font |
|---|---|---|
| `02_BRAND/TYPOGRAPHY.md` | **Cairo** | Inter |
| `12_DESIGN_SYSTEM/TYPOGRAPHY.md` (v2.0, Approved) | **Noto Kufi Arabic** | Inter |

English font matches (Inter, both documents). Arabic font does not. This conflict was not previously logged anywhere in `DECISION_LOG.md` — it is a new finding from this review, parallel in shape to the already-known color-source conflict (Decision 35) but not covered by that decision's scope.

### 3.3 Photography style

`12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §4 requires "Real technicians following approved working and safety procedures" and explicitly lists "Visibly artificial people, tools, uniforms, locations, or results" under Reject. §10 (Prohibited Patterns) separately bans "AI-generated media presented as real company evidence."

Per §2.4 above, the current approved image library is **confirmed 100% AI-generated** (not merely photorealistic-looking — verified via embedded metadata). This is the same conflict Decision 36 flagged as open and unresolved at the time ("does not amend `LUXURY_DESIGN_DIRECTION.md` §10... flags this as an open conflict requiring separate Owner reconciliation"). This report does not resolve it — it upgrades the finding from "suspected/flagged" to "confirmed by direct technical evidence," which the Owner may want to weigh before any further use of these images as customer-facing "real company evidence."

### 3.4 Usage rules

Folder structure, no-duplication, and no-embedded-text/watermark rules from the Design Freeze (`DESIGN_FREEZE_REPORT.md`) are being followed structurally across both libraries. No violation of the *structural* usage rules was found.

---

## 4. Points Requiring Owner Decision Only

1. **AI-generation vs. `LUXURY_DESIGN_DIRECTION.md` §10 — now confirmed, not suspected.** All 172 brand icons (Canva AI) and all 9 approved service images (gpt-image 2.0) are AI-generated per embedded content-credentials metadata. This was already open per Decision 36; this report adds hard confirmation for the Owner to act on.
2. **Icon system duality is undocumented.** Whether `public/brand/icons/` (illustrated) and Lucide Icons (line, UI) are two intentionally separate systems, and if so, where that decision should be recorded.
3. **New font conflict:** `02_BRAND/TYPOGRAPHY.md` (Cairo) vs `12_DESIGN_SYSTEM/TYPOGRAPHY.md` (Noto Kufi Arabic) for the Arabic typeface — not previously logged, needs a decision on which is canonical (mirrors the color-source pattern already resolved by Decision 35).
4. **Image resolution vs. `02_BRAND/BRAND_IMAGES.md`'s stated 1920×1080 minimum** — current approved images (max 1536 px wide) fall short if ever used in hero/full-bleed contexts; likely fine for card use as-is, but not decided here.
5. **Two missing pest-control images** — still open, no image-generation tool available, spec ready and waiting.

---

## Related Documents

- `00_GOVERNANCE/DESIGN_FREEZE_REPORT.md` — asset inventory and freeze baseline.
- `00_GOVERNANCE/IMAGE_LIBRARY_REVIEW_REPORT.md` — prior structural review (duplicates, corruption, extensions).
- `00_GOVERNANCE/DECISION_LOG.md` — Decision 35 (color source), Decision 36 (photography direction, still-open AI conflict).
- `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §4, §10.
- `02_BRAND/ICONOGRAPHY.md`, `02_BRAND/TYPOGRAPHY.md`, `02_BRAND/BRAND_IMAGES.md`.

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-08-01 | Initial alignment review of `12_DESIGN_SYSTEM/` against `public/brand/icons/` and `public/brand/images/`, per Owner instruction. Confirmed via embedded file metadata that all 172 brand icons and all 9 approved service images are AI-generated (previously only suspected/flagged in Decision 36). Identified a new, previously unlogged Arabic-font conflict between `02_BRAND/TYPOGRAPHY.md` and `12_DESIGN_SYSTEM/TYPOGRAPHY.md`. No file modified. |
