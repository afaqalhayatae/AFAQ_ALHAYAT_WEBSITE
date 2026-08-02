# Service Catalog

## Purpose

The official list of services offered by AFAQ Alhayat, each with a stable identifier per `99_STANDARDS/NAMING_CONVENTIONS.md`. This is the single source of truth for "what services exist" — website, CRM, booking, AI, and analytics must reference these IDs rather than maintain their own lists, per `SYSTEM_ARCHITECTURE.md` Sec. 6.

Source: [`01_BUSINESS/COMPANY_PROFILE.md`](../01_BUSINESS/COMPANY_PROFILE.md) "Core Services" (canonical, approved per decision 1 in `00_GOVERNANCE/DECISION_LOG.md`).

On 2026-07-23 the business owner confirmed that every service in this catalog
is currently offered across all seven UAE emirates. Coverage is implemented
through `SERVICE_MATRIX.md`; this catalog does not duplicate location data.

---

# Services

| ID | Name | Category | Knowledge package status |
|---|---|---|---|
| `SVC-PEST-CONTROL` | Pest Control | Cleaning & Pest Control | ✅ Approved 2026-07-31 (Owner-approved for publication) — [`01_PEST_CONTROL/`](01_PEST_CONTROL/) |
| `SVC-AC-MAINTENANCE` | AC Maintenance | General Maintenance | ✅ Approved 2026-07-31 (Service Completion Phase, general operational content) — [`02_AC_MAINTENANCE/`](02_AC_MAINTENANCE/) |
| `SVC-GENERAL-CLEANING` | General Cleaning | Cleaning & Pest Control | ✅ Approved 2026-07-31 (Service Completion Phase, general operational content) — [`03_GENERAL_CLEANING/`](03_GENERAL_CLEANING/) |
| `SVC-DEEP-CLEANING` | Deep Cleaning | Cleaning & Pest Control | ✅ Approved 2026-07-31 (Service Completion Phase, general operational content) — [`04_DEEP_CLEANING/`](04_DEEP_CLEANING/) |
| `SVC-WATER-TANK-CLEANING` | Water Tank Cleaning | Cleaning & Pest Control | ✅ Approved 2026-07-31 (Service Completion Phase, general operational content) — [`05_WATER_TANK_CLEANING/`](05_WATER_TANK_CLEANING/) |
| `SVC-PLUMBING` | Plumbing | General Maintenance | ✅ Approved 2026-07-31 (Service Completion Phase, general operational content) — [`06_PLUMBING/`](06_PLUMBING/) |
| `SVC-ELECTRICAL-MAINTENANCE` | Electrical Maintenance | General Maintenance | ✅ Approved 2026-07-31 (Service Completion Phase, general operational content) — [`07_ELECTRICAL_MAINTENANCE/`](07_ELECTRICAL_MAINTENANCE/) |
| `SVC-PAINTING` | Painting | General Maintenance | ✅ Approved 2026-07-31 (Service Completion Phase, general operational content) — [`08_PAINTING/`](08_PAINTING/) |
| `SVC-HANDYMAN` | Handyman Services | General Maintenance | ✅ Content approved 2026-07-31; still no real card image (excluded from website grids until one exists) — [`09_HANDYMAN/`](09_HANDYMAN/) |
| `SVC-DRAIN-UNBLOCKING` | Drain Unblocking | Drainage & Water Protection | ✅ Approved 2026-07-31 (Service Completion Phase, general operational content) — [`10_DRAIN_UNBLOCKING/`](10_DRAIN_UNBLOCKING/) |
| `SVC-WATERPROOFING` | Waterproofing | Drainage & Water Protection | ✅ Content approved 2026-07-31; card image pulled same day (baked-in AI-rendering typo), excluded from website grids until a real replacement photo exists — [`11_WATERPROOFING/`](11_WATERPROOFING/) |
| `SVC-WATER-LEAK-DETECTION` | Water Leak Detection | Drainage & Water Protection | ✅ Approved 2026-07-31 (Service Completion Phase, general operational content) — [`12_WATER_LEAK_DETECTION/`](12_WATER_LEAK_DETECTION/) |
| `SVC-VILLA-CLEANING` | Villa Cleaning | Cleaning & Pest Control | ✅ Approved 2026-07-31 — new service, content authored directly in `afaqalhayatae-app/src/data/SERVICE_DATABASE.json`; no dedicated knowledge-base folder created yet (documentation-parity gap, tracked in `docs/SERVICE_COMPLETION_MATRIX.md`) |
| `SVC-OFFICE-CLEANING` | Office Cleaning | Cleaning & Pest Control | ✅ Approved 2026-07-31 — same as Villa Cleaning above; no dedicated knowledge-base folder yet |
| `SVC-POST-CONSTRUCTION-CLEANING` | Post-Construction Cleaning | Cleaning & Pest Control | ✅ Approved 2026-07-31 — same as Villa Cleaning above; no dedicated knowledge-base folder yet |
| `SVC-CARPET-UPHOLSTERY-CLEANING` | Carpet & Upholstery Cleaning | Cleaning & Pest Control | ✅ Approved 2026-07-31 — same as Villa Cleaning above; no dedicated knowledge-base folder yet |
| `SVC-CCTV-INSTALLATION` | CCTV Installation | General Maintenance | ⚠ Structural entry only (2026-07-31, Service Expansion Phase) — catalog/SEO/i18n in place, no image (requested asset never found), no content yet |
| `SVC-SMART-HOME-INSTALLATION` | Smart Home Installation | General Maintenance | ⚠ Structural entry + image (2026-07-31) — catalog/SEO/i18n/card image in place, no full content yet |
| `SVC-SWIMMING-POOL-MAINTENANCE` | Swimming Pool Maintenance | General Maintenance | ⚠ Structural entry + image (2026-07-31) — same as Smart Home Installation |
| `SVC-KITCHEN-INSTALLATION` | Kitchen Installation | General Maintenance | ⚠ Structural entry + image (2026-07-31) — same as Smart Home Installation |
| `SVC-INTERIOR-DECORATION` | Interior Decoration | General Maintenance | ⚠ Structural entry + image (2026-07-31) — same as Smart Home Installation |
| `SVC-INTERLOCK-INSTALLATION` | Interlock Installation | General Maintenance | ⚠ Structural entry + image (2026-07-31) — same as Smart Home Installation |
| `SVC-LIGHTING-MAINTENANCE` | Lighting Maintenance | General Maintenance | ⚠ Structural entry + image (2026-07-31) — same as Smart Home Installation |
| `SVC-WOOD-ALTERNATIVE-INSTALLATION` | Wood Alternative Installation | General Maintenance | ⚠ Structural entry + image (2026-07-31) — same as Smart Home Installation |
| `SVC-WALLPAPER-INSTALLATION` | Wallpaper Installation | General Maintenance | ⚠ Structural entry + image (2026-07-31) — same as Smart Home Installation |
| `SVC-THERMAL-INSULATION` | Thermal Insulation | General Maintenance | ⚠ Structural entry + image (2026-07-31) — distinct from Waterproofing (water-ingress only, decision 19); same status as Smart Home Installation otherwise |
| `SVC-ROOFTOP-SPACE-UTILIZATION` | Rooftop Space Utilization | General Maintenance | ⚠ Structural entry + image (2026-07-31) — same as Smart Home Installation |

