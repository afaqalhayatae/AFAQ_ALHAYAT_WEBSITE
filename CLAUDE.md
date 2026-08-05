# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is **not a software codebase**. It is the governed Markdown knowledge base for AFAQ Alhayat, a UAE home-services company (pest control, AC maintenance, cleaning, plumbing, electrical, painting, handyman, drain unblocking, waterproofing, water leak detection). There is no build, lint, or test tooling — every task here is reading, writing, and cross-checking Markdown documents against the rules below. Do not introduce package.json, CI configs, or app code unless the user explicitly asks for a real implementation phase (see "Not yet built" below).

Read these three files first, in order, before making non-trivial edits:

1. `README.md` — repository map and authority rules.
2. `PROJECT_MANIFEST.md` — vision, principles, scope/out-of-scope.
3. `SYSTEM_ARCHITECTURE.md` — the full architectural constitution (source-of-truth registry, non-duplication rules, naming rules, domain relationships).
4. `00_GOVERNANCE/CURRENT_PROJECT_STATUS.md` — live status; more current than `FINAL_PROJECT_STATUS.md`, which is a frozen historical snapshot and must never be treated as current.

## The operating model (read before doing anything autonomous)

The business has exactly **one internal human** — the owner. Everything else (this assistant included) is a governed agent operating under `00_GOVERNANCE/AI_OPERATING_MODEL.md` and `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`. Key rules:

- Agents may research, draft, classify, validate, and execute *reversible, approved* work. They may not invent business facts, spend money, publish high-risk content, or make legal/safety/regulatory commitments.
- **Never fabricate**: prices, discounts, warranties, licenses, certifications, response-time/emergency commitments, contact details, coverage claims, or regulatory claims. If a fact isn't in a canonical source, say so and stop rather than filling the gap.
- Automation levels gate what can be done without asking: `A0` read/recommend, `A1` draft only, `A2` reversible internal edits with logs, `A3` pre-approved external publishing, `A4` owner approval required every time (money, credentials, DNS/hosting, contracts, destructive/irreversible changes, any legal/safety/licensing claim). Default is `A1` unless a workflow is explicitly approved higher.
- If canonical sources conflict, or evidence is missing, stop and surface the decision — do not silently resolve it or pick one.

### Agent Operating System

Use the repository's Agent Operating System instead of inventing a new role or
asking the owner to relay long prompts:

1. Select a role from `00_GOVERNANCE/AGENT_REGISTRY.md`.
2. Follow `08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_RUNBOOK.md`.
3. Apply the owner gates in
   `00_GOVERNANCE/AGENT_APPROVAL_WORKFLOW.md` and
   `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`.
4. Select the model route from
   `00_GOVERNANCE/MODEL_ROUTING_POLICY.md`.
5. Use the job envelope in
   `08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_ORCHESTRATION.md`.
6. Send produced work to the read-only Quality & Integration agent before
   integration.

Project commands in `.claude/commands/` provide short entry points:

- `/readiness` — read-only change-set readiness review.
- `/audit` — bounded read-only repository audit.
- `/stabilize` — prepare and run the next reversible stabilization job under
  the approval workflow.
- `/architect` — produce a high-capability architecture decision and bounded
  execution job.
- `/review` — run independent, read-only acceptance review.

Do not interrupt the owner for routine `A0`/`A1` work. Surface only material
business decisions, `A4` gates, unresolved canonical conflicts, genuine
blockers, and final phase-acceptance summaries.

## Single source of truth — where facts actually live

The repository's core discipline is: **write each fact once, in its owning domain; every other document links to it instead of copying it.** Before adding any factual claim, check whether it's already owned elsewhere:

