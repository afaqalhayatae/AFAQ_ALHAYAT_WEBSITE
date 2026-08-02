# Maintenance Content Sync Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only; no file copied, no service file modified, no website touched
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Authorizing decision:** Owner approval of Option C (Hybrid) in `00_GOVERNANCE/MAINTENANCE_CONTENT_SOURCE_DECISION.md`
- **Scope:** Planning only. No file was copied, created, or edited in `04_SERVICE_KNOWLEDGE/`, no website file in either repository was modified, nothing staged or committed in either repository.

## Purpose

Define exactly which application-repository files/fields become which knowledge-base files/sections for the 5 Maintenance services, how the transcription is verified before anything is treated as approved, and what audit trail preserves the move. Execution does not begin until this plan itself is reviewed.

---

## 1. Source Files in the Application Repository

Location: `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app` (confirmed accessible, read-only reference for this plan).

| File | Role |
|---|---|
| `src/data/SERVICE_DATABASE.json` | **Primary source.** Structured, per-service bilingual content: `name`, `content.{en,ar}.{heroTagline, overview, commonProblems[], scope.{included[],excluded[]}, process[], benefits[], safety[]}`, `faqs[]` (`id`, `question.{en,ar}`, `answer.{en,ar}`), `seoTitle.{en,ar}`, `metaDescription.{en,ar}`, `keywords.{en,ar}[]`, `status`, `sourceDocs[]`. |
| `docs/SERVICE_COMPLETION_MATRIX.md` | Cross-reference for verifying each service's claimed completeness and the 2026-07-31 authorship/authority basis (`DECISION_LOG.md` #38). |
| `src/lib/catalog/service-content.ts` | Defines `ServiceContentBlock` shape and `APPROVED_SERVICE_CONTENT_SLUGS` — confirms which slugs the application itself treats as approved/indexable, useful as a cross-check that the JSON content is actually live, not orphaned data. |

**Discrepancy noted, not resolved here:** each of the 5 services' `sourceDocs` field in `SERVICE_DATABASE.json` claims lineage from *this* knowledge repository (e.g., `ac-maintenance`'s `sourceDocs`: `["02_AC_MAINTENANCE/CONTENT_EN.md", "02_AC_MAINTENANCE/README.md"]`) — but those exact files, in this repository, are confirmed-empty governance templates (`SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`). The app repository's own provenance metadata is therefore inaccurate for these 5 services; it does not describe real lineage. This plan's verification steps (§5) do not rely on that metadata being correct — it is flagged here so execution doesn't repeat it as if it were true.

---

## 2. Target Knowledge Base Files

Per service, following the same structure already used successfully for General Cleaning and Water Tank Cleaning (per `MAINTENANCE_CONTENT_PHASE_PLAN.md` §3):

| File | Purpose |
|---|---|
| `CONTENT_EN.md` / `CONTENT_AR.md` | Service title, description/overview, common problems, scope, process, benefits, general safety notes, CTA |
| `FAQ.md` | Real question/answer pairs, replacing the current unanswered backlog |
| `SEO_AI.md` | SEO title, meta description, keywords, entity/category framing |
| `README.md` | Status banner update, citing `DECISION_LOG.md` #38 and this sync, once content clears verification |
| `CHANGELOG.md` | One appended audit entry per service recording the sync |

**Not in scope for this sync:** `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md` (the competent-safety-review file, distinct from the general safety notes below), `TRAINING.md`, `MEDIA.md`, `CUSTOMER_GUIDE.md`, `SOURCE_DRAFT.md` — same exclusions already established in `SERVICE_KNOWLEDGE_SYNC_PLAN.md` and unaffected by this sync. Images/assets and any website code in either repository are also out of scope, per the Owner's instruction.

---

## 3. Five-Service Scope

| # | Service | Knowledge-base folder | App-repo slug |
|---|---|---|---|
| 1 | AC Maintenance | `04_SERVICE_KNOWLEDGE/02_AC_MAINTENANCE/` | `ac-maintenance` |
| 2 | Plumbing | `04_SERVICE_KNOWLEDGE/06_PLUMBING/` | `plumbing` |
| 3 | Electrical Maintenance | `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/` | `electrical-maintenance` |
| 4 | Painting | `04_SERVICE_KNOWLEDGE/08_PAINTING/` | `painting` |
| 5 | Handyman Services | `04_SERVICE_KNOWLEDGE/09_HANDYMAN/` | `handyman` |

