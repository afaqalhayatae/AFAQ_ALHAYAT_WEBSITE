# Website Experience Architecture Audit Report

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — audit only. No document modified, no code, no component, no asset touched. No redesign recommended.
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Last Updated:** 2026-08-01
- **Package:** `00_GOVERNANCE/`
- **Scope reviewed:** `07_WEBSITE/` — `01_HOMEPAGE/*`, `IMPLEMENTATION/*`, `WORDPRESS/*` (legacy, non-canonical), `README.md`, `GOOGLE_LIVE_ECOSYSTEM.md`. Read-only.

## Purpose

This report audits existing website-architecture documentation only. It does not recommend redesign, does not assume information that isn't documented, and flags every gap or conflict as found rather than filling it in. Where the live application's actual state is described in `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md` (a prior, code-verified audit), that document's findings are cited as the current state — this report does not re-verify code itself, only the documentation about it.

---

## 1. Current Website Architecture

### Existing pages / folders

Per `07_WEBSITE/README.md`, only `01_HOMEPAGE/` has documentation ("In Review — documents exist"). Every other channel folder is explicitly marked "Not yet built": `02_ABOUT/`, `03_SERVICE_PAGES/`, `04_LOCATIONS/`, `05_BOOKING/`, `06_BLOG/`, `07_CONTACT/`, `08_LEGAL_PAGES/`, `09_ERROR_PAGES/`. `WORDPRESS/` is explicitly labeled "Legacy implementation research; non-canonical for the approved build" — the canonical stack is Next.js per `00_GOVERNANCE/TECH_STACK.md`, so `WORDPRESS/*` content is out of scope for current architecture and not treated as live guidance in this report.

**Separately, the actual live application** (a different repository, `afaqalhayatae-app`, audited in `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md`) already implements more than this repository's page-folder documentation suggests: home, services index + `[slug]` + `[slug]/[location]`, locations index + `[slug]`, about, contact, FAQ, blog index + `[slug]`, legal pages (privacy, terms, cookie policy), and a customer portal (account overview, profile, bookings, quotes, requests). **This is a documentation/reality gap** — the knowledge repository's `07_WEBSITE/` folders read as "not yet built" while the application repository has already built pages for most of them.

### Sections (Homepage)

Per `01_HOMEPAGE/00_HOMEPAGE_ARCHITECTURE.md`, the homepage has 13 defined sections in order: (1) Announcement Bar, (2) Header, (3) Hero Section, (4) Company Statistics, (5) Featured Services, (6) Why Choose AFAQ, (7) Service Areas, (8) Testimonials, (9) Call To Action, (10) FAQ, (11) Latest Articles, (12) Contact Information, (13) Footer. `01_HOMEPAGE/02_HOMEPAGE_UI_UX.md`'s "Layout Structure" list matches this order exactly. `01_HOMEPAGE/04_HOMEPAGE_COMPONENTS.md` documents 11 of these as named components (`CMP-001`–`CMP-011`); Company Statistics and Service Areas are not separately assigned component IDs in that file, though they are listed as homepage structure sections in the architecture doc.

### Navigation

No dedicated navigation-structure document exists in `07_WEBSITE/`. Navigation is only described as a sub-element of the Header component: `00_HOMEPAGE_ARCHITECTURE.md` §02 and `04_HOMEPAGE_COMPONENTS.md` `CMP-002` both list Header's components as "Company Logo, Main Navigation, Language Switcher, Search, Call Button, Book Now Button" — but neither document enumerates the actual navigation menu items (which pages/services appear in the menu, dropdown structure, mobile menu behavior). `12_DESIGN_SYSTEM/SIDEBAR_NAVIGATION.md` exists but scopes to the authenticated customer-portal sidebar, not the public site's main navigation (confirmed by `IMPLEMENTATION/03_COMPONENT_STRATEGY.md` §5, "Sidebar Navigation — Scope Boundary").

### Content hierarchy

