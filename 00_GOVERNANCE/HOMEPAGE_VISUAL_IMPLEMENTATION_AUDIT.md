# Homepage Visual Implementation Audit

**Date:** 2026-08-01
**Scope:** Static code audit of the Next.js homepage as it exists on disk in the working tree of `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app` (entry point `src/app/[locale]/page.tsx`, and every component/lib file it transitively imports), compared against `/Users/ashrafeladrousi/Documents/AFAQ_ALHAYAT_ENTERPRISE_KNOWLEDGE/12_DESIGN_SYSTEM/`.
**Method:** Read-only. No dev server was started, no browser or Lighthouse automation was run. All performance statements are static-analysis inferences from source code, not measurements.
**Audit-only notice:** No code was changed, no fixes were applied, and no commit was made in the app repo as part of this audit. This document is the only file written.

**Working-tree note:** The app repo has extensive uncommitted changes as of 2026-08-01 (`git status` shows ~45 modified tracked files and ~35 new untracked files/directories). This audit reads the working tree (what actually renders today), not `HEAD`. `src/lib/catalog/blog.ts`'s `BLOG_POSTS = []`, `src/lib/catalog/reviews.ts`'s `VERIFIED_REVIEWS = []`, and `src/lib/catalog/faq.ts`'s `APPROVED_FAQS = []` are intentional, explicitly-commented content gates awaiting Owner-approved content — not bugs — but their current emptiness does materially change what the homepage renders today, so it is reported factually below.

---

## Executive Summary

The homepage (`src/app/[locale]/page.tsx`, 547 lines) is a single server component composed of eleven sections. Core mechanics are solid: the hero and the three service-card images use `next/image` correctly with real (non-demo) photography, bilingual alt text, and `priority` on the hero; the design-token file (`src/styles/tokens.css`) transcribes `COLORS.md`/`SPACING.md`/`TYPOGRAPHY.md`'s numeric values almost verbatim; RTL/LTR is handled thoughtfully throughout, including a documented, deliberate exception for the hero's fixed photo composition. The main risks are: (1) three of the page's content sections (Reviews, FAQ, Latest Articles) currently render nothing at all because their backing registries are empty, so roughly half of the "trust-building" content described in `LUXURY_DESIGN_DIRECTION.md` §6 is not actually visible today; (2) all four photographic assets reachable from the homepage are literally raw PNG data saved with a `.webp` extension, not real WebP files; (3) the custom icon set intentionally diverges from `ICONS.md`'s documented Lucide preference (this is disclosed in a code comment, not hidden); (4) a handful of hardcoded off-palette hex colors and a card-grid breakpoint that skips the documented tablet-2-column step are present. None of these are visually broken, but several are concrete, low-to-medium effort fixes with real perf/consistency payoff.

---

## 1. Hero Section

### Current State