No other service (Drain Unblocking, Water Leak Detection, Waterproofing — grouped under "Maintenance" in the app repo but under "Drainage & Water Protection" in this repository's `SERVICE_CATALOG.md`) is in scope for this sync, even though the app repository has equivalent content for them. Extending this sync to those 3 is a separate, not-yet-authorized decision.

---

## 4. Mapping — Source Content → Knowledge Base Structure

| Source field (`SERVICE_DATABASE.json`) | Target file | Target section |
|---|---|---|
| `name.en` / `name.ar` | `CONTENT_EN.md` / `CONTENT_AR.md` | Service Title |
| `content.{en,ar}.overview` | `CONTENT_EN.md` / `CONTENT_AR.md` | Short Description / Customer-Facing Overview |
| `content.{en,ar}.heroTagline` | `CONTENT_EN.md` / `CONTENT_AR.md` | Optional supporting line under the title (not a substitute for the overview) |
| `content.{en,ar}.commonProblems[]` | `CONTENT_EN.md` / `CONTENT_AR.md` | New "Common Problems" subsection |
| `content.{en,ar}.scope.included[]` / `.excluded[]` | `CONTENT_EN.md` / `CONTENT_AR.md` | "Scope" subsection (Included / Excluded), matching `99_STANDARDS/SERVICE_TEMPLATE.md`'s Service Scope section |
| `content.{en,ar}.process[]` | `CONTENT_EN.md` / `CONTENT_AR.md` | "Process Summary" (numbered steps, matching the General Cleaning pattern) |
| `content.{en,ar}.benefits[]` | `CONTENT_EN.md` / `CONTENT_AR.md` | "Why Choose Us" / benefits list |
| `content.{en,ar}.safety[]` | `CONTENT_EN.md` / `CONTENT_AR.md` | General customer-facing safety notes — **not** a substitute for `SAFETY.md`'s separate competent-safety-review gate, which stays untouched and unresolved |
| `faqs[]` (`question`, `answer`, both languages) | `FAQ.md` (+ new `FAQ_AR.md` if the package needs a dedicated Arabic FAQ file, matching Pest Control's pattern) | Replaces the current unanswered "Approved Question Backlog" with real Q&A |
| `seoTitle.{en,ar}`, `metaDescription.{en,ar}`, `keywords.{en,ar}[]` | `SEO_AI.md` | SEO title/meta/keyword fields, carrying forward the existing "illustrative/unresearched keyword" caveat already standard in this repository |
| *(no source field — not present in the JSON)* | `CONTENT_EN.md` / `CONTENT_AR.md` | Call to Action — no per-service CTA exists in the source; use the same generic, already-approved CTA pattern already in place for General Cleaning/Water Tank Cleaning ("Request an assessment through an approved contact channel...") rather than inventing new per-service wording |
| `status.packageStatus`, this sync itself | `README.md` | Status banner, citing `DECISION_LOG.md` #38 and this sync as the basis, once verification (§5) passes |

---

## 5. Verification Steps

No content moves from "transcribed" to "approved" in this repository until all four checks pass, per service:

### Bilingual consistency
- Confirm `content.en` and `content.ar` express the same facts (not a literal word-for-word translation, but no fact present in one language and missing or different in the other), per `PROJECT_MANIFEST.md`'s bilingual-equality principle.
- Confirm every `faqs[]` entry has both `question.en`/`question.ar` and `answer.en`/`answer.ar` populated and consistent.

### Claim safety
- Re-check every `overview`, `commonProblems`, `scope`, `process`, `benefits`, and `safety` line against this repository's Hard Publication Blocks — no price, discount, warranty, guarantee, license, certification, or exact response-time claim, even though `SERVICE_COMPLETION_MATRIX.md` already asserts this is clean. This repository's own rule (`ENTERPRISE_PUBLICATION_GATE_MODEL.md` §10) is that a producing role cannot self-approve — the app repository's self-assessment is not treated as sufficient on its own.
- Specifically confirm every FAQ answer touching warranty, pricing, or commitment uses the Owner's standardized "subject to company policy" / "يخضع ذلك لسياسة الشركة" hedge (confirmed present in the AC Maintenance warranty FAQ on inspection) rather than a firmer claim slipping through in any of the other 4 services.

### SEO review
- Confirm `seoTitle`/`metaDescription` restate only facts already present in the transcribed content — no new claim introduced via the SEO fields that isn't already in the body copy.
- Confirm `keywords[]` are carried over labeled as illustrative/unresearched, consistent with this repository's standing keyword caveat (`07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`) — not elevated to "researched" status by virtue of having come from the app repository.

### FAQ review
- Confirm each transcribed FAQ question is a genuine, plausible customer question (not a keyword phrased as a question).
- Confirm no FAQ answer commits to a specific price, timeframe, or guarantee.
- Confirm question/answer pairs read naturally in both languages, not as a mechanical translation of each other.

**Verification owner:** consistent with this repository's existing rule that a producing role cannot self-approve, whoever performs the transcription (steps in §6) should not be the same party who signs off on these four checks — an independent pass is required before any `README.md` status is updated, mirroring `SERVICE_KNOWLEDGE_SYNC_PLAN.md`'s validation discipline.

---

## 6. Migration Rules

- **Preserve original source reference.** Every transcribed file must record its provenance — source repository (`afaqalhayatae-app`), source file (`src/data/SERVICE_DATABASE.json`), and the date/commit state read — so a future reader can trace the content back to where it actually came from (correcting, not repeating, the inaccurate `sourceDocs` metadata noted in §1).
- **Do not delete existing drafts.** The current empty-template `CONTENT_EN.md`/`CONTENT_AR.md`/`FAQ.md`/`SEO_AI.md` content (the "Content Gate," "Content Pending Approval" checklist, "Approved Question Backlog") is replaced by real content, not deleted-then-recreated — the file's edit history in Git preserves the prior state; no separate backup copy is required beyond normal version control.
- **Maintain audit trail.** Each service's `CHANGELOG.md` gets exactly one new appended entry recording: what was transcribed, from where, that verification (§5) was completed and by whom, and that no new claim was introduced beyond what the source already contained. This follows the same append-only pattern already used in `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`.
- **No status change without verification.** A `README.md` status banner is only updated after §5's four checks pass for that specific service — services do not move as an all-or-nothing batch; a service that fails verification stays in its current (empty-template) state rather than being partially synced.

---

## 7. Homepage Readiness Criteria After Sync

The Maintenance category becomes eligible for full homepage content (per `HOMEPAGE_CONTENT_DECISION_APPLIED.md` §1, Decision 2) only once, for each of the 5 services:

1. `CONTENT_EN.md`/`CONTENT_AR.md`, `FAQ.md`, and `SEO_AI.md` contain transcribed, verified content (§5 passed).
2. `README.md`'s status banner has been updated citing `DECISION_LOG.md` #38 and this sync.
3. `CHANGELOG.md` carries the audit entry required by §6.
4. No Hard Publication Block condition is present (no price/warranty/certification/license/response-time claim survived transcription).

If fewer than all 5 services clear these criteria, the Owner may still choose a partial-launch homepage treatment (e.g., showing only the services that passed) — but this plan does not decide that; it is the same kind of homepage-treatment choice already recorded as Owner-decidable in `HOMEPAGE_CONTENT_APPROVAL_DECISION.md`.

---

## What This Document Does Not Do

- Does not copy any file from `afaqalhayatae-app` into this repository.
- Does not modify any file in `04_SERVICE_KNOWLEDGE/`.
- Does not modify any website file in either repository.
- Does not commit or push anything in either repository.

---

## Related Documents

- `00_GOVERNANCE/MAINTENANCE_CONTENT_SOURCE_DECISION.md` — the Owner decision authorizing this plan (Option C)
- `00_GOVERNANCE/MAINTENANCE_CONTENT_PHASE_PLAN.md`
- `00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_PLAN.md`, `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`
- `00_GOVERNANCE/HOMEPAGE_CONTENT_DECISION_APPLIED.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `99_STANDARDS/SERVICE_TEMPLATE.md`
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json`, `docs/SERVICE_COMPLETION_MATRIX.md` — external repository, read-only reference