The homepage's user journey is explicitly defined in `00_HOMEPAGE_ARCHITECTURE.md`: Visitor → Trust Building → Service Discovery → Service Details → Booking → Confirmation → Customer Relationship. This journey maps directly onto the 13 homepage sections in order (trust-building sections first, service-discovery sections mid-page, conversion/contact sections toward the end).

---

## 2. Service Architecture

### Maintenance, Cleaning, Pest Control (per `IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md`, dated 2026-07-28)

This roadmap groups the (at the time) 12 catalog services into: **Maintenance** (8: AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman, Drain Unblocking, Waterproofing, Water Leak Detection), **Cleaning** (3: General Cleaning, Deep Cleaning, Water Tank Cleaning), **Pest Control** (1: Pest Control). Per-service status at that time: Pest Control's knowledge package was "marked Complete — most mature of all 12"; General Cleaning and Water Tank Cleaning were "Review-ready"; the five remaining Maintenance services were "Structurally complete draft"; Drain Unblocking/Waterproofing/Water Leak Detection had "scope owner-confirmed but technical detail pending"; Deep Cleaning was "Blocked pending owner scope — no source draft exists."

**Currency note:** this roadmap (2026-07-28) has not been updated since three later Decision Log entries changed the picture materially: Decision 37 (2026-07-31) approved the Pest Control content package for publication and confirmed Gecko Control as an 11th pest-control sub-service; Decision 38 (2026-07-31) authored content for the remaining Maintenance and Cleaning services (including Deep Cleaning's previously-blocked status) and added 4 new Cleaning services; Decision 39 (2026-07-31) added 11 further catalog services under General Maintenance. **The roadmap document itself was not found to reference any of these three decisions or the 15 services they added.**

### Service pages

Per `07_EXISTING_APP_INTEGRATION_AUDIT.md` §0 of the service roadmap and its own §2/§3, the route `src/app/[locale]/services/[slug]/page.tsx` "already generates a route for every catalog service dynamically" — confirmed structurally solved app-wide; what varies is content depth and image readiness per service, not routing.

### City/service pages

Confirmed implemented: `07_EXISTING_APP_INTEGRATION_AUDIT.md` §3 lists `services index + [slug] + [slug]/[location]` among implemented public pages — a combined service+location route pattern already exists in the live app.

---

## 3. Location Architecture

### Seven Emirates structure

Per `IMPLEMENTATION/13_LOCATION_EXPANSION_ROADMAP.md` §0 (2026-07-28, code-verified): all seven emirates are `Active` with "All catalog services" coverage in `03_MARKET/SERVICE_AREAS.md`'s Approved Registry, but **only Dubai (`LOC-AE-DU`) has a generated location page today.** Abu Dhabi (`LOC-AE-AZ`), Sharjah (`LOC-AE-SH`), Ajman (`LOC-AE-AJ`), Umm Al Quwain (`LOC-AE-UQ`), Ras Al Khaimah (`LOC-AE-RK`), and Fujairah (`LOC-AE-FU`) are approved in the registry but have no page yet. The same finding is independently confirmed in `07_EXISTING_APP_INTEGRATION_AUDIT.md` §4: "6 of 7 approved emirates are missing."

### City pages

Community-level (Tier 1) pages (e.g., Palm Jumeirah) are explicitly out of scope for the current emirate-level roadmap — "a separate, later tier requiring their own SEO/ops quality checklist per `SERVICE_AREAS.md`," per `13_LOCATION_EXPANSION_ROADMAP.md` §0.

### SEO location strategy

Coverage claims are required to stay strictly at emirate level per `SERVICE_AREAS.md`'s Publication Rules — no city/district/community claim until that area separately clears its own registry review (`13_LOCATION_EXPANSION_ROADMAP.md` §3). Each new emirate page requires "genuine local context" (§2) — verifiable, emirate-specific facts, locally relevant FAQ content, or real internal links generated from `SERVICE_MATRIX.md` — and if no genuinely unique content exists beyond swapping the emirate name, `LUXURY_DESIGN_DIRECTION.md` §6 requires the page not be published rather than shipped as a thin duplicate.

---

## 4. User Experience

### Mobile experience

`01_HOMEPAGE/02_HOMEPAGE_UI_UX.md` states the homepage "must be designed Mobile First," with all sections adapting to Mobile/Tablet/Desktop. `IMPLEMENTATION/10_ANNOUNCEMENT_BAR_ARCHITECTURE.md` §10 documents specific mobile behavior for that one component (44×44px minimum touch target for the dismiss control, no special fixed/floating treatment). No dedicated, site-wide "Mobile Experience" specification document beyond these two sources was found.

### Desktop experience

No distinct "Desktop Experience" document exists — desktop is covered only as one of three responsive targets ("Mobile, Tablet, Desktop") in `02_HOMEPAGE_UI_UX.md`, with no desktop-specific requirements beyond that.

### Booking journey

The homepage user journey (§1 above) names Booking as a distinct stage. `IMPLEMENTATION/02_FOLDER_STRUCTURE.md` proposes a `(booking)/book/` route group, explicitly "gated until approved," sourced from `06_CUSTOMER_AND_SALES/BOOKING/` (per `07_WEBSITE/README.md`, not yet authored). Per `07_EXISTING_APP_INTEGRATION_AUDIT.md` §9, full request/response plumbing for bookings, quotes, and enquiries already exists in the live app, gated by session ownership — but runs entirely against in-memory repositories with no live database, so "no request submitted today would survive a server restart" and the feature set is "not yet usable beyond local development/testing."

### Login requirements

Two documents describe this differently in depth and currency. `IMPLEMENTATION/01_APPLICATION_ARCHITECTURE.md` §5 (v1.0) frames authentication as an entirely open Phase-3 decision with no provider chosen. `IMPLEMENTATION/08_AUTHENTICATION_ARCHITECTURE.md` (v1.1, same prepared date) is materially more advanced: it documents password authentication as **already implemented in code** (scrypt hashing, httpOnly session cookies), Google and Apple OAuth as planned with reserved-but-unimplemented adapter interfaces, and a 4-phase rollout plan. This is a **currency/depth conflict between two documents in the same folder** — §6 below.

### Chatbot position

No chatbot architecture document exists within `07_WEBSITE/`. The only mention found inside this domain is `IMPLEMENTATION/00_PHASE1_APPROVAL.md`, which lists "chatbot" among live third-party integrations **explicitly out of scope for Phase 1** ("live third-party integrations (analytics, CRM, chatbot, payment, email/SMS/WhatsApp)... explicitly out of scope"). No chatbot placement, UI position, or trigger behavior is documented anywhere in `07_WEBSITE/`. A substantive conversational-assistant standard exists at `09_AI_KNOWLEDGE/CONVERSATIONAL_ASSISTANT_STANDARD.md`, but that file is outside this task's reviewed scope (`07_WEBSITE/`) and is not itself a website-placement document.

---

## 5. SEO Architecture

### URL structure

Per `IMPLEMENTATION/02_FOLDER_STRUCTURE.md` §2: locale-prefixed routes (`/ar/...`, `/en/...`), with `services/[serviceId]` (one per catalog `SVC-<NAME>`) and `locations/[areaId]` (one per approved `LOC-AE-<EMIRATE>[-<AREA>]`). `05_SEO_IMPLEMENTATION_PLAN.md` §4 requires route naming to be lowercase, hyphenated, locale-prefixed, and stable once published, per `10_MARKETING_AND_SEO/URL_AND_INTERNAL_LINKING_STANDARD.md`.

### Internal linking

Per `05_SEO_IMPLEMENTATION_PLAN.md` §4: service and location pages must cross-link to each other, generated from `SERVICE_MATRIX.md` rather than hand-authored per page, so the link graph cannot drift from approved coverage data. Every publishable page must be reachable from at least its relevant index page and the sitemap — no orphan pages.

### Content organization

Structured data (Organization, LocalBusiness, Service, FAQ, Breadcrumb, WebSite schema) is required to be generated as "a projection of the content adapter's output, not a separately maintained data source" (`05_SEO_IMPLEMENTATION_PLAN.md` §2) — explicitly to prevent visible content and schema markup diverging.

### Bilingual SEO readiness

Per `05_SEO_IMPLEMENTATION_PLAN.md` §5: `hreflang` alternates (`ar`, `en`, `x-default`) generated automatically from locale routing, separate per-locale sitemap entries, and meta titles/descriptions authored per language (not machine-translated). Per `07_EXISTING_APP_INTEGRATION_AUDIT.md` §7/§8, `hreflang`/canonical generation and locale-aware sitemap content-gating are already implemented in the live app; `ar` (default, RTL) and `en` (LTR) are both routed and rendered, with `i18n/messages/{ar,en}.json` files being line-count-equal (631 lines each) as a structural signal of parity — though that audit notes full semantic parity (same facts, not just same key count) "was not independently re-verified" even in that document. One documented gap: no `robots.ts`/`robots.txt` exists yet, and Organization/LocalBusiness schema sourced correctly from approved-only fields "was not located" in that audit's pass.

---

## 6. Missing Items or Conflicts

1. **Documentation/reality gap:** `07_WEBSITE/README.md` marks nearly every channel folder "Not yet built," while the separate application repository has already built pages for most of them (home, services, locations, about, contact, FAQ, blog, legal, customer portal). The knowledge repository's page-folder status table has not been updated to reflect this.
2. **Authentication documentation currency conflict:** `01_APPLICATION_ARCHITECTURE.md` §5 describes auth as an entirely open decision; `08_AUTHENTICATION_ARCHITECTURE.md` (same folder, same prepared date, later version number) describes password auth as already implemented with a detailed 15-section plan for OAuth expansion. The two documents disagree on how much progress exists.
3. **Homepage document status conflict:** `01_HOMEPAGE/00_HOMEPAGE_ARCHITECTURE.md` states Status = "In Review / Not for Implementation," while `01_HOMEPAGE/02_HOMEPAGE_UI_UX.md` and `01_HOMEPAGE/03_HOMEPAGE_SEO_AI.md` (same folder, same version 1.0) both state Status = "Build Phase" — three sibling documents for the same page disagree on lifecycle status.
4. **Service Expansion Roadmap is stale:** `12_SERVICE_EXPANSION_ROADMAP.md` (2026-07-28) predates and does not reference Decision Log entries 37, 38, and 39 (all 2026-07-31), which changed Pest Control's publication status and added 15 new catalog services not reflected anywhere in that roadmap.
5. **Folder structure vs. built architecture:** `07_EXISTING_APP_INTEGRATION_AUDIT.md` §2/§12 documents that the live app uses a layered `services → adapters → API routes` architecture, which "disagrees" (the audit's own word) with the flatter structure `02_FOLDER_STRUCTURE.md` originally planned — flagged in that audit as an open question for the Owner on which document should be revised.
6. **No dedicated navigation-structure document.** Main Navigation is named as a Header sub-component in two places but its actual menu contents/hierarchy are not documented anywhere in `07_WEBSITE/`.
7. **No dedicated Desktop Experience or site-wide Mobile Experience document** beyond the Mobile-First principle stated once in `02_HOMEPAGE_UI_UX.md` and one component's mobile behavior section in the announcement-bar plan.
8. **No chatbot architecture or placement documentation exists in `07_WEBSITE/`** — only an explicit Phase-1 scope exclusion.
9. **Critical, previously-documented finding restated here for completeness (not newly found by this audit):** `07_EXISTING_APP_INTEGRATION_AUDIT.md` §11 documents that the live application hardcodes and publicly renders a WhatsApp number, an `Info@afaqalhayatae.com` email, a physical address, working hours, and eight social profile links — all of which `02_BRAND/CONTACT_INFORMATION.md` and `02_BRAND/LOCAL_SEO_PROFILE.md` mark `Pending`/`Owner Input Required`, not `Approved`. That audit calls this "the most significant finding" and states it "should be treated as blocking any public deployment until resolved by the Owner." This report does not re-verify the code; it surfaces that this finding exists and remains open per the source document.
10. **No live database wiring.** Per `07_EXISTING_APP_INTEGRATION_AUDIT.md` §4, the Prisma schema exists and validates, but no adapter calls it — booking/quote/enquiry data does not persist across a server restart.

---

## 7. Implementation Readiness

### Ready

- Homepage section order/structure (`00_HOMEPAGE_ARCHITECTURE.md`, `02_HOMEPAGE_UI_UX.md`) — internally consistent between the two documents.
- URL/routing pattern for services and locations (`02_FOLDER_STRUCTURE.md`) — already implemented in the live app per the integration audit.
- Bilingual routing mechanism (locale-prefixed, `hreflang`, RTL/LTR) — documented and confirmed implemented.
- SEO technical foundation (canonical URLs, sitemap gating, schema-from-adapter pattern) — documented and largely confirmed implemented, apart from `robots.ts` and Organization/LocalBusiness schema (§6 above).
- Announcement bar architecture (`10_ANNOUNCEMENT_BAR_ARCHITECTURE.md`) — Owner-approved decisions recorded (dismiss behavior, priority order, display rules), detailed 15-section plan, not yet built.

### Needs decision

- Which authentication document (`01_APPLICATION_ARCHITECTURE.md` §5 vs. `08_AUTHENTICATION_ARCHITECTURE.md`) reflects the Owner's intended current status, and whether `01_APPLICATION_ARCHITECTURE.md` should be updated to match.
- Whether `02_FOLDER_STRUCTURE.md` should be revised to match the layered architecture actually built, per `07_EXISTING_APP_INTEGRATION_AUDIT.md` §12 open question 2.
- Whether the six missing emirate pages should be built next, or Dubai-only remains intentional (audit §12 open question 4).
- Resolution of the unverified-contact-facts finding (§6 item 9) — the single largest blocker per the existing audit.
- Homepage document status reconciliation (§6 item 3) — which status is current across the three sibling homepage documents.

### Needs documentation

- A dedicated navigation-structure document (menu items, hierarchy, mobile menu behavior).
- Updating `12_SERVICE_EXPANSION_ROADMAP.md` to reflect Decision Log entries 37–39.
- Updating `07_WEBSITE/README.md`'s page-folder status table against the live app's actual built pages.
- Chatbot placement/architecture documentation, if and when chatbot integration is approved beyond Phase 1's explicit exclusion.
- A site-wide Desktop Experience specification, if one is intended beyond the current Mobile-First-only framing.

---

## Related Documents

- `07_WEBSITE/README.md`
- `07_WEBSITE/01_HOMEPAGE/00_HOMEPAGE_ARCHITECTURE.md`, `02_HOMEPAGE_UI_UX.md`, `03_HOMEPAGE_SEO_AI.md`, `04_HOMEPAGE_COMPONENTS.md`
- `07_WEBSITE/IMPLEMENTATION/01_APPLICATION_ARCHITECTURE.md`, `02_FOLDER_STRUCTURE.md`, `05_SEO_IMPLEMENTATION_PLAN.md`, `07_EXISTING_APP_INTEGRATION_AUDIT.md`, `08_AUTHENTICATION_ARCHITECTURE.md`, `10_ANNOUNCEMENT_BAR_ARCHITECTURE.md`, `12_SERVICE_EXPANSION_ROADMAP.md`, `13_LOCATION_EXPANSION_ROADMAP.md`
- `00_GOVERNANCE/DECISION_LOG.md` — decisions 37, 38, 39 (service catalog currency, §6 item 4).
- `03_MARKET/SERVICE_AREAS.md` — Approved Registry (seven emirates).

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-08-01 | Initial audit of `07_WEBSITE/` architecture documentation across homepage structure, service architecture, location architecture, UX, SEO architecture, and cross-document conflicts, per Owner instruction. No redesign recommended, no document modified. |