- Location: `src/app/[locale]/page.tsx:108-179`, a `<section>` using `next/image` (`Image` imported at `page.tsx:4`) with `fill`, at `page.tsx:109-119`.
- Source selection: `src={SHOW_DEMO_VISUALS ? DEMO_VISUAL_SRC : HOMEPAGE_HERO_SRC}` (`page.tsx:110`). `SHOW_DEMO_VISUALS` is `false` (`src/lib/media/demo-visuals.ts:16`), so the **real, approved** hero photo is rendered: `HOMEPAGE_HERO_SRC = "/brand/images/afaq-alhayat-home-services-hero-banner-uae-21x9.webp"` (`src/lib/media/homepage-hero.ts:7`).
- Alt text: bilingual and descriptive — `HOMEPAGE_HERO_ALT.en`/`.ar` (`homepage-hero.ts:9-12`), selected per locale at `page.tsx:111`. Meets `ACCESSIBILITY.md`'s "every important image needs alt text" rule.
- Loading/LCP: `priority` is set (`page.tsx:113`), `sizes="100vw"` (`page.tsx:114`) — correct practice for a full-bleed hero that is almost certainly the LCP element.
- Responsiveness: one single source image is used at all breakpoints; responsiveness comes from the *container* (`min-h-[480px] tablet:min-h-[560px] desktop:aspect-[21/9]`, `page.tsx:108`) plus a biased `object-[80%_center]` crop (`page.tsx:118`), not from separate mobile/desktop image variants or `<picture>` art-direction. There is no dedicated narrow/mobile crop of the hero photo.
- File reality: the file at `public/brand/images/afaq-alhayat-home-services-hero-banner-uae-21x9.webp` is **not actually WebP** — `file` reports `PNG image data, 1915 x 821, 8-bit/color RGB` — despite the `.webp` extension and filename. Raw size on disk: 1,915,354 bytes (~1.9 MB).
- EN/AR handling: the hero deliberately does **not** use logical RTL properties for the text block's horizontal position. Per the comment at `page.tsx:98-107`, the source photo's subject is composed toward the physical right with negative space on the physical left, so the text block is pinned with literal `mr-auto`/`text-left`/`text-right` (`page.tsx:129`) rather than `ms-`/`text-start` — this is a documented, intentional exception, not an RTL bug. Only the text's own alignment (right for Arabic, left for English) follows locale.
- A second `priority` image exists elsewhere in the render tree: the header logo, `src/components/header.tsx:39-46` (`priority`, 40×40 render of a 2000×2000 source PNG at `public/brand/logo-mark.png`, 356 KB). Two `priority`-flagged images compete for the browser's preload scanner.

### Missing / Gaps / Risks

- No responsive art-direction (different crop/subject framing for narrow mobile vs. desktop) beyond CSS `object-position` bias — acceptable per code comment, but means very narrow viewports still crop a wide 21:9 photo.
- The hero image's actual bytes are raw PNG mislabeled as `.webp` (see §4/§5 below) — larger than a true WebP encode would be, though `next/image`'s optimizer re-encodes on request per `next.config.ts`'s `formats` setting regardless of source extension (unverified without a live request — static-analysis limit).
- Two competing `priority` images (hero + header logo) on every homepage load; only one image should typically carry `priority` for LCP purposes.
- `12_DESIGN_SYSTEM/GRID.md`'s Hero Section spec (title, description, one CTA, image) and `COMPONENTS.md`'s Hero Component spec (title, description, one CTA button, visual) both describe a single CTA; the implementation intentionally ships two (WhatsApp + Call, `page.tsx:159-176`), documented at `page.tsx:154-158` as a deliberate reference-design choice, not an oversight.

---

## 2. Service Cards

### Current State

- The homepage renders exactly **3** service cards — `maintenance`, `cleaning`, `pest-control` (`page.tsx:234-272`) — out of the full 27-entry catalog in `src/lib/catalog/services.ts:32-108`. This is by design: `LUXURY_DESIGN_DIRECTION.md` §6 "Homepage" calls for explaining "core service categories," not the full catalog (the full list lives at `/services`), so this is not a "missing services" gap, just worth noting explicitly since it doesn't literally show "all 12/27 services."
- Card markup (`page.tsx:274-318`): a bordered `<article>` (`rounded-2xl border border-(--color-border) bg-(--color-surface)`) containing an icon-badge header row, a `BrandPanel` photo slot, then description + "Learn more" link.
- Images used per card:

| Card | Source constant | File path | Real dims | Notes |
|---|---|---|---|---|
| Maintenance (AC) | `getServiceCardImage("ac-maintenance")` (`service-content.ts:186-188`) | `public/brand/images/services/maintenance/ac-maintenance-service-card-afaq-v1.webp` | 1314×1197 | Real approved photo, alt from `SERVICE_DATABASE.json` |
| Cleaning | `getServiceCardImage("general-cleaning")` | `public/brand/images/services/cleaning/home-cleaning-service-card-afaq-v1.webp` | 1536×1024 | Real approved photo |
| Pest Control | `getServiceHero("pest-control")` (`service-content.ts:125-127`) — no dedicated `cardImage` exists for this service | `public/brand/images/services/pest-control/pest-control-hero-banner-afaq-branded-21x9-v2.webp` | 1915×821 | A 21:9 hero photo reused in the 4:3 card slot via `imagePosition="78% center"` (`page.tsx:270`), documented gap at `page.tsx:259-267` and `docs/MISSING_SERVICE_IMAGES_REPORT.md` |

