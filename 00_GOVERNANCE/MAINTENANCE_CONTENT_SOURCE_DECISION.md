# Maintenance Content Source Decision

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — presents options only; no option is selected by this document
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning/recommendation only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Authorizing decision:** `00_GOVERNANCE/MAINTENANCE_CONTENT_PHASE_PLAN.md` §2's "Open sourcing question," which this document resolves the *information gap* on (but not the decision itself).
- **Scope:** Planning and research only. No Maintenance content was written, no `04_SERVICE_KNOWLEDGE/` service file was modified, no website file (in either repository) was modified. Nothing staged or committed in either repository.

## Purpose

Every prior report in this workstream (`HOMEPAGE_CONTENT_IMPLEMENTATION_PLAN.md`, `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`, `MAINTENANCE_CONTENT_PHASE_PLAN.md`) stated that the application repository referenced throughout `DECISION_LOG.md` (`afaqalhayatae-app`) could not be found on this machine. **That was incorrect, and this report corrects it.** A broader filesystem search (beyond the narrower paths checked previously) located it at `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app`, a real, active Next.js repository with its own git history. This materially changes the Maintenance Content Source Decision — Option A is no longer theoretical.

---

## 1. Current Maintenance Content State

### In this knowledge repository (`04_SERVICE_KNOWLEDGE/`)

Confirmed by direct file inspection during `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`'s execution: `02_AC_MAINTENANCE/`, `06_PLUMBING/`, `07_ELECTRICAL_MAINTENANCE/`, `08_PAINTING/`, and `09_HANDYMAN/` each contain only an empty governance template in `CONTENT_EN.md`/`CONTENT_AR.md`/`FAQ.md`/`SEO_AI.md` — a "Content Gate," a "Content Pending Approval" checklist of items not yet written, and an unanswered "Approved Question Backlog." No real customer-facing description, FAQ answer, or SEO field exists in this repository for any of the 5 Maintenance services.

### In the application repository (`afaqalhayatae-app`) — now confirmed accessible

Directly inspected this session, read-only:

- **`docs/SERVICE_COMPLETION_MATRIX.md`** (dated 2026-07-31) records all 8 of the app's "Maintenance" category services — AC Maintenance, Electrical Maintenance, Plumbing, Painting, Drain Unblocking, Water Leak Detection, Waterproofing, Handyman — as content-**COMPLETE**: real AR/EN overview, common problems, scope (included/excluded), process, benefits, safety, FAQ, distinct SEO title/meta/keywords, all authored 2026-07-31 "directly from general operational/industry knowledge per the Owner's explicit... instruction," with an explicit note that this content "deliberately contains no invented license, certification, warranty, guarantee, exact response-time, or other unsupported company claim."
- **`src/data/SERVICE_DATABASE.json`** contains this content in structured form. Spot-checked `ac-maintenance` directly: real `overview`, `commonProblems`, `scope.included`/`excluded`, `process`, `benefits`, `safety` fields in both languages; 3 real FAQ entries checked, including a warranty question answered with the standardized hedge "Warranty terms are subject to company policy — please confirm directly with our team before the visit" / "تخضع شروط الضمان لسياسة الشركة" — exactly the no-fabrication pattern this repository's own rules require, not a placeholder and not an invented commitment.
- **Categorization note:** the app groups Drain Unblocking, Water Leak Detection, and Waterproofing under "Maintenance," while this knowledge repository's `SERVICE_CATALOG.md` places them in a separate "Drainage & Water Protection" category. The 5 services this workstream has been calling "Maintenance" (AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman) are a subset of the app's 8 — all 5 are covered.
- **Working-tree state:** the app repository currently has uncommitted local changes (`git status` shows modifications across `blog`, `locations`, `services`, and layout pages, plus `package.json`) and `src/data/SERVICE_DATABASE.json` itself is untracked (`??`) in that repository's own git history — meaning this content, while real and substantive, is not yet committed even in its own repository.

---

## 2. Available Sources

| Source | State | Usable as-is? |
|---|---|---|
| **Existing knowledge base** (`04_SERVICE_KNOWLEDGE/02_AC_MAINTENANCE/` etc.) | Empty governance templates only | No — nothing to import from here; this is the destination, not a source |
| **Application repository** (`afaqalhayatae-app`, now confirmed accessible at `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app`) | Complete, real, bilingual content for all 5 required services in `src/data/SERVICE_DATABASE.json`, cross-verified against `docs/SERVICE_COMPLETION_MATRIX.md`; content itself is uncommitted in that repo | Content quality appears production-ready on inspection; formally still uncommitted work-in-progress there |

---

## 3. Options

### Option A — Import existing approved content from the application repository

**Benefits**

