# Homepage Visual Fix Plan

**Date:** 2026-08-01
**Based on:** `00_GOVERNANCE/HOMEPAGE_VISUAL_IMPLEMENTATION_AUDIT.md`
**Scope:** Implementation plan for the findings in the audit above, covering `src/app/[locale]/page.tsx` and its component/asset dependencies in `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app`.
**Planning-only notice:** This document is a plan only. No code was modified, no assets were modified, and no commit was made in the app repo as part of producing this plan. Nothing below has been implemented yet.

---

## Executive Summary

This plan sequences the audit's 12-item punch list into three priority bands, as directed: **P1** (image format correction, performance, font correction), **P2** (brand icon integration, service card improvements), **P3** (visual polish). Two audit items are not scheduled as code fixes at all — they are content-governance and asset-cleanup decisions already tracked elsewhere — and are listed separately under "Deferred / Out of Scope" so they aren't lost. Every fix below follows the project's standing workflow: implement → test → live preview (desktop/mobile × EN-LTR/AR-RTL) → owner commit approval. This plan does not authorize implementation by itself.

---

## Priority Order

| Priority | # | Fix | Area | Risk |
|---|---|---|---|---|
| P1 | 1 | Re-encode the 4 mislabeled `.webp` files (actually raw PNG) as true WebP/AVIF | Image format correction | LOW |
| P1 | 2 | Remove `priority` from the header logo so only the hero competes for LCP preload | Performance | LOW |
| P1 | 3 | Correct `BrandPanel`'s card `sizes` attribute from `50vw` to match the real ~33vw desktop card width | Performance | LOW |
| P1 | 4 | Resolve Arabic font-family mismatch: `TYPOGRAPHY.md` says Cairo, implementation loads Noto Kufi Arabic | Font correction | MEDIUM |
| P2 | 5 | Decide and document the Lucide-vs-custom-icon-set question | Brand icon integration | LOW (doc) / MEDIUM (if migrated) |
| P2 | 6 | Add `hover:`/`transition-*` classes to the 3 homepage service cards | Service card improvements | LOW |
| P2 | 7 | Restore the documented tablet 2-column step for the service-card grid | Service card improvements | LOW |
| P2 | 8 | Add mobile-specific card padding (16px) distinct from the flat 24px used today | Service card improvements | LOW–MEDIUM |
| P3 | 9 | Reconcile the 6 hardcoded off-palette hex colors against `COLORS.md` | Visual polish / design system | MEDIUM |
| P3 | 10 | Add explicit `focus-visible:` styling to homepage interactive elements | Visual polish / accessibility | LOW–MEDIUM |

---

## P1 — Image Format Correction, Performance, Font Correction

### P1-1: Re-encode mislabeled images as true WebP/AVIF

- **Finding:** Hero banner, AC-maintenance card, cleaning card, and pest-control hero/card images are all raw PNG data saved under a `.webp` filename (audit §4).
- **Files expected to change (assets only, no source code):**
  - `public/brand/images/afaq-alhayat-home-services-hero-banner-uae-21x9.webp`
  - `public/brand/images/services/maintenance/ac-maintenance-service-card-afaq-v1.webp`
  - `public/brand/images/services/cleaning/home-cleaning-service-card-afaq-v1.webp`
  - `public/brand/images/services/pest-control/pest-control-hero-banner-afaq-branded-21x9-v2.webp`
- **Risk level:** LOW — filenames/paths stay identical, so no code path changes; the only exposure is a visible quality/crop difference if the re-encode isn't a faithful re-save of the same approved photo.
- **Validation method:** Run `file <path>` on all 4 after re-encoding and confirm each reports `WebP` (or `RIFF ... WEBP`), not `PNG image data`. Compare on-disk byte size before/after. Load the homepage locally and visually diff hero + 3 service cards at desktop and mobile, EN and AR, against the current screenshots to confirm no visible quality loss or crop shift.

### P1-2: Remove `priority` from the header logo

- **Finding:** Both the hero image and the header logo carry `priority`, so two images compete for the browser's preload scanner (audit §1, §5).
- **Files expected to change:** `src/components/header.tsx` (the `priority` prop on the logo `<Image>`, ~line 44).
- **Risk level:** LOW — single prop removal, no layout or visual change; the logo still renders identically, just without an eager preload hint.
- **Validation method:** View page source / browser dev tools "Network" tab and confirm only the hero image has a `<link rel="preload" as="image">` / high-priority fetch. Confirm the logo still renders correctly on load (no flash/delay). Re-check homepage still passes lint/typecheck/build.

### P1-3: Correct `BrandPanel`'s card `sizes` attribute

