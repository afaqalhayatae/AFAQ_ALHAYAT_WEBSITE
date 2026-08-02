# Homepage Content Implementation Plan

**Date:** 2026-08-01
**Status:** Planning only. No application code, components, pages, assets, images, or translations were modified in producing this document.
**Scope:** AFAQ AL HAYAT — Maintenance & Cleaning & Pest Control, UAE. Content plan for the homepage only.
**Method:** Built entirely from documents already in this repository. Every fact below is cited to its source file with its actual approval status. Where two approved-looking sources disagree, this plan states the conflict explicitly rather than picking a side — per this repo's own Answer Policy ("do not merge conflicting sources, flag the conflict").

---

## 0. Critical Conflict — Must Be Resolved Before Service-Card Copy Is Written

**`04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`** (updated 2026-07-31) states that Pest Control, AC Maintenance, General Cleaning, and Deep Cleaning content is Owner-approved for publication, citing `00_GOVERNANCE/DECISION_LOG.md` decisions #37–#38 and a `SERVICE_COMPLETION_MATRIX.md` said to live in a sibling repo (`afaqalhayatae-app`).

Every individual package file inside those four services' own folders (`README.md`, `CONTENT_EN.md`, `CONTENT_AR.md`, `FAQ.md`) still carries the older status: *"Review Required — Not Approved for Publication,"* *"Draft — Not Approved for Publication,"* or *"Answers Pending Owner Approval."*

The `afaqalhayatae-app` repo referenced as the source of truth for the newer approval was not found on this machine, so this plan cannot independently verify which status is current. **This is not resolved here.** Section 9 (Content Gaps) restates it as the single highest-priority open item. Until the owner confirms which side is current, this plan only uses the small set of service facts that are consistent regardless of which status wins (see §3).

---

## 1. Homepage Content Structure

Final section order, reconciling the owner's required section list with what the current homepage already builds structurally (`src/app/[locale]/page.tsx`) and with the in-review `07_WEBSITE/01_HOMEPAGE/00_HOMEPAGE_ARCHITECTURE.md` (Status: *In Review / Not for Implementation*):

| # | Section | Purpose | User Intent | Content Requirements | Arabic Direction | English Direction |
|---|---|---|---|---|---|---|
| 1 | **Hero** | Establish brand + one dominant action | "What is this company and how do I start?" | Headline, subtitle, primary CTA (Book Appointment), secondary actions (WhatsApp, Call). No stats, no unverified claims. | Warm, respectful, direct — see §8 | Modern, professional, direct — see §8 |
| 2 | **Trust bar (compact facts)** | Quick, factual reassurance | "Is this a real, reachable business?" | Only approved, non-numeric facts: UAE-wide coverage, real contact channels, professional service positioning. No "X years," no counts. | Same tone, same facts | Same tone, same facts |
| 3 | **Services overview (Maintenance / Cleaning / Pest Control)** | Explain the 3 core categories | "Do they do what I need?" | Category name, one short description each, link to category hub. See §3. | Per-category, see §3 | Per-category, see §3 |
| 4 | **How it works** | Reduce booking friction | "What happens after I click Book?" | Simple 3–4 step process (book → confirm → visit → done), no promised timeframes | Short, numbered, plain | Short, numbered, plain |
| 5 | **Why choose AFAQ** | Differentiate on real, approved grounds | "Why this company over another?" | Only brand-voice/positioning language and approved process facts — no invented awards/certifications/ratings | See §5 | See §5 |
| 6 | **About / company introduction** | Build legitimacy | "Who is behind this?" | Mission/vision language already approved by cross-reference (§5) | See §5 | See §5 |
| 7 | **Emirates coverage** | Show geographic relevance | "Do they serve my area?" | All 7 emirates, equal footing, no city-level claims beyond the approved Priority Community Registry | See §4 | See §4 |
| 8 | **Booking section** | Convert intent into a booking | "How do I actually book?" | Heading, description, link to the real `/book` flow — see §6 | See §6 | See §6 |
| 9 | **Reviews / testimonials** | Social proof | "Can I trust other customers' experience?" | **No approved reviews exist anywhere in the repository.** Section must render hidden/empty until real, consented, verifiable reviews exist — never invented. | N/A until content exists | N/A until content exists |
| 10 | **FAQ** | Pre-empt common questions | "What do I need to know before booking?" | **No approved FAQ answers exist for the homepage's general questions or for Pest Control/Maintenance/Cleaning specifically** (see §0, §9). Section stays empty/hidden until real approved Q&A exists. | N/A until content exists | N/A until content exists |
| 11 | **Latest articles / blog** | SEO + engagement | "Does this company know what it's doing?" | No approved blog posts exist yet (matches the existing empty `BLOG_POSTS = []` pattern) | N/A until content exists | N/A until content exists |
| 12 | **Closing contact CTA** | Final conversion opportunity | "One more easy way to reach them" | Real approved contact channels only (phone, WhatsApp, contact form) | Direct, warm | Direct, clear |

