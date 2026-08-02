# Homepage Foundation Alignment — Implementation Report

**Date:** 2026-08-01
**Scope:** `src/app/[locale]/page.tsx` and its dependencies in `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app`, compared against the owner's stated approved-foundation requirements.
**Method:** Full read of the current working tree (not just `git log`/`HEAD` — the repo has extensive uncommitted WIP layered on top of the last commit, and that WIP is what actually renders locally today). Every claim below is sourced to an exact file and line.

---

## Important context before the findings below

The owner's problem list was written against an expectation of the homepage's state. The working tree already contains a large amount of uncommitted work that changes several of those findings. This report corrects the record before proposing any implementation, so nothing gets rebuilt that already exists, and nothing gets silently skipped because it looked "already there" when it isn't actually wired up.

---

## 1. Current Missing Components

| Owner's claim | Verified current state | Real gap |
|---|---|---|
| "Brand service icons are missing" | No real gap in *rendering* — `src/components/icons.tsx` (377 lines, 36 inline-SVG components) already renders a service icon on every homepage service card (`page.tsx:289`, via `CATEGORY_BADGE_COLOR`/`section.Icon`). The gap is that these are **code-drawn icons, not real brand-designed icon image assets** — `public/brand/icons/` does not exist anywhere in the repo. | Real brand icon *artwork* (as files) does not exist yet — see §"Decisions needed" below. |
| "Location/emirate icons are missing" | Same situation — 7 emirate icons already render on the homepage (`page.tsx:489-518`, `MosqueDomeIcon`/`SkylineIcon`/etc.), but as inline SVG code, not real icon asset files. | Same as above. |
| "Booking form is missing" | **False as stated — a full booking form already exists.** `src/components/booking/booking-form.tsx` is a complete 5-step wizard (Service → Location/Property → Schedule/Problem → Customer → Summary) live at the `/book` route (`src/app/[locale]/book/page.tsx`), with every field the owner listed (name, phone, email, emirate, service category, preferred date, preferred time, notes) plus more (pest type, property type/size, file upload, contact-method preference). | The real gap: **this form is not linked from the homepage anywhere.** `grep` of `page.tsx` for `/book`, `BookingForm`, or booking-options returns zero matches. It also has no backend persistence yet (`submitBookingRequest()` is a 600ms `setTimeout` stub returning a fake `PREVIEW-XXXXXX` reference, `src/lib/booking/submit-booking-request.ts:89-140`) — the form itself is real, submission is not yet live. |
| CTA says "Request Service", should say "Book Appointment" | **No CTA on the homepage currently says "Request Service."** Homepage CTAs today are WhatsApp (`t.home.hero.secondaryCta` = "WhatsApp"/"واتساب") and Phone (`t.common.phone`), plus a closing "Contact us" CTA. Interestingly, `home.hero.primaryCta` = **"Book Now" / "احجز الآن"** already exists in both `en.json:92` and `ar.json:92` — but it is **completely unused** in any component (`grep -rn "primaryCta" src` finds only the two JSON definitions, no consumer). | See "Decisions needed" — there is a documented prior design reason the hero currently shows only 2 buttons, which this translation key's presence (but non-use) seems to contradict. |
| "Hero banner is not correctly adapted for desktop and mobile" | Confirmed — one single photo (`afaq-alhayat-home-services-hero-banner-uae-21x9.webp`) is used at every breakpoint via CSS `object-[80%_center]` only (`page.tsx:108-119`); no separate mobile crop/asset exists. `docs/HOMEPAGE_HERO_GENERATION_BRIEF.md:5` is explicitly labeled **"Status: Specification only. No image has been generated"** and, notably, doesn't even call for a mobile variant — only a single 21:9 asset. | Real gap, but the fix doesn't require new photography — see "Decisions needed." |
| "Homepage content, services, headings, and SEO sections are not yet implemented" | **False as stated.** The homepage already has 11 built sections: Hero, Trust bar, Services (3 category cards), How It Works, Why AFAQ AL HAYAT, About Us, Latest Articles, Reviews, FAQ, Service Areas (7 emirates), closing Contact CTA. SEO metadata (`src/lib/seo/metadata.ts`) is wired. Reviews/FAQ/Latest-Articles render nothing today only because their content registries (`VERIFIED_REVIEWS`, `APPROVED_FAQS`, `BLOG_POSTS`) are intentionally empty pending owner-approved real content — a deliberate no-fabrication hold, not an oversight. | The only structural gap versus the owner's requested list: there is no dedicated **"Booking section"** as its own homepage block (distinct from a CTA button). |