- `requireCardImage()` (`page.tsx:66-77`) throws a build-time error if any of these three images is ever missing — a good robustness guard against a silently broken card.

### Missing / Gaps / Risks vs. `CARDS.md`

| `CARDS.md` rule | Spec | Implementation | Match? |
|---|---|---|---|
| Border radius | 16px | `rounded-2xl` = 16px (`page.tsx:276`) | ✅ |
| Border color | `#E5E7EB` | `border-(--color-border)` token = `#E5E7EB` | ✅ |
| Background | White | `bg-(--color-surface)` = `#FFFFFF` | ✅ |
| Padding | 24px desktop / **16px mobile** | Flat `p-space-3` (24px) at every breakpoint, no mobile override (`page.tsx:284,306`) | ❌ no responsive reduction |
| Hover interaction ("simple change + light motion, signals clickability") | Required | The 3 service-card `<article>`/`<Link>` elements (`page.tsx:274-318`) carry **no** `hover:`/`transition-*` classes at all | ❌ missing entirely (contrast: the emirate cards further down, `page.tsx:509`, do have `hover:border-(--color-primary) hover:text-(--color-primary) transition-colors`) |
| Images: optimized, WebP where possible, fixed aspect ratio, alt text | Required | `next/image` via `BrandPanel`, `aspect-[4/3]` fixed (`brand-panel.tsx:74`), real bilingual alt required by the type system (`brand-panel.tsx:31-33`) — but see §4/§5 on actual file format | ✅ mechanism / ⚠️ underlying file format |

- Icon badges use one custom SVG icon per category (`WrenchIcon`, `CleaningIcon`, `PestIcon`), colored via `CATEGORY_BADGE_COLOR` (`service-visuals.tsx:92-96`) — blue for maintenance/pest-control, green for cleaning, both drawn from approved COLORS.md tokens.

---

## 3. Brand Icon Usage

### Current State

- `src/components/icons.tsx` (378 lines) is a hand-drawn inline-SVG icon set, not an icon library. Every icon shares one `Icon()` wrapper (`icons.tsx:12-27`): `viewBox="0 0 24 24"`, `stroke="currentColor"`, `strokeWidth={1.75}`, round caps/joins — internally consistent style across all ~35 icons in the file.
- The file's own top comment is explicit and self-aware about the drift: *"Lucide is the documented preference but is a new dependency this job can't add, so these are hand-drawn to match its proportions and visual language instead"* (`icons.tsx:1-6`).
- `12_DESIGN_SYSTEM/ICONS.md` (lines 32-46) defines **two separate systems**: "Brand Icons" (illustrations, at `public/brand/icons/`) and "UI Icons" (Lucide, for interface controls), and explicitly forbids mixing their styles. `public/brand/icons/` does not exist in this repo (`ls` returns "No such file or directory") — there is only the one hand-drawn set in `icons.tsx`, used for both illustrative service/emirate icons and interface controls (menu, phone, WhatsApp, user) alike.
- Homepage icon sizes in use: `h-5 w-5` (20px) trust-strip icons (`page.tsx:147`), `h-6 w-6` (24px) card badges (`page.tsx:289`), `h-7 w-7` (28px) trust-section icons (`page.tsx:194`), `h-9 w-9` (36px) emirate icons (`page.tsx:511`), `h-4 w-4` (16px) arrow icons (`page.tsx:315,376`).

### Missing / Gaps / Risks vs. `ICONS.md`

- Library choice: implementation uses a fully custom SVG set instead of the documented Lucide preference. This is disclosed in-code, not a silent deviation, but it is a real, unresolved drift from the design-system source of truth.
- Sizing: `ICONS.md` defines exactly three named size tokens — Small 16px, Medium 24px, Large 32–48px. The homepage's 20px (trust strip) and 28px (trust section) icon sizes fall between these named tokens rather than matching one exactly.
- Consistency: within the custom set, style is internally coherent (one stroke weight, one cap/join style, no mixing of filled/outline/emoji) — this specific rule from `ICONS.md`/`LUXURY_DESIGN_DIRECTION.md` §3 ("do not mix icon styles") is satisfied even though the underlying library choice is not.