- **Finding:** `BrandPanel` requests `sizes="(min-width: 1024px) 50vw, 100vw"` for every card, but the homepage's service-card grid is already 3 columns at `tablet:` and above, so real desktop card width is closer to ~33vw (audit §4).
- **Files expected to change:** `src/components/brand-panel.tsx` (~line 94, the `sizes` prop value).
- **Risk level:** LOW — a single attribute value change affecting which responsive image variant `next/image` selects; no markup/layout change.
- **Validation method:** Inspect the Network tab's requested image URL/width parameter at desktop, tablet, and mobile viewport widths, confirming a smaller variant is selected at desktop widths than before. Visually confirm no blurriness is introduced on any card at any breakpoint.

### P1-4: Resolve the Arabic font-family mismatch

- **Finding:** `TYPOGRAPHY.md` (v2.0) names Cairo as the approved Arabic family; the implementation loads Noto Kufi Arabic (`layout.tsx:14-18`, `tokens.css:23`) — a direct, checkable mismatch between the documented source of truth and the live token file (audit §6).
- **Files expected to change:**
  - `src/app/[locale]/layout.tsx` (~lines 14-18, the `next/font/google` Arabic font import), **or**
  - `12_DESIGN_SYSTEM/TYPOGRAPHY.md` (knowledge-base repo) if the owner decides Noto Kufi Arabic is the accepted substitution and the doc should be updated instead of the code.
  - `src/styles/tokens.css` (~line 23, `--font-arabic`) if the code path changes.
- **Risk level:** MEDIUM — this is an owner decision point first (which direction is correct), then a site-wide typography change if code changes: a live font swap has line-height/wrapping ripple effects across every Arabic page (homepage, services, locations, blog), not just the homepage.
- **Validation method:** Owner decision recorded in `00_GOVERNANCE/DECISION_LOG.md` before any change. If the font is swapped: visual QA across all major Arabic page templates (homepage, a service page, a location page, blog) checking for text overflow, line-height shifts, and letter-spacing issues, at desktop and mobile. If the doc is updated instead: confirm `TYPOGRAPHY.md` and `tokens.css`'s header comment (which claims to be "sourced from TYPOGRAPHY.md") are reconciled, no code change needed.

---

## P2 — Brand Icon Integration, Service Card Improvements

### P2-5: Decide and document the Lucide-vs-custom-icon-set question

- **Finding:** `12_DESIGN_SYSTEM/ICONS.md` documents Lucide as the preferred UI icon library; `icons.tsx` is a fully custom hand-drawn SVG set, disclosed in its own top comment as a stand-in because Lucide "is a new dependency this job can't add" (audit §3).
- **Files expected to change:**
  - Documentation-only path: `12_DESIGN_SYSTEM/ICONS.md` (knowledge-base repo) updated to record the accepted custom-icon exception, plus a `DECISION_LOG.md` entry.
  - Migration path (only if the owner decides to actually adopt Lucide): `package.json` (new dependency), `src/components/icons.tsx`, and every homepage/site file importing icons from it — a much larger, separate effort not sized as part of this plan.
- **Risk level:** LOW if documentation-only. MEDIUM–HIGH if a real migration is chosen — new dependency, and icon usages are spread across many components beyond just the homepage.
- **Validation method:** Owner decision recorded in `DECISION_LOG.md`. If documentation-only: confirm `ICONS.md` reflects the accepted exception and no code changes are needed. If migration is chosen: that becomes its own separate implementation ticket with its own plan, out of scope for this document's LOW-effort assumption.

### P2-6: Add hover/transition states to the 3 service cards

- **Finding:** The 3 homepage service-card `<article>`/`<Link>` elements carry no `hover:`/`transition-*` classes at all, unlike the emirate cards further down the page which already have this pattern (`page.tsx:509`) — a direct `CARDS.md` compliance gap (audit §2).
- **Files expected to change:** `src/app/[locale]/page.tsx` (~lines 274-318, the 3 service-card containers).
- **Risk level:** LOW — additive Tailwind classes matching an existing, already-approved pattern elsewhere on the same page.
- **Validation method:** Manual hover test in a desktop browser on all 3 service cards, confirming behavior matches the emirate-card hover pattern. Confirm no layout shift on hover. Confirm keyboard focus (Tab key) still reaches each card without visual regression.

### P2-7: Restore the tablet 2-column grid step

