# Website Implementation Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only, no implementation authorized by this document
- **Version:** 1.0
- **Prepared:** 2026-07-27
- **Depends on:** `01_PROJECT_AUDIT_REPORT.md`, `00_GOVERNANCE/TECH_STACK.md`, `00_GOVERNANCE/IMPLEMENTATION_READINESS_REPORT.md`

## Note on scope

This plan describes architecture and sequencing only. No repository, package manifest, or application code is created by this document. Per `IMPLEMENTATION_READINESS_REPORT.md`, only the "Authorized First Implementation Scope" (scaffolding, non-production infrastructure) may begin without further owner approval; production deployment and any commercial/legal claim remain gated regardless of this plan.

---

## 1. Website Architecture

The canonical stack, per `00_GOVERNANCE/TECH_STACK.md` v1.2 and `DECISION_LOG.md` decisions 22/34, is:

| Layer | Technology |
|---|---|
| Frontend framework | Next.js (App Router), TypeScript, React |
| Styling | Tailwind CSS |
| Icons / motion | Lucide React / Framer Motion |
| Backend | Next.js API routes, Node.js, REST |
| Database | MySQL |
| ORM | Prisma |
| Hosting | Hostinger (Next.js/Node.js/MySQL support confirmed 2026-07-26) |
| Domain | `afaqalhayatae.com` (apex vs. `www` redirect to be finalized at deployment) |
| CI | GitHub Actions (planned) |
| Analytics | Google Analytics, Search Console, Tag Manager |
| Languages | Arabic (primary, RTL) and English (LTR) — equal first-class per `PROJECT_MANIFEST.md` and `12_DESIGN_SYSTEM/README.md` |

Architectural principles carried over from governance:

- **Knowledge, not code, is the source of truth.** Page content is rendered from governed Markdown/data, not authored directly in JSX. Facts are fetched by reference (service ID, area ID, contact field), never duplicated into components.
- **Design system first.** All UI is built from `12_DESIGN_SYSTEM/` tokens (`COLORS.md`, `TYPOGRAPHY.md`, `SPACING.md`, `GRID.md`, `BUTTONS.md`, `FORMS.md`, `CARDS.md`, `ICONS.md`, `COMPONENTS.md`, `MOBILE.md`, `ACCESSIBILITY.md`, `ANIMATIONS.md`) and the binding `LUXURY_DESIGN_DIRECTION.md` / `SIDEBAR_NAVIGATION.md` direction — not ad hoc styling.
- **Blocked-field pattern.** Any fact still `Pending`/`Draft` (WhatsApp, email, hours, address, pricing, warranty terms) must render as an explicit empty/blocked state in code, never a placeholder value, per the non-fabrication rule.
- **Bilingual routing.** Arabic and English are parallel route trees (e.g. `/ar/...`, `/en/...` or locale-prefixed), sharing the same data layer, never diverging in fact content.

---

## 2. The WordPress Question — Addressed Directly

`07_WEBSITE/WORDPRESS/` contains substantial architecture work (custom post types, taxonomies, Rank Math SEO config, module architecture, live maps architecture, a "project constitution"). However, **this repository has twice decided WordPress is not the implementation path**:

- `TECH_STACK.md`: *"Documents under `07_WEBSITE/WORDPRESS/` ... are retained as non-canonical historical research. They do not authorize a WordPress or hybrid implementation unless the owner records a new decision."*
- `DECISION_LOG.md` decisions 22 and 34: canonical direction is Next.js/TypeScript/React/Tailwind/Node/MySQL/Prisma; WordPress exclusion explicitly untouched by the later MySQL amendment.
- `07_WEBSITE/README.md`: *"The implementation stack is owned by `00_GOVERNANCE/TECH_STACK.md`. Website documents define presentation and channel behavior, not an alternative stack."*

**This plan follows the ratified decision and does not propose a WordPress build.** The WordPress documents remain valuable as a secondary reference for content-modeling ideas (post types ≈ service/location entities, taxonomies ≈ categories) that can inform the Prisma data model, but they do not drive folder structure, hosting, or CMS choice.

If the Owner wants to reopen this — for example, to use WordPress as a faster-to-market interim CMS — that requires a new, explicit decision recorded in `DECISION_LOG.md`, the same way decision 34 superseded decision 22's database choice. Until then, treat `07_WEBSITE/WORDPRESS/` as archival input only.

---

## 3. Required Folders

Target structure per `SYSTEM_ARCHITECTURE.md` §4, compared against current state:

| Folder | Status | Notes |
|---|---|---|
| `07_WEBSITE/01_HOMEPAGE/` | Exists | Architecture, content, UI/UX, SEO/AI, components docs present. |
| `07_WEBSITE/02_ABOUT/` | **Missing** | References `01_BUSINESS/COMPANY_PROFILE.md`, `VISION.md`, `MISSION.md` — does not restate them. |
| `07_WEBSITE/03_SERVICE_PAGES/` | **Missing** | One content-mapping doc per `SERVICE_CATALOG.md` entry (see `03_CONTENT_TO_WEBSITE_MAPPING.md`). |
| `07_WEBSITE/04_LOCATIONS/` | **Missing** | Emirate pages first (7, fully approved); community pages gated by SEO/ops quality review. |
| `07_WEBSITE/05_BOOKING/` | **Missing** | Depends on `06_CUSTOMER_AND_SALES/BOOKING/` clearing Draft status. |
| `07_WEBSITE/06_BLOG/` | **Missing** | No content strategy blocker beyond `10_MARKETING_AND_SEO/CONTENT_STRATEGY.md` guidance. |
| `07_WEBSITE/07_CONTACT/` | **Missing** | Only phone + domain publishable today; rest blocked pending owner input. |
| `07_WEBSITE/08_LEGAL_PAGES/` | **Missing** | Requires legal review before any draft text is written — do not author terms/privacy text speculatively. |
| `07_WEBSITE/09_ERROR_PAGES/` | **Missing** | No content dependency; can be built early alongside scaffolding. |
| `07_WEBSITE/WORDPRESS/` | Exists | Retained, non-canonical, do not extend further. |

