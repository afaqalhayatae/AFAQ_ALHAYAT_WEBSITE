# Service Areas

## Document Information

- **Owner:** Business Operations
- **Status:** Blocked — Owner Approval Required
- **Version:** 0.1
- **Language:** English; approved Arabic names required before publication
- **Authority:** Canonical location registry after approval

## Purpose

This document is the only permitted source for geographic service coverage.
Website pages, CRM availability, booking, campaigns, structured data, and AI
answers must reference approved location IDs from this registry rather than
maintaining independent area lists.

## Current Publication State

No emirate, city, district, or neighborhood is currently approved here as a
confirmed service area. Three legacy drafts contain overlapping and conflicting
coverage claims and remain on HOLD under decision `CNF-04`.

Until the owner approves a reconciled registry:

- Do not claim UAE-wide coverage.
- Do not generate service-plus-location landing pages.
- Do not publish location schema or area-specific response commitments.
- Do not infer coverage from target markets, addresses, WordPress examples, or
  historical marketing drafts.

## Required Registry Fields

Every approved location must use this schema:

| Field | Requirement |
|---|---|
| `area_id` | Stable identifier; never reused |
| `name_en` | Approved English name |
| `name_ar` | Approved Arabic name |
| `area_type` | Emirate, city, district, community, or service zone |
| `parent_area_id` | Parent identifier where applicable |
| `coverage_status` | Active, limited, planned, suspended, or inactive |
| `service_ids` | Approved service IDs available in this location |
| `constraints` | Scheduling, access, or scope restrictions |
| `effective_from` | Approval effective date |
| `reviewed_on` | Most recent owner review date |
| `approved_by` | Accountable owner or role |
| `evidence` | Operational evidence supporting coverage |

## Approved Registry

No approved rows yet.

## Source Drafts Awaiting Reconciliation

- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/18_SERVICE_LOCATIONS.md`
- `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/19_SERVICE_AREAS_BY_EMIRATE.md`
- `00_START/TEMP/01_BRAND/02_MARKET/SERVICE_AREAS.md`

These sources are evidence for review only and must not be used as publication
authority.

## Approval Checklist

- [ ] Confirm actual operating emirates.
- [ ] Confirm cities and districts currently served.
- [ ] Map available services to each area.
- [ ] Confirm whether the business has physical branches or operates as a
      service-area business.
- [ ] Approve English and Arabic place names.
- [ ] Record evidence, approver, and effective date.
- [ ] Update `04_SERVICE_KNOWLEDGE/SERVICE_MATRIX.md`.
- [ ] Validate website, CRM, schema, marketing, and AI consumers.
- [ ] Archive or supersede the three legacy drafts after approval.

## Related Documents

- `02_BRAND/CONTACT_INFORMATION.md`
- `02_BRAND/LOCAL_SEO_PROFILE.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_MATRIX.md`
- `09_AI_KNOWLEDGE/ANSWER_POLICY.md`
- `99_STANDARDS/SEO_STANDARD.md`

