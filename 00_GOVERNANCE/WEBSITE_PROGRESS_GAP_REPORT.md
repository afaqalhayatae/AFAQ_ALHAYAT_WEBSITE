# Website Progress & Gap Report

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — read-only audit, requires Owner review
- **Version:** 1.0
- **Prepared:** 2026-08-02
- **Audited target:** `~/Documents/GitHub/afaqalhayatae-app` (local path, separate repository per `07_WEBSITE/IMPLEMENTATION/00_PHASE1_APPROVAL.md` decision #3)
- **Method:** Read-only. No file in the application repository was modified, staged, or committed. The application's own `next dev` server (already running, PID `48882`, started 05:05:38 today) was left untouched — not restarted, not stopped. All findings below come from reading source files and requesting pages from that already-running server.

**Context:** This audit was requested while the application repository has an actively running dev process and ~100 uncommitted, in-progress files (booking flow, new pest-control/cleaning/maintenance pages, city-page scaffolding, announcement bar, new hero imagery). This report describes what that in-progress state actually contains right now — it is a snapshot, not a final verdict, and will be stale the moment the in-progress work is committed.

---

## 1. Live Page-by-Page Check (requested in browser against `localhost:3000`)

All routes below returned **HTTP 200** on the Arabic (`/ar`, default, RTL) locale once the dev server finished compiling each route (first requests to several routes timed out at 8s under compile load — not a defect, just cold-compile latency; all resolved to 200 on retry with a longer timeout).

| Page | Route | Status | Notes |
|---|---|---|---|
| Homepage | `/ar` | ✓ 200 | Renders |
| About | `/ar/about` | ✓ 200 | Renders |
| Services (index) | `/ar/services` | ✓ 200 | 23 service cards linked (see §2) |
| Services (category hubs) | `/ar/services/maintenance`, `/ar/services/cleaning`, `/ar/services/pest-control` | ✓ 200 | All three render |
| Service detail | `/ar/services/pest-control/cockroach-control` | ✓ 200 | Full content renders |
| Service + legacy location | `/ar/services/ac-maintenance/dubai` | ✓ 200 | Legacy `[slug]/[location]` pattern still resolves |
| Locations (index) | `/ar/locations` | ✓ 200 | Only Dubai is a clickable link; the other 6 emirates appear as plain (non-linked) names |
| Location detail | `/ar/locations/dubai` | ✓ 200 | Renders |
| Blog (index) | `/ar/blog` | ✓ 200 | Renders an **empty state** — "لا توجد" (no articles) — zero posts exist |
| Blog post | `/ar/blog/[slug]` | Not tested | No published slug exists to test against (registry is empty, see §2) |
| FAQ | `/ar/faq` | ✓ 200 | Renders |
| Contact | `/ar/contact` | ✓ 200 | Renders |
| Booking | `/ar/book` | ✓ 200 | Renders |

No route returned a real error (4xx/5xx) in this pass.

---

## 2. Requirement-by-Requirement Comparison

### "60 service structure"
**No canonical document in either repository specifies an exact figure of 60.** I searched `07_WEBSITE/IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md`, `13_LOCATION_EXPANSION_ROADMAP.md`, `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`, and the app's own `docs/SERVICE_COMPLETION_MATRIX.md` and found no "60" reference. Flagging this rather than guessing which combination (services × cities, or a different count) "60" was meant to describe — this should be clarified with whoever set that number so it can be checked against something real.

What actually exists: **27 catalog services**, added in three approved phases (`DECISION_LOG.md` #38, #39):
- 16 "original scope" services (12 original + 4 Cleaning) — **content-complete**: 14 fully complete (content + image + SEO), 2 (Handyman, Waterproofing) content-complete but missing a card photo by an explicit, logged Owner decision.
- 11 Pest Control sub-service pages — 10 fully complete, 1 (Bed Bug Control) content-complete but missing a photo, same Owner-decision pattern.
- 11 "Service Expansion Phase" services (CCTV Installation, Smart Home Installation, Swimming Pool Maintenance, Kitchen Installation, Interior Decoration, Interlock Installation, Lighting Maintenance, Wood Alternative Installation, Wallpaper Installation, Thermal Insulation, Rooftop Space Utilization) — **structural only**: catalog entry, i18n name/description, SEO title/meta/keywords exist; **no full page content** (overview, scope, process, benefits, safety, FAQ) yet. These stay `NOINDEX_FOLLOW` until written.

On `/ar/services`, 23 of the 27 are visible as cards (pest-control's 11 sub-pages live under their own hub, not this grid; Handyman/Waterproofing/Bed-Bug are correctly withheld from grids/related-links per the no-placeholder-image rule).

### Maintenance / Cleaning / Pest Control (3-category structure)
**Done.** `ServiceCategory` in `src/lib/catalog/services.ts` has exactly 3 values, and both the services grid and the booking form (`src/lib/catalog/booking-options.ts`) group the real catalog into these three sections. Booking form's own header comment explicitly documents that pest *types* (cockroach, ant, etc.) are offered as a detail field on the one real "Pest Control" service, not as five separate services — a deliberate reconciliation against an earlier mismatched request, not an oversight.

### UAE seven Emirates
**Partially done.** `src/lib/catalog/locations.ts`'s `ALL_EMIRATES` correctly lists all 7 emirates with stable IDs, matching `03_MARKET/SERVICE_AREAS.md`. But only **Dubai has `hasPage: true`** — it is the only emirate with an actual generated `/locations/[slug]` page today. The other 6 render as plain text in the locations index, explicitly not linked (`hasPage: false` routes to the general index, never a route that doesn't exist) — correct behavior given no content exists yet, but 6 of 7 emirate pages are still missing.

### Service + City SEO pages, Pest Type + City pages
**Structure only — zero live pages.** `docs/CITY_PAGES_STRUCTURE.md` (dated 2026-07-30) confirms this directly: the full routing skeleton exists for both tiers —
- Section-level: `/{locale}/services/{maintenance|cleaning|pest-control}/city/{citySlug}`
- Service-level: `/{locale}/services/{maintenance|cleaning|pest-control}/{serviceOrSubServiceSlug}/{citySlug}`

— across all 7 emirate slugs, with metadata, internal links, and LocalBusiness schema all wired. But `CITY_SERVICE_CONTENT` and `CITY_SECTION_CONTENT` in `src/lib/catalog/city-content.ts` are **both empty objects**. Every route sets `dynamicParams = false`, so every one of these URLs returns a **hard 404** today — confirmed by the doc's own note that `npm run build` generates exactly 0 static pages across all 6 route groups. Publishing one real page is described as a single data-entry step (add one entry to the registry) — no further code change needed — but none has been written yet.

### Three articles per service
**Not started — 0 articles exist.** `src/lib/catalog/blog.ts`'s `BLOG_POSTS` array is empty; its own comment says it "stays empty until real, reviewed articles exist." The blog index correctly renders an empty state rather than placeholder content. The architecture (categories, related-post logic, per-service article linking via `getPostsForService`) is fully built and ready to receive content — but against a target of 3 articles × 27 services (81 articles) or × 16 content-complete services (48 articles), the actual count is 0 either way.

### Marketing email foundation
**Done, at foundation scope.** A newsletter/lead-capture form (`src/components/newsletter-form.tsx`) posts to the existing `/api/enquiries` endpoint and separately records consent (channel, purpose, wording, timestamp) via `/api/consents`, per `EMAIL_MARKETING.md`'s audience-consent rules. `docs/email-dns-readiness.md` is a complete, unexecuted runbook for SPF/DKIM/DMARC — explicitly states no ESP is chosen and no DNS record has been touched (DNS changes are `A4`, Owner-only, correctly deferred). This matches "foundation" as scoped — it is not a live sending capability, and isn't supposed to be yet.

### Chatbot readiness
**Minimal — data scaffolding only, no chatbot exists.** The only chatbot-related code is a `relatedServiceSections` field attached to each emirate in `locations.ts`, explicitly commented as being there so "a future website/WhatsApp assistant can look up 'what does AFAQ offer in `<emirate>`' without re-deriving it." There is no chatbot UI, widget, webhook, or AI integration anywhere in the codebase. This is closer to "a data shape a future chatbot could consume" than "chatbot readiness" in the sense of an integration point being wired.

---

## 3. What Exists in Code but Is Not Connected / Not Visible

- **City + service SEO pages** (§2 above) — full routing/metadata/schema skeleton, zero content, all 404.
- **Persistence layer** — `src/lib/adapters/` has only `in-memory` and `password` subdirectories; no `@prisma/client` import exists anywhere under `src/lib/adapters`. `prisma/schema.prisma` exists and validates but nothing in the running app talks to it. Every booking, quote, enquiry, and account created against this app today is lost on server restart.
- **Google ecosystem integrations** — `docs/google-ecosystem-setup.md` confirms the app already reads `GOOGLE_SITE_VERIFICATION` / GTM container env vars and renders the corresponding tags only when set; both are unset, so nothing renders publicly yet. This is correctly inert, not broken.
- **11 Service Expansion Phase pages** — routes exist and will resolve, but render generic shared sections rather than real content (no `overview`/`scope`/`process`/`benefits`/`safety`/`FAQ`), and stay `NOINDEX_FOLLOW`.

## 4. Missing Items (confirmed absent, not just unconnected)

1. Real database wiring (Prisma adapter) — schema-only today.
2. 6 of 7 emirate location pages (only Dubai exists).
3. All Service+City and Pest-Type+City SEO pages (0 of the full matrix).
4. Blog articles (0 published; target of 3-per-service undefined against which service count).
5. Full content for the 11 Service Expansion Phase services.
6. 3 card images (Handyman, Waterproofing, Bed Bug Control) — open by explicit Owner decision, blocked on real photography, not a code gap.
7. A real chatbot integration (only a future-facing data field exists).
8. `robots.ts` (environment-aware crawl rules) — flagged as missing in the prior `07_EXISTING_APP_INTEGRATION_AUDIT.md` and not found in this pass either.
9. Any live email-sending capability (ESP selection and DNS records are explicitly deferred to the Owner, `A4`).

## 5. Suggested Priority Order to Finish

This order follows dependency and reuse — later items build directly on earlier ones, so sequencing them out of order would mean redoing work:

1. **Wire a real Prisma-backed adapter set** (local/CI MySQL only, per the already-approved Phase 1 scope) — every booking/quote/account feature already built is currently unusable beyond a single dev session without this.
2. **Write the remaining 6 emirate location pages** — smallest, most self-contained gap; the registry/route pattern already supports it.
3. **Populate `CITY_SERVICE_CONTENT` / `CITY_SECTION_CONTENT`** for at least the highest-value service × city combinations — the routing/schema work is already done; this is the single highest-leverage SEO gap since it currently 404s everywhere.
4. **Write full content for the 11 Service Expansion Phase services** — brings all 27 catalog services to the same completeness bar as the original 16.
5. **Write and publish blog articles** — architecture is ready; this is pure content production, no code blocking it. Clarify the actual target count first (see §2's "60" and "3 per service" flags) so this isn't built against an undefined number.
6. **Chatbot integration** — lowest priority; no code path currently depends on it, and building it before the content/data it would answer from exists (§3/§4) would mean re-testing it repeatedly as that content changes.
7. **`robots.ts` and Google/ESP live connections** — last, since they're either quick (`robots.ts`) or fully gated on Owner-only `A4` actions (DNS, ESP account, Google account) that this report cannot resolve.

Photography for Handyman/Waterproofing/Bed Bug Control is a standing open item outside this sequence — it only needs a real photo supplied, not development work.

---

## Related Documents

- `07_WEBSITE/IMPLEMENTATION/00_PHASE1_APPROVAL.md`
- `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md`
- `docs/SERVICE_COMPLETION_MATRIX.md` (app repo)
- `docs/CITY_PAGES_STRUCTURE.md` (app repo)
- `docs/email-dns-readiness.md` (app repo)
- `docs/google-ecosystem-setup.md` (app repo)
- `00_GOVERNANCE/DECISION_LOG.md` (#38, #39)
