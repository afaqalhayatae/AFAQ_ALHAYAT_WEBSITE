# Migration Plan

- Plan ID (approved): `MIGPLAN-20260723-0326-4ff3164091`
- Superseded plan ID: `MIGPLAN-20260723-0311-1147028ce7` (invalidated by applying decisions 1–12; underlying content inventory unchanged between the two)
- Approval statement received: `APPROVE MIGRATION PLAN MIGPLAN-20260723-0326-4ff3164091`
- Baseline commit: `46fa2a2` — `chore(migration): capture untouched pre-migration baseline`
- Baseline tag: `pre-architecture-migration-20260723-0326`
- Migration branch: `chore/architecture-migration-20260723`
- Target architecture: `SYSTEM_ARCHITECTURE.md` v1.0 (2026-07-23)

## Approved decisions (govern all batch execution below)

1. BUSINESS Company Profile canonical; TEMP copy archived intact.
2. BUSINESS Brand Guidelines canonical; TEMP copy archived intact.
3. Non-empty Competitor Analysis canonical; empty TEMP stub archived intact.
4. Service Areas (3 documents) held — no auto-merge; deferred to a separate manual reconciliation batch after structural migration.
5. Both maintenance and cleaning/pest-control service lines are in scope; preserved under one service catalog with clear categories.
6. 11-file Pest Control service-knowledge package canonical; other two Pest Control drafts archived, preserved for later content comparison.
7. General FAQ and per-service FAQs kept separate — different ownership levels.
8. Zero-byte extensionless `01_HOMEPAGE` object treated as accidental unclassified residue; archived, not deleted.
9. WordPress Project Constitution placed under `07_WEBSITE/WORDPRESS/`.
10. Contact information moved as-is, marked Draft/Unverified; placeholder phone/WhatsApp never treated as authoritative.
11. Empty directories `00_START/01_BRAND` and `00_START/02_MARKET` confirmed to hold no expected content; preserved in the migration record, nothing deleted.
12. Explicit approval required before every migration batch below — this document does not pre-authorize batch execution.

## Batch plan

| # | Batch | Item count | Status | Depends on |
|---|---|---|---|---|
| 0 | Baseline protection (this document set) | — | **Executed** — Git init, `.gitignore`, baseline commit, tag, branch, governance artifacts written | Plan approval |
| 1 | Governance & baseline | 12 moves + 2 empty-dir records | Awaiting per-batch approval | Batch 0 |
| 2 | Standards & design system | 21 moves + 1 archive (stray object) | Awaiting per-batch approval | Batch 0 |
| 3 | Business & brand | 19 moves + 3 archives (CNF-01/02/03) | Awaiting per-batch approval | Batch 0 |
| 4 | Market | 10 moves + 3 holds (CNF-04, deferred by design) | Awaiting per-batch approval | Batch 3 |
| 5 | Service knowledge | 12 direct moves + 4 archives (CNF-05, CNF-06) + 21 items pending sub-decisions (7 new-package IDs, 14 sales/ops placements) | Awaiting per-batch approval and remaining sub-decisions | Batches 3–4 |
| 6 | Website & WordPress | 5 kept in place + 8 standards moves (Batch 2) + 8 WordPress moves | Awaiting per-batch approval | Batch 0 |
| 7 | Remaining & legacy archive | Consolidates all ARCHIVE-action items from Batches 2, 3, 5 | Awaiting per-batch approval | Batches 2, 3, 5 |
| 8 | Link updates & validation | 0 items currently; re-evaluated after Batch 7 | Deferred | Batch 7 |

Full item-level detail (source, destination, action, checksum, collision status, approval requirement) is recorded in `MIGRATION_MAP.csv` in this directory.

## Execution rules in force

- Only approved move-map rows execute. HOLD rows do not move under this plan.
- `git mv` used for all tracked-file relocations.
- Before every move: verify source checksum matches `CURRENT_STATE_INVENTORY.md` and destination does not already exist. Either check failing marks that row BLOCKED and stops that item only.
- Target directories created only as required by the row being executed.
- Archived items preserved byte-for-byte under `98_LEGACY_ARCHIVE/`, recorded in `98_LEGACY_ARCHIVE/ARCHIVE_MANIFEST.csv`.
- Empty files are moved/archived per their assigned action, never deleted.
- One commit per approved batch; unrelated batches never combined.
- Checkpoint summary and verification shown after each batch; per decision 12, execution stops and waits for explicit approval before the next batch begins.

## Next step

Batch 1 (Governance & baseline) is ready to execute pending your explicit per-batch approval. No batch will run automatically.