---

## 4. Image Usage

### Current State — every image reachable from the homepage render tree

| Image | Rendered via | `next/image`? | Alt text | Real dims | On-disk format vs. extension |
|---|---|---|---|---|---|
| Hero banner | `page.tsx:109-119` | Yes, `fill` + `priority` | ✅ bilingual, real | 1915×821 | **PNG data saved as `.webp`** |
| Header logo | `header.tsx:39-46` | Yes, fixed `width`/`height` + `priority` | ✅ (wordmark text) | 2000×2000 source, rendered 40×40 | Real PNG (`.png` extension correct) |
| AC maintenance card | `page.tsx:296-304` via `BrandPanel` | Yes, `fill` | ✅ bilingual, from `SERVICE_DATABASE.json` | 1314×1197 | **PNG data saved as `.webp`** |
| Cleaning card | same | Yes, `fill` | ✅ | 1536×1024 | **PNG data saved as `.webp`** |
| Pest control card (reused hero) | same | Yes, `fill` | ✅ | 1915×821 | **PNG data saved as `.webp`** |
| Demo placeholder SVG | referenced by `demo-visuals.ts:18` | would be, if reachable | n/a | n/a | Not currently rendered — `SHOW_DEMO_VISUALS=false` and `BLOG_POSTS=[]` (see below), so this asset is dead code on the homepage today |
| Blog card illustrations | `BlogPostCard` → `BrandPanel` (illustration-only path, no `src`) | n/a (decorative scene, not a photo) | n/a (`aria-hidden`) | n/a | `latestArticles` is empty (see §6 below), so zero `BlogPostCard`s actually render today |

All four confirmed via the Unix `file` command — each reports `PNG image data`, not WebP, despite the `.webp` filename extension used throughout the catalog and hero-media modules. This affects every photographic asset the homepage renders.

- No `<img>` tags and no CSS `background-image` are used for any of these photos — every one goes through `next/image` (via direct `<Image>` or the shared `BrandPanel` wrapper), which is the correct, optimized path.
- `BrandPanel`'s `alt` is type-required whenever `src` is passed (`brand-panel.tsx:31-33`), so a real photo can never ship without alt text through this component — a good structural guard.
- Duplicate-image note (relevant to the prior known 45-pair finding): the `ac-maintenance` card image exists at **two** paths with identical byte size (1,951,588 bytes) — `public/brand/images/services/ac-maintenance-service-card-afaq-v1.webp` (flat) and `public/brand/images/services/maintenance/ac-maintenance-service-card-afaq-v1.webp` (nested). Similarly the pest-control hero exists at `public/brand/images/pest-control/...` (flat) and `public/brand/images/services/pest-control/...` (nested), both 2,154,718 bytes. In both cases the homepage's code path (`service-content.ts:116,182`) references only the **nested** path — the flat duplicates sit unused on disk but are not directly referenced by any homepage code today.
- `sizes` mismatch on card images: `BrandPanel` requests `sizes="(min-width: 1024px) 50vw, 100vw"` (`brand-panel.tsx:94`) for every card, but the homepage's service-card grid is already 3 columns at the `tablet` breakpoint and above (`page.tsx:233`, `tablet:grid-cols-3`), meaning each card's real rendered width at desktop is closer to ~33vw than 50vw. `next/image` will select a larger source image than the card actually needs at desktop widths.

### Missing / Gaps / Risks

- All four `.webp`-named photographic files are actually raw PNG bytes (see table above) — the largest is 2,582,334 bytes (cleaning card). This doesn't necessarily change what bytes reach the browser (Next's image optimizer transcodes based on `next.config.ts`'s configured `formats`, independent of source extension — unverified live), but it is a real, verifiable file-integrity discrepancy in the source asset library.
- `BrandPanel`'s `sizes` value is too generous for the 3-up desktop card grid it's actually used in.

