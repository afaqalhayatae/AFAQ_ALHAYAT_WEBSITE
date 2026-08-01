# Navigation Architecture

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — architecture plan only. No code, component, or navigation menu is implemented by this document.
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Scope:** `afaqalhayatae-app` — public-site main navigation (desktop and mobile), global header elements, and the SEO/bilingual principles governing their content.
- **Depends on:** `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `03_MARKET/SERVICE_AREAS.md`, `02_BRAND/CONTACT_INFORMATION.md`, `07_WEBSITE/01_HOMEPAGE/00_HOMEPAGE_ARCHITECTURE.md`, `07_WEBSITE/01_HOMEPAGE/04_HOMEPAGE_COMPONENTS.md`, `07_WEBSITE/IMPLEMENTATION/02_FOLDER_STRUCTURE.md`, `07_WEBSITE/IMPLEMENTATION/05_SEO_IMPLEMENTATION_PLAN.md`, `07_WEBSITE/IMPLEMENTATION/08_AUTHENTICATION_ARCHITECTURE.md`, `07_WEBSITE/IMPLEMENTATION/13_LOCATION_EXPANSION_ROADMAP.md`, `00_GOVERNANCE/WEBSITE_ARCHITECTURE_DECISION_UPDATE.md`, `12_DESIGN_SYSTEM/{TYPOGRAPHY,SIDEBAR_NAVIGATION}.md`.

## Purpose

Per `WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` §5, the creation of a dedicated navigation-structure document is approved, to close the gap identified in `WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §5: "Main Navigation" was previously named only as an unelaborated Header sub-component, with no document specifying its actual content. This document defines that content — menu items, order, grouping, mobile behavior, global elements, SEO principles, and bilingual requirements — **before** implementation, per the Owner's instruction. It writes no code, adds no component, and authorizes no build step.

## Note on scope

This document does not invent any business fact. Every service and location listed below is drawn directly from `SERVICE_CATALOG.md` and `SERVICE_AREAS.md`'s Approved Registry. Where a catalog entry is not yet ready for public linking (§1.3 below), it is explicitly excluded from the navigation rather than included with an invented status.

---

## 1. Desktop Navigation

### 1.1 Main menu items and order

Left-to-right order (mirrored right-to-left in Arabic, per §5):

1. **Home** — `/`
2. **Services** — dropdown, §1.3
3. **Locations** — dropdown, §1.4
4. **About** — `/about` (per `07_WEBSITE/README.md`, sourced from `01_BUSINESS/COMPANY_PROFILE.md`; not yet built as a knowledge-repo page but already implemented in the live app per `07_EXISTING_APP_INTEGRATION_AUDIT.md` §3)
5. **Blog** — `/blog` (implemented in the live app; per `07_WEBSITE/README.md`, "Not yet built" as a knowledge-repo page)
6. **Contact** — `/contact`

This order follows the homepage's own documented user journey (`00_HOMEPAGE_ARCHITECTURE.md`: Trust Building → Service Discovery → ... → Customer Relationship) — Services and Locations (service-discovery items) sit immediately after Home, before the lower-urgency About/Blog/Contact items.

### 1.2 Dropdown structure — general rule

Both Services and Locations render as a mega-menu-style dropdown (multi-column, grouped) rather than a flat list, given the catalog's size (27 services) and the registry's size (7 emirates, with deeper community tiers). A flat single-column list of 27 services would fail `12_DESIGN_SYSTEM/ICONS.md`'s adjacent "don't overload one place with too many icons/items" spirit and `LUXURY_DESIGN_DIRECTION.md`'s "Quiet Luxury" principle — grouping is a usability requirement, not a stylistic choice.

### 1.3 Services grouping

Grouped by the catalog's own three categories (`SERVICE_CATALOG.md` "# Categories"), each rendered as its own dropdown column:

