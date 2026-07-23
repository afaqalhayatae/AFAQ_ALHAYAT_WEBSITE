# Service Catalog

## Purpose

The official list of services offered by AFAQ Alhayat, each with a stable identifier per `99_STANDARDS/NAMING_CONVENTIONS.md`. This is the single source of truth for "what services exist" — website, CRM, booking, AI, and analytics must reference these IDs rather than maintain their own lists, per `SYSTEM_ARCHITECTURE.md` Sec. 6.

Source: [`01_BUSINESS/COMPANY_PROFILE.md`](../01_BUSINESS/COMPANY_PROFILE.md) "Core Services" (canonical, approved per decision 1 in `00_GOVERNANCE/DECISION_LOG.md`).

---

# Services

| ID | Name | Category | Knowledge package status |
|---|---|---|---|
| `SVC-PEST-CONTROL` | Pest Control | Cleaning & Pest Control | ✅ Complete — [`01_PEST_CONTROL/`](01_PEST_CONTROL/) |
| `SVC-AC-MAINTENANCE` | AC Maintenance | General Maintenance | Draft source exists, package not yet built |
| `SVC-GENERAL-CLEANING` | General Cleaning | Cleaning & Pest Control | Draft source exists, package not yet built |
| `SVC-DEEP-CLEANING` | Deep Cleaning | Cleaning & Pest Control | No dedicated draft source found; scope confirmed by Company Profile only |
| `SVC-WATER-TANK-CLEANING` | Water Tank Cleaning | Cleaning & Pest Control | Draft source exists, package not yet built |
| `SVC-PLUMBING` | Plumbing | General Maintenance | Draft source exists, package not yet built |
| `SVC-ELECTRICAL-MAINTENANCE` | Electrical Maintenance | General Maintenance | Draft source exists, package not yet built |
| `SVC-PAINTING` | Painting | General Maintenance | Draft source exists, package not yet built |
| `SVC-HANDYMAN` | Handyman Services | General Maintenance | Draft source exists, package not yet built |

---

# Categories

Per approved decision 5 (`00_GOVERNANCE/DECISION_LOG.md`), AFAQ Alhayat covers two service lines, both in scope:

- **Cleaning & Pest Control** — Pest Control, General Cleaning, Deep Cleaning, Water Tank Cleaning.
- **General Maintenance** — AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman Services.

---

# Draft source material (not yet approved packages)

Held pending a folder-numbering convention decision (see `00_GOVERNANCE/MIGRATION/VALIDATION_REPORT.md` Sec. 3):

- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/01_AC_MAINTENANCE.md`
- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/02_CLEANING_SERVICES.md`
- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/04_PLUMBING.md`
- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/05_ELECTRICAL_MAINTENANCE.md`
- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/06_PAINTING_SERVICES.md`
- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/07_HANDYMAN_SERVICES.md`
- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/08_WATER_TANK_CLEANING.md`

These are unapproved drafts — do not treat their content as canonical until they are reviewed and formally migrated into a `04_SERVICE_KNOWLEDGE/<NN_SERVICE>/` package following `99_STANDARDS/SERVICE_TEMPLATE.md`.

Two superseded overview drafts that informed this catalog's reconciliation are preserved at `98_LEGACY_ARCHIVE/00_START/.../00_SERVICES_OVERVIEW.md` and `98_LEGACY_ARCHIVE/07_WEBSITE/03_SERVICES/00_SERVICES_OVERVIEW.md` (see `98_LEGACY_ARCHIVE/ARCHIVE_MANIFEST.csv`).

---

# Status

Draft — catalog structure and IDs are established; 8 of 9 services still need their full knowledge package authored from the held draft material after review.