---

# Categories

Per approved decision 5 (`00_GOVERNANCE/DECISION_LOG.md`), AFAQ Alhayat covers two service lines, both in scope:

- **Cleaning & Pest Control** — Pest Control, General Cleaning, Deep Cleaning, Water Tank Cleaning, Villa Cleaning, Office Cleaning, Post-Construction Cleaning, Carpet & Upholstery Cleaning.
- **General Maintenance** — AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman Services, CCTV Installation, Smart Home Installation, Swimming Pool Maintenance, Kitchen Installation, Interior Decoration, Interlock Installation, Lighting Maintenance, Wood Alternative Installation, Wallpaper Installation, Thermal Insulation, Rooftop Space Utilization.
- **Drainage & Water Protection** — Drain Unblocking, Waterproofing, Water Leak Detection.

Villa Cleaning, Office Cleaning, Post-Construction Cleaning, and Carpet & Upholstery Cleaning were added 2026-07-31 per the Owner's Service Completion Phase order (see `00_GOVERNANCE/DECISION_LOG.md` #38). CCTV Installation, Smart Home Installation, Swimming Pool Maintenance, Kitchen Installation, Interior Decoration, Interlock Installation, Lighting Maintenance, Wood Alternative Installation, Wallpaper Installation, Thermal Insulation, and Rooftop Space Utilization were added 2026-07-31 per the Owner's Service Expansion Phase order (see `00_GOVERNANCE/DECISION_LOG.md` #39) — the catalog now has 27 services, not 12.

---

# Draft package policy

The seven migrated service drafts are preserved as `SOURCE_DRAFT.md` inside
their assigned packages. They remain non-authoritative until reviewed and
converted into the document set required by
`99_STANDARDS/SERVICE_TEMPLATE.md`. Deep Cleaning has no source draft and is
explicitly blocked pending owner scope.

Two superseded overview drafts that informed this catalog's reconciliation are preserved at `98_LEGACY_ARCHIVE/00_START/.../00_SERVICES_OVERVIEW.md` and `98_LEGACY_ARCHIVE/07_WEBSITE/03_SERVICES/00_SERVICES_OVERVIEW.md` (see `98_LEGACY_ARCHIVE/ARCHIVE_MANIFEST.csv`).

---

# Status

Approved service list — stable service IDs and package paths are established.
As of 2026-07-31 (Service Completion Phase, DECISION_LOG #38), all 16 services
have Owner-approved, general-operational-knowledge content published on the
website (`afaqalhayatae-app`), with two open, non-content items: Handyman has
no real card image yet (page complete, excluded from grids until one exists),
and Waterproofing's only card image was pulled the same day for a baked-in
AI-rendering defect (also excluded from grids pending a real replacement
photo). No price, warranty, license, certification, or response-time claim
was added anywhere in this content pass — see each package's `CONTENT_EN.md`
Evidence Gate section, which remains open for those specific fact categories.
Full detail and a per-service checklist is tracked in
`afaqalhayatae-app/docs/SERVICE_COMPLETION_MATRIX.md`.

A further 11 services were added 2026-07-31 (Service Expansion Phase,
DECISION_LOG #39) as structural entries only: catalog ID/slug/category,
bilingual name, and SEO title/meta description/keywords are in place for
all 11, and 10 of the 11 also have an Owner-approved real card image
(CCTV Installation has none — the requested asset was never located).
None of the 11 has full page content (overview, scope, process, benefits,
safety, FAQ) yet, so none is in the website's `APPROVED_SERVICE_CONTENT_SLUGS`
and all 11 remain `noindex` pending a future content phase — tracked in
`afaqalhayatae-app/docs/VISUAL_ASSET_MASTER_PLAN.md` and
`afaqalhayatae-app/docs/SERVICE_COMPLETION_MATRIX.md`.
