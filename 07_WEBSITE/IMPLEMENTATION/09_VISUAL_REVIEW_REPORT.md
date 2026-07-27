# Visual Review Report

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — review findings only, no code changed
- **Version:** 1.0
- **Prepared:** 2026-07-27
- **Target:** `afaqalhayatae-app`, running locally at `http://localhost:3000`

## Method — Important Limitation

**This is not a screenshot-based visual review.** A real browser review was attempted through two paths and both failed in this environment:

1. **Claude in Chrome extension** — would not connect across five attempts, including after a reinstall and full Chrome restart.
2. **macOS screen capture (`screencapture`)** — failed with a Screen Recording permission error. The permission was granted to Visual Studio Code and VS Code was restarted twice, but the underlying process (PID `9141`) never actually changed across restarts, so the permission never took effect. This looks like an environment quirk tied to VS Code running from a mounted volume (`/Volumes/VS Code/`) rather than `/Applications`.

Per the Owner's direction, this report instead reviews the **rendered server-side HTML and the exact source of every component in scope**, cross-checked against `12_DESIGN_SYSTEM/{BUTTONS,ICONS,COMPONENTS,LUXURY_DESIGN_DIRECTION}.md`. This finds real, concrete layout/consistency defects (see below), but it cannot judge things that only show up visually at runtime — exact spacing rhythm, color contrast as rendered, font rendering, or genuine cross-browser quirks. That gap is stated explicitly per finding, not glossed over.

---

## Desktop Layout

Structure reviewed: `max-w-desktop` (1200px) containers throughout, `desktop:grid-cols-2/3` breakpoints on the hero and service grids, sticky header. Nothing structurally broken found in source — grid classes are applied consistently and match `GRID.md`'s documented breakpoints (`tablet: 768px`, `desktop: 1200px`, `desktop-lg: 1440px`).

**Not verifiable without rendering:** whether the 1200px container actually feels well-proportioned at 1440px+ screens, or whether any text wraps awkwardly at real font metrics.

## Mobile Layout

`MobileCtaBar` (fixed bottom bar, `desktop:hidden`) and the header's hamburger menu are the two mobile-specific UI pieces. Both use safe-area-aware padding and 44px+ tap targets in source. `ConsentBanner` sits at `bottom-20` specifically to clear `MobileCtaBar`'s height on mobile, and drops to `bottom-0` at `desktop:` — a deliberate, documented layout coordination between two independent fixed-position components.

**Not verifiable without rendering:** whether `ConsentBanner` and `MobileCtaBar` actually clear each other correctly on real narrow-screen devices with on-screen keyboards or notches, or whether long Arabic labels wrap the mobile menu items awkwardly (`LUXURY_DESIGN_DIRECTION.md` §8 specifically calls out testing "long Arabic labels" as a requirement this review cannot fulfill).

## RTL Arabic Experience

Confirmed via rendered HTML: `/ar` serves `<html lang="ar" dir="rtl">`, `/en` serves `<html lang="en" dir="ltr">`. The one directional icon in use (`ArrowRightIcon`, "Learn More" links) correctly carries `rtl:rotate-180`. Layout code consistently uses logical properties (`start-`/`end-` in `BrandPanel`'s decorative blur and icon badge, `margin-inline` patterns implied by Tailwind's logical utilities) rather than hardcoded `left`/`right`, which is the correct approach for RTL/LTR parity.

**Not verifiable without rendering:** actual mirrored appearance, icon-to-text spacing in Arabic, and whether any icon that *shouldn't* mirror (e.g., a universal icon like search/close) was accidentally given a mirroring class — none was found in source, but a live check is the only way to be certain.

## Buttons

Reflects the button/icon refinement pass completed earlier this session (`BUTTON_ICON_REVIEW.md`) — heights and hover states are now consistent across header, hero, consent banner, and blog sidebar CTAs. **One instance was missed in that pass and is a new finding here:**

- **`src/app/[locale]/services/page.tsx`, bottom CTA button** (`t.services.cta.button`) still uses the old `py-space-2`-only sizing (no explicit `h-12`), identical to the pattern already fixed everywhere else. This is the same class of inconsistency `BUTTON_ICON_REVIEW.md` §2.1 addressed, just not caught in that pass because this page wasn't in the file list scanned at the time.

## Icons