---

## 5. Loading Performance (static-analysis only — no Lighthouse/browser run performed)

### Current State

- Hero image: `priority` set correctly (`page.tsx:113`) — the single highest-impact LCP practice, done right.
- `next.config.ts:5-13` configures `images.formats: ["image/avif", "image/webp"]` (AVIF-first, WebP fallback) and `dangerouslyAllowSVG: true` (scoped to the local demo SVG per its own comment). `sharp` (the native encoder Next's image optimizer prefers) is present in `package-lock.json` (`@img/sharp-darwin-arm64`, etc.), so the optimization pipeline has what it needs, at least for local/dev builds on this machine.
- Client-side JS high in the tree: `src/components/header.tsx:1`, `src/components/announcement-bar.tsx:1`, `src/components/consent-banner.tsx:1`, and `src/components/google-tag-manager.tsx:1` are all `"use client"`, and all four render above `<main>` in `src/app/[locale]/layout.tsx:65-71` — i.e., on every load of the homepage (and every other page). `footer.tsx`, `mobile-cta-bar.tsx` are not client components (no `"use client"` found); `language-switcher.tsx:1` is client but is nested inside the already-client `Header`.
- No `<video>` element and no CSS `background-image` is used anywhere in the homepage's render path — avoids a render-blocking/heavy media pattern the design system explicitly prohibits (`LUXURY_DESIGN_DIRECTION.md` §10).
- Non-priority images (the 3 service cards) receive no explicit `loading` attribute, which means they get `next/image`'s correct default (`lazy`) — appropriate, no action needed there.

### Missing / Gaps / Risks

- Two `priority`-flagged images per page load (hero + header logo) — only the true LCP candidate should typically carry `priority`; the logo is small (40×40 rendered) and unlikely to be the LCP element, so marking it `priority` adds an unnecessary high-priority fetch competing with the hero.
- Source photo files are 1.9–2.6 MB raw PNGs (mislabeled `.webp`) — larger uncompressed originals for the optimizer to transcode from than a properly-encoded WebP/AVIF source would be. Whether this measurably affects served bytes/TTFB for the optimized output cannot be determined without a live request — **explicitly unverified, not measured**.
- `next.config.ts` has no `images.remotePatterns`/`domains`, but the homepage doesn't need any (all images are local under `/public`) — not a gap, noted for completeness.
- No actual Largest Contentful Paint time, Cumulative Layout Shift score, or Lighthouse score can be stated — that requires a running build and browser measurement, which is out of scope for this static, read-only audit.

---

## 6. Design System Application

### Current State — token-level compliance

| Token family | `12_DESIGN_SYSTEM/*.md` spec | Implementation | Match? |
|---|---|---|---|
| Colors | `COLORS.md`: Primary `#0F4C81`, Success `#16A34A`, Warning `#F59E0B`, Danger `#DC2626`, Info `#0EA5E9`, WhatsApp `#25D366`, surfaces `#FFFFFF`/`#F8FAFC`, text `#111827`/`#6B7280`/`#9CA3AF`, border `#E5E7EB` | `src/styles/tokens.css:9-20` transcribes every one of these values exactly | ✅ base palette |
| Spacing | `SPACING.md`: Space 1–8 = 8/16/24/32/40/48/64/96px | `tokens.css:38-45` — exact match | ✅ |
| Type scale | `TYPOGRAPHY.md` clamp() table for Display/H1–H6/Lead/Small | `tokens.css:27-35` — values copied verbatim | ✅ |
| Container widths | `GRID.md`: Desktop 1200px, Large Desktop 1440px | `tokens.css:48-49` (`--container-desktop`, `--container-desktop-lg`) — exact match, and `page.tsx` uses `max-w-desktop` consistently on every section | ✅ |
| Arabic font family | `TYPOGRAPHY.md` (v2.0): **Cairo** | `layout.tsx:14-18` loads **Noto Kufi Arabic** via `next/font/google`; `tokens.css:23` sets `--font-arabic: "Noto Kufi Arabic", Tahoma, Arial, sans-serif` | ❌ documented spec says Cairo, implementation uses a different Arabic font family |
| English font family | `TYPOGRAPHY.md`: Inter | `layout.tsx:20-24`, `tokens.css:24-25` | ✅ |

### Missing / Gaps / Risks

- **Hardcoded off-palette hex colors.** None of the following six hex values appear anywhere in `COLORS.md`'s approved palette, yet all are used directly in homepage-reachable component code instead of a design token:
  - `#0a2f52` — trust-bar section background, `page.tsx:186`, and `BrandPanel`'s default (no-category) gradient end color, `brand-panel.tsx:69`
  - `#123f66` — maintenance category gradient end, `brand-panel.tsx:36`
  - `#1a5f95` / `#0d3660` — cleaning category gradient start/end, `brand-panel.tsx:37`
  - `#0c3d68` / `#071f38` — pest-control category gradient start/end, `brand-panel.tsx:38`
- **Font family drift.** Arabic body/heading text loads "Noto Kufi Arabic" (`layout.tsx:14-18`) where the current `TYPOGRAPHY.md` (v2.0) names "Cairo" as the approved Arabic family. This is a direct, checkable mismatch between the documented source of truth and the live token file's own header comment, which claims to be "sourced from ... TYPOGRAPHY.md" (`tokens.css:1-4`).
- **Service-card grid breakpoint skips the documented tablet step.** `GRID.md`'s "Service Cards Layout" section specifies Desktop 3 columns / **Tablet 2 columns** / Mobile 1 column. The homepage's actual class is `grid gap-space-4 tablet:grid-cols-3` (`page.tsx:233`) — mobile is 1 column (Tailwind default), but the `tablet:` breakpoint (768px) jumps straight to 3 columns and stays there through desktop, so there is no distinct 2-column tablet layout at all.
- **Card padding does not shrink on mobile.** `CARDS.md` specifies 24px padding on desktop and 16px on mobile; every card-shaped container on the homepage (service cards, "how it works" steps, FAQ items, emirate cards, etc.) uses a flat `p-space-3`/`p-space-4` (24/32px) with no mobile-specific override anywhere in `page.tsx`.
- **Button height.** `BUTTONS.md` specifies a 56px "Large" button height for homepage/booking contexts. The hero's two CTAs use `h-12` (48px, `page.tsx:164,171`) — `BUTTONS.md`'s "Medium" height, used elsewhere in the doc for "most site interfaces" rather than the homepage specifically.
- **No explicit focus-visible styling.** `grep -n "focus"` across `page.tsx` returns zero matches — no interactive element on the homepage (links, WhatsApp/call CTAs, emirate cards) carries an explicit `focus:`/`focus-visible:` Tailwind class. Browsers' native default focus ring will still appear, but `ACCESSIBILITY.md`'s explicit requirement that "every clickable element must show focus clearly" has no deliberate, testable implementation in this file — compliance depends entirely on browser defaults, which weren't evaluated here (out of scope for static review).
- **Reduced motion — correctly handled, not a gap.** For completeness: the one continuous animation reachable from every page load (the announcement-bar ticker, `globals.css:17-24`'s `@keyframes marquee`) is properly gated with Tailwind's `motion-reduce:animate-none` utility at its call site (`announcement-bar.tsx:85`), matching `ANIMATIONS.md`'s reduced-motion requirement. Verified so this isn't mis-flagged.
- **Content sections currently rendering nothing.** Three of the page's eleven sections are conditionally gated on registries that are currently empty in the working tree:
  - Reviews (`page.tsx:443`, `ReviewsSection`) — `VERIFIED_REVIEWS = []` (`src/lib/catalog/reviews.ts:24`) → renders `null` (`reviews-section.tsx:23`)
  - FAQ (`page.tsx:450-486`) — `APPROVED_FAQS = []` (`src/lib/catalog/faq.ts:38`) → `homepageFaqs.length === 0`, section hidden
  - Latest Articles (`page.tsx:409-436`) — `BLOG_POSTS = []` (`src/lib/catalog/blog.ts:73`) → `latestArticles.length === 0`, section hidden

  This is the same intentional, explicitly-documented content-governance gate described in each file's own comments (real content pending Owner approval) — not a code bug — but it means that, as currently deployed, the homepage a visitor sees today omits the Reviews, FAQ, and Latest Articles sections entirely, leaving Hero, Trust bar, Service cards (3), How It Works, Why Us, About, Service Areas (7 emirates), and the closing Contact CTA as the sections that actually render.

---

## Prioritized Punch List

Findings to consider — not implemented as part of this audit.

| # | Finding | Impact | Risk to fix | Area |
|---|---|---|---|---|
| 1 | Re-encode the 4 homepage-reachable "`.webp`" files that are actually raw PNG (hero, AC card, cleaning card, pest-control hero/card) as true WebP/AVIF at the source | Perf (smaller true source for the optimizer to work from; removes a real file-integrity defect) | LOW — re-export/re-save existing approved photography, no code change required | Perf / Image usage |
| 2 | Remove `priority` from the header logo (`header.tsx:44`) so only the hero image competes for preload priority | Perf (LCP) | LOW — one prop removal | Perf |
| 3 | Add `hover:`/`transition-*` classes to the 3 homepage service cards (`page.tsx:274-318`), matching the pattern already used on the emirate cards (`page.tsx:509`) | Visual/consistency, and closes a direct `CARDS.md` compliance gap | LOW | Visual / Design system |
| 4 | Correct `BrandPanel`'s card `sizes` attribute (`brand-panel.tsx:94`) from `50vw` to something closer to the real ~33vw desktop card width | Perf (avoids over-fetching larger image variants than needed) | LOW | Perf / Image usage |
| 5 | Reconcile the 6 hardcoded off-palette hex colors (`page.tsx:186`; `brand-panel.tsx:36-38,69`) with `COLORS.md`, either by adding them to the approved palette or replacing them with existing tokens | Design-system consistency | MEDIUM — touches visible section backgrounds and card gradients, needs an Owner/design decision on which is correct | Design system |
| 6 | Resolve the Arabic font-family mismatch between `TYPOGRAPHY.md` ("Cairo") and the implementation ("Noto Kufi Arabic", `layout.tsx:14-18`) — either update the doc to reflect an approved substitution, or swap the font | Visual identity / brand consistency, affects every Arabic page not just the homepage | MEDIUM — a live font swap has layout/line-height ripple effects across the whole site; needs deliberate QA | Design system |
| 7 | Restore a distinct tablet (2-column) step for the service-card grid per `GRID.md`, or update `GRID.md` if the current 1→3 jump is an intentional revision | Visual/layout consistency at tablet widths | LOW — one Tailwind class change, but should be visually re-checked at 768–1023px | Design system |
| 8 | Add mobile-specific card padding (16px) per `CARDS.md`, distinct from the current flat 24px used everywhere | Visual polish on small screens | LOW | Design system |
| 9 | Decide and document the Lucide-vs-custom-icon-set question (`icons.tsx:1-6` already flags this as a known, deliberate substitution) | Design-system-doc alignment; no visual change needed if the custom set stays | LOW (documentation-only) to MEDIUM (if a real migration to Lucide is later decided) | Icons |
| 10 | Add explicit `focus-visible:` treatment to homepage interactive elements (links, CTAs) rather than relying solely on browser defaults | Accessibility | LOW–MEDIUM | Accessibility |
| 11 | When Reviews/FAQ/Blog content is Owner-approved and populated, re-verify the homepage's visual balance — currently 3 of 11 sections are invisible in production today | Content/visual completeness | N/A — content governance decision, not a code fix | Content |
| 12 | Consider deleting the now-unused flat duplicate copies of `ac-maintenance-service-card-afaq-v1.webp` and the pest-control hero banner (already flagged in the prior 45-pair duplicate-image audit) once Owner approval for that broader cleanup is given | Disk hygiene, avoids future confusion about which copy is canonical | LOW, but gated on the existing pending approval for the broader duplicate-image cleanup | Image usage |

---

*End of audit. No files other than this report were modified. No commits were made.*