| Column | Services included | Basis |
|---|---|---|
| **Cleaning & Pest Control** (8) | Pest Control, General Cleaning, Deep Cleaning, Water Tank Cleaning, Villa Cleaning, Office Cleaning, Post-Construction Cleaning, Carpet & Upholstery Cleaning | All 8 have Owner-approved published content (`SERVICE_CATALOG.md` "Status": "all 16 services have Owner-approved... content") |
| **General Maintenance** (5 of 16 catalog entries) | AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman Services | These 5 have approved published content; **the other 11 General Maintenance catalog entries (CCTV Installation, Smart Home Installation, Swimming Pool Maintenance, Kitchen Installation, Interior Decoration, Interlock Installation, Lighting Maintenance, Wood Alternative Installation, Wallpaper Installation, Thermal Insulation, Rooftop Space Utilization) are deliberately excluded from this dropdown** |
| **Drainage & Water Protection** (3) | Drain Unblocking, Waterproofing, Water Leak Detection | All 3 have approved published content |

**Exclusion rationale (not an oversight):** per `SERVICE_CATALOG.md`'s own "Status" section, the 11 excluded entries are "structural entries only" — catalog ID/SEO/i18n in place, no full page content, and explicitly marked `noindex` pending a future content phase. Linking to a `noindex`, content-incomplete page from primary navigation would create exactly the "thin page reachable from top-level nav" problem `05_SEO_IMPLEMENTATION_PLAN.md` §4's "avoid orphan pages" rule and `LUXURY_DESIGN_DIRECTION.md` §6 both warn against in the location-page context — the same principle applies here. **This dropdown must be updated to include each excluded service once its content phase completes and it clears `noindex`** — this document does not decide when that happens, only that inclusion should follow content-readiness, not catalog membership alone.

**Handyman Services and Waterproofing note:** both have approved content but currently lack a real card image (`SERVICE_CATALOG.md`); per that document, they are excluded from *card grids* elsewhere on the site but that exclusion does not extend to this text-based navigation dropdown — a nav link is not a card.

A "View All Services" link at the foot of the dropdown routes to `/services` (the services index page, already implemented per `07_EXISTING_APP_INTEGRATION_AUDIT.md` §3).

### 1.4 Emirates grouping

Per `WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` §4's approved priority order, all seven emirates appear in the Locations dropdown in this order:

1. Dubai (`LOC-AE-DU` / دبي)
2. Abu Dhabi (`LOC-AE-AZ` / أبوظبي)
3. Sharjah (`LOC-AE-SH` / الشارقة)
4. Ajman (`LOC-AE-AJ` / عجمان)
5. Ras Al Khaimah (`LOC-AE-RK` / رأس الخيمة)
6. Fujairah (`LOC-AE-FU` / الفجيرة)
7. Umm Al Quwain (`LOC-AE-UQ` / أم القيوين)

**Build-status note:** per `13_LOCATION_EXPANSION_ROADMAP.md` §0 and `07_EXISTING_APP_INTEGRATION_AUDIT.md` §4, only Dubai has a live page today; the other six have no page yet. Listing all seven here reflects the *approved target structure* this document defines, not current build completeness — per §4 of `WEBSITE_ARCHITECTURE_DECISION_REPORT.md`, six of these links cannot go live until their respective page is built and cleared for genuine local content, per §2 of the location roadmap. **This document does not authorize disabling or hiding the six unbuilt links** — that implementation-sequencing decision belongs to whoever executes the location-page build, not to this navigation document.

Community/Tier-level pages (e.g., Palm Jumeirah, Downtown Dubai) that exist in `SERVICE_AREAS.md`'s registry are **not included in the primary navigation dropdown** — per `13_LOCATION_EXPANSION_ROADMAP.md` §0, they are "a separate, later tier requiring their own SEO/ops quality checklist," out of scope for emirate-level navigation. They remain reachable via internal links from their parent emirate's page (§4 below), not from the global header.

A "View All Locations" link at the foot of the dropdown routes to `/locations` (the locations index page, already implemented).

### 1.5 CTA buttons