This order matches the already-approved-in-principle "empty registry until approved content" pattern already implemented in the current homepage (`page.tsx`) for Reviews/FAQ/Blog, and matches the section list in `01_HOMEPAGE_ARCHITECTURE.md` (In Review) reordered so Emirates coverage precedes Booking, per the Owner's prior explicit instruction on this exact reordering (Homepage Foundation Alignment ticket).

---

## 2. Hero Content Plan

**Primary CTA (fixed, owner-specified):** "Book Appointment" / "احجز موعد" — already implemented on the homepage.
**Secondary actions (fixed):** WhatsApp, Call — already implemented, using the Approved contact channels (`02_BRAND/CONTACT_INFORMATION.md`).

**Headline & subtitle — DRAFT direction only, not final approved copy** (no headline/subtitle exists anywhere in this repo marked Approved; the closest reference is `07_WEBSITE/01_HOMEPAGE/01_HOMEPAGE_CONTENT.md`, itself Status: *In Review / Not for Publication*):

- **Headline direction:** State the three core categories and UAE-wide reach plainly, without superlatives. Example shape (draft, needs owner sign-off): *"Reliable Maintenance, Cleaning & Pest Control — Across the UAE."* Mirrors the approved tagline "Reliable Service. Professional Results." (`02_BRAND/BRAND_IDENTITY.md`) without adding unapproved claims.
- **Subtitle direction:** One supporting sentence naming the audience and the booking action, no promised response time. Example shape (draft): *"Professional technicians for your home or business — book online in minutes."* ("Book online in minutes" describes the booking flow's mechanics, not a service-delivery time promise — safe to keep; avoid anything implying same-day/emergency arrival, since emergency-service availability is still Pending per `02_BRAND/CONTACT_INFORMATION.md`.)

**Rules applied:**
- Luxury professional tone, no exaggerated claims — per `02_BRAND/BRAND_VOICE.md` ("avoid exaggerated promises, aggressive sales language") and `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §2 ("Evidence Before Claims").
- No numbers, no "years of experience," no "trusted by X customers" — none are approved anywhere (§9).
- Suitable for the UAE market: UAE-specific framing (Emirates, Arabic-first) without naming unapproved cities/districts.

---

## 3. Services Section (Maintenance / Cleaning / Pest Control)

**Reminder: §0's conflict applies to all three of these.** The descriptions below are the specific facts the research identified as consistent regardless of which side of that conflict is current — i.e., safe to plan around, but still pending final owner confirmation before publication.

### Maintenance
- **Section title:** "Maintenance" (`t.services.sections.maintenance.name` already exists in the app).
- **Short description:** No approved descriptive copy exists for AC Maintenance (the category's representative sub-service) — `02_AC_MAINTENANCE/CONTENT_EN.md` explicitly defers all customer-facing description language as "Pending Owner Input." **This is a genuine content gap**, not just a status dispute — restated in §9.
- **Service card purpose:** Route to `/services/maintenance`, represent the category via its highest-content sub-service (AC Maintenance) per the existing card/photo pattern.
- **Required supporting text:** Needs owner-authored (or owner-approved) short description before this card can carry real copy beyond the bare category name.

### Cleaning
- **Section title:** "Cleaning."
- **Short description (consistent across both sides of §0's conflict):** *"Routine cleaning for agreed residential and commercial areas, delivered through a clearly defined scope, controlled process, and documented quality check"* (`03_GENERAL_CLEANING/CONTENT_EN.md`), explicitly excluding deep cleaning, hazardous materials, work at height, and pest control unless separately scoped.
- **Service card purpose:** Route to `/services/cleaning`, representing General Cleaning + (once scoped) Deep Cleaning.
- **Required supporting text:** The General Cleaning description above is usable as a draft; **Deep Cleaning has zero approved scope or description** — `04_DEEP_CLEANING` is "blocked entirely... no scope has been defined by the owner" (§9).

### Pest Control
- **Section title:** "Pest Control."
- **Short description (consistent across both sides of §0's conflict):** *"AFAQ Alhayat provides professional pest control services using safe, approved, and effective treatment methods to protect homes, businesses, and industrial facilities from all types of pests"* (`01_PEST_CONTROL/CONTENT_EN.md`).
- **Service card purpose:** Route to `/services/pest-control`, representing the 7 covered pest types (cockroach, ant, bed bug, rodent, termite, mosquito, fly — plus fleas per the FAQ).
- **Required supporting text:** The description above is the most usable of the three category summaries today — still gated on §0's conflict being resolved before treating it as publication-ready.

**Cross-cutting rule for all three:** no claim of "certified," "licensed," "guaranteed," "fast response," or "municipality-compliant" without separate evidence — `01_PEST_CONTROL/01_SERVICE_PROFILE.md` explicitly flags these exact phrases as **not** approved benefits today.

---

## 4. Emirates Coverage Section

**Source:** `03_MARKET/SERVICE_AREAS.md` — Status: *"Approved at emirate level; lower-level areas pending,"* verified 2026-07-23.

All 7 emirates are confirmed Active with full catalog coverage, on equal footing (no "primary vs. future expansion" tiering — that framing exists only in the outdated `01_BUSINESS/TARGET_AUDIENCE.md` and must not be used for the homepage; see the conflict noted in §9).

| Emirate | Card purpose | SEO intention | Local content requirements |
|---|---|---|---|
| Abu Dhabi | Confirm coverage, link to location hub | Emirate-level location entity (per `03_HOMEPAGE_SEO_AI.md`, Status: Build Phase) | No city/district copy beyond approved Priority Community Registry (e.g. Saadiyat Island, Yas Island — Tier 1/2) |
| Dubai | Same — Dubai is the only emirate with a live built location page today (`13_LOCATION_EXPANSION_ROADMAP.md`) | Same | Approved communities: Palm Jumeirah, Downtown Dubai, Dubai Marina (Tier 1), others Tier 2/3 |
| Sharjah | Same | Same | Approved: Al Zahia, Aljada (Tier 1/2) |
| Ajman | Same | Same | Approved: Al Zorah and others (Tier 2) |
| Umm Al Quwain | Same | Same | Tier 3 — minimal approved community-level detail |
| Ras Al Khaimah | Same | Same | Approved: Al Marjan Island and others (Tier 2) |
| Fujairah | Same | Same | Tier 3 ("Test" status per the registry) — minimal approved community-level detail |

**Rules:** no district/community claim outside the approved Priority Community Registry; no implied same-day/emergency availability; every card's coverage claim must be paired with the source document's own caveat that coverage does not guarantee a specific date/time booking slot. `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §6 explicitly bans "mass-produced copies with only the place name changed" — each emirate card needs at least its own approved community references, not a single templated paragraph with the name swapped.

---

## 5. Trust / Company Section

**Why choose us / trust signals — only what's actually approved:**
- Brand promise language: *"Professional Service. Trusted Technicians. Fast Response. Guaranteed Quality"* (`02_BRAND/BRAND_IDENTITY.md`) — use as brand-voice/tagline language, not as a literal warranty or SLA claim (a literal "guaranteed" or "fast response" service promise is not evidenced anywhere and would conflict with `LUXURY_DESIGN_DIRECTION.md` §2/§10's ban on unsupported guarantees).
- Personality traits safe to reflect in tone: Professional, Trustworthy, Modern, Friendly, Reliable, Efficient, Premium, Customer-Focused.
- Process-based trust (safe, since it's operational fact, not a numeric/certification claim): the real booking flow (inspection/quotation before work begins, per `06_CUSTOMER_AND_SALES/CUSTOMER_SUPPORT/GENERAL_SERVICE_FAQ_DRAFT.md`'s two answered questions).

**Company introduction — approved:**
- Mission: *"To provide reliable, professional, and high-quality maintenance, cleaning, and pest control services that exceed customer expectations while ensuring safety, efficiency, and long-term value"* (`01_BUSINESS/MISSION.md`).
- Vision: *"To become one of the leading maintenance, cleaning, and pest control companies in the United Arab Emirates by delivering exceptional quality, innovative solutions, and outstanding customer experiences"* (`01_BUSINESS/VISION.md`).
- Company overview: *"AFAQ Alhayat is a professional maintenance and cleaning company dedicated to delivering high-quality residential and commercial services. The company combines experienced technicians, modern equipment, and customer-focused solutions..."* (`01_BUSINESS/COMPANY_PROFILE.md`).

**Explicitly excluded — do not invent, ever, per `00_GOVERNANCE/CURRENT_PROJECT_STATUS.md`'s Hard Publication Blocks and confirmed by exhaustive search (§9):**
- No years-in-business figure.
- No certification/license claim.
- No completed-jobs or customer count.
- No star rating or review count.
- No named staff/team beyond the single owner (never imply a "team" of named employees — `00_GOVERNANCE/DECISION_LOG.md` #20).

---

## 6. Booking Section

**Heading direction:** "Book Appointment" (already the approved wording, per the Owner's explicit instruction in the prior Booking Foundation ticket — never "Request Service").
**Description direction:** Plain, action-oriented — invite the visitor to pick a service, emirate, and time; no promised confirmation speed beyond what's true today (the booking form is real but not yet connected to automatic staff notification — see the existing `BookingSubmissionResult` architecture already implemented).
**Form purpose:** Capture name, phone, email (optional), emirate, service category, preferred date/time, notes — matches the already-implemented `BookingRequestPayload` shape.
**User journey:** Homepage → "Book Appointment" (hero or dedicated section) → `/book` wizard (service → location/property → schedule → customer → summary) → confirmation with a real reference number → (today) owner must also be reached by WhatsApp/phone to guarantee timely follow-up, since automatic staff notification isn't wired up yet — this caveat should stay visible in the booking confirmation copy until that changes.

---

## 7. SEO Content Planning

**Primary/secondary keywords:** **None exist as approved, researched targets anywhere in this repository.** `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` states this outright: *"No real keyword-volume, ranking, competitor, or search-demand data exists anywhere in this repository, and none is fabricated here... Every keyword shown is an illustrative, structurally-derived candidate... not a validated target."* This plan does not invent keyword targets either. Structural entities that are safe to build around (from `03_HOMEPAGE_SEO_AI.md`, Status: Build Phase): AFAQ Alhayat (brand), Pest Control, Cleaning Services, Facility Management, Water Tank Cleaning, Disinfection, and all 7 emirates as location entities.

**Homepage title/meta description direction:** No approved copy exists. Direction only: brand name + the 3 core categories + "UAE," following `URL_AND_INTERNAL_LINKING_STANDARD.md`'s structural rules (primary keyword once, natural phrasing) — actual title/description text needs owner review before use, per `99_STANDARDS/QUALITY_CHECKLIST.md`.

**Internal linking opportunities (this part IS on solid ground — `URL_AND_INTERNAL_LINKING_STANDARD.md`, Status: *Active for architecture*):**
- Homepage → service category hubs (`/services/maintenance`, `/services/cleaning`, `/services/pest-control`) → individual service pages.
- Homepage → emirate location pages (Dubai live today; others per `13_LOCATION_EXPANSION_ROADMAP.md`).
- Homepage → `/book` (booking flow).
- Homepage → trust/about page.
- Service pages → related services + relevant locations + booking, generated from the catalog/service-area registry, never hand-authored per page.

---

## 8. Arabic-First Strategy

**RTL content considerations:** Arabic and English are equal first-class languages per `99_STANDARDS/DOCUMENTATION_STANDARD.md`'s bilingual-content rule — paired content must express the *same facts*, phrasing can differ. The homepage's existing hero already handles a documented RTL exception correctly (photo-composition bias is a property of the image, not of reading direction — text alignment still follows locale). This plan does not require any change to that existing, working pattern.

**Arabic wording quality requirements (`02_BRAND/BRAND_VOICE.md`):** professional, warm, respectful, easy to read; avoid overly formal classical Arabic that feels distant, and avoid overly casual dialect; match the same no-exaggeration, no-unsupported-claim discipline as English.

**English adaptation rules:** modern, professional, friendly, direct; not a literal word-for-word translation of the Arabic — same facts, natural English phrasing. Every content requirement in §§1–7 above applies identically to both languages; neither language gets a claim the other doesn't have.

---

## 9. Content Gaps

**Missing approvals:**
1. **§0's conflict** — Pest Control / AC Maintenance / General Cleaning / Deep Cleaning: catalog-level "Approved" claim vs. package-level "Draft/Review Required" status disagree; the resolving evidence (`afaqalhayatae-app` repo's `SERVICE_COMPLETION_MATRIX.md`) isn't accessible. **Highest priority — resolve before writing any service-card copy beyond the bare category name.**
2. Company headquarters/address: `01_BUSINESS/COMPANY_PROFILE.md` still says "Owner Verification Required"; `02_BRAND/LOCAL_SEO_PROFILE.md` says the same address is Approved (verified 2026-07-27). Needs reconciliation.
3. Geographic priority framing: `01_BUSINESS/TARGET_AUDIENCE.md`'s "primary vs. future expansion" language for emirates is superseded by `03_MARKET/SERVICE_AREAS.md`'s all-seven-equal Active status, but the older document hasn't been formally updated/retired.
4. `99_STANDARDS/QUALITY_CHECKLIST.md` is still Draft, not yet a formally approved hard release gate.

**Missing business facts:**
- No years-in-business figure.
- No certification/license identifiers.
- No completed-jobs, customer, or technician count.
- No verified response-time or emergency-service commitment (explicitly Pending).
- Exact Google Business Profile listing name, branch structure, coordinates, and Place ID (Pending per `02_BRAND/LOCAL_SEO_PROFILE.md`) — blocks full `LocalBusiness` schema, not the address itself.

**Missing images:** Not directly re-audited in this research pass — see the separate, already-existing `HOMEPAGE_VISUAL_IMPLEMENTATION_AUDIT.md` and `MISSING_SERVICE_IMAGES_REPORT.md` for the current image-gap inventory (Handyman and Bed Bug Control both lack dedicated card images as of the last audit).

**Missing testimonials/reviews:** None exist anywhere in the repository. No provenance, consent, or verifiable source has been established for any review. The homepage Testimonials section must stay hidden/empty until real, verifiable reviews exist — never invented, per `LUXURY_DESIGN_DIRECTION.md` §5 and the Hard Publication Blocks list.

**Missing FAQ content:** No approved general-company FAQ exists (`GENERAL_SERVICE_FAQ_DRAFT.md` is Draft/Blocked, with only 2 of its questions actually answered). No approved per-service FAQ exists for Pest Control, AC Maintenance, General Cleaning, or Deep Cleaning (all Draft/Review-status, and gated further by §0's conflict). The homepage FAQ section must stay hidden/empty until real approved Q&A exists for at least the general-company track.

---

## 10. Implementation Roadmap

**Phase 1 — Homepage content**
- Resolve §0's service-content conflict with the owner.
- Reconcile the address/headquarters conflict (§9.2).
- Finalize hero headline/subtitle wording (draft direction in §2) with owner sign-off.
- Write real Maintenance category description (currently has none) and confirm Cleaning/Pest Control descriptions once §0 is resolved.
- Keep Reviews/FAQ/Blog sections empty until real approved content exists — no timeline dependency, purely content-availability-gated.

**Phase 2 — Service pages**
- Build out full page content per service once §0's conflict is resolved and each package's real approval status is confirmed individually.
- Prioritize per `07_WEBSITE/IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md`'s existing sequencing (re-verified against current statuses first, since that document predates the 2026-07-31 decisions).

**Phase 3 — Location pages**
- Dubai already has a live page; build the remaining 6 emirates per `13_LOCATION_EXPANSION_ROADMAP.md`, respecting the ban on templated place-name-swap copies and using only the approved Priority Community Registry per emirate.

**Phase 4 — SEO expansion**
- Commission real keyword research (none exists today) before setting any target keyword.
- Finalize homepage/service meta title-description copy once underlying content is approved.
- Build out the internal linking graph per `URL_AND_INTERNAL_LINKING_STANDARD.md` as pages go live.
- Revisit schema markup once the Local SEO Pending items (GBP listing name, Place ID, coordinates) are resolved.

---

## Consistency Check Against Existing Governance Decisions

Cross-checked against `00_GOVERNANCE/DECISION_LOG.md` in full:
- **Consistent** with decision #1 (`COMPANY_PROFILE.md` canonical for identity), #17 (all-7-emirates coverage, emirate-level only), #18 (Priority Community Registry), #19 (Drain Unblocking/Waterproofing/Water Leak Detection scope limits), #20 (owner is the only internal human, never invent staff), #35 (`12_DESIGN_SYSTEM/COLORS.md` as the implementation color source — not directly relevant to content but not contradicted here).
- **Explicitly surfaces, rather than silently resolves,** the tension in decisions #37–#39 (service-content approval) against the package-file statuses — see §0 and §9.1.
- **Does not rely on** decision #36's photography direction (out of scope for a content-only plan) beyond noting it exists.
- Confirms and extends the existing "empty registry until approved content" pattern (Reviews, FAQ, Blog) already implemented in the current homepage — no change requested to that pattern, only reaffirmed as this plan's model for handling missing content.

No governance decision was contradicted by this plan. Where two governed sources disagreed with each other (not with this plan), the disagreement is reported to the owner rather than resolved unilaterally.

---

## Report

- **File created:** `00_GOVERNANCE/HOMEPAGE_CONTENT_IMPLEMENTATION_PLAN.md` (this document).
- **Documents referenced:** `02_BRAND/BRAND_IDENTITY.md`, `BRAND_VOICE.md`, `CONTACT_INFORMATION.md`, `LOCAL_SEO_PROFILE.md`, `BRAND_CHECKLIST.md`; `01_BUSINESS/COMPANY_PROFILE.md`, `MISSION.md`, `VISION.md`, `TARGET_AUDIENCE.md`; `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `SERVICE_MASTER_DATABASE.md`, and the `01_PEST_CONTROL`, `02_AC_MAINTENANCE`, `03_GENERAL_CLEANING`, `04_DEEP_CLEANING` package folders; `03_MARKET/SERVICE_AREAS.md`; `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md`; `99_STANDARDS/QUALITY_CHECKLIST.md`; `09_AI_KNOWLEDGE/ANSWER_POLICY.md`, `AI_SYSTEM_PROMPT.md`; `10_MARKETING_AND_SEO/SEO_STRATEGY.md`, `LOCAL_SEO.md`, `SCHEMA_STRATEGY.md`, `URL_AND_INTERNAL_LINKING_STANDARD.md`, `CONTENT_STRATEGY.md`, `LANDING_PAGE_STANDARD.md`; `00_GOVERNANCE/DECISION_LOG.md`, `CURRENT_PROJECT_STATUS.md`, `CONTACT_INFORMATION_DECISION_UPDATE.md`; `07_WEBSITE/IMPLEMENTATION/04_CONTENT_INTEGRATION_PLAN.md` through `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`; `07_WEBSITE/01_HOMEPAGE/00_HOMEPAGE_ARCHITECTURE.md` through `04_HOMEPAGE_COMPONENTS.md`; `06_CUSTOMER_AND_SALES/CUSTOMER_SUPPORT/GENERAL_SERVICE_FAQ_DRAFT.md`.
- **Content gaps found:** see §9 in full (service-content approval conflict, address/headquarters conflict, geographic-framing conflict, no approved numeric/certification facts, no approved reviews, no approved FAQ content, incomplete Local SEO schema inputs).
- **No implementation performed.** No application code, components, pages, assets, images, or translations were modified.

Not committed, not pushed. Stopping here as instructed.
