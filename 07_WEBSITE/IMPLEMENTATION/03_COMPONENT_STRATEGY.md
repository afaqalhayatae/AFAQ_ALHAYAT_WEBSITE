# Component Strategy

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only, no components built by this document
- **Version:** 1.0
- **Prepared:** 2026-07-27
- **Depends on:** `12_DESIGN_SYSTEM/COMPONENTS.md`, `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md`, `12_DESIGN_SYSTEM/SIDEBAR_NAVIGATION.md`, `01_APPLICATION_ARCHITECTURE.md`

## Note on scope

This document translates the already-approved component inventory in `12_DESIGN_SYSTEM/COMPONENTS.md` into a React/Next.js implementation strategy. It does not invent new components, and it does not write component code.

`12_DESIGN_SYSTEM/COMPONENTS.md` and `12_DESIGN_SYSTEM/COLORS.md` each contain a "WordPress Implementation" section referencing Gutenberg Blocks. Per the ratified stack (`00_GOVERNANCE/TECH_STACK.md`, `05_TECHNOLOGY_FINAL_DECISION.md`), those sections are **not applied** — every component below is implemented as a React component, never a Gutenberg block or WordPress theme component.

---

## 1. Component Inventory (from `12_DESIGN_SYSTEM/COMPONENTS.md`)

| Design system component | React component (proposed) | Consumers |
|---|---|---|
| Header Component | `<Header />` | All public pages |
| Navigation Component | `<MainNav />`, `<MobileNav />` | All public pages |
| Hero Component | `<Hero />` | Homepage, service pages, location pages |
| CTA Component | `<CtaSection />` | Homepage, service pages |
| Service Grid Component | `<ServiceGrid />`, `<ServiceCard />` | Homepage, service index |
| Location Component | `<LocationList />`, `<LocationCard />` | Homepage, location pages |
| Booking Widget Component | `<BookingWidget />` (multi-step) | Booking flow — gated, see below |
| Review Component | `<ReviewList />`, `<ReviewCard />` | Homepage, service pages |
| FAQ Component | `<FaqAccordion />` | Homepage, service pages (paired with FAQ schema) |
| Gallery Component | `<MediaGallery />` | Service pages, About |
| Map Component | `<CoverageMap />` | Homepage, location pages, contact |
| Contact Component | `<ContactBlock />` | Header, Footer, Contact page |
| Footer Component | `<Footer />` | All public pages |
| Dashboard Card | `<DashboardCard />` | Future admin/portal only |
| Data Table | `<DataTable />` | Future admin/portal only |
| Status Badge | `<StatusBadge />` | Future admin/portal, booking status |

Every component is built once in `src/components/` and reused across all page types, per the design system's own "golden rule" (`12_DESIGN_SYSTEM/README.md`: *"If a new component cannot be reused multiple times, redesign it until it becomes reusable"*).

---

## 2. Design Token Integration

| Token source | Implementation target |
|---|---|
| `12_DESIGN_SYSTEM/COLORS.md` | Tailwind `theme.colors` — see the color-token conflict flagged in `01_APPLICATION_ARCHITECTURE.md` §6 before finalizing values. |
| `12_DESIGN_SYSTEM/TYPOGRAPHY.md` | Tailwind `theme.fontFamily` (`Noto Kufi Arabic` for `:lang(ar)`, `Inter` for `:lang(en)`), `theme.fontSize` using the documented `clamp()` scale (Display, H1–H6, Lead, Body, Small), `theme.fontWeight` restricted to 400/500/600/700 only. |
| `12_DESIGN_SYSTEM/SPACING.md` | Tailwind `theme.spacing` on the 8px-multiple scale (8/16/24/32/40/48/64/96px) — no arbitrary values. |
| `12_DESIGN_SYSTEM/GRID.md` | Tailwind `theme.screens`/container config: mobile <768px (4-col), tablet 768–1199px (8-col), desktop ≤1200px container (12-col), large desktop 1440px container; gutters 16/20/24px respectively. |
| `12_DESIGN_SYSTEM/ICONS.md` | Single icon set via Lucide React (`TECH_STACK.md`), consistent stroke weight — no mixed icon families per the Luxury Design Direction. |

