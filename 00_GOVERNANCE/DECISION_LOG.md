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

## 2026-07-25 — Program C Phase C.2 Work Package 4: canonical file creation

| # | Decision | Scope and guardrail |
|---|---|---|
| 33 | Following Owner authorization of Program C Phase C.2 Work Package 4 (design proposals, then the file-creation plan), three canonical files were created, each independently reviewed by `AGT-QA` before commit: `04_SERVICE_KNOWLEDGE/SERVICE_DNA_REGISTRY.md` (commit `0e3c6db`, fulfilling decision 24), `04_SERVICE_KNOWLEDGE/SERVICE_RELATIONSHIPS.md` (commit `690c1fc`, fulfilling decision 25), and `00_GOVERNANCE/ENTERPRISE_CUSTOMER_INTENT_MODEL.md` (commit `d0dcd72`, resolving decision 26/30's previously undecided canonical path). | Each file is `Status: Draft`, not Approved — none is elevated beyond the resolved content already Owner-confirmed across Phase C.1 and Phase C.2 Work Packages 1–3. This entry does not reopen or re-approve decisions 24, 25, 26, 30, or 31; at the time decision 31 was recorded, none of these files existed, and decision 31 explicitly anticipated their creation only "through a later, separately approved build step" — this entry records that step having occurred, not a revision of decision 31's own historical accuracy. Creation does not enable live automation, publishing, or customer-facing use, and does not modify `ENTERPRISE_SERVICE_META_MODEL.md` or `ENTERPRISE_PUBLICATION_GATE_MODEL.md`. |

## 2026-07-26 — Technical stack: MySQL adopted as canonical database engine

| # | Decision | Scope and guardrail |
|---|---|---|
| 34 | Following Hostinger plan verification (decision 16's open gate) — confirmed: Next.js, Node.js, and MySQL are supported; PostgreSQL is not available on the current plan — the Business Owner adopts MySQL as the canonical database engine, superseding the PostgreSQL references in decision 22 and `TECH_STACK.md`. Prisma remains the canonical ORM. Next.js, TypeScript, React, Tailwind CSS, and Node.js are unchanged. | This decision amends decision 22's database-engine component only; its WordPress/hybrid exclusion and decision 16's Hostinger-provider guardrail are untouched. It does not authorize any external database provider, does not approve production deployment or credentials, and does not change any other stack component. Implementation has not started; no code or schema exists to migrate. |

## 2026-07-27 — Phase 1 implementation preparation approved

| # | Decision | Scope and guardrail |
|---|---|---|
| 35 | The Business Owner approves five Phase 1 implementation-preparation decisions, recorded in `07_WEBSITE/IMPLEMENTATION/00_PHASE1_APPROVAL.md`: (a) `12_DESIGN_SYSTEM/COLORS.md` is the single implementation color source; (b) `02_BRAND/BRAND_COLORS.md` remains brand/print reference only until a future reconciliation; (c) the website application is built as a separate repository/project (proposed name `afaqalhayatae-web`, not yet created); (d) no application code is added inside this knowledge repository; (e) the canonical stack remains Next.js, TypeScript, React, Tailwind CSS, Node.js, MySQL, Prisma. | Resolves the color-token conflict `01_APPLICATION_ARCHITECTURE.md` §6 flagged for Owner decision, in the direction that section already recommended — `02_BRAND/BRAND_COLORS.md` is not edited or deleted. Confirms decision 34 (MySQL) and the existing two-repository model (`02_FOLDER_STRUCTURE.md` §1) as Owner decisions rather than proposals. Authorizes only Phase 1 scaffolding scope as defined in `00_PHASE1_APPROVAL.md` §2; does not authorize writing application code before that file's readiness review completes, and does not authorize staging, production, credentials, DNS/hosting changes, or any commercial/legal/safety claim. |

## 2026-07-28 — Realistic photography image direction approved

| # | Decision | Scope and guardrail |
|---|---|---|
| 36 | The Business Owner approves realistic professional photography style — luxury corporate, official AFAQ AL HAYAT logo only, consistent team uniform identity, UAE professional environment — as the platform's image direction for service pages, hero images, service cards, process images, trust images, and marketing assets, recorded in `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md` §3 (v2.0). This supersedes that document's prior v1.0 rule requiring illustration/line-art style for any AI-generated placeholder imagery. | Real photography remains the preferred, primary source (§2 of the same document, unchanged). Brand-safety rules (official logo only, no invented logos/company names/phone numbers, consistent uniform, UAE environment) and evidence-based-claims rules (testimonials, before/after, fake identities, the §7 method-gating rule) are explicitly carried forward and not loosened by this decision. Does not authorize generating, sourcing, or publishing any image — no image-generation tool/API/credential is selected. Does not amend `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §10's absolute prohibition on "AI-generated media presented as real company evidence" — `11_VISUAL_ASSET_STRATEGY.md` §3 flags this as an open conflict requiring separate Owner reconciliation of that document before any photorealistic AI-generated image is used in a way that could be mistaken for real company evidence. |

## 2026-07-31 — Service Completion Phase, Pest Control approval

| # | Decision | Scope and guardrail |
|---|---|---|
| 37 | Following the Service Completion Audit (`afaqalhayatae-app` repo, `docs/SERVICE_COMPLETION_MATRIX.md`), the Business Owner approves the drafted Pest Control content package (`01_PEST_CONTROL/02_SEO_DATA.md`, `06_PAGE_CONTENT.md`, `04_FAQ.md`, and the 11 sub-service pages in `src/lib/catalog/pest-control-pages.ts`) for publication as-is, clearing the Evidence Gate that previously held it in Review Draft. The Owner also confirms Gecko Control is kept as an 11th approved pest-control service alongside the original 10-item list (resolving the 2026-07-30 reconciliation gap), and confirms Bed Bug Control's missing card image stays an open item — excluded from the sub-service grid until a real photograph exists, not a defect requiring a placeholder. | Approval covers only the Pest Control content package already drafted and reviewed; it does not approve any Maintenance or Cleaning content (still content-gate stubs, "Pending Owner Input" per `04_SERVICE_KNOWLEDGE/<NN_SERVICE>/CONTENT_EN.md`), does not authorize inventing scope/process/warranty/safety facts for any other service, and does not authorize any image-generation tooling (none selected/available). Separately, the Owner directed the defective Waterproofing card image (baked-in AI-rendering typo, "FOR MAINTTNANCE ANDD CLEANLINESS") be pulled from customer-facing use rather than repaired, since no image tool exists to fix it — Waterproofing now has no card image pending a real replacement photo. |

## 2026-07-31 — Service Completion Phase, Maintenance + Cleaning content and 4 new services

| # | Decision | Scope and guardrail |
|---|---|---|
| 38 | Following decision 37 (Pest Control), the Business Owner directs completion of the remaining Maintenance and Cleaning services: content (overview, common problems, scope, professional workflow, benefits, safety, FAQ) and SEO (title, meta description, keywords) may be authored directly from general operational/industry knowledge for AC Maintenance, Electrical Maintenance, Plumbing, Painting, Drain Unblocking, Water Leak Detection, Waterproofing, Handyman, General Cleaning, Deep Cleaning, and Water Tank Cleaning — explicitly excluding any invented price, discount, warranty, guarantee, license, certification, or exact response-time commitment. The Owner also approves four new catalog services — Villa Cleaning (`SVC-VILLA-CLEANING`), Office Cleaning (`SVC-OFFICE-CLEANING`), Post-Construction Cleaning (`SVC-POST-CONSTRUCTION-CLEANING`), Carpet & Upholstery Cleaning (`SVC-CARPET-UPHOLSTERY-CLEANING`) — added to `SERVICE_CATALOG.md` and `services.ts`, using the same authored-content approach and existing pre-staged card images. | This decision does not authorize any price, warranty, license, certification, or response-time claim anywhere — those fact categories remain governed by each service's `CONTENT_EN.md` Evidence Gate (per decision text above, "must not be inferred from a service name, generic industry practice, or a source draft" — that instruction is unchanged and still binding for those specific fact categories; only the non-gated categories listed above were authored). It does not create a `04_SERVICE_KNOWLEDGE/` folder for the 4 new services (content lives directly in `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` with a provenance note; a documentation-parity gap tracked in `docs/SERVICE_COMPLETION_MATRIX.md`, not resolved by this entry). It does not authorize any image-generation tooling (none selected/available) — Handyman and Waterproofing remain without a real card image and stay excluded from the website's grids/related-links per the same no-placeholder rule as decision 37. Full detail: `afaqalhayatae-app/docs/SERVICE_COMPLETION_MATRIX.md`. |

## 2026-07-31 — Service Expansion Phase: 11 new catalog services (structural only)

| # | Decision | Scope and guardrail |
|---|---|---|
| 39 | Following the Visual Asset Master Plan/Specification List and a batch of Owner-delivered candidate images (inspected against brand rules 2026-07-31 — see `afaqalhayatae-app/docs/VISUAL_ASSET_MASTER_PLAN.md` §5), the Business Owner approves onboarding 11 new catalog services: CCTV Installation (`SVC-CCTV-INSTALLATION`), Smart Home Installation (`SVC-SMART-HOME-INSTALLATION`), Swimming Pool Maintenance (`SVC-SWIMMING-POOL-MAINTENANCE`), Kitchen Installation (`SVC-KITCHEN-INSTALLATION`), Interior Decoration (`SVC-INTERIOR-DECORATION`), Interlock Installation (`SVC-INTERLOCK-INSTALLATION`), Lighting Maintenance (`SVC-LIGHTING-MAINTENANCE`), Wood Alternative Installation (`SVC-WOOD-ALTERNATIVE-INSTALLATION`), Wallpaper Installation (`SVC-WALLPAPER-INSTALLATION`), Thermal Insulation (`SVC-THERMAL-INSULATION`), and Rooftop Space Utilization (`SVC-ROOFTOP-SPACE-UTILIZATION`) — all under the General Maintenance category. Each received a catalog entry, bilingual (EN/AR) name, unique slug, and SEO title/meta description/keywords authored from general operational knowledge (no invented price, warranty, license, certification, or response-time claim). 10 of the 11 also received an Owner-approved real card image, moved from storage-only into active use; CCTV Installation has no image (the requested asset was never located) and stays excluded from grids per the site's existing no-placeholder rule (same treatment as Handyman/Waterproofing/Bed Bug Control). | This decision covers **structure only** — none of the 11 has full page content (overview, scope, process, benefits, safety, FAQ) yet, so none is added to the website's content-approval gate and all 11 remain `noindex` until a future, separately-approved content phase. Does not modify, rewrite, or de-scope any of the 16 already-complete services (decisions 37, 38). Does not authorize any image-generation tooling. Does not create a `04_SERVICE_KNOWLEDGE/` folder for any of the 11 (same documentation-parity gap already open for the 4 Cleaning services from decision 38). Full detail: `afaqalhayatae-app/docs/VISUAL_ASSET_MASTER_PLAN.md` and `docs/SERVICE_COMPLETION_MATRIX.md`. |

## Deferred / open (see `00_GOVERNANCE/MIGRATION/VALIDATION_REPORT.md` for full detail)

- Folder-numbering convention for 7 additional service-knowledge packages (AC Maintenance, Cleaning Services, Plumbing, Electrical Maintenance, Painting Services, Handyman Services, Water Tank Cleaning) — content in scope per decision 5, destination IDs not yet assigned.
- Per-file placement for 14 cross-cutting sales/operations drafts.
- Manual reconciliation of the 3 held Service Areas documents into one canonical `03_MARKET/SERVICE_AREAS.md`.
