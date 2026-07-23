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

## Deferred / open (see `00_GOVERNANCE/MIGRATION/VALIDATION_REPORT.md` for full detail)

- Folder-numbering convention for 7 additional service-knowledge packages (AC Maintenance, Cleaning Services, Plumbing, Electrical Maintenance, Painting Services, Handyman Services, Water Tank Cleaning) — content in scope per decision 5, destination IDs not yet assigned.
- Per-file placement for 14 cross-cutting sales/operations drafts.
- Manual reconciliation of the 3 held Service Areas documents into one canonical `03_MARKET/SERVICE_AREAS.md`.
