# Hero Finalization & Brand Icon Integration — Implementation Report

**Date:** 2026-08-01
**Scope:** `src/app/[locale]/page.tsx` hero section, header/navigation icons, service-card icons, `public/brand/icons/` — in `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app`, compared against `/Users/ashrafeladrousi/Documents/AFAQ_ALHAYAT_ENTERPRISE_KNOWLEDGE/12_DESIGN_SYSTEM/`.
**Pre-implementation notice:** Written before any code change, per instruction. No content, SEO copy, service catalog, or location pages are touched by this work.

---

## 1. Current Problems

### Hero (Phase 1)

- **CTA hierarchy conflicts with the design system's own "one dominant action" rule.** `LUXURY_DESIGN_DIRECTION.md` line 138/144: *"Communicate one clear promise, one supporting statement, and one primary action"* / *"Each section should have one dominant action."* The current hero (`page.tsx:220-236`) renders WhatsApp and Call as two equally-weighted filled/outline buttons, with no Booking CTA at all — it does not have a single dominant action, and it doesn't have the one the Owner just specified as required ("Book Appointment"/"احجز موعد").
- **Mobile crop reuses the desktop's object-position bias.** The mobile-specific crop (`afaq-alhayat-home-services-hero-banner-uae-mobile.webp`, added in the prior Homepage Foundation Alignment pass) is already a tighter, subject-focused crop of the same approved photo — but the `<img>` tag still applies `object-[80%_center]` (`page.tsx:~178`), a bias tuned for the *wide* 21:9 image's off-center subject. Reapplying that same 80%-right bias on top of an image that's already framed around the subject risks pushing the person/equipment further right than intended on some viewport ratios, working against the "no cropped faces/equipment" requirement. Verified visually: the mobile crop itself is fine (full face, mask, and sprayer visible, comfortable margins) — the risk is the redundant CSS bias on top of it, not the crop itself.
- **Focal point / overlay**: verified acceptable — the scrim (`bg-gradient-to-r from-black/60 via-black/25 to-transparent`, `page.tsx:187-190`) already darkens only the text side and fades over the subject, and contrast on the white `text-h1`/`text-white/85` text reads cleanly against it. No change needed here.
- **Headline hierarchy**: eyebrow (`text-small` uppercase) → `h1` (`text-h1` bold) → subtitle (`text-lead`) is already a real, distinct 3-step scale from `TYPOGRAPHY.md`'s clamp() tokens — structurally sound. The gap is the CTA row beneath it competing for attention (see above), not the type scale itself.

### Icon system (Phase 2)

- **`public/brand/icons/` does not exist.** Confirmed via direct filesystem check — `public/brand/` only contains an `images/` subfolder. No real brand/marketing/service icon image assets exist anywhere in the repository, and none are referenced by any code path.
- The only pre-existing icon files in the whole repo are 8 small, already-committed, unused legacy SVGs at `public/images/brand/icons/` (`service-request.svg`, `maintenance.svg`, `whatsapp.svg`, `trust.svg`, `phone.svg`, `location.svg`, `pest-control.svg`, `cleaning.svg`) — a different path than the one specified in this ticket (`public/brand/icons/`), referenced by zero code, and not a full set (no emirate icons at all, and only 2 of the 3 requested service categories).
- Today, every icon on the homepage — service badges, emirate cards, trust strip, UI controls — is a hand-drawn inline SVG component from `src/components/icons.tsx` (377 lines, ~36 components). `icons.tsx`'s own top comment already discloses this is a stand-in for Lucide on UI controls; the prior ticket already moved the header's menu-toggle and account icon to real Lucide components, which remains correct and unaffected by this ticket.
- Per `docs/VISUAL_ASSET_MASTER_PLAN.md` (already in the repo, independent confirmation): only 5 of 16 services have a genuinely unique icon today; 11 share 3 generic icons (`WrenchIcon` covers 4 trades, `CleaningIcon` covers 6 services, `DropletIcon` covers 4 services) — this is a pre-existing, documented gap in the current code-drawn set, separate from the missing-asset-files question, and out of scope to fix by drawing more inline SVGs (that would be fabricating icons under time pressure, which this ticket explicitly prohibits).