- Service-card icon badges (`BrandPanel`'s absolutely-positioned circle) use `h-7 w-7` (28px) icons in a `h-11 w-11` (44px) circle. `ICONS.md`'s Large tier (32–48px) is explicitly named for "الخدمات" (services) — 28px sits just under that range. Minor, not the same category of issue as the button-icon findings (those were 20px against a 24px "buttons" spec; this is 28px against a 32–48px "services" spec, a smaller gap).
- Homepage trust-badge icons (`TrustIcon`, the four items above "How it works") use `h-5 w-5` (20px) inside `h-11 w-11` circles. `ICONS.md`'s Medium tier (24px) explicitly covers "البطاقات" (cards) — these badges are card-like elements, so 20px is arguably one tier under-spec here too, consistent with (but not part of) the icon-sizing pattern already fixed for buttons.
- Both are real, minor, low-risk observations — not applied, since this task is review-only.

## Header

Matches source reviewed in the earlier button/icon pass: logo, nav, account link, WhatsApp icon button (now 24px per the refinement), primary CTA (now `h-12`), language switcher, and a hamburger menu on mobile. No new structural issue found. `aria-current="page"` is correctly applied to the active nav item.

## Footer

Newsletter form, logo/tagline/socials column, quick links, contact column (phone/WhatsApp/email/address, all rendering the now-approved business facts), legal links, and copyright row. Structurally sound. The one open item from the earlier audit stands: the 8 social icon circles are `h-9 w-9` (36px), under the commonly recommended 44px minimum mobile tap target — flagged then, still open, not touched here either (review-only task).

## Hero Section

Homepage hero: eyebrow label, `h1`, subtitle, two CTAs (primary "Contact," WhatsApp), and a `BrandPanel` visual on desktop (`desktop:grid-cols-2`). One clear promise, one primary action, matching `LUXURY_DESIGN_DIRECTION.md` §5's Hero Sections guidance ("one clear promise... avoid rotating sliders, multiple competing headlines"). No carousel, no autoplay, no competing CTA — compliant by source inspection.

## Service Cards

Two independent implementations of what is conceptually the same card exist:

1. **Homepage preview** (`src/app/[locale]/page.tsx`, first 6 services): card includes a "Learn More" link **with** `ArrowRightIcon` (RTL-mirrored).
2. **Full services listing** (`src/app/[locale]/services/page.tsx`, all 12 services): visually identical card markup, but its "Learn More" link has **no icon at all**.

This is a real, concrete inconsistency — the same component pattern rendering with a visible feature difference depending on which page it's on, which is exactly what `LUXURY_DESIGN_DIRECTION.md` §10 prohibits under "Inconsistent components created for one page only." Both card blocks are near-duplicated JSX rather than a shared component, which is also why this drifted apart in the first place — the same root cause `BUTTON_ICON_REVIEW.md` §3 already named for buttons (no shared `Button`/`Card` primitive under `src/components/ui/`) applies here too.

---

## Visual Issues Found (this pass)

1. Services page bottom CTA button uses outdated `py-space-2` sizing, missed in the earlier button/icon fix pass.
2. Service card "Learn More" link is inconsistent between the homepage preview and the full services page — one has a directional arrow icon, the other doesn't.
3. Service-card icon badges (28px) and homepage trust-badge icons (20px) both sit slightly under their respective `ICONS.md` size-tier spec (32–48px "services," 24px "cards").
4. (Carried over, not new) Footer social icon touch targets remain 36px, below the 44px mobile-tap-target guideline.

## UX Improvements Suggested

1. **Extract a shared `ServiceCard` component** used by both the homepage preview and the full services page, so the arrow-icon inconsistency (and any future drift) becomes structurally impossible rather than something to catch by review each time.
2. **Add the same "Learn More" arrow icon to the services-page cards**, matching the homepage — small, consistent, low-risk once approved.
3. Consider bumping service-card and trust-badge icons to their spec sizes (32px and 24px respectively) in a future icon-sizing follow-up, alongside the footer social-icon touch-target fix already flagged in `BUTTON_ICON_REVIEW.md`.
4. A genuine visual/rendered pass is still recommended before this component set is considered launch-ready — this report closes the source-level gaps it can see, but spacing rhythm, real contrast, and RTL mirroring "in the flesh" need actual eyes on a real render once the browser-access issue is resolved.

---

## What This Report Does Not Do

- Does not include any screenshot (browser access unavailable, see Method above).
- Does not modify any code — every finding above is reported, not applied, per this task's explicit rule.
- Does not re-verify items already confirmed compliant in `BUTTON_ICON_REVIEW.md` (border radius, disabled states, motion) — those stand as previously reported.

---

## Related Documents

- `07_WEBSITE/IMPLEMENTATION/BUTTON_ICON_REVIEW.md`
- `12_DESIGN_SYSTEM/BUTTONS.md`
- `12_DESIGN_SYSTEM/ICONS.md`
- `12_DESIGN_SYSTEM/COMPONENTS.md`
- `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md`
