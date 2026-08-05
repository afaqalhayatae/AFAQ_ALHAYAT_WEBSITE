# Photography Production Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — production backlog, not yet sourced
- **Version:** 1.0
- **Prepared:** 2026-08-05

## Purpose

A precise shot list for every real photograph the live website (`afaqalhayatae-app`) is
still missing, found by tracing every hero/card image slot in the actual code back to
whether a real photo is wired in. This is the *complete* list — every other image slot
in the app already has one (see `00_GOVERNANCE/AFAQ_ROADMAP_EXECUTION_STATUS.md`,
Production Completion Pass and Visual Production Pass entries, 2026-08-05). This
document defines what to shoot; it does not itself add or approve any factual claim
about the business (see [`BRAND_IMAGES.md`](BRAND_IMAGES.md) for the general style
policy this plan applies).

---

## Style Requirements (every shot)

- **Format:** 21:9 wide crop, minimum 1920×822px source (matches the homepage hero and
  both existing category hero banners already live in the codebase).
- **No text baked into the image.** Photography only — no captions, taglines, or slogans
  rendered into the pixels. **This is not a stylistic preference — it is why one existing
  candidate photo (Waterproofing's) was rejected**: the source generation baked in a
  uniform-text typo ("MAINTTNANCE ANDD CLEANLINESS") that isn't fixable without
  re-shooting/re-generating the source, because there's no image-editing tooling in
  this environment. Any brand wordmark that appears incidentally (e.g. on a uniform,
  as in the existing approved photos) must be legible and correctly spelled — verified
  before delivery, not after wiring into code.
- **No fake claims.** A photo must not depict anything not true of the business:
  no fabricated certifications/badges, no equipment or scenes implying a service AFAQ
  AL HAYAT doesn't offer, no skyline or landmark that ties the shot to one specific
  emirate unless the shot is *for* that emirate (see Location Heroes below — this is
  exactly why the existing homepage hero, which has a Dubai skyline, can't be reused
  generically across all 7 emirate pages).
- **Premium UAE service-brand style**, matching the existing approved photo set:
  bright, clean, high-resolution, real AFAQ AL HAYAT branded uniform/equipment,
  UAE villa or premium-residential settings, natural light.
- **Consistent visual identity** with what's already live: same navy uniform, same
  AFAQ AL HAYAT logo placement (back of shirt / cap), same premium-villa production
  value as the existing approved service-card photos
  (`public/brand/images/services/*.webp`).

---

## Shot List

### A. Emirate Location Heroes (7 shots — highest priority)

Every emirate hub page (`/locations/dubai`, `/locations/abu-dhabi`, etc. — all 7 build
and are live today) and the `/locations` index page currently show a generic brand
illustration instead of a photo, because the only existing real hero photo
(`afaq-alhayat-home-services-hero-banner-uae-21x9.webp`) has a **visible Dubai skyline**
in it — using it on the Abu Dhabi or Sharjah page would visually misrepresent which
emirate the page is about.

| # | Slug | Subject | Notes |
|---|---|---|---|
| 1 | `dubai` | AFAQ technician at a premium Dubai villa/community | May reuse the *existing* Dubai-skyline hero if a fresh crop works — this is the one emirate that photo is actually correct for. |
| 2 | `abu-dhabi` | AFAQ technician at a premium Abu Dhabi villa | No Dubai skyline or landmark. Generic premium-villa setting, or a real Abu Dhabi landmark only if genuinely shot there. |
| 3 | `sharjah` | AFAQ technician, Sharjah setting | Same rule — no other-emirate landmark. |
| 4 | `ajman` | AFAQ technician, Ajman setting | |
| 5 | `umm-al-quwain` | AFAQ technician, Umm Al Quwain setting | |
| 6 | `ras-al-khaimah` | AFAQ technician, Ras Al Khaimah setting | |
| 7 | `fujairah` | AFAQ technician, Fujairah setting | |

**Practical fallback if 7 unique shoots aren't feasible immediately:** one genuinely
generic UAE-villa photo with **no identifiable skyline or landmark at all** (interior
shot, or an exterior with no city-identifying background) can safely serve all 7 pages
at once — it just can't be the current Dubai-skyline photo. That single generic shot
would unblock all 7 pages in one delivery; the per-emirate set above is the enhancement
once that exists.

**Integration:** each photo becomes `public/brand/images/locations/<emirate-slug>-hero-
21x9.webp`; wiring is a small code change to `locations/[slug]/page.tsx` and
`locations/page.tsx` (currently hard-coded to the illustration branch — see
`AFAQ_ROADMAP_EXECUTION_STATUS.md`), plus real alt text per photo (English + Arabic).

### B. Waterproofing Service Card (1 shot — replacement)

`SERVICE_DATABASE.json`'s `waterproofing` entry already documents the rejection:
*"Rejected 2026-07-31 — the only candidate card image has a baked-in AI-rendering typo
('FOR MAINTTNANCE ANDD CLEANLINESS' on the technician's uniform)."* Content and SEO for
this service are already Owner-approved (`DECISION_LOG #38`) — only the photo is
missing.

- **Subject:** AFAQ technician applying/torch-welding a waterproofing membrane on a
  villa rooftop (same scene as the rejected candidate — roof waterproofing membrane
  application is accurate to the service; the technician's back should not carry any
  small-print tagline text, or it must be verified letter-by-letter before delivery).
- **Format:** matches the existing card-image aspect ratio (`services/*.webp`, ~4:3
  crop source, same as `ac-maintenance-service-card-afaq-v1.webp`).
- **Integration:** `SERVICE_DATABASE.json` → `waterproofing.cardImage` (field already
  exists on sibling services — see `ac-maintenance` for the exact shape to match).

### C. Maintenance Section Hero (1 shot — for a page that doesn't exist yet)

Cleaning and Pest Control each already have a real, approved 21:9 branded hero banner
sitting in the asset library (`cleaning-services-hero-banner-afaq-branded-21x9-v1.webp`,
`pest-control-hero-banner-afaq-branded-21x9-v2.webp` — both now wired into
`city-page-content.tsx` as of this pass). Maintenance has no equivalent. The pages that
would use it (`services/maintenance/city/[city]`) generate zero live URLs today because
`city-content.ts` has no section-level entries yet — so this is a "have it ready before
that content ships" item, not an active gap on a live page.

- **Subject:** AFAQ technician performing general maintenance work (AC unit, electrical,
  or plumbing — whichever is most representative) in a premium UAE home, matching the
  cleaning/pest-control banners' composition and lighting.
- **Integration:** `public/brand/images/services/maintenance/maintenance-services-hero-
  banner-afaq-branded-21x9-v1.webp`, added to `SECTION_HERO_IMAGES` in
  `city-page-content.tsx`.

### D. About Page Hero (1 shot)

`about/page.tsx`'s hero `BrandPanel` never receives a `src` at all — every other major
page (home, services, locations, blog) has at least a conditional path to a real photo;
About is the one page with zero code path to one. `BRAND_IMAGES.md` itself lists
"About Us" and "Team" as recommended real-photo sections.

- **Subject:** team or founder photo, or a genuine company/office/vehicle shot — real
  people/assets, not a staged generic stock scene (per `BRAND_IMAGES.md`'s "Preferred
  Photography" list: team members in uniform, service vehicles).
- **Integration:** `about/page.tsx`'s single unconditional `<BrandPanel icon={...} />`
  call gains a `src`/`alt` once a photo exists.

---

## Explicitly Out of Scope

The 11 newer services (CCTV installation, smart home installation, swimming pool
maintenance, kitchen installation, interior decoration, interlock installation,
lighting maintenance, wood-alternative installation, wallpaper installation, thermal
insulation, rooftop space utilization) are **not** part of this plan. Each one's own
`04_SERVICE_KNOWLEDGE/*/FOUNDATION.md` explicitly marks itself Draft, not Owner-approved
for publication, and not yet wired into `SERVICE_DATABASE.json` — photography for a
service that isn't approved to publish yet would be premature spend. Revisit this list
once each service clears that gate.

---

## Delivery & Integration Process

1. Photo delivered as WebP (or high-quality JPG/PNG, per `BRAND_IMAGES.md`), matching
   the format/aspect ratio column above.
2. Before wiring: read the image and check uniform/equipment text for legibility and
   correct spelling — the one defect this codebase has actually hit was exactly this,
   not a composition or lighting problem.
3. File placed under `public/brand/images/...` following the existing
   `<purpose>-<context>-v<N>.webp` naming convention (`99_STANDARDS/NAMING_CONVENTIONS.md`).
4. Real, accurate bilingual alt text written describing what's literally in the frame —
   no invented claims about licensing, certification, or service scope.
5. Wired into the specific code location named per shot above; typecheck/lint/tests/
   build run before commit (same verification bar as every other change to this app).

---

## Related Documents

- [`BRAND_IMAGES.md`](BRAND_IMAGES.md) — general brand image style policy.
- `00_GOVERNANCE/AFAQ_ROADMAP_EXECUTION_STATUS.md` — Production Completion Pass and
  Visual Production Pass sections, tracking what's already fixed vs. what this plan
  covers.

---

End of Document
