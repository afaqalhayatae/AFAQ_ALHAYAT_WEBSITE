# Rank Math Configuration Standard

## Document Information

- **Owner:** Web Platform and SEO
- **Status:** Draft — validate against the installed Rank Math edition/version
- **Version:** 1.0

## Role

Rank Math may help implement metadata, canonical tags, XML sitemaps, schema,
robots controls, redirects, breadcrumbs, and editorial checks. It is a
configuration and QA tool—not a substitute for helpful content, technical
quality, approved facts, or professional judgment.

An SEO score must never be treated as a publishing decision or ranking
guarantee.

## Configuration Principles

- Use one system of record for each SEO function; avoid two sitemap, schema, or
  redirect systems producing conflicting output.
- Map titles and descriptions to approved page templates while allowing unique
  editorial review.
- Include only canonical, indexable content types in XML sitemaps.
- Exclude Draft, HOLD, private, thin, duplicate, internal-search, and test
  content.
- Use self-referencing canonicals unless an approved exception exists.
- Configure breadcrumbs to match visible hierarchy and URL architecture.
- Implement schema from verified canonical fields; do not invent missing data.
- Restrict redirect management to reviewed mappings with rollback evidence.
- Keep access to global settings limited and record configuration changes.

## Content Analysis

Use focus-keyword and content-analysis checks as editorial prompts only.
Writers must prioritize user intent, accuracy, completeness, natural language,
Arabic/English quality, and conversion usefulness over achieving a plugin
score.

## Sitemap QA

- Confirm every submitted URL returns the intended status and canonical.
- Confirm excluded content is absent.
- Validate language architecture and pagination behavior.
- Check last-modified values reflect meaningful updates.
- Submit and monitor through the verified search-console property.

## Schema QA

- Match visible page facts.
- Use stable entity IDs and canonical URLs.
- Avoid fake ratings, reviews, prices, availability, addresses, or branches.
- Test output after theme, plugin, template, and content-model changes.

## Change Checklist

- [ ] Backup and rollback point created
- [ ] Staging configuration reviewed
- [ ] Conflicting SEO plugins/functions identified
- [ ] Sitemap, canonical, robots, breadcrumbs, and schema tested
- [ ] Cache cleared and production output verified
- [ ] Search monitoring annotation recorded

## Official Reference

- [Rank Math SEO Analysis documentation](https://rankmath.com/kb/seo-analysis/)

