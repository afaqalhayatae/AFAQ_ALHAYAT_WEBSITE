# Booking Service Catalog

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — preparation for future booking-system integration. Not connected to any live booking system, website, or CRM.
- **Version:** 1.0
- **Prepared:** 2026-07-29
- **Depends on:** `SERVICE_CATALOG.md`, `SERVICE_MATRIX.md`, `03_MARKET/SERVICE_AREAS.md`.

## Purpose

Groups every catalog service by category for booking-flow design (category picker → service picker → detail fields). Per-service dropdown/field detail lives in each service's own `03_BOOKING_OPTIONS.md` (currently built for Pest Control only — see `SERVICE_MASTER_DATABASE.md` for what's built vs. pending).

## Note on category grouping

The request that produced this document suggested grouping services as "Maintenance, Cleaning, Pest Control, Landscape, Outdoor Services, Decoration, Security Systems." Checked against `SERVICE_CATALOG.md` — the only source of truth for what AFAQ Alhayat actually offers — **the company has no Landscape, Outdoor Services, Decoration, or standalone Security Systems service**, and its actual category structure is three groups, not seven. Rather than invent booking categories the business doesn't offer, this catalog uses the real three: **Cleaning & Pest Control**, **General Maintenance**, and **Drainage & Water Protection**. If the Owner wants to add new service lines (landscaping, security systems, etc.), that starts with a `SERVICE_CATALOG.md` decision, not a booking-catalog entry.

---

## Category: Cleaning & Pest Control

| Service ID | Service Name (EN) | Service Name (AR) | Booking Status |
|---|---|---|---|
| `SVC-PEST-CONTROL` | Pest Control | مكافحة الحشرات | Ready (draft) — see `01_PEST_CONTROL/03_BOOKING_OPTIONS.md` |
| `SVC-GENERAL-CLEANING` | General Cleaning | التنظيف العام | Not started |
| `SVC-DEEP-CLEANING` | Deep Cleaning | التنظيف العميق | ⚠ Blocked — facts pending owner scope decision |
| `SVC-WATER-TANK-CLEANING` | Water Tank Cleaning | تنظيف خزانات المياه | Not started |

## Category: General Maintenance

| Service ID | Service Name (EN) | Service Name (AR) | Booking Status |
|---|---|---|---|
| `SVC-AC-MAINTENANCE` | AC Maintenance | صيانة التكييف | Not started |
| `SVC-PLUMBING` | Plumbing | السباكة | Not started |
| `SVC-ELECTRICAL-MAINTENANCE` | Electrical Maintenance | الصيانة الكهربائية | Not started |
| `SVC-PAINTING` | Painting | الدهانات | Not started |
| `SVC-HANDYMAN` | Handyman Services | خدمات الصيانة العامة (هاندي مان) | Not started |

## Category: Drainage & Water Protection

| Service ID | Service Name (EN) | Service Name (AR) | Booking Status |
|---|---|---|---|
| `SVC-DRAIN-UNBLOCKING` | Drain Unblocking | تسليك المجاري | Not started |
| `SVC-WATERPROOFING` | Waterproofing | العزل المائي | Not started |
| `SVC-WATER-LEAK-DETECTION` | Water Leak Detection | كشف تسربات المياه | Not started |

---

## Standard Customer Selection Fields (all services)

Per `SERVICE_MATRIX.md`'s consumer rules — coverage confirms the company *offers* a service in an emirate, not real-time availability, price, or response time. Every booking flow, regardless of service, must therefore collect enough to let a human confirm rather than promise instantly:

- **Location** — emirate (dropdown: the 7 approved emirates only — Abu Dhabi, Dubai, Sharjah, Ajman, Umm Al Quwain, Ras Al Khaimah, Fujairah) + free-text area/community, since community-level coverage isn't in the canonical registry yet.
- **Property Type** — dropdown: Residential – Villa / Residential – Apartment / Office / Commercial (generic categories; per-service refinement lives in each service's own `03_BOOKING_OPTIONS.md`).
- **Required Date** — date picker, no past dates.
- **Preferred Time** — dropdown: Morning / Afternoon / Evening (a time-of-day preference, not a guaranteed slot — no specific hour should be offered as confirmed without operational confirmation).
- **Notes** — free text, optional.
- **Phone Number** — required, UAE format validation.

**Explicitly not included as a field anywhere in this catalog:** price, discount, or response-time commitment. None of those are established facts in this repository (see `06_CUSTOMER_AND_SALES/*` for the eventual owner of pricing/warranty facts) and none should be surfaced to a customer as if confirmed.

---

## Related Documents

- `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_MATRIX.md`
- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/03_BOOKING_OPTIONS.md`
