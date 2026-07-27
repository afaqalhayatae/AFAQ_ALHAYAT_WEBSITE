# Content-to-Website Mapping

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only
- **Version:** 1.0
- **Prepared:** 2026-07-27
- **Depends on:** `02_WEBSITE_IMPLEMENTATION_PLAN.md`

## Rule this mapping follows

Per `SYSTEM_ARCHITECTURE.md` §7 (non-duplication), website pages must **reference** canonical facts, never copy them. Every row below names the owning source and the page that consumes it by reference — the page never becomes a second authority for that fact.

---

## 1. Service Knowledge → Service Pages (`07_WEBSITE/03_SERVICE_PAGES/`)

One page per `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` entry. Page readiness follows package maturity, not folder existence:

| Service ID | Package | Package status | Page readiness |
|---|---|---|---|
| `SVC-PEST-CONTROL` | `01_PEST_CONTROL/` | Complete | Ready to build first — full BUSINESS/OPERATIONS/SAFETY/CUSTOMER_GUIDE/FAQ/SEO_AI/CONTENT_AR/CONTENT_EN source. |
| `SVC-GENERAL-CLEANING` | `03_GENERAL_CLEANING/` | Review-ready | Build second; confirm review sign-off before publishing claims. |
| `SVC-WATER-TANK-CLEANING` | `05_WATER_TANK_CLEANING/` | Review-ready | Build alongside General Cleaning. |
| `SVC-AC-MAINTENANCE` | `02_AC_MAINTENANCE/` | Structurally complete draft (`SOURCE_DRAFT.md` present) | Scaffold page shell now; hold published claims until owner/evidence review. |
| `SVC-PLUMBING` | `06_PLUMBING/` | Structurally complete draft | Same as AC Maintenance. |
| `SVC-ELECTRICAL-MAINTENANCE` | `07_ELECTRICAL_MAINTENANCE/` | Structurally complete draft | Same. |
| `SVC-PAINTING` | `08_PAINTING/` | Structurally complete draft | Same. |
| `SVC-HANDYMAN` | `09_HANDYMAN/` | Structurally complete draft | Same. |
| `SVC-DRAIN-UNBLOCKING` | `10_DRAIN_UNBLOCKING/` | Structurally complete draft | Same; owner confirmed service exists, methods/pricing not yet approved. |
| `SVC-WATERPROOFING` | `11_WATERPROOFING/` | Structurally complete draft | Same; scope currently interpreted as water-ingress protection only. |
| `SVC-WATER-LEAK-DETECTION` | `12_WATER_LEAK_DETECTION/` | Structurally complete draft | Same. |
| `SVC-DEEP-CLEANING` | `04_DEEP_CLEANING/` | Blocked pending owner scope | Do not build a live page; empty-state placeholder only. |

Each page template consumes, per service: `BUSINESS.md` (what/who), `OPERATIONS.md` (process description, not internal SOP detail), `SAFETY.md` (public-facing safety notes only), `CUSTOMER_GUIDE.md` + `FAQ.md` (on-page FAQ, paired with FAQ schema), `SEO_AI.md` (meta/schema/AI-answer guidance), `CONTENT_AR.md`/`CONTENT_EN.md` (bilingual copy pair — must express the same facts), `MEDIA.md` (approved imagery only).

---

## 2. Market & Coverage → Location Pages (`07_WEBSITE/04_LOCATIONS/`)

- Source: `03_MARKET/SERVICE_AREAS.md` (sole authority).
- 7 emirate pages (`LOC-AE-AZ`, `LOC-AE-DU`, `LOC-AE-SH`, `LOC-AE-AJ`, `LOC-AE-UQ`, `LOC-AE-RK`, `LOC-AE-FU`) may be built now — coverage is approved at this level.
- Priority-community rows (Tier 1–3, e.g. Palm Jumeirah, Saadiyat Island, Al Zahia) are approved as **marketing priorities**, not branch proof — a community page must not imply a physical branch, must pass the SEO quality gate (unique content, not thin duplication of the emirate page), and Tier 3 areas require the "short commercial validation" the registry calls for before dedicated campaigns.
- Location pages select service availability from `SERVICE_MATRIX.md` — they do not restate coverage lists inline.
- Legacy HOLD documents (`18_SERVICE_LOCATIONS.md`, `19_SERVICE_AREAS_BY_EMIRATE.md`, the TEMP `SERVICE_AREAS.md`) are superseded and must not be consulted for city/district data.

---

## 3. Brand & Contact → Header/Footer/Contact Page

- Source: `02_BRAND/CONTACT_INFORMATION.md`, `02_BRAND/LOCAL_SEO_PROFILE.md`.
- Publishable now: phone (`+971 58 543 1766`, with `tel:` link format already specified), domain.
- Blocked (render as absent, not placeholder): WhatsApp button, email link, working hours, street address, Google Maps embed, social icons, emergency-service banner.
- Consumes into: Header call/WhatsApp buttons, Footer contact block, `07_CONTACT` page, Homepage §12 (Contact Information) and §09 (CTA) per `07_WEBSITE/01_HOMEPAGE/00_HOMEPAGE_ARCHITECTURE.md`.

---

## 4. Company Identity → About Page