- **Finding:** `GRID.md`'s Service Cards Layout specifies Desktop 3 / Tablet 2 / Mobile 1 columns. The actual class (`page.tsx:233`, `tablet:grid-cols-3`) jumps straight from 1 to 3 columns at the tablet breakpoint, skipping the documented 2-column tablet step (audit §6).
- **Files expected to change:** `src/app/[locale]/page.tsx` (~line 233, the service-card grid's Tailwind class).
- **Risk level:** LOW — a single breakpoint class change, but needs a visual re-check specifically in the 768–1023px tablet range since that's exactly the range being changed.
- **Validation method:** Resize the browser (or use device emulation) across 768–1023px and confirm a clean 2-column layout with no card squishing or overflow. Re-confirm mobile (1-column) and desktop (3-column) are unaffected.

### P2-8: Add mobile-specific card padding

- **Finding:** `CARDS.md` specifies 24px desktop / 16px mobile padding; every card-shaped container on the homepage (service cards, "how it works" steps, FAQ items, emirate cards) currently uses a flat `p-space-3`/`p-space-4` (24/32px) at every breakpoint, with no mobile override (audit §2, §6).
- **Files expected to change:** `src/app/[locale]/page.tsx` (multiple card-shaped containers across several homepage sections — service cards, how-it-works steps, FAQ items, emirate cards).
- **Risk level:** LOW–MEDIUM — the change itself is additive responsive padding classes, but it touches several distinct sections, so it needs a visual re-check across all affected card types, not just one.
- **Validation method:** View each affected section at mobile widths (320–414px) and confirm 16px padding renders without text feeling cramped or overflowing, compared against the `CARDS.md` spec. Re-confirm desktop padding (24px) is unchanged.

---

## P3 — Visual Polish

### P3-9: Reconcile hardcoded off-palette hex colors

- **Finding:** Six hex values used directly in homepage-reachable code (`#0a2f52`, `#123f66`, `#1a5f95`, `#0d3660`, `#0c3d68`, `#071f38`) do not appear anywhere in `COLORS.md`'s approved palette (audit §6).
- **Files expected to change:** `src/app/[locale]/page.tsx` (~line 186, trust-bar section background) and `src/components/brand-panel.tsx` (~lines 36-38, 69 — category gradient colors).
- **Risk level:** MEDIUM — requires an owner/design decision first (add these to the approved palette, or replace them with existing tokens) before any code touches visible section backgrounds and card gradients.
- **Validation method:** Owner/design decision recorded in `DECISION_LOG.md` and, if applicable, `COLORS.md` updated first. Then visual comparison of the trust-bar background and all three card gradients before/after, across EN/AR and desktop/mobile, to confirm no unintended color shift.

### P3-10: Add explicit focus-visible styling

- **Finding:** No interactive element on the homepage (links, WhatsApp/call CTAs, emirate cards) carries an explicit `focus:`/`focus-visible:` Tailwind class — compliance with `ACCESSIBILITY.md`'s "every clickable element must show focus clearly" currently depends entirely on unstyled browser defaults (audit §6).
- **Files expected to change:** `src/app/[locale]/page.tsx` (links, CTAs, emirate cards), and possibly a shared focus-ring utility added to `src/app/globals.css` or `src/styles/tokens.css` if a single reusable class is introduced.
- **Risk level:** LOW–MEDIUM — additive, accessibility-only change with low visual risk on its own, but needs deliberate keyboard-navigation testing across every interactive element, including ones that sit on top of photos (hero CTAs) where contrast may need special handling.
- **Validation method:** Tab through the entire homepage using only the keyboard, confirming every link/button/CTA shows a clear, sufficiently contrasted focus ring — including CTAs rendered over photographic backgrounds. Repeat in both EN (LTR tab order) and AR (RTL tab order).

---

## Deferred / Out of Scope for This Plan

These two audit findings are not scheduled as homepage code fixes — they are decisions already tracked elsewhere and are listed here only so they aren't lost between documents.

| Audit finding | Why it's deferred |
|---|---|
| Re-verify homepage visual balance once Reviews/FAQ/Latest-Articles content is owner-approved (currently 3 of 11 sections render nothing because their registries are empty) | Content-governance decision gated on owner-approved content, not a code fix. Revisit once `VERIFIED_REVIEWS`, `APPROVED_FAQS`, or `BLOG_POSTS` are populated. |
| Delete the unused flat duplicate copies of the AC-maintenance card image and the pest-control hero banner | Already flagged in `00_GOVERNANCE/PROJECT_CLEANUP_AUDIT_REPORT.md`'s List B (needs owner approval) as part of the broader 45-pair duplicate-image finding. This plan does not modify assets, so it defers to that existing pending approval rather than duplicating it. |

---

## Validation & Approval Workflow (applies to every fix above, once implementation is approved)

Per the project's standing ticket workflow, none of the fixes above should be committed without: implement → lint/typecheck/test/build all green → start the dev server and share the live local preview URL → verify desktop + mobile + English-LTR + Arabic-RTL → report any visual issues found → only then request explicit commit approval with an exact commit message. This plan does not itself authorize implementation of any item above.

---

*End of plan. No code was modified, no assets were modified, and no commits were made in producing this document.*