Per `00_HOMEPAGE_ARCHITECTURE.md` §02 (Header components) and `04_HOMEPAGE_COMPONENTS.md` `CMP-002`:

| CTA | Target | Basis |
|---|---|---|
| **Call** | `tel:+971585431766` | Phone is `Approved` per `02_BRAND/CONTACT_INFORMATION.md` |
| **WhatsApp** | `https://wa.me/message/JMZVJDFDQL3VD1` | WhatsApp is `Approved` per `CONTACT_INFORMATION.md` (verified 2026-07-27) — see the currency note in §6 below regarding an earlier, now-outdated finding that treated this value as unverified |
| **Book Now** | `/book` (route group already reserved per `02_FOLDER_STRUCTURE.md`, "gated until approved") | Per `07_WEBSITE/README.md`, `06_CUSTOMER_AND_SALES/BOOKING/` is "Not yet authored" — this CTA is architecturally reserved, not yet fully live for commercial bookings |

Per `12_DESIGN_SYSTEM/BUTTONS.md`'s "no more than one Primary button per section" rule (already cited precedent in `10_ANNOUNCEMENT_BAR_ARCHITECTURE.md` §8), **Book Now is the single Primary button**; Call and WhatsApp are Secondary/icon-style actions, consistent with `02_HOMEPAGE_UI_UX.md`'s Button section (Primary = "Drive bookings," Secondary = "Generate enquiries," WhatsApp Button = "Quick customer communication").

---

## 2. Mobile Navigation

### 2.1 Menu behavior

A slide-in or full-screen overlay menu triggered by a hamburger icon in the mobile header, consistent with `02_HOMEPAGE_UI_UX.md`'s Mobile First principle. It must not obstruct essential content on open (per `LUXURY_DESIGN_DIRECTION.md` §10's prohibition on "Pop-ups that obstruct essential content on arrival," applied here to the mobile menu overlay by the same logic).

### 2.2 Accordion sections

Services and Locations — flat dropdowns on desktop — become collapsible accordion sections on mobile, one per category:

- Services (accordion, expands to the same 3 category sub-groups as §1.3, each itself a nested accordion or scrollable sub-list)
- Locations (accordion, expands to the same 7-emirate list as §1.4, in the same priority order)

Home, About, Blog, and Contact remain flat, non-accordion links, since they have no sub-items.

### 2.3 Ordering

Same top-level order as desktop (§1.1): Home, Services, Locations, About, Blog, Contact — mobile does not reorder items relative to desktop, to avoid a user re-learning the menu structure between breakpoints.

### 2.4 CTA placement

Per `10_ANNOUNCEMENT_BAR_ARCHITECTURE.md` §2 and §10, the app already has an existing fixed-position `MobileCtaBar` component at the bottom of the viewport. **This document does not propose a second, competing mobile CTA bar** — the Call/WhatsApp/Book Now actions in §1.5 are surfaced through that existing component on mobile, not duplicated inside the slide-in menu itself, to avoid the exact "two independent fixed-position elements colliding" problem that document's §2 already had to solve once (`MobileCtaBar` and `ConsentBanner` coordinating via `bottom-20`/`bottom-0`). The in-menu list may still repeat simple text links to `/contact` and `/book` for completeness, but the primary tap targets for Call/WhatsApp/Book remain the existing bottom bar.

---

## 3. Global Elements

### 3.1 Logo

Company logo, linking to `/` (home), positioned at the leading edge (start, not hardcoded left) per `12_DESIGN_SYSTEM/TYPOGRAPHY.md`'s logical-properties RTL requirement — leading edge is the right side in Arabic (RTL), the left side in English (LTR).

### 3.2 Language switch

Per §5 below — a two-state toggle (Arabic / English) in the header, per `00_HOMEPAGE_ARCHITECTURE.md` §02's "Language Switcher" component. Switching preserves the current page (locale-prefixed route swap, e.g. `/ar/services/pest-control` ↔ `/en/services/pest-control`), not a reset to home, consistent with the locale-routing structure already implemented (`07_EXISTING_APP_INTEGRATION_AUDIT.md` §2).