- Source: `01_BUSINESS/COMPANY_PROFILE.md`, `VISION.md`, `MISSION.md`, `STAKEHOLDERS.md` (internal facts only — do not publish internal stakeholder names without an explicit publishing decision).
- Consumes into: `07_WEBSITE/02_ABOUT/`, Homepage "Why Choose AFAQ" section (differentiators must be evidence-backed per the homepage architecture doc, not aspirational copy).

---

## 5. Customer & Sales → Booking / Pricing / Legal Pages

- `06_CUSTOMER_AND_SALES/BOOKING/BOOKING_PROCESS_DRAFT.md` → `07_WEBSITE/05_BOOKING/` — Draft status; page must not go live with a booking flow until this clears review, per the `A4` gate on commercial/booking commitments.
- `06_CUSTOMER_AND_SALES/PRICING/*` (packages, strategy) → any pricing display anywhere on the site — hard-blocked; quoting a price is always `A4`.
- `06_CUSTOMER_AND_SALES/POLICIES/WARRANTY_POLICY_DRAFT.md`, `06_CUSTOMER_AND_SALES/WARRANTY/*` → warranty claims on service pages — same hard block.
- `06_CUSTOMER_AND_SALES/POLICIES/SERVICE_POLICIES_DRAFT.md` → `07_WEBSITE/08_LEGAL_PAGES/` — requires legal review before any text is drafted for publication; do not treat the draft as legal-ready copy.

---

## 6. SEO & AI Knowledge → Cross-Cutting Implementation

| Source | Consumes into |
|---|---|
| `99_STANDARDS/SEO_STANDARD.md`, `10_MARKETING_AND_SEO/SEO_STRATEGY.md` | Global metadata rules, title/description templates. |
| `10_MARKETING_AND_SEO/SCHEMA_STRATEGY.md` | LocalBusiness, Organization, Service, FAQ schema.org markup across all page types (matches Homepage's "AI & GEO Requirements" section). |
| `10_MARKETING_AND_SEO/LOCAL_SEO.md`, `02_BRAND/LOCAL_SEO_PROFILE.md` | `04_LOCATIONS` pages, Google Business Profile integration (blocked until profile URL confirmed). |
| `10_MARKETING_AND_SEO/URL_AND_INTERNAL_LINKING_STANDARD.md` | Site-wide URL structure and internal link rules. |
| `10_MARKETING_AND_SEO/CONTENT_STRATEGY.md` | `07_WEBSITE/06_BLOG/` editorial structure. |
| `99_STANDARDS/AI_GEO_STANDARD.md`, `09_AI_KNOWLEDGE/GEO_STRATEGY.md` | Site-wide AI-discoverability requirements (semantic HTML, entity markup). |
| `09_AI_KNOWLEDGE/ANSWER_POLICY.md`, `RETRIEVAL_POLICY.md`, `ENTITY_REGISTRY.md` | Any on-site AI assistant/chat feature — must cite sources and refuse to fill gated facts, per policy. |
| `09_AI_KNOWLEDGE/EVALUATIONS/CORE_TEST_CASES.md` | Release-blocking test suite for AI features before launch. |

---

## 7. Design System → Implementation

| Source | Implementation target |
|---|---|
| `12_DESIGN_SYSTEM/COLORS.md`, `TYPOGRAPHY.md`, `SPACING.md`, `GRID.md` | Tailwind theme config (`tailwind.config`) — design tokens as the single source for the CSS layer. |
| `12_DESIGN_SYSTEM/BUTTONS.md`, `FORMS.md`, `CARDS.md`, `ICONS.md`, `COMPONENTS.md` | Shared React component library (`Button`, `Card`, `FormField`, icon set via Lucide React per `TECH_STACK.md`). |
| `12_DESIGN_SYSTEM/MOBILE.md` | Responsive breakpoints, mobile-first layout rules (design system is explicitly mobile-first). |
| `12_DESIGN_SYSTEM/ACCESSIBILITY.md` + `99_STANDARDS/ACCESSIBILITY_STANDARD.md` | WCAG 2.2 AA implementation checklist, cross-referenced rather than duplicated per the standards doc's own note. |
| `12_DESIGN_SYSTEM/ANIMATIONS.md` | Framer Motion usage rules (lightweight, performance-conscious per design principles). |
| `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md`, `SIDEBAR_NAVIGATION.md` | Binding visual direction and navigation pattern — overrides generic component defaults where they conflict. |

---

## 8. Homepage — Direct 1:1 Mapping

`07_WEBSITE/01_HOMEPAGE/` already contains page-ready specification docs; these map directly to implementation with no further translation needed:

- `00_HOMEPAGE_ARCHITECTURE.md` → page section order and component list (13 sections, Announcement Bar through Footer).
- `01_HOMEPAGE_CONTENT.md` → copy source (subject to the same blocked-field rules as everywhere else).
- `02_HOMEPAGE_UI_UX.md` → layout/interaction spec.
- `03_HOMEPAGE_SEO_AI.md` → homepage-specific metadata/schema.
- `04_HOMEPAGE_COMPONENTS.md` → component inventory, should reconcile with `12_DESIGN_SYSTEM/COMPONENTS.md` (shared component library takes precedence if the two ever diverge — flag, don't silently pick one).

---

## Related Documents

- `01_PROJECT_AUDIT_REPORT.md`
- `02_WEBSITE_IMPLEMENTATION_PLAN.md`
- `04_FINAL_RECOMMENDATION.md`