These folders are **not created by this document** — creating them (even as empty `README.md`-only scaffolds) is an `A2` reversible internal edit and should happen as part of the approved Phase 1 scaffolding step below, not as a side effect of planning.

---

## 4. Required Development Phases

### Phase 0 — Confirm the working base (governance, no code)
- Confirm which Git branch implementation proceeds from (see audit report §5.1).
- Confirm the Owner's authorization to begin Phase 1 scaffolding specifically (the Readiness Report pre-authorizes the *category* of work; the Owner should confirm the *start*).

### Phase 1 — Scaffolding (authorized now per `IMPLEMENTATION_READINESS_REPORT.md`)
- Initialize the application repository (separate from, or as a subdirectory of, this knowledge repository — Owner's choice) with Git protections.
- Scaffold Next.js + TypeScript + Tailwind + Prisma against a local/test MySQL instance — no production credentials.
- Implement design tokens and base components from `12_DESIGN_SYSTEM/` (colors, type scale, spacing, buttons, cards, forms).
- Implement bilingual routing (AR/EN) and RTL/LTR layout handling.
- Implement accessibility baseline (WCAG 2.2 AA per `99_STANDARDS/ACCESSIBILITY_STANDARD.md`).
- Implement typed data contracts (service, location, contact-field types) mirroring `08_DIGITAL_SYSTEMS/DATA_MODEL.md` and `API_CONTRACTS.md`, with all pending facts modeled as nullable/blocked states, not defaults.
- Stand up empty-state pages for every `07_WEBSITE/*` page domain (including the 7 missing folders above) so routing exists before content does.
- Set up CI (lint, type-check, automated tests) via GitHub Actions.

### Phase 2 — Content-gated build
- Populate the Homepage from `07_WEBSITE/01_HOMEPAGE/*` docs, with every conditional section (WhatsApp CTA, hours, address, emergency banner) wired to the blocked-field pattern.
- Build `03_SERVICE_PAGES` starting with Pest Control (only fully complete package), then General Cleaning / Water Tank Cleaning, adding remaining services as each clears its owner/evidence gate.
- Build `04_LOCATIONS` for the 7 emirates only; hold community pages until SEO/ops quality gates in `SERVICE_AREAS.md`'s review checklist are satisfied.
- Build `02_ABOUT`, `06_BLOG` (structure only, content per marketing calendar), `09_ERROR_PAGES`.
- Hold `05_BOOKING` and `08_LEGAL_PAGES` until their source domains (`06_CUSTOMER_AND_SALES/BOOKING/`, legal review) exit Draft status.

### Phase 3 — System integration (test mode only)
- Connect CRM/booking/analytics/consent/email/social adapters in test mode per `08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_ORCHESTRATION.md` and the Agent Runbook — no live credentials or customer-facing effects yet.
- Wire AI assistant behavior to `09_AI_KNOWLEDGE/ANSWER_POLICY.md` and `RETRIEVAL_POLICY.md`, running `09_AI_KNOWLEDGE/EVALUATIONS/CORE_TEST_CASES.md` as a release gate.

### Phase 4 — Controlled launch
- Stage-gate launch per `CURRENT_PROJECT_STATUS.md`'s priority order: verify plan → scaffold → implement → confirm facts → integrate in test mode → launch in controlled stages → measure → scale.
- Every step requiring money, credentials, DNS/hosting changes, or a legal/safety/regulatory claim is `A4` — owner approval required each time, no exceptions from this plan.

---

## 5. Deployment Plan

- **Host:** Hostinger, plan verified to support Next.js, Node.js, MySQL (2026-07-26). Exact deployment method (Node app hosting vs. static export vs. container), SSH/CI access, staging environment, backup cadence, and region still need confirmation before first deploy.
- **Domain:** `afaqalhayatae.com`, apex vs. `www` canonicalization to be decided and configured at deployment time — not before.
- **Environments:** local → CI-tested → staging (if available on the plan) → production. No environment before staging touches real credentials or live contact/booking data.
- **Rollback:** Git-based, following the same non-destructive posture as `SYSTEM_ARCHITECTURE.md` §14 (revert, never hard reset/force-push) for both the knowledge repo and the new application repo.
- **Gate before go-live:** all Hard Publication Blocks in `CURRENT_PROJECT_STATUS.md` must show clear — no unverified contact/account details, no unapproved prices/warranties/licenses/safety claims, no fabricated branches/reviews/staff.

---

## Related Documents

- `01_PROJECT_AUDIT_REPORT.md`
- `03_CONTENT_TO_WEBSITE_MAPPING.md`
- `04_FINAL_RECOMMENDATION.md`
- `00_GOVERNANCE/TECH_STACK.md`
- `00_GOVERNANCE/IMPLEMENTATION_READINESS_REPORT.md`
- `SYSTEM_ARCHITECTURE.md`
