# Folder Structure

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only, no folders or files created by this document
- **Version:** 1.0
- **Prepared:** 2026-07-27
- **Depends on:** `01_APPLICATION_ARCHITECTURE.md`

## Note on scope

This document describes the proposed folder structure for the future, separate application repository. It does not create that repository, and it does not create or rename any folder inside `AFAQ_ALHAYAT_ENTERPRISE_KNOWLEDGE`. Nothing in this knowledge repository's structure changes as a result of this plan.

---

## 1. Two-Repository Model

| Repository | Contents | Status |
|---|---|---|
| `AFAQ_ALHAYAT_ENTERPRISE_KNOWLEDGE` (this repo) | Governed facts, standards, this implementation plan | Exists |
| `afaqalhayatae-web` (proposed name, Owner's choice) | Next.js application code, Prisma schema, tests, CI config | Not yet created |

Keeping them separate preserves `PROJECT_MANIFEST.md`'s "Out of Scope: Source code implementation" boundary and lets the knowledge repository keep evolving (new services, new decisions) without touching application deployment history, and vice versa.

---

## 2. Proposed Application Repository Structure

```text
afaqalhayatae-web/
├── app/
│   ├── [locale]/                      # "ar" | "en" — bilingual route root
│   │   ├── (marketing)/
│   │   │   ├── page.tsx               # Homepage — 07_WEBSITE/01_HOMEPAGE/*
│   │   │   ├── about/                 # 07_WEBSITE/02_ABOUT ← 01_BUSINESS/COMPANY_PROFILE.md
│   │   │   ├── services/
│   │   │   │   ├── page.tsx           # Service index — 04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md
│   │   │   │   └── [serviceId]/       # One route per SVC-<NAME>
│   │   │   ├── locations/
│   │   │   │   └── [areaId]/          # One route per approved LOC-AE-<EMIRATE>[-<AREA>]
│   │   │   ├── blog/
│   │   │   ├── contact/
│   │   │   └── legal/[slug]/
│   │   ├── (booking)/
│   │   │   └── book/                  # 06_CUSTOMER_AND_SALES/BOOKING/ — gated until approved
│   │   ├── (portal)/                  # Authenticated customer portal — sidebar nav per SIDEBAR_NAVIGATION.md
│   │   │   ├── layout.tsx
│   │   │   ├── overview/
│   │   │   ├── bookings/
│   │   │   └── requests/
│   │   └── not-found.tsx / error.tsx  # 07_WEBSITE/09_ERROR_PAGES
│   └── api/
│       ├── bookings/route.ts          # Booking Request entity, Approval-gated
│       ├── enquiries/route.ts         # Enquiry entity
│       ├── consent/route.ts           # Consent entity
│       └── webhooks/                  # Test-mode adapters only until live-approved
│
├── src/
│   ├── components/
│   │   ├── ui/                        # Button, Card, FormField, Badge — from 12_DESIGN_SYSTEM/COMPONENTS.md
│   │   ├── sections/                  # Hero, ServiceGrid, Testimonials, FAQ, CTA
│   │   ├── navigation/                # Header, MobileNav, SidebarNav (portal only)
│   │   └── booking/                   # BookingWidget and its steps
│   ├── content/                       # Content adapter — see 04_CONTENT_INTEGRATION_PLAN.md
│   │   ├── services.ts                # Reads/mirrors 04_SERVICE_KNOWLEDGE structure
│   │   ├── locations.ts               # Reads/mirrors 03_MARKET/SERVICE_AREAS.md
│   │   ├── brand.ts                   # Reads/mirrors 02_BRAND/CONTACT_INFORMATION.md (blocked-field aware)
│   │   └── seo.ts                     # Reads/mirrors SEO_AI.md + SCHEMA_STRATEGY.md
│   ├── lib/
│   │   ├── prisma.ts
│   │   ├── auth.ts                    # Placeholder — provider not yet chosen (see architecture doc §5)
│   │   └── i18n.ts
│   └── styles/
│       └── tokens.css / tailwind.config.ts   # From 12_DESIGN_SYSTEM/{COLORS,TYPOGRAPHY,SPACING,GRID}.md
│
├── prisma/
│   └── schema.prisma                  # Mirrors 08_DIGITAL_SYSTEMS/DATA_MODEL.md entities exactly
│
├── public/
│   └── (optimized brand/media assets, per 02_BRAND/BRAND_IMAGES.md and LUXURY_DESIGN_DIRECTION.md media rules)
│
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
│
├── .github/workflows/                 # CI — lint, typecheck, test (per TECH_STACK.md "GitHub Actions (planned)")
├── tailwind.config.ts
├── next.config.js
├── package.json
└── README.md                          # Must state: this repo implements, does not own, business facts
```

---

## 3. Folder-to-Governance Mapping

| Application folder | Owning knowledge-repo source | Notes |
|---|---|---|
| `app/[locale]/(marketing)/services/[serviceId]` | `04_SERVICE_KNOWLEDGE/<NN_SERVICE>/*` | One route per catalog entry; publishable state gated by package maturity (see `03_CONTENT_TO_WEBSITE_MAPPING.md`). |
| `app/[locale]/(marketing)/locations/[areaId]` | `03_MARKET/SERVICE_AREAS.md` | Only registry `area_id` values generate routes — no invented locations. |
| `app/[locale]/(marketing)/about` | `01_BUSINESS/COMPANY_PROFILE.md`, `VISION.md`, `MISSION.md` | |
| `app/[locale]/(marketing)/contact`, Header/Footer contact blocks | `02_BRAND/CONTACT_INFORMATION.md` | Blocked-field pattern mandatory. |
| `app/[locale]/(booking)/book` | `06_CUSTOMER_AND_SALES/BOOKING/` | Held until Draft status clears. |
| `app/[locale]/(portal)/*` | `08_DIGITAL_SYSTEMS/CRM_AND_PORTALS.md` | Uses `SIDEBAR_NAVIGATION.md`, not the public header. |
| `src/styles/tokens.css` | `12_DESIGN_SYSTEM/{COLORS,TYPOGRAPHY,SPACING,GRID}.md` | Subject to the color-token conflict flagged in `01_APPLICATION_ARCHITECTURE.md` §6. |
| `prisma/schema.prisma` | `08_DIGITAL_SYSTEMS/DATA_MODEL.md` | No new entities beyond the approved model without a governance update. |

---

## 4. What This Document Does Not Do

- It does not create `afaqalhayatae-web` or any file/folder within it.
- It does not modify this knowledge repository's structure.
- It does not select the exact route-grouping library conventions beyond illustrating intent — final routing detail is an implementation-time decision within the approved Next.js App Router pattern.

---

## Related Documents

- `01_APPLICATION_ARCHITECTURE.md`
- `03_COMPONENT_STRATEGY.md`
- `04_CONTENT_INTEGRATION_PLAN.md`