---

## 3. Mandatory Interaction States

Per `LUXURY_DESIGN_DIRECTION.md` §5 and `SIDEBAR_NAVIGATION.md` §7, every interactive component's implementation contract must include, not as an afterthought:

- Default, hover, keyboard-focus, active/pressed, disabled.
- Loading and error-recovery states for anything backed by remote data (booking submission, form validation).
- Success state for confirmations (e.g., booking submitted).
- Reduced-motion-respecting transitions, typically 150–250ms.

Color alone must never carry meaning (e.g., active nav state needs `aria-current="page"` plus a visible surface/indicator change, not color alone).

---

## 4. Bilingual / RTL Implementation Approach

- Use CSS logical properties (`margin-inline-start`, not `margin-left`) wherever Tailwind's RTL-aware utilities apply, so components mirror correctly under `dir="rtl"` without duplicate component variants.
- Directional icons (chevrons, arrows) mirror with direction; universal icons (search, close) do not — per `SIDEBAR_NAVIGATION.md` §4.
- Phone numbers, URLs, and mixed-direction content require explicit bidirectional (`dir="auto"` / Unicode isolation) handling, per `TYPOGRAPHY.md`.
- Every component must be reviewed independently in Arabic and English — not assumed to mirror correctly by default. This is a required step in the Design Acceptance Gate (`LUXURY_DESIGN_DIRECTION.md` §11), not optional polish.

---

## 5. Sidebar Navigation — Scope Boundary

`SIDEBAR_NAVIGATION.md` explicitly reserves the sidebar pattern for **authenticated portals, dashboards, and complex directories** — not the public marketing site, which uses `<Header />` + `<MobileNav />`. The component strategy respects this boundary: `<SidebarNav />` is only imported inside the `(portal)` route group described in `02_FOLDER_STRUCTURE.md`, never on public pages.

---

## 6. Accessibility Baked into Component Contracts

Every component's acceptance criteria (not a separate audit pass) includes, per `99_STANDARDS/ACCESSIBILITY_STANDARD.md` and `12_DESIGN_SYSTEM/ACCESSIBILITY.md`:

- Semantic HTML and correct landmark roles.
- Visible keyboard focus, logical tab order.
- Minimum touch target `44×44px`.
- WCAG 2.2 AA contrast on every state, in both languages.
- No information conveyed by color or icon alone.

---

## 7. Component Build Priority

Matches the phased content plan in `02_WEBSITE_IMPLEMENTATION_PLAN.md`:

1. `<Header />`, `<Footer />`, `<MainNav />`, `<Hero />`, `<ServiceCard />`/`<ServiceGrid />`, `<FaqAccordion />`, `<CtaSection />` — needed for Homepage and the first service page (Pest Control).
2. `<LocationCard />`/`<LocationList />`, `<CoverageMap />` — needed for emirate-level location pages.
3. `<ReviewList />`, `<MediaGallery />` — needed once verified review/media evidence exists (per Luxury Design Direction's evidence-before-claims rule).
4. `<BookingWidget />` — built but not wired to a live submission path until `06_CUSTOMER_AND_SALES/BOOKING/` clears Draft status.
5. `<DashboardCard />`, `<DataTable />`, `<StatusBadge />`, `<SidebarNav />` — portal/admin phase, later.

---

## What This Document Does Not Do

- It does not write any component code, story, or test.
- It does not resolve the color-token conflict — see `01_APPLICATION_ARCHITECTURE.md` §6.
- It does not select a specific icon package version or Tailwind plugin — implementation-time detail within the approved stack.

---

## Related Documents

- `01_APPLICATION_ARCHITECTURE.md`
- `02_FOLDER_STRUCTURE.md`
- `04_CONTENT_INTEGRATION_PLAN.md`