### 3.3 Booking

Surfaced as the Book Now CTA (§1.5) and, once the customer portal is reached, as a "My Bookings" entry inside the account area (§3.4) — not as a separate top-level nav item, since Booking is an action (CTA), not a content section to browse.

### 3.4 Login

Per `08_AUTHENTICATION_ARCHITECTURE.md`, password authentication is already implemented in the live app, with a customer portal (account overview, profile, bookings, quotes, requests) already built (`07_EXISTING_APP_INTEGRATION_AUDIT.md` §3). The header therefore includes a **Login/Account** element: when signed out, a "Login" link/button to `/account/login`; when signed in, an account icon/avatar opening a small menu (Account Overview, My Bookings, My Quotes, Logout) rather than the full portal sidebar (`SIDEBAR_NAVIGATION.md` is explicitly scoped to the authenticated portal's own internal navigation, per `03_COMPONENT_STRATEGY.md` §5 — the public header's Login element is a single entry point into that portal, not a duplicate of its sidebar).

### 3.5 Contact actions

Call and WhatsApp (§1.5) plus a full **Contact** page link (§1.1, item 6) for the contact form, address (once approved — see §6), and map. No email `mailto:` link is proposed as a header-level CTA — email is `Approved` in `CONTACT_INFORMATION.md` but per that document's own available channels, phone and WhatsApp are the faster, more immediate contact methods appropriate for a persistent header element; email remains reachable from the Contact page.

---

## 4. SEO Considerations

### 4.1 Service discoverability

Every service with approved, indexable content (16 of 27, per §1.3) is reachable from the Services dropdown, the `/services` index page, and the sitemap — satisfying `05_SEO_IMPLEMENTATION_PLAN.md` §4's "every publishable page must be reachable from at least the relevant index page and the sitemap; avoid orphan pages." The 11 `noindex` entries are intentionally *not* linked from primary navigation (§1.3) but remain reachable from the `/services` index page's full catalog listing if that page chooses to show them as "coming soon" — a content-page decision, not a navigation decision, out of scope here.

### 4.2 Location discoverability

All seven emirates are reachable from the Locations dropdown regardless of build status (§1.4), satisfying discoverability for the target structure; each live emirate page cross-links to its own available services and, where they exist, its Tier 1/2 community pages — per `05_SEO_IMPLEMENTATION_PLAN.md` §4's rule that these cross-links are "generated from `SERVICE_MATRIX.md`, not hand-authored per page."

### 4.3 Internal linking principles

- No orphan pages: every page reachable from navigation, an index page, or the sitemap — never solely from a deep link.
- Cross-links between services and locations are generated from `SERVICE_MATRIX.md`, not manually authored per page (`05_SEO_IMPLEMENTATION_PLAN.md` §4), keeping the navigation and the link graph from drifting out of sync with approved coverage data.
- Navigation link labels match the page's actual `<h1>`/title content — no keyword-stuffed menu labels, per `LUXURY_DESIGN_DIRECTION.md` §10's prohibition on "keyword-stuffed headings."
- Breadcrumb schema (`05_SEO_IMPLEMENTATION_PLAN.md` §2) is derived from the route hierarchy this navigation defines (`/services/[serviceId]`, `/locations/[areaId]`) — the breadcrumb structure and the nav structure must describe the same hierarchy, never two different ones.

---

## 5. Bilingual Requirements

