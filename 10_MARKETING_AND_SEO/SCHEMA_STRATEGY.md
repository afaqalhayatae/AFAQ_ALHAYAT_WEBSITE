# Structured Data Strategy

## Principle

Structured data describes visible, verified content. It must never manufacture
entities, locations, ratings, prices, availability, or credentials.

## Supported Types

- `Organization`
- `WebSite`
- `BreadcrumbList`
- `Service`
- `FAQPage` when eligible and visible
- `Article`
- `LocalBusiness` only for an eligible, verified business entity/location

## Field Ownership

| Field group | Canonical source |
|---|---|
| Organization identity | `01_BUSINESS/COMPANY_PROFILE.md` and `02_BRAND/` |
| Contact and NAP | `02_BRAND/CONTACT_INFORMATION.md` and `LOCAL_SEO_PROFILE.md` |
| Service facts | Approved package in `04_SERVICE_KNOWLEDGE/` |
| Coverage | `03_MARKET/SERVICE_AREAS.md` |
| FAQ answers | Approved general or service-specific FAQ |
| Page URL and breadcrumb | `07_WEBSITE/` implementation |

## Validation

- Schema values equal visible page content.
- Required fields are present and approved.
- IDs and URLs are stable.
- Arabic and English entities use consistent identifiers.
- Validation passes current search-engine tooling.
- Deployment removes schema when the underlying fact becomes Draft or
  inactive.