---

## 2. Existing Components That Need Replacement

**Nothing needs deleting or replacing.** Every existing homepage section, the icon components, and the booking form are real, working, and should be kept per "do not delete existing work." The work here is additive/wiring, not replacement:

- Add a homepage → `/book` link/CTA (currently absent).
- Add a dedicated Booking section to the homepage content flow.
- Decide what happens to the hero's current documented "exactly 2 CTA buttons" design rule (see below) now that a 3rd, booking-specific CTA is being requested.

---

## 3. Decisions Needed Before Full Implementation (flagging now, not guessing)

Two categories of this request touch things I can't safely resolve by code alone, consistent with this project's standing no-fabrication discipline (the same discipline that keeps `VERIFIED_REVIEWS`/`APPROVED_FAQS`/`BLOG_POSTS` empty until real approved content exists):

1. **Real brand/emirate icon artwork.** No such image assets exist anywhere in the repo (a small set of 8 unused legacy SVGs at `public/images/brand/icons/` — `service-request.svg`, `maintenance.svg`, `whatsapp.svg`, `trust.svg`, `phone.svg`, `location.svg`, `pest-control.svg`, `cleaning.svg` — sit orphaned, referenced by zero code, and don't cover "emirate" icons at all). Designing new "Luxury AFAQ AL HAYAT visual direction" icon artwork is a brand-identity decision, not a code task — I'm not going to invent and silently commit new brand iconography as if it were already approved. `icons.tsx`'s own top comment already flags this exact tension (Lucide/real icons vs. hand-drawn stand-in) as an unresolved, disclosed deviation.
2. **A real mobile-specific hero photo.** No mobile crop/asset exists, and the one hero generation brief on file doesn't call for one either. I can improve the *responsive handling* of the existing approved photo (a server-side re-crop for narrow viewports using the same source image, no new photography), but a true art-directed mobile shot would need either a real second source photo or an owner decision to proceed with a derived crop as "good enough."
3. **The hero's documented 2-button CTA rule.** `page.tsx:154-158`'s comment explicitly states the hero shows "exactly the 2 buttons the approved reference shows... not a 3rd generic contact button" as a past, deliberate design decision. The now-unused `primaryCta`/"Book Now" translation key suggests a booking CTA was originally planned and then intentionally dropped. Adding a prominent "Book Appointment" CTA per this instruction means consciously superseding that prior approved decision — flagging it rather than silently overriding a documented design choice.

I'm proceeding with everything below that doesn't depend on those three open questions, and will ask before touching the three above.

---

## 4. Files Expected to Change (safe portion, no new assets required)

| File | Change |
|---|---|
| `src/i18n/messages/en.json`, `ar.json` | Add/reuse booking-CTA and Booking-section copy keys (reusing existing `home.hero.primaryCta` = "Book Now"/"احجز الآن" where it fits; add a homepage Booking-section eyebrow/title/subtitle/button set). |
| `src/app/[locale]/page.tsx` | Add a homepage → `/book` link (as a new Booking section between Service Areas and the closing Contact CTA, per the owner's requested content order), reusing the existing `BookingForm`/`/book` route rather than duplicating it. |
| `src/lib/media/homepage-hero.ts` (or a new sibling module) | Add a server-derived mobile crop of the existing approved hero photo, if the owner confirms a derived crop (not new photography) is acceptable. |
| `public/brand/images/` | One new derived (not newly photographed) mobile hero asset, if approved per above. |

Nothing here deletes or replaces existing sections, the booking form, or the icon components.

---

## 5. Implementation Order

1. Resolve the three open decisions above with the owner (icons, mobile hero approach, hero CTA rule).
2. Add the homepage Booking section + CTA wiring to the existing `/book` route (no new form logic — reuse what's built).
3. If approved, generate the derived mobile hero crop from the existing approved source photo and wire responsive `<picture>`/art-direction.
4. If approved, stand up a `public/brand/icons/`-backed icon-loading path that falls back to the current `icons.tsx` components when no real asset file exists yet (same pattern already used for empty content registries) — so nothing regresses visually today, and real icon files can be dropped in later with no code change.
5. Re-verify desktop/tablet/mobile × EN-LTR/AR-RTL.
6. Run lint, typecheck, tests, build.
7. Report files changed, preview status, and remaining gaps. No commit.

---

*This report reflects the working tree as of 2026-08-01. No code was changed in producing it.*
