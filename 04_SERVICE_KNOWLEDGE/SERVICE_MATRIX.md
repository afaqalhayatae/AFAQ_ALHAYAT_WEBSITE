# Service Matrix

## Purpose

Maps the services in `SERVICE_CATALOG.md` to the approved emirates in
`03_MARKET/SERVICE_AREAS.md`. Website landing pages, booking, CRM, campaigns,
analytics, and AI must read this matrix rather than maintain independent
coverage claims.

## Status

Approved at emirate level by direct owner confirmation on 2026-07-23.
Operational date/time availability and lower-level locations remain subject to
booking confirmation and the canonical area registry.

## Approved Emirate Set

- `LOC-AE-AZ` — Abu Dhabi
- `LOC-AE-DU` — Dubai
- `LOC-AE-SH` — Sharjah
- `LOC-AE-AJ` — Ajman
- `LOC-AE-UQ` — Umm Al Quwain
- `LOC-AE-RK` — Ras Al Khaimah
- `LOC-AE-FU` — Fujairah

## Coverage Matrix

| Service ID | Approved Location IDs | Coverage Status | Booking Constraint |
|---|---|---|---|
| `SVC-PEST-CONTROL` | All approved emirates | Active | Confirm date/time and service scope |
| `SVC-AC-MAINTENANCE` | All approved emirates | Active | Confirm date/time and service scope |
| `SVC-GENERAL-CLEANING` | All approved emirates | Active | Confirm date/time and service scope |
| `SVC-DEEP-CLEANING` | All approved emirates | Active | Knowledge package still requires completion before detailed publication |
| `SVC-WATER-TANK-CLEANING` | All approved emirates | Active | Confirm date/time and service scope |
| `SVC-PLUMBING` | All approved emirates | Active | Confirm date/time and service scope |
| `SVC-ELECTRICAL-MAINTENANCE` | All approved emirates | Active | Confirm date/time and service scope |
| `SVC-PAINTING` | All approved emirates | Active | Confirm date/time and service scope |
| `SVC-HANDYMAN` | All approved emirates | Active | Confirm date/time and service scope |
| `SVC-DRAIN-UNBLOCKING` | All approved emirates | Active | Confirm affected drainage point, site conditions, date/time, and service scope |
| `SVC-WATERPROOFING` | All approved emirates | Active | Confirm surface, affected area, site inspection, date/time, and approved system |
| `SVC-WATER-LEAK-DETECTION` | All approved emirates | Active | Confirm suspected leak location, site conditions, date/time, and diagnostic scope |

`All approved emirates` expands only to the seven IDs listed above.
Every approved priority community in `03_MARKET/SERVICE_AREAS.md` inherits its
parent emirate’s service availability unless an explicit constraint is added.

## Consumer Rules

- Coverage means the company offers the service in the emirate; it does not
  promise immediate availability, travel time, price, or response time.
- A detailed service page cannot exceed the approved knowledge package.
- No city or community page may be generated until that location exists in the
  canonical registry.
- Booking systems must recheck current operational availability.
- AI must state uncertainty about scheduling and lower-level coverage.
- New service IDs require explicit matrix review.
