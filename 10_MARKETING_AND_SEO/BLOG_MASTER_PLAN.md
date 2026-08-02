# Blog Master Plan

## Document Information

- **Status:** Draft — content architecture, not yet through Evidence Gate/Owner publication approval
- **Prepared:** 2026-08-02
- **Depends on:** `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `00_GOVERNANCE/SERVICE_MASTER_MATRIX.md`, `10_MARKETING_AND_SEO/CONTENT_STRATEGY.md`, `SEO_STRATEGY.md`, `URL_AND_INTERNAL_LINKING_STANDARD.md`

## Purpose

Establish the structure, categories, and production rules for `10_MARKETING_AND_SEO/BLOG/` — the article set produced under this directive's Phase 2 and any future blog content.

---

## 1. Blog Categories

| Category | Maps to catalog category | Services covered in this phase |
|---|---|---|
| Maintenance | General Maintenance | AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman Services |
| Cleaning | Cleaning & Pest Control (cleaning subset) | General Cleaning, Deep Cleaning |
| Pest Control | Cleaning & Pest Control (pest subset) | Cockroach Control, Ant Control, Bed Bug Control, Termite Control (pest **types**, not separate catalog services — see §5) |

Future categories (not built in this phase): the remaining 2 Cleaning services (Water Tank Cleaning, and the 4 newer Cleaning add-ons), Drainage & Water Protection (3 services), and the 11 structural-only Maintenance-expansion services once their base content exists.

## 2. Folder Structure

```
10_MARKETING_AND_SEO/BLOG/
  ac-maintenance/
    article-1-{slug}.md
    article-2-{slug}.md
    article-3-{slug}.md
  plumbing/
  electrical-maintenance/
  painting/
  handyman/
  general-cleaning/
  deep-cleaning/
  cockroach-control/
  ant-control/
  bed-bug-control/
  termite-control/
```

One folder per service/topic, matching the service's catalog slug (or, for pest types, the sub-topic name — see §5).

## 3. Article Structure (mandatory for every article)

Per this directive's requirement, every article includes:

1. Arabic title
2. English title
3. SEO title
4. Meta description
5. Main content (structured body — see §4)
6. FAQ section (2–3 Q&A, reusing or consistent with the service's approved FAQ)
7. Internal link suggestions
8. Target keywords (EN + AR)

Plus a Document Information header stating source/status, and an Evidence Gate note — consistent with every other content package in this repository.

## 4. Main Content Angle Per Article (3 per service, each distinct)

To avoid three near-duplicate articles per service, each set of three uses a different angle, all grounded in the same service's already-approved `commonProblems`/`scope`/`process`/`benefits`/`safety` facts:

1. **Signs/Problem-led** — "Signs You Need [Service]" — built from the service's approved `commonProblems` list.
2. **Scope/Process-led** — "What's Included in a [Service] Visit" — built from the service's approved `scope.included`/`process` fields.
3. **Guidance-led** — a practical buyer/booking-guide angle (choosing, preparing for, or understanding cost/booking for the service) — built from the service's approved `benefits`/FAQ content, always hedging cost per the source FAQ's existing "subject to company policy" language.

## 5. Pest-Type Articles — Sourcing Note (important)

Per `LOCAL_SEO_MASTER_PLAN.md` §6, **no separate catalog service ID exists for individual pest types** — Cockroach Control, Ant Control, and Termite Control exist only as **Draft, not-yet-Evidence-Gated `subServices` entries** in `SERVICE_DATABASE.json` (status: "content generated 2026-07-30 per Owner request; not yet through this package's Evidence Gate or linguistic review"). Bed Bug Control has **no dedicated subService entry at all** — only a general mention in `SVC-PEST-CONTROL`'s top-level scope/keywords/FAQ.

**How this phase's 4 pest-type article sets handle that:**
- Cockroach/Ant/Termite Control articles use the Draft subService short description/SEO fields as one input, explicitly labeled Draft in each article's header, combined with the approved parent Pest Control service's scope/FAQ/safety content for anything claim-sensitive (safety, warranty, duration, prevention).
- Bed Bug Control articles are grounded entirely in the approved parent Pest Control service's content (its scope explicitly includes "Bed Bug Treatment"; its FAQ answers apply pest-agnostically) plus general, non-company-specific pest-education framing (e.g., common signs of activity) — no AFAQ-specific claim is made beyond what the approved Pest Control package already states.
- **No article in any of the four pest-type folders states a specific chemical, product name, or guaranteed-effective method** — every operational claim defers to "your technician will select an approved method suited to your property," matching the approved Pest Control FAQ's own hedge.
- **No new catalog service ID is created** by this blog content — these remain content topics under `SVC-PEST-CONTROL`, not new services, consistent with Option A in `LOCAL_SEO_MASTER_PLAN.md` §6. Creating dedicated catalog IDs (Option B) remains a separate, unresolved Owner decision.

## 6. SEO Strategy

Each article's SEO title/meta description/keywords follow the same convention as approved service pages: `[Topic] | AFAQ AL HAYAT` title pattern, meta description restating the article's real content (not keyword-stuffed), and keyword sets drawn from or consistent with the parent service's already-approved keyword list plus long-tail, question-style variants — per the existing 10-category framework in `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` (reused, not duplicated).

## 7. Internal Linking Plan

- Every article links to its parent service page (e.g., all 3 AC Maintenance articles link to the AC Maintenance service page).
- Every article links to the sitewide FAQ page and the Contact/booking page.
- Pest-type articles link to the parent Pest Control service page (not to each other by pest type, to avoid implying an unapproved dedicated pest-type page exists yet).
- Future: once Service+City pages exist (`LOCAL_SEO_MASTER_PLAN.md`), articles link to the relevant city page for their service.

## 8. Claim-Safety Rule (applies to every article without exception)

No price, discount, warranty term, license, certification, specific response time, or emergency-service promise is stated in any article. Every article inherits the same Evidence Gate discipline as this repository's service packages — hedged language ("subject to company policy," "a technician will assess," "contact us for an accurate quote") is used identically to the approved source FAQs, not invented per article.

## 9. Status

All 33 articles produced under this directive's Phase 2 are **Draft — content production, not yet through Evidence Gate/Owner publication approval**, identical in status to every other new page in this phase.

---

## What This Document Does Not Do

- Does not create any new catalog service ID.
- Does not modify any `04_SERVICE_KNOWLEDGE/` service file or `SERVICE_DATABASE.json`.
- Does not itself approve any article for publication.

## Related Documents

- `10_MARKETING_AND_SEO/BLOG/` — the article set this plan governs
- `00_GOVERNANCE/SERVICE_MASTER_MATRIX.md`, `10_MARKETING_AND_SEO/LOCAL_SEO_MASTER_PLAN.md`
- `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`