- The content already exists, is substantive, bilingual, and — on direct inspection — already follows this repository's no-fabrication rules (no invented price/warranty/certification/response-time; uses the Owner's standardized "subject to company policy" hedge exactly where a real commercial fact is genuinely pending).
- Fastest path to closing the gap — no new authoring effort, only transcription/formatting into this repository's file structure.
- Restores this repository's "single source of truth, write each fact once" principle (`PROJECT_MANIFEST.md`) for these 5 services, which currently only exists in the application repository.
- The content was reportedly authored under the same 2026-07-31 Owner instruction (`DECISION_LOG.md` #38) already governing the other services already synced in this repository — importing it is executing an already-made decision, not making a new content decision.

**Risks**

- **Direction-of-flow inversion:** `PROJECT_MANIFEST.md`'s "Knowledge First" principle states knowledge does not depend on applications — this content was authored directly in the application repository, bypassing the knowledge repository entirely, which is the reverse of the intended architecture. Importing it now is a backfill correcting that inversion, not a normal knowledge-first authoring step — worth the Owner's awareness even though the fix itself is straightforward.
- The source content in the app repository is itself uncommitted (`src/data/SERVICE_DATABASE.json` is untracked there) — importing now means importing a moving target; a later change in the app repo would not automatically propagate back.
- Requires a content-fidelity review to confirm every imported sentence actually matches this repository's no-fabrication rules line-by-line, rather than trusting the app repository's own self-description at face value (the same independent-review discipline this repository already applies everywhere else).
- Cross-repository content movement is new — this repository has no existing "import checklist" or tooling for pulling content from `afaqalhayatae-app`; the process itself needs to be defined, not just executed once.

**Required work**

1. Independently re-review the app repository's Maintenance content (all 5 services, both languages) against this repository's no-fabrication rules — do not take `SERVICE_COMPLETION_MATRIX.md`'s self-assessment as sufficient on its own.
2. Map each app-side field (`overview`, `commonProblems`, `scope`, `process`, `benefits`, `safety`, `faqs`, `seoTitle`, `metaDescription`, `keywords`) onto this repository's file structure (`CONTENT_EN.md`/`CONTENT_AR.md`, `FAQ.md`, `SEO_AI.md`), following the pattern already used for General Cleaning/Water Tank Cleaning.
3. Transcribe (not re-author) the content into each of the 5 services' knowledge-base files.
4. Update each service's `README.md` status banner citing `DECISION_LOG.md` #38 and this import, per the same pattern as `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`.
5. Record provenance clearly (source: `afaqalhayatae-app`, `src/data/SERVICE_DATABASE.json`, as of a stated commit/date) so a future reader knows this was imported, not independently authored here.

### Option B — Author new Maintenance content in the knowledge base

**Benefits**

- Content is authored directly in this repository, consistent with the intended "Knowledge First" architecture — no cross-repository dependency or provenance question.
- Full control over exact wording and structure from the start, without needing to reconcile an external source's format.

**Benefits and risks re-assessed given the new discovery below.**

**Risks**

- **Now the clearly weaker option**, given that Option A's source content already exists, is real, bilingual, and appears compliant — re-authoring from scratch duplicates work that has already been done once, with no evident quality problem in the existing version to justify redoing it.
- Real risk of producing content that diverges from what the application repository already renders live-ish (uncommitted but present) — creating a *new* two-repository inconsistency rather than resolving the existing one.
- Slower — full drafting, review, and approval cycle per service, five times over, versus transcription and verification.

**Required work**

1. Draft `CONTENT_EN.md`/`CONTENT_AR.md`, `FAQ.md`, `SEO_AI.md` for each of the 5 services from general operational/industry knowledge, following the same boundary as `DECISION_LOG.md` #38 and `MAINTENANCE_CONTENT_PHASE_PLAN.md` §2.
2. Independent review pass per service.
3. Owner sign-off per service.
4. Status sync per service.

### Option C — Hybrid approach

**Benefits**

- Uses Option A's existing content as the base (avoiding redundant authoring) while allowing this repository's own review/editing pass to adjust structure, tone, or emphasis where the app repository's version doesn't fully match this repository's conventions.
- Lets the independent-review step (required under Option A anyway) double as a light editorial pass rather than a separate later step.

**Risks**

- Blurs provenance if not carefully recorded — a reader needs to know which parts are transcribed verbatim and which were edited, or the "no invented facts" audit trail becomes harder to verify later.
- Marginal added effort over Option A for a benefit (editorial polish) that may not be necessary, since the spot-checked content already reads as professional and rule-compliant.

**Required work**

Same as Option A steps 1–5, plus an explicit editorial-adjustment pass with each change logged (what changed and why) so the transcription-vs-edit distinction stays auditable.

---

## Summary Comparison

| | Speed | Provenance clarity | Risk of new inconsistency | Owner effort |
|---|---|---|---|---|
| **A — Import** | Fastest | High, if provenance is recorded per §"Required work" | Low — content already exists and appears compliant | Low |
| **B — Author fresh** | Slowest | High (single-repository origin) | Moderate — risk of diverging from what's already live-ish in the app | Highest (5 full drafting/review cycles) |
| **C — Hybrid** | Moderate | Requires care to preserve | Low, same base as A | Moderate |

---

## Decision

**Not made by this report.** The Business Owner selects Option A, B, or C (or a variant). No content is written, no service file is modified, and no website file in either repository is touched until that selection is recorded.

---

## What This Document Does Not Do

- Does not write any Maintenance service content.
- Does not modify any file in `04_SERVICE_KNOWLEDGE/`.
- Does not modify any file in this repository's website documentation or in `afaqalhayatae-app`.
- Does not commit or push anything in either repository.

---

## Related Documents

- `00_GOVERNANCE/MAINTENANCE_CONTENT_PHASE_PLAN.md` — the open sourcing question this report informs
- `00_GOVERNANCE/HOMEPAGE_CONTENT_DECISION_APPLIED.md`
- `00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`
- `00_GOVERNANCE/DECISION_LOG.md` #38
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `afaqalhayatae-app/docs/SERVICE_COMPLETION_MATRIX.md`, `src/data/SERVICE_DATABASE.json` — external repository, read-only reference
