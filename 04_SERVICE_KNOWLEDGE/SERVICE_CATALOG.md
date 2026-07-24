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
| `SVC-PEST-CONTROL` | Pest Control | Cleaning & Pest Control | ✅ Complete — [`01_PEST_CONTROL/`](01_PEST_CONTROL/) |
| `SVC-AC-MAINTENANCE` | AC Maintenance | General Maintenance | Structurally complete draft — [`02_AC_MAINTENANCE/`](02_AC_MAINTENANCE/) |
| `SVC-GENERAL-CLEANING` | General Cleaning | Cleaning & Pest Control | Review-ready package — [`03_GENERAL_CLEANING/`](03_GENERAL_CLEANING/) |
| `SVC-DEEP-CLEANING` | Deep Cleaning | Cleaning & Pest Control | Structurally complete; facts blocked pending owner scope — [`04_DEEP_CLEANING/`](04_DEEP_CLEANING/) |
| `SVC-WATER-TANK-CLEANING` | Water Tank Cleaning | Cleaning & Pest Control | Review-ready package — [`05_WATER_TANK_CLEANING/`](05_WATER_TANK_CLEANING/) |
| `SVC-PLUMBING` | Plumbing | General Maintenance | Structurally complete draft — [`06_PLUMBING/`](06_PLUMBING/) |
| `SVC-ELECTRICAL-MAINTENANCE` | Electrical Maintenance | General Maintenance | Structurally complete draft — [`07_ELECTRICAL_MAINTENANCE/`](07_ELECTRICAL_MAINTENANCE/) |
| `SVC-PAINTING` | Painting | General Maintenance | Structurally complete draft — [`08_PAINTING/`](08_PAINTING/) |
| `SVC-HANDYMAN` | Handyman Services | General Maintenance | Structurally complete draft — [`09_HANDYMAN/`](09_HANDYMAN/) |
| `SVC-DRAIN-UNBLOCKING` | Drain Unblocking | Drainage & Water Protection | Structurally complete draft — [`10_DRAIN_UNBLOCKING/`](10_DRAIN_UNBLOCKING/) |
| `SVC-WATERPROOFING` | Waterproofing | Drainage & Water Protection | Structurally complete draft — [`11_WATERPROOFING/`](11_WATERPROOFING/) |
| `SVC-WATER-LEAK-DETECTION` | Water Leak Detection | Drainage & Water Protection | Structurally complete draft — [`12_WATER_LEAK_DETECTION/`](12_WATER_LEAK_DETECTION/) |

---

# Categories

Per approved decision 5 (`00_GOVERNANCE/DECISION_LOG.md`), AFAQ Alhayat covers two service lines, both in scope:

- **Cleaning & Pest Control** — Pest Control, General Cleaning, Deep Cleaning, Water Tank Cleaning.
- **General Maintenance** — AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman Services.
- **Drainage & Water Protection** — Drain Unblocking, Waterproofing, Water Leak Detection.

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
Package maturity remains independent: Pest Control is structurally complete but
requires evidence review, General
Cleaning and Water Tank Cleaning are review-ready, other packages require
owner and competent evidence review, and Deep Cleaning requires owner scope.
Drain Unblocking, Waterproofing, and Water Leak Detection are owner-confirmed
services whose technical scope must be approved before detailed publication.
