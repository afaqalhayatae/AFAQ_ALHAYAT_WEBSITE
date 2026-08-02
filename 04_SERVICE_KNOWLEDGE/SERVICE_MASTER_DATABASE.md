# Service Master Database

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — index only, does not itself approve any service for publication, booking, or field execution. Each service's own `README.md` Evidence Gate remains the governing status for that package.
- **Version:** 1.0
- **Prepared:** 2026-07-29
- **Depends on:** `SERVICE_CATALOG.md` (canonical service list/IDs), `SERVICE_MATRIX.md` (canonical coverage), `03_MARKET/SERVICE_AREAS.md` (canonical geography).

## Purpose

Single index of every service's production-readiness across four tracks: SEO, Booking, Page content, and Image assets. This document does not duplicate facts already owned elsewhere — it points to them. If a row here ever conflicts with `SERVICE_CATALOG.md` or `SERVICE_MATRIX.md`, those two remain authoritative and this file must be corrected, not the other way around.

**Scope note on Task 1's premise:** the originating request asked to scan "all existing service images and cards." A scan of every `assets/` subfolder under `04_SERVICE_KNOWLEDGE/` found real image files in exactly one place: `01_PEST_CONTROL/assets/` (2 files — see its own `05_IMAGE_METADATA.md`). Every other service's `assets/` subfolder structure exists but is empty. This table reflects that honestly rather than inventing image references for services that don't have any yet.

---

## Master Table

| Service ID | Service Name (EN) | Service Name (AR) | Category | Image(s) | SEO Data Status | Booking Data Status | Page Content Status | Knowledge Package Status |
|---|---|---|---|---|---|---|---|---|
| `SVC-PEST-CONTROL` | Pest Control | مكافحة الحشرات | Cleaning & Pest Control | 2 images (`assets/hero/`, `assets/service-cards/`) — see `01_PEST_CONTROL/05_IMAGE_METADATA.md` | Complete — `01_PEST_CONTROL/02_SEO_DATA.md` | Complete (draft) — `01_PEST_CONTROL/03_BOOKING_OPTIONS.md` | Complete — `01_PEST_CONTROL/06_PAGE_CONTENT.md` | ✅ Complete package — Review Required (Evidence Gate open) |
| `SVC-AC-MAINTENANCE` | AC Maintenance | صيانة التكييف | General Maintenance | None | Not started | Not started | Not started | Structurally complete draft |
| `SVC-GENERAL-CLEANING` | General Cleaning | التنظيف العام | Cleaning & Pest Control | None | Not started | Not started | Not started | Review-ready package |
| `SVC-DEEP-CLEANING` | Deep Cleaning | التنظيف العميق | Cleaning & Pest Control | None | Not started | Not started | Not started | ⚠ Blocked — facts pending owner scope decision |
| `SVC-WATER-TANK-CLEANING` | Water Tank Cleaning | تنظيف خزانات المياه | Cleaning & Pest Control | None | Not started | Not started | Not started | Review-ready package |
| `SVC-PLUMBING` | Plumbing | السباكة | General Maintenance | None | Not started | Not started | Not started | Structurally complete draft |
| `SVC-ELECTRICAL-MAINTENANCE` | Electrical Maintenance | الصيانة الكهربائية | General Maintenance | None | Not started | Not started | Not started | Structurally complete draft |
| `SVC-PAINTING` | Painting | الدهانات | General Maintenance | None | Not started | Not started | Not started | Structurally complete draft |
| `SVC-HANDYMAN` | Handyman Services | خدمات الصيانة العامة (هاندي مان) | General Maintenance | None | Not started | Not started | Not started | Structurally complete draft |
| `SVC-DRAIN-UNBLOCKING` | Drain Unblocking | تسليك المجاري | Drainage & Water Protection | None | Not started | Not started | Not started | Structurally complete draft |
| `SVC-WATERPROOFING` | Waterproofing | العزل المائي | Drainage & Water Protection | None | Not started | Not started | Not started | Structurally complete draft |
| `SVC-WATER-LEAK-DETECTION` | Water Leak Detection | كشف تسربات المياه | Drainage & Water Protection | None | Not started | Not started | Not started | Structurally complete draft |

**Arabic service names:** standard industry terminology, not yet run through a dedicated Owner linguistic-review pass the way `01_PEST_CONTROL/CONTENT_AR.md`'s title was (confirmed against that file). Treat as accurate-but-unreviewed pending the same review the rest of each package still needs.

**Coverage (all rows):** all 7 emirates (Abu Dhabi, Dubai, Sharjah, Ajman, Umm Al Quwain, Ras Al Khaimah, Fujairah) per `SERVICE_MATRIX.md` — approved at emirate level only; booking systems must still confirm date/time/scope per service.

**Status legend:**
- **Not started** — no `0X_*.md` file created yet for that track.
- **Complete (draft)** — file exists with real content sourced from this repository's canonical documents; still carries the same Evidence Gate / "Review Required" status as the rest of its package until the Owner approves it.
- **Blocked** — cannot be completed until a named upstream decision is made.

---

## Production Progress (this batch)

Of 12 catalog services, **1 (`SVC-PEST-CONTROL`) has a complete `01`–`06` file set** as of this update. The remaining 11 are queued — see `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/` for the file structure and sourcing approach to be replicated per service. This is disclosed here rather than implied complete, per this repository's no-fabrication standard.

---

## Related Documents

- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` — canonical service list and IDs
- `04_SERVICE_KNOWLEDGE/SERVICE_MATRIX.md` — canonical coverage
- `04_SERVICE_KNOWLEDGE/BOOKING_SERVICE_CATALOG.md` — booking-oriented grouping
- `03_MARKET/SERVICE_AREAS.md` — canonical geography
