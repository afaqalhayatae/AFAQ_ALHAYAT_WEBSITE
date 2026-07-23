# Duplicate and Conflict Report

Plan ID: MIGPLAN-20260723-0326-4ff3164091
Baseline commit: 46fa2a2 (tag `pre-architecture-migration-20260723-0326`)

No byte-identical (true duplicate) non-empty files exist anywhere in the repository. The empty files (`README.md`, `TEMP/.../TARGET_CUSTOMERS.md`, `TEMP/.../COMPETITOR_ANALYSIS.md`, `99_STANDARDS/05_ACCESSIBILITY_STANDARD.md`, and the stray zero-byte `01_HOMEPAGE` object) share the universal empty-file SHA-256 (`e3b0c44298fc...`) by definition, not because they were copied from one another.

## Conflict register and resolution status

| ID | Paths | Relationship | Resolution (approved decision) |
|---|---|---|---|
| CNF-01 | `00_START/01_BUSINESS/00_COMPANY_PROFILE.md` ↔ `00_START/TEMP/01_BRAND/COMPANY_PROFILE.md` | Overlapping | **Resolved** — BUSINESS copy canonical → `01_BUSINESS/COMPANY_PROFILE.md`. TEMP copy → `98_LEGACY_ARCHIVE`, preserved intact (decision 1). |
| CNF-02 | `00_START/01_BUSINESS/02_BRAND/08_BRAND_GUIDELINES.md` ↔ `00_START/TEMP/01_BRAND/BRAND_GUIDELINES.md` | Overlapping | **Resolved** — BUSINESS copy canonical → `02_BRAND/BRAND_GUIDELINES.md`. TEMP copy → `98_LEGACY_ARCHIVE`, preserved intact (decision 2). |
| CNF-03 | `00_START/01_BUSINESS/06_COMPETITOR_ANALYSIS.md` ↔ `00_START/TEMP/01_BRAND/02_MARKET/COMPETITOR_ANALYSIS.md` | Destination collision (both target `03_MARKET/COMPETITOR_ANALYSIS.md`) | **Resolved** — non-empty BUSINESS copy canonical. Empty TEMP stub → `98_LEGACY_ARCHIVE`, preserved intact (decision 3). |
| CNF-04 | `00_START/TEMP/01_BRAND/02_MARKET/SERVICE_AREAS.md` ↔ `.../04_SERVICES/18_SERVICE_LOCATIONS.md` ↔ `.../04_SERVICES/19_SERVICE_AREAS_BY_EMIRATE.md` | Overlapping (3-way) | **Deferred by design** — held, not auto-merged. Scheduled for a separate manual reconciliation batch after structural migration (decision 4). |
| CNF-05 | `.../04_SERVICES/00_SERVICES_OVERVIEW.md` ↔ `07_WEBSITE/03_SERVICES/00_SERVICES_OVERVIEW.md` | Overlapping | **Resolved for scope; content deferred** — both service lines (maintenance + cleaning/pest-control) confirmed in scope (decision 5). Both draft overview files → `98_LEGACY_ARCHIVE` as source input; a new unified `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` is authored separately (content authoring, outside structural-migration scope). |
| CNF-06 | `.../04_SERVICES/03_PEST_CONTROL.md` ↔ `07_WEBSITE/03_SERVICES/01_PEST_CONTROL.md` ↔ `07_WEBSITE/.../03_SERVICE_KNOWLEDGE/01_PEST_CONTROL/BUSINESS.md` | Overlapping (3-way) | **Resolved** — 11-file service-knowledge package canonical → `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/*`. Other two drafts → `98_LEGACY_ARCHIVE`, preserved for later content comparison (decision 6). |
| CNF-07 | `.../04_SERVICES/20_SERVICE_FAQ.md` ↔ `07_WEBSITE/.../03_SERVICE_KNOWLEDGE/01_PEST_CONTROL/FAQ.md` | Overlapping (scope ambiguity) | **Resolved** — kept as two separate documents at different ownership levels: general FAQ (company-wide) and per-service FAQ (decision 7). Both proceed to MOVE. |
| CNF-08 | `00_START/01_BUSINESS/02_BRAND/06_DESIGN_SYSTEM/07_WEBSITE/01_HOMEPAGE` (zero-byte stray file) | Unknown/ambiguous | **Resolved** — treated as accidental unclassified residue → `98_LEGACY_ARCHIVE`, preserved, not deleted (decision 8). |
| CNF-09 | `.../05_WORDPRESS/08_PROJECT_CONSTITUTION.md` | Ambiguous placement | **Resolved** — placed under `07_WEBSITE/WORDPRESS/` as it governs the WordPress implementation (decision 9). |

## Remaining open items not covered by the approved decisions

- **7 per-service maintenance/cleaning drafts** (AC Maintenance, Cleaning Services, Plumbing, Electrical Maintenance, Painting Services, Handyman Services, Water Tank Cleaning) — in scope per decision 5, but each needs a `04_SERVICE_KNOWLEDGE/<NN_SERVICE>/` folder-numbering convention before an exact destination can be assigned.
- **14 cross-cutting sales/operations drafts** (Service Packages, Annual Maintenance Contracts, Emergency Services, Pricing Strategy, Service Workflow, Service Standards, Quality Assurance, Customer Support, Booking Process, Service Policies, Warranty Policy, After-Service Process, Upsell/Cross-sell, Service Checklist) — each needs a per-file placement decision under `06_CUSTOMER_AND_SALES/*` or `05_OPERATIONS/*`.
- **`05_DATABASE_ARCHITECTURE.md`** — minor open question, not addressed by decisions 1–12: remains under `07_WEBSITE/WORDPRESS/` (current proposal) or moves to `11_TECHNICAL/ARCHITECTURE/`.

## Placeholder / unverified data carried forward

- `CONTACT_INFORMATION.md` contains placeholder phone/WhatsApp (`+971 XX XXX XXXX`). Moves as-is to `02_BRAND/CONTACT_INFORMATION.md`, marked **Draft / Unverified**, and must never be treated as publishable or authoritative until the user supplies real values (decision 10).
