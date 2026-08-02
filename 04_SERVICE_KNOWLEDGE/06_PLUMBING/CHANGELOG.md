# Plumbing Changelog

| Version | Date | Status | Description |
|---|---|---|---|
| 0.1 | 2026-07-24 | Draft | Created governed package skeleton and evidence gates; no service facts approved. |
| 0.2 | 2026-07-28 | Draft | Added `IMAGE_SEO_LIBRARY.md`, `IMAGE_GENERATION_BRIEF.md`, and `assets/{hero,service-cards,process,trust,blog}/` (image library addition; corrects an earlier version mistakenly created under a differently-numbered folder — see `07_WEBSITE/IMPLEMENTATION/IMAGE_LIBRARY_CREATION_REPORT.md`). Planning only; no images generated; no service facts approved. |
| 0.3 | 2026-08-01 | Draft | Reviewed for Owner-approved sync (`00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_PLAN.md`, `DECISION_LOG.md` #38) — not executed. `CONTENT_EN.md`, `CONTENT_AR.md`, `FAQ.md`, and `SEO_AI.md` remain unpopulated content-gate templates: no customer-facing description, FAQ answer, or SEO field has been authored into this repository for this service. The general operational content decision #38 approved was authored directly in a separate application repository (`afaqalhayatae-app`) and was never mirrored here. Flipping this package's status without populated content would misrepresent an empty template as approved, so no status field was changed. See `00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md` for detail. |
| 0.4 | 2026-08-01 | Migrated (Pilot) | Executed the Owner-approved Plumbing pilot migration (`00_GOVERNANCE/PLUMBING_CONTENT_SYNC_EXECUTION_PLAN.md`, following the AC Maintenance precedent): transcribed real bilingual content from `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` (`plumbing` record) into `CONTENT_EN.md`/`CONTENT_AR.md` (overview, common problems, scope included/excluded, process, benefits, general safety notes, CTA), `FAQ.md` (4 real Q&A pairs, replacing the unanswered backlog), and `SEO_AI.md` (SEO title/meta/keywords, publication half only — Live AI Answers gate unchanged). CTA applied directly per Owner instruction: "Book Appointment" / "احجز موعد" — no service-specific wording invented. No price, warranty, certification, or response-time/emergency claim was introduced; each file's Evidence Gate is preserved, reworded only to confirm these categories remain unapproved. The one response-time-adjacent FAQ ("same day" question) was checked and migrated as-is — its answer defers to real-time scheduling, no commitment made. The "Pipe Repair UAE" keyword was checked against the excluded-scope item on major re-piping and found consistent with the included scope (pipe joint/fitting repair) — no removal needed, unlike the AC Maintenance precedent. Per Owner instruction, `README.md`'s status was **not** changed — package status remains exactly as recorded in entry 0.3 until the plan's §6 approval checkpoint clears. Only this service's allowed files were touched; no other service, no website file, no catalog file, and no commit/push. |

## Pending Milestones

- Owner scope confirmation
- Competent operational, safety, and compliance review
- Bilingual content review
- Commercial and publication approval

## Traceability

Where present, `SOURCE_DRAFT.md` remains preserved as non-authoritative source
material. This changelog does not promote it to an approved source.