- **Arabic is primary** — the app's default locale (`defaultLocale = "ar"`, per `07_EXISTING_APP_INTEGRATION_AUDIT.md` §2), rendered RTL. **English is secondary**, rendered LTR at `/en/...`.
- Every navigation label (menu items, dropdown headers, CTA button text, "View All" links) is authored as a paired `{ ar, en }` string, matching the existing bilingual-content discipline (`i18n/messages/{ar,en}.json`) — no navigation item may exist in one language without its approved counterpart, per `PROJECT_MANIFEST.md`'s "Arabic and English are equal first-class languages."
- RTL mirroring: the entire menu order visually mirrors (leading edge = right in Arabic, left in English) using logical properties (`start-`/`end-`), not hardcoded `left`/`right` — per `12_DESIGN_SYSTEM/TYPOGRAPHY.md` and the existing `BrandPanel`/header/footer precedent cited in `10_ANNOUNCEMENT_BAR_ARCHITECTURE.md` §5.
- Directional vs. universal icons: a dropdown-caret or "next" arrow icon mirrors (`rtl:rotate-180`, the same established pattern already used for `ArrowRightIcon` on service cards, per `10_ANNOUNCEMENT_BAR_ARCHITECTURE.md` §5); a universal icon (hamburger, search, account/user icon) does not mirror, per `SIDEBAR_NAVIGATION.md`'s existing icon-mirroring rule.
- Emirate and service names render in their approved bilingual form exactly as recorded in `SERVICE_AREAS.md` and `SERVICE_CATALOG.md` (e.g., "أبوظبي" for Abu Dhabi, "الشارقة" for Sharjah) — never machine-translated at render time.

---

## 6. Currency Note — Contact Value Approval Status

`00_GOVERNANCE/WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §7 and `WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` §7 (both 2026-08-01, restating a finding from `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md` §11) treated the WhatsApp number, email, address, hours, and social links as unverified/`Pending`. **Checking the current canonical source directly for this document:** `02_BRAND/CONTACT_INFORMATION.md`'s own "Status" section now marks Phone, Website domain, WhatsApp, Email, Working hours (24/7), and Social profile URLs all `Approved` (verified 2026-07-23/27) — only "Emergency Service" availability remains `Pending`. This document's Call/WhatsApp CTAs (§1.5) are written against this current, `Approved` status. The physical-address question from the earlier audit is not resolved by this note — `LOCAL_SEO_PROFILE.md` was not re-checked here — and this document does not surface an address anywhere in the navigation, so that open item does not affect this document's content. This currency gap between the two governance documents and the current canonical source is flagged here for the Owner's awareness; reconciling those two documents' text is separate, not-yet-executed follow-up work, not performed by this document.

---

## What This Document Does Not Do

- Does not create any component, route, or line of code.
- Does not implement the menu, dropdown, accordion, or CTA bar it describes.
- Does not decide when the 11 excluded services or the 6 unbuilt emirate pages should go live — only that they are excluded/included as described until those separate decisions are made.
- Does not resolve the currency gap noted in §6 between the two prior governance documents and the current `CONTACT_INFORMATION.md` state.
- Does not modify `12_DESIGN_SYSTEM/COMPONENTS.md`'s component inventory, `SIDEBAR_NAVIGATION.md`, or any homepage document.

---

## Related Documents

- `00_GOVERNANCE/WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` — the approval this document fulfills (§5).
- `00_GOVERNANCE/WEBSITE_ARCHITECTURE_DECISION_REPORT.md` — the original gap identification (§5).
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `03_MARKET/SERVICE_AREAS.md` — sources for §1.3/§1.4.
- `02_BRAND/CONTACT_INFORMATION.md` — source for §1.5/§6.
- `07_WEBSITE/01_HOMEPAGE/00_HOMEPAGE_ARCHITECTURE.md`, `04_HOMEPAGE_COMPONENTS.md` — Header component baseline.
- `07_WEBSITE/IMPLEMENTATION/08_AUTHENTICATION_ARCHITECTURE.md` — Login element basis (§3.4).
- `07_WEBSITE/IMPLEMENTATION/10_ANNOUNCEMENT_BAR_ARCHITECTURE.md` — `MobileCtaBar` precedent (§2.4).
- `07_WEBSITE/IMPLEMENTATION/05_SEO_IMPLEMENTATION_PLAN.md` — internal linking principles (§4).

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-08-01 | Initial navigation architecture: desktop/mobile structure, global elements, SEO considerations, and bilingual requirements, per Owner approval in `WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` §5. No code or component created. |
