# Decision Log

## Purpose

Records architectural and content-governance decisions for the AFAQ Alhayat Enterprise Knowledge System, so future contributors and AI systems understand not just the current state but why it is structured this way.

---

## 2026-07-23 — Repository architecture migration

Source: `SYSTEM_ARCHITECTURE.md` v1.0, migration plan `MIGPLAN-20260723-0326-4ff3164091`. Full detail in `00_GOVERNANCE/MIGRATION/`.

| # | Decision | Rationale |
|---|---|---|
| 1 | `01_BUSINESS/COMPANY_PROFILE.md` (former `00_START/01_BUSINESS/00_COMPANY_PROFILE.md`) is canonical over the TEMP draft. | More complete: includes vision, mission, and core values. TEMP copy archived intact, not deleted. |
| 2 | `02_BRAND/BRAND_GUIDELINES.md` (former `00_START/.../08_BRAND_GUIDELINES.md`) is canonical over the TEMP draft. | More complete: covers logo, color, typography, photography, and print rules. TEMP copy archived intact. |
| 3 | `03_MARKET/COMPETITOR_ANALYSIS.md` (former `00_START/01_BUSINESS/06_COMPETITOR_ANALYSIS.md`) is canonical over the TEMP stub. | TEMP copy was empty (0 bytes); this copy has real content. Empty stub archived intact. |
| 4 | Service Areas — three overlapping documents (`TEMP/.../SERVICE_AREAS.md`, `18_SERVICE_LOCATIONS.md`, `19_SERVICE_AREAS_BY_EMIRATE.md`) are held, not merged. | No canonical geographic-coverage list existed; auto-merging risked silently dropping or duplicating area data. Deferred to manual reconciliation. |
| 5 | Both a general-maintenance service line and a cleaning/pest-control service line are confirmed in scope for the company. | AFAQ Alhayat's source documents describe both; the final `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` must categorize rather than choose one. |
| 6 | The 11-file Pest Control service-knowledge package is canonical over two competing single-file Pest Control drafts. | Most complete and structured source; the two drafts were shallower and inconsistent with it. Both archived, preserved for later comparison. |
| 7 | General (company-wide) FAQ and per-service FAQ are kept as separate documents. | Different ownership scope — one answers cross-cutting questions, the other answers questions specific to one service. Not a duplicate. |
| 8 | A zero-byte, extensionless file nested at `.../06_DESIGN_SYSTEM/07_WEBSITE/01_HOMEPAGE` is treated as accidental unclassified residue. | No plausible intended use identified; archived rather than deleted, in case it is later found to matter. |
| 9 | `PROJECT_CONSTITUTION.md` is placed under `07_WEBSITE/WORDPRESS/` rather than `00_GOVERNANCE/`. | Its content governs the WordPress implementation specifically, not project-wide governance. |
| 10 | `CONTACT_INFORMATION.md` moved as-is; its placeholder phone/WhatsApp values are marked Draft/Unverified. | Real values were never supplied. Placeholder contact data must never be treated as publishable per `SYSTEM_ARCHITECTURE.md` Sec. 10.2. |
| 11 | Empty directories `00_START/01_BRAND/` and `00_START/02_MARKET/` are confirmed to hold no expected content. | Investigated during Phase A discovery; nothing was lost, nothing needed migrating from them. |
| 12 | Every migration batch required explicit user approval before execution. | Chosen migration-safety posture given the volume of overlapping/conflicting source material discovered during Phase A. |
| 13 | `WORDPRESS_DATABASE_ARCHITECTURE.md` (former `05_DATABASE_ARCHITECTURE.md`) placed under `08_DIGITAL_SYSTEMS/DATABASE/`, not `07_WEBSITE/WORDPRESS/`. | Defines a hybrid WordPress + operational database architecture — belongs to the Digital Systems database domain per `SYSTEM_ARCHITECTURE.md` Sec. 5. |

## 2026-07-23 — Owner-confirmed operating inputs

| # | Decision | Scope and guardrail |
|---|---|---|
| 14 | Canonical phone is `+971 58 543 1766`. | Phone only; WhatsApp remains unconfirmed and must not be inferred. |
| 15 | Production domain is `afaqalhayatae.com`. | Canonical host and redirect configuration require deployment verification. |
| 16 | Hosting provider is Hostinger. | Exact plan compatibility with Next.js, Node.js, PostgreSQL, CI/CD, backups, and staging requires technical verification. |
| 17 | All services in the current canonical catalog are offered across all seven UAE emirates. | Approval is emirate-level only; it does not authorize city/community pages, virtual branches, response-time promises, or automatic booking availability. |
| 18 | The project may select premium-property and high-value communities as initial marketing priorities, with all catalog services available. | Priority is based on property and market characteristics, not individual personal data. Coverage remains UAE-wide; dedicated pages and campaigns still require quality, operational, and measurement gates. |
| 19 | Drain Unblocking, Waterproofing, and Water Leak Detection are official services and are available across the approved UAE coverage. | Detailed methods, equipment, materials, licenses, prices, response times, and warranties remain unpublished until verified by the appropriate owner and technical reviewers. “Waterproofing” is currently interpreted as water-ingress protection; thermal insulation is not included unless separately confirmed. |
| 20 | The business owner is the only internal human operator; the project will not assume employees or internal departments. | Business functions are performed by governed AI agents and automated systems. The owner retains final authority. External licensed providers may be used for physical, regulated, or specialist work but are not represented as internal staff. |
| 21 | The governed Agent Operating System and risk-based model-routing policy are approved. | Specialist agents use bounded roles, independent QA, Git-first recovery, and owner gates. Current flagship models handle high-impact architecture and review; balanced models handle routine implementation; efficient models are limited to deterministic, easily verified work. |
| 22 | The canonical implementation direction remains Next.js, TypeScript, React, Tailwind CSS, Node.js, PostgreSQL, and Prisma. | This is the existing approved direction in `TECH_STACK.md`. WordPress and hybrid documents are retained as non-canonical research and cannot drive implementation without a new owner decision. Hostinger plan compatibility remains a required verification gate. |