### Homepage visual check (Phase 3, review only)

- **Service cards**: icon badges (`page.tsx:~301`) are legible, consistent size/color per category — no visibility issue found.
- **Icon visibility**: all icons in current use are `currentColor`-stroked SVGs against sufficient-contrast backgrounds (white cards, dark trust bar, primary-color badges) — no contrast failures found.
- **Booking section**: present and functional (added in the prior ticket), links to `/book`, uses "Book Appointment"/"احجز موعد" wording already.
- **Navigation visuals**: header logo/menu/account icons render correctly at both breakpoints; no visual defects found.
- **Mobile layout**: hero, service cards, and booking section all reflow correctly at mobile width; the one real issue found is the hero CTA hierarchy/object-position point above.

---

## 2. Files to Modify (Phase 1 only — Phase 2 has no approved assets to wire in)

| File | Change |
|---|---|
| `src/app/[locale]/page.tsx` | Make "Book Appointment" (`/book`) the hero's single dominant, filled-primary CTA; demote WhatsApp/Call to a smaller secondary row beneath it; fix the mobile `<img>`'s object-position so it no longer reapplies the desktop-only 80%-right bias on top of the already-subject-framed mobile crop. |
| `src/i18n/messages/en.json` / `ar.json` | Reuse the existing `home.booking.button` ("Book Appointment"/"احجز موعد") string for the new hero CTA — no new key needed, same wording already approved in the prior ticket. |

No other files change in this pass. Service content, SEO metadata, the service catalog, and location pages are untouched, per instruction.

---

## 3. Missing Assets (Phase 2 — reported, not fabricated)

**`public/brand/icons/` does not exist and none of the following approved icon files are present anywhere in the repository:**

| Needed icon | Purpose | Status |
|---|---|---|
| Maintenance service icon | Service cards / brand icon system | **Missing** — no file at `public/brand/icons/` |
| Cleaning service icon | Service cards / brand icon system | **Missing** |
| Pest Control service icon | Service cards / brand icon system | **Missing** |
| Abu Dhabi emirate icon | Emirates coverage section | **Missing** |
| Dubai emirate icon | Emirates coverage section | **Missing** |
| Sharjah emirate icon | Emirates coverage section | **Missing** |
| Ajman emirate icon | Emirates coverage section | **Missing** |
| Umm Al Quwain emirate icon | Emirates coverage section | **Missing** |
| Ras Al Khaimah emirate icon | Emirates coverage section | **Missing** |
| Fujairah emirate icon | Emirates coverage section | **Missing** |

Per instruction, none of these are being fabricated. The homepage continues to render its existing, disclosed, hand-drawn `icons.tsx` components for services and emirates until real approved icon files are supplied at `public/brand/icons/` — no visual regression, no invented brand asset presented as final. Phase 2 cannot proceed beyond this report until real files exist.

---

## 4. Implementation Plan

1. Hero: reorder/restyle CTAs so "Book Appointment" is the one filled-primary, dominant action; move WhatsApp and Call to a visually secondary row (still present, still functional, just no longer competing for primary attention) — matching `LUXURY_DESIGN_DIRECTION.md`'s "one dominant action" rule and the Owner's explicit CTA requirement.
2. Hero: correct the mobile image's `object-position` so it doesn't double-apply the desktop bias on the already-cropped mobile photo.
3. Re-verify at desktop, tablet, and mobile widths, in both English-LTR and Arabic-RTL.
4. Run lint, typecheck, tests, build.
5. Report files changed, visual improvements, remaining gaps (including the Phase 2 missing-asset list above, unchanged), and `git status`. No commit, no push.

---

*End of report. No code was changed in producing this document.*
