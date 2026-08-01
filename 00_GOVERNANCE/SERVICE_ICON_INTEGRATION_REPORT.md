# Service Brand Icons Integration Report

**Date:** 2026-08-01
**Scope:** The 3 homepage service-category card badges (Maintenance, Cleaning, Pest Control) in `src/app/[locale]/page.tsx`, `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app`.
**Pre-implementation notice:** Written before any code change.

---

## 1. Current Icon Source

All 3 category badges currently render a hand-drawn inline SVG component from `src/components/icons.tsx`: `WrenchIcon` (Maintenance), `CleaningIcon` (Cleaning), `PestIcon` (Pest Control). Cleaning already has a real approved-asset badge from the prior Brand Icon Integration ticket (`public/brand/icons/cleaning/icon-cleaning-general.svg`) — Maintenance and Pest Control still use the temporary hand-drawn icons.

## 2. Selected Replacement Assets

Searched `AFAQ_ALHAYAT_ENTERPRISE_KNOWLEDGE/public/brand/icons/` (the same approved library used for the emirate/cleaning integration). **Owner clarification received mid-task: a specific sub-service icon must never stand in for a category icon** (e.g. no AC-repair icon for "Maintenance," no termite/cockroach icon for "Pest Control") — only a genuine general-category icon qualifies; otherwise report it missing. Two earlier candidates were rejected under this rule after review:

| Category | Selected file | Why |
|---|---|---|
| **Cleaning** | `cleaning/icon-cleaning-general.svg` (already integrated) | Exact, unambiguous "general" match — no change needed. |
| **Pest Control** | `pest-control/icon-pest-target-crosshair.svg` | Of the 21 pest-control files, this is the **only** one that doesn't depict a specific pest — a generic targeting/scope graphic, applicable to the category as a whole. (Rejected: `icon-pest-protection-shield.svg`, initially selected, was found on closer visual review to depict a specific bug silhouette inside the shield — exactly the kind of "specific pest as category icon" the Owner ruled out.) |
| **Maintenance** | **None — reported as missing.** | All 58 maintenance files are trade-specific (AC repair, plumbing, electrical, carpentry, etc.); none represent the category generally. An earlier pick (`icon-maintenance-ac-repair.svg`, chosen to match the card's existing AC-maintenance photo) was reverted per the Owner's clarification that a specific sub-service icon must not substitute for a category icon, full stop, regardless of any existing photo precedent. The Maintenance card keeps its current `icons.tsx` `WrenchIcon` unchanged. |

Two other pest-control candidates (`icon-pest-spray-bottle.svg`, `icon-pest-insecticide-can.svg`) were also considered and rejected for an unrelated reason: both carry AI-hallucinated, nonsensical product-label text baked into the artwork (e.g. "PETCAL PECIVE," "Spetual Brogehtr") — not real products, not usable regardless of the specificity question.

All candidates were visually verified (rendered via `sharp`, not just opened as text) before selection or rejection.

## 3. Missing Assets

**Maintenance has no approved general-category icon.** All 58 available files are named for one specific trade; there is no "general maintenance," "tools," or "handyman" file the way Cleaning has `icon-cleaning-general.svg`. The Maintenance card keeps its existing `icons.tsx` `WrenchIcon` badge. Recommend either supplying a dedicated general-maintenance icon (e.g. a tools/wrench badge matching the style of the Pest Control crosshair or Cleaning general icon) or confirming the current hand-drawn `WrenchIcon` is acceptable long-term for this category.

## 4. Files to Modify

| File | Change |
|---|---|
| `src/app/[locale]/page.tsx` | Add `brandIconSrc` for the `pest-control` card entry only (mirroring how `cleaning` already works); `maintenance` keeps `brandIconSrc: undefined` and its existing `WrenchIcon`. |
| `public/brand/icons/pest-control/icon-pest-target-crosshair.svg` (new) | Copied from the knowledge-base repo, C2PA metadata stripped (same lossless cleanup as the emirate/cleaning icons — artwork pixels untouched). |

`icons.tsx`'s `WrenchIcon` stays in active use on the Maintenance card (no approved replacement exists). `PestIcon` becomes unused on the homepage specifically now that Pest Control has a real icon, but the component itself stays in `icons.tsx` since other pages (service detail pages, `service-visuals.tsx`) still reference it.

---

*End of report. No code changed in producing this document.*