| Fact type | Owning source | Notes |
|---|---|---|
| Phone, WhatsApp, email, domain, hosting, address, hours, social URLs | `02_BRAND/CONTACT_INFORMATION.md`, `02_BRAND/LOCAL_SEO_PROFILE.md` | All owner-approved (confirmed 2026-07-27, `00_GOVERNANCE/BUSINESS_FACTS_VERIFICATION.md`) — phone `+971 58 543 1766`, domain `afaqalhayatae.com`, address, hours (24/7), Google Maps/Business Profile link, and social URLs all safe to publish. Only emergency-service availability/response-time commitments remain Pending — never present those as final. |
| NAP / map / business-profile data | `02_BRAND/LOCAL_SEO_PROFILE.md` | |
| Company identity/description | `01_BUSINESS/COMPANY_PROFILE.md` | |
| Geographic coverage & areas | `03_MARKET/SERVICE_AREAS.md` | Service pages reference area IDs, never re-list coverage. |
| Service catalog & IDs | `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` | Stable ID format `SVC-<NAME>` (e.g. `SVC-PEST-CONTROL`). |
| Per-service operational facts | `04_SERVICE_KNOWLEDGE/<NN_SERVICE>/*` | |
| SOP / QA / safety | `05_OPERATIONS/*` | |
| Prices, packages, warranty, booking policy | `06_CUSTOMER_AND_SALES/*` | Quoting a price or warranty is always `A4` (owner gate every time). |
| AI retrieval/entity/answer policy | `09_AI_KNOWLEDGE/*` | Defines *how* AI answers; never a source of new facts itself. |
| Global naming/doc/quality rules | `99_STANDARDS/*` | |

Full registry: `SYSTEM_ARCHITECTURE.md` §6 (source-of-truth registry) and §7 (non-duplication rules). Folder-level "must not own" boundaries are in §5.

`98_LEGACY_ARCHIVE/` is preserved history and is **never** an authority — don't cite it as current fact, and don't delete from it.

## Conventions when writing or editing documents

- **File/folder naming**: `UPPER_SNAKE_CASE.md`, English only, two-digit order prefix on top-level folders (see `99_STANDARDS/NAMING_CONVENTIONS.md`, `SYSTEM_ARCHITECTURE.md` §8). Stable ID formats: services `SVC-<NAME>`, locations `LOC-AE-<EMIRATE>-<AREA>`, components `CMP-###`, decisions `ADR-####`, forms `FORM-<DOMAIN>-###`, SOPs `SOP-<DOMAIN>-###`.
- **Document structure**: one H1, H2 for major sections, H3 for subsections, `---` between sections. Include Document Information (Owner, Status, Version, effective/updated date) where the file is authoritative — see `99_STANDARDS/DOCUMENTATION_STANDARD.md`.
- **Status vocabulary**: `Draft`, `In Review` / `Review`, `Approved`, `Deprecated`, `Archived`. Content in `Draft`, `HOLD`, or `Unverified` state must never be presented as approved or publication-ready.
- **Bilingual content**: Arabic and English are equal first-class languages. Paired content must express the *same facts* — phrasing can differ, facts cannot diverge.
- **Before marking anything publish-ready**, run it against `99_STANDARDS/QUALITY_CHECKLIST.md` (itself still in Draft status) — checks contact data is pulled from the canonical source and not Draft/Unverified, service claims match the service catalog/package, coverage matches the finalized `03_MARKET/SERVICE_AREAS.md`, and no invented license/certification/guarantee/regulatory claim is present.

## Not yet built

Per `PROJECT_MANIFEST.md` scope and `TECH_STACK.md`, this repo is the knowledge foundation *for* a future stack (Next.js/TypeScript/React/Tailwind frontend, Next.js API routes on Node, MySQL+Prisma, hosted on Hostinger at `afaqalhayatae.com`) — none of that is implemented here yet. Source code implementation, accounting, HR, and financial reporting are explicitly out of scope for this repository. Don't scaffold an application in this repo unless the user is deliberately starting that phase.

## Governance artifacts worth knowing about

- `00_GOVERNANCE/DECISION_LOG.md` — record of approved decisions; check before assuming something is undecided.
- `00_GOVERNANCE/MIGRATION/` — evidence from the repo's architecture migration (inventory, conflict report, migration map, validation, rollback). Historical/audit trail, not a place to make new factual edits.
- `00_GOVERNANCE/GLOSSARY.md`, `PROJECT_SCOPE.md`, `PROJECT_GOALS.md`, `PROJECT_ROADMAP.md` — supporting context for scope and direction questions.
