# Service Areas

## Document Information

- **Owner:** Business Owner and Operations
- **Status:** Approved at emirate level; lower-level areas pending
- **Version:** 1.0
- **Effective Date:** 2026-07-23
- **Authority:** Canonical geographic coverage registry

## Purpose

This document is the only permitted source for geographic service coverage.
Website pages, CRM availability, booking, campaigns, structured data, and AI
answers must reference approved location IDs from this registry.

## Owner Decision

On 2026-07-23, the business owner confirmed that AFAQ Alhayat provides every
service listed in `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` across all seven
emirates of the United Arab Emirates.

This approval applies at **emirate level only**. It does not create or approve:

- Physical branches.
- Street addresses.
- Google Business Profile locations.
- City, district, or community coverage records.
- Response-time commitments.
- Same-day or emergency availability.
- Service availability outside the current canonical catalog.

## Approved Registry

| Area ID | Name EN | Name AR | Type | Parent | Coverage | Services | Effective |
|---|---|---|---|---|---|---|---|
| `LOC-AE-AZ` | Abu Dhabi | أبوظبي | Emirate | `LOC-AE` | Active | All catalog services | 2026-07-23 |
| `LOC-AE-DU` | Dubai | دبي | Emirate | `LOC-AE` | Active | All catalog services | 2026-07-23 |
| `LOC-AE-SH` | Sharjah | الشارقة | Emirate | `LOC-AE` | Active | All catalog services | 2026-07-23 |
| `LOC-AE-AJ` | Ajman | عجمان | Emirate | `LOC-AE` | Active | All catalog services | 2026-07-23 |
| `LOC-AE-UQ` | Umm Al Quwain | أم القيوين | Emirate | `LOC-AE` | Active | All catalog services | 2026-07-23 |
| `LOC-AE-RK` | Ras Al Khaimah | رأس الخيمة | Emirate | `LOC-AE` | Active | All catalog services | 2026-07-23 |
| `LOC-AE-FU` | Fujairah | الفجيرة | Emirate | `LOC-AE` | Active | All catalog services | 2026-07-23 |

`All catalog services` means the stable service IDs in
`04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` at the time of use. A newly proposed
service does not inherit coverage until it is added to the approved catalog.

## Publication Rules

- UAE-wide and emirate-level coverage may be stated using this registry.
- City, district, community, neighborhood, and branch claims remain blocked.
- Emirate landing pages require unique useful content and the normal SEO quality gate.
- Coverage does not prove availability for a particular date or time.
- Booking must confirm operational availability before making a commitment.
- Google Business Profile configuration must follow service-area-business and
  ownership rules; coverage does not justify creating virtual branches.
- AI answers must distinguish general coverage from confirmed booking availability.

## Lower-Level Registry

No city, district, community, or physical branch rows are approved yet.

When added, every row must include:

| Field | Requirement |
|---|---|
| `area_id` | Stable identifier; never reused |
| `name_en` | Approved English name |
| `name_ar` | Approved Arabic name |
| `area_type` | City, district, community, branch, or service zone |
| `parent_area_id` | One approved emirate ID |
| `coverage_status` | Active, limited, planned, suspended, or inactive |
| `service_ids` | Explicit approved services |
| `constraints` | Scheduling, access, or scope restrictions |
| `effective_from` | Approval effective date |
| `reviewed_on` | Most recent owner review |
| `approved_by` | Accountable owner or role |
| `evidence` | Operational evidence supporting coverage |

## Legacy Drafts

The following migration HOLD files remain preserved as historical evidence:

- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/18_SERVICE_LOCATIONS.md`
- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/19_SERVICE_AREAS_BY_EMIRATE.md`
- `00_START/TEMP/01_BRAND/02_MARKET/SERVICE_AREAS.md`

They are superseded for emirate-level authority by this approved registry.
Their unapproved city and district lists must not be published or silently
merged.

## Review Checklist

- [x] Actual operating emirates confirmed by owner.
- [x] All current catalog services mapped to each emirate.
- [x] Approved English and Arabic emirate names recorded.
- [ ] Confirm cities, districts, and communities when operational evidence is available.
- [ ] Confirm service-area-business versus physical branch structure.
- [ ] Record Google Business Profile and Place IDs when verified.
- [ ] Validate booking constraints and scheduling by area.
- [ ] Review coverage at least quarterly.

## Related Documents

- `02_BRAND/CONTACT_INFORMATION.md`
- `02_BRAND/LOCAL_SEO_PROFILE.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_MATRIX.md`
- `09_AI_KNOWLEDGE/ANSWER_POLICY.md`
- `99_STANDARDS/SEO_STANDARD.md`
