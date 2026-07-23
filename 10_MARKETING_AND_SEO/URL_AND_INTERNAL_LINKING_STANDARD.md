# URL and Internal Linking Standard

## Document Information

- **Owner:** SEO and Web Platform
- **Status:** Active for architecture; implementation requires final routes
- **Version:** 1.0
- **Applies to:** Public website, sitemap, schema, campaigns, and analytics

## Objectives

Create URLs that are stable, readable, crawlable, shareable, and aligned with
real user intent. URL design must support Arabic and English without generating
duplicate or doorway pages.

## Core URL Rules

- Use HTTPS only.
- Use lowercase ASCII slugs.
- Separate words with hyphens.
- Keep slugs short, descriptive, and stable.
- Never place phone numbers, prices, dates, tracking codes, or internal database
  keys in canonical URLs.
- Avoid unnecessary nesting and repeated words.
- Choose one trailing-slash policy and enforce it globally.
- One approved content entity has one canonical URL per language.
- Query parameters must not create indexable duplicates.

## Recommended Route Model

```text
/
/en/
/ar/
/en/about/
/ar/about/
/en/services/
/ar/services/
/en/services/{service-slug}/
/ar/services/{service-slug}/
/en/locations/
/ar/locations/
/en/services/{service-slug}/{approved-location-slug}/
/ar/services/{service-slug}/{approved-location-slug}/
/en/blog/{article-slug}/
/ar/blog/{article-slug}/
/en/contact/
/ar/contact/
```

Use the same stable ASCII entity slug across languages unless a documented
localization decision and redirect map prove that localized slugs can be
maintained safely. Visible headings, metadata, breadcrumbs, and content must be
properly localized.

## Service and Location Controls

- Service routes may be generated only from active IDs in
  `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`.
- Location routes may be generated only from approved IDs in
  `03_MARKET/SERVICE_AREAS.md`.
- A service-location page may exist only when the combination is approved in
  `04_SERVICE_KNOWLEDGE/SERVICE_MATRIX.md`.
- Do not create hundreds of pages by swapping place names in duplicated copy.
- Planned, limited, suspended, or inactive coverage must follow its documented
  indexing policy.

## Canonical and Language Signals

- Every indexable page has a self-referencing canonical URL.
- Arabic and English equivalents reference each other with valid `hreflang`.
- Provide `x-default` only for a genuine language selector or default entry
  page.
- Canonical URLs, sitemap URLs, internal links, Open Graph URLs, and structured
  data URLs must agree.
- Do not canonicalize Arabic content to English or vice versa.

## Redirect Policy

- Use a single-hop permanent redirect for a permanently changed URL.
- Maintain a versioned redirect map with old URL, new URL, reason, owner, and
  effective date.
- Redirect to the closest true replacement; do not redirect unrelated removed
  pages to the homepage.
- Prevent chains, loops, soft 404s, and mixed HTTP/HTTPS routes.
- Preserve valuable legacy URLs during migrations.

## Internal Linking Architecture

Every indexable page must be reachable through normal HTML links and should
belong to a clear topic cluster:

- Homepage → service catalog, priority approved services, and core trust pages
- Service hub → individual approved services
- Service page → related approved services, relevant guides, booking, and
  approved locations
- Location hub → approved location pages
- Article → canonical service and related educational content
- Breadcrumbs → valid parent hierarchy

Use concise, natural anchor text that describes the destination. Avoid
keyword-stuffed anchors, generic repeated “click here” links, hidden links, and
links to Draft/HOLD content.

## Pagination, Filters, and Parameters

- Filters and sorting must not create uncontrolled indexable URL combinations.
- Tracking parameters are excluded from canonical URLs.
- Pagination must expose crawlable links where pagination is necessary.
- Search results, internal account pages, staging routes, and duplicate filtered
  views must use the appropriate indexing controls.

## Slug Governance

The route registry must record:

- Entity ID
- Language
- Current canonical path
- Previous paths
- Page type
- Indexing status
- Approval status
- Effective and review dates

Changing a slug requires impact analysis, redirect mapping, sitemap update,
internal-link update, analytics annotation, and post-release validation.

## Google-Facing Validation

Before release:

- Confirm successful crawl and index eligibility.
- Validate canonical and `hreflang` reciprocity.
- Validate sitemap status codes and last-modified behavior.
- Test redirects and 404/410 handling.
- Verify structured data URLs match canonical visible pages.
- Confirm mobile rendering, Core Web Vitals, and accessible link names.
- Check for orphan pages, broken links, duplicate titles, and duplicate content.

This standard improves technical quality and search clarity; it does not
guarantee rankings.