## 2026-07-24 — EAOS v1 approval

| # | Decision | Scope and guardrail |
|---|---|---|
| 23 | The Enterprise Agent Operating System v1 (`00_GOVERNANCE/EAOS/`, 8 documents: `EAOS_CHARTER.md`, `EAOS_ARCHITECTURE.md`, `REGISTRIES.md`, `AGENT_LIFECYCLE.md`, `COMMUNICATION_PROTOCOL.md`, `DECISION_FLOW.md`, `QUALITY_GATES.md`, `README.md`) is approved as the governing protocol description for agent job structure, lifecycle, communication, decision flow, and quality gates. | Approval covers the documented protocol only, following independent QA (`JOB-000001`, `AGT-QA`, 0 defects, Pass) and a successful pilot. It does not enable live automation, create new agent roles, create new capabilities beyond `REGISTRIES.md`'s existing Capability Registry, start Program C, or authorize any credential, spend, or publishing action. |

## 2026-07-24 — ESMM governance decisions

Source: Enterprise Service Meta-Model (ESMM) proposal and its Owner review
package. ESMM itself is not yet ratified and has not been written to a
repository file; these decisions govern its future build, not its current
existence.

| # | Decision | Scope and guardrail |
|---|---|---|
| 24 | A future `SERVICE_DNA_REGISTRY` is approved in concept, to be placed within the `04_SERVICE_KNOWLEDGE` domain when built. | No file is created by this decision. Structure and fields remain subject to ESMM's own design and a later, separately approved build step. |
| 25 | A future `SERVICE_RELATIONSHIPS` registry is approved in concept, to be placed within the `04_SERVICE_KNOWLEDGE` domain when built. | No file is created by this decision. Once built, every relationship entry must validate against an existing `SVC-` ID in `SERVICE_CATALOG.md`. |
| 26 | The Customer Intent Model is approved as a future enterprise-wide canonical model serving AI, CRM, Booking, and Analytics jointly. | AI Experience is explicitly **not** the sole owner. Exact file placement is undecided and remains an open blocker before ratification. |
| 27 | `SERVICE_CATALOG.md` categories remain classification labels only; no Parent Service Object is created at this stage. | ESMM §12 (Parent-Child Lifecycle Constraints) and §14 (Object Inheritance Rules) remain dormant until a future, separately approved decision revisits this. |
| 28 | The Enterprise Publication Gate Model (EPGM) remains a separate model from ESMM — cross-referenced, never merged. | Preserves the "no new architectural layer" boundary both models were built under; each keeps its own review and ratification cycle. |
| 29 | Future ESMM and EPGM governed documents, once created, will be placed under `00_GOVERNANCE/`. | No file is created by this decision. Placement only — content, drafting, review, and ratification remain separate future steps. |
| 30 | The Customer Intent Model's ownership is Enterprise Knowledge Governance; AI, CRM, Booking, and Analytics are consumers, not owners. | Resolves the placement blocker from decision 26 — AI Experience is confirmed a consumer only, not sole owner. Exact file name and path within governance remain undecided. No file is created by this decision; the model itself is not yet drafted. |

## 2026-07-24 — ESMM and EPGM ratification

| # | Decision | Scope and guardrail |
|---|---|---|
| 31 | `ENTERPRISE_SERVICE_META_MODEL.md` and `ENTERPRISE_PUBLICATION_GATE_MODEL.md` are approved, and EPGM's `Blocked`/`Suspended` status modifiers are formally adopted alongside the existing five-value status vocabulary. | Approval covers the documented model and computation only, following independent QA (0 defects, Pass) accepted by the Owner. It does not create `SERVICE_DNA_REGISTRY`, `SERVICE_RELATIONSHIPS`, or a Customer Intent Model file, does not start Program C, and does not enable live automation. `Suspended` may be set only by the Business Owner, or provisionally by `AGT-QA` pending immediate Owner confirmation, per `ENTERPRISE_PUBLICATION_GATE_MODEL.md` §14. |

## 2026-07-24 — Enterprise Constitution ratification

| # | Decision | Scope and guardrail |
|---|---|---|
| 32 | `ENTERPRISE_CONSTITUTION.md` is ratified by the Business Owner as v1.0, Approved, effective retroactively to 2026-07-24 — the date it was drafted and the date the EAOS v1 (decision 23) and ESMM/EPGM (decision 31) approvals were recorded. | Retroactive effect confirms EAOS v1, ESMM, and EPGM remain validly approved under the ratified Constitution; decisions 23 and 31 are not reopened, re-reviewed, or re-approved by this entry. Ratification covers the Constitution's text only. It does not start Program C, does not create `SERVICE_DNA_REGISTRY`, `SERVICE_RELATIONSHIPS`, or a Customer Intent Model file, and does not enable live automation. |

## Deferred / open (see `00_GOVERNANCE/MIGRATION/VALIDATION_REPORT.md` for full detail)

- Folder-numbering convention for 7 additional service-knowledge packages (AC Maintenance, Cleaning Services, Plumbing, Electrical Maintenance, Painting Services, Handyman Services, Water Tank Cleaning) — content in scope per decision 5, destination IDs not yet assigned.
- Per-file placement for 14 cross-cutting sales/operations drafts.
- Manual reconciliation of the 3 held Service Areas documents into one canonical `03_MARKET/SERVICE_AREAS.md`.
