# Service Knowledge Source of Truth Decision Report

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — decision options only; no option is selected by this report
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning/recommendation only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Scope:** Read-only governance decision report. No service file, website file, or application code was modified. Nothing was staged or committed.

## Purpose

Resolve — by presenting Owner-decidable options, not by an agent picking one — the service-documentation authority conflict identified in `00_GOVERNANCE/CONTENT_APPROVAL_RESOLUTION_REPORT.md` §1.2, before any website homepage or service-page content implementation proceeds. This report does not select a winning source. Per `00_GOVERNANCE/ENTERPRISE_PUBLICATION_GATE_MODEL.md` §15 ("an agent picking 'the more recent' or 'the more complete' source on its own authority" is forbidden), the choice below is reserved for the Business Owner.

---

## 1. Current Conflict

Two layers of documentation describe the same 27 services' readiness, and they disagree:

**Layer 1 — Catalog/decision layer** (`04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, dated 2026-07-31, and `00_GOVERNANCE/DECISION_LOG.md` decisions #37–#39): states 16 of 27 services are "✅ Approved... Owner-approved, general-operational-knowledge content published on the website," with the underlying approved content and evidence located in a separate application repository, `afaqalhayatae-app`, and its `docs/SERVICE_COMPLETION_MATRIX.md` / `docs/VISUAL_ASSET_MASTER_PLAN.md`.

**Layer 2 — Per-service package layer** (`04_SERVICE_KNOWLEDGE/<NN_SERVICE>/README.md`, `CONTENT_EN.md`, dated 2026-07-24 through 2026-07-29, i.e. before the Layer-1 decisions): every one of the 12 pre-existing service packages, including Pest Control, still self-reports "Draft," "Structurally Complete Draft — Owner and Technical Evidence Required," or "Review Required — Not Approved for Publication or Field Execution." None was updated after the 2026-07-31 approval decisions.

Compounding factors, confirmed during review:

- `afaqalhayatae-app` — the repository holding the actual approved content and the evidence the Layer-1 approval decisions cite — **does not exist anywhere in this filesystem**. This knowledge repository cannot independently inspect or re-verify what was approved there.
- 4 of the 16 Layer-1-approved services (Villa Cleaning, Office Cleaning, Post-Construction Cleaning, Carpet & Upholstery Cleaning) have **no `04_SERVICE_KNOWLEDGE/` folder at all** — a documentation-parity gap `DECISION_LOG.md` #38 itself already acknowledges as open and unresolved.
- `07_WEBSITE/IMPLEMENTATION/04_CONTENT_INTEGRATION_PLAN.md` §3 and `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` key their planned publishability logic to an older `SERVICE_CATALOG.md` status-column vocabulary (`Complete` / `Review-ready` / `Structurally complete draft` / `Blocked`) that the current catalog no longer uses, and both predate the 15 services added 2026-07-31.
- `07_WEBSITE/NAVIGATION_ARCHITECTURE.md` (2026-08-01) is already written consistently with Layer 1 (the current 16-approved/11-structural framing) — it is the one document that has kept pace, but it inherits the same unresolved authority question rather than answering it.
- `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md` and `BOOKING_SERVICE_CATALOG.md` (both 2026-07-29) explicitly defer to Layer 2 ("each service's own `README.md` Evidence Gate remains the governing status"), which itself is now out of step with Layer 1.

No fabrication was found on either side of this conflict (see `CONTENT_APPROVAL_RESOLUTION_REPORT.md` §3) — this is a **staleness and authority-precedence** problem, not a truthfulness problem.

---

## 2. Available Sources

| Source | What it claims | Last updated | Verifiable from this repository? |
|---|---|---|---|
| `SERVICE_CATALOG.md` | 16/27 approved and live; 11/27 structural-only | 2026-07-31 | Partially — the catalog entry itself is here, but its underlying evidence is not |
| `DECISION_LOG.md` #37–#39 | Records the Owner approval events behind the catalog's current status | 2026-07-31 | Yes — the decision text itself is here and is the authoritative record of what the Owner approved |
| `04_SERVICE_KNOWLEDGE/<NN_SERVICE>/README.md` + `CONTENT_EN.md` (per service) | 11 of 12 pre-existing packages: Draft/Not Approved. Pest Control: Review Draft/Review Required | 2026-07-24 to 2026-07-29 | Yes — fully present and inspectable, but not reflective of the 2026-07-31 decisions |
| `afaqalhayatae-app` (external, `docs/SERVICE_COMPLETION_MATRIX.md`, `docs/VISUAL_ASSET_MASTER_PLAN.md`) | The actual approved, live page content and its own completion tracking | Referenced 2026-07-31 | **No — not present in this workspace; cannot be inspected or re-verified from here** |
| `07_WEBSITE/NAVIGATION_ARCHITECTURE.md` | Consistent with `SERVICE_CATALOG.md`'s current 16/11 split | 2026-08-01 | Yes |
| `07_WEBSITE/IMPLEMENTATION/04_CONTENT_INTEGRATION_PLAN.md`, `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` | Adapter/keyword planning keyed to a superseded catalog schema and a 12-service list | 2026-07-27/28 | Yes, but stale relative to Layer 1 |
| `00_GOVERNANCE/CONTENT_APPROVAL_RESOLUTION_REPORT.md` | Prior read-only analysis of this same conflict | 2026-08-01 | Yes |

---

## 3. Risks of Each Option

### Option A — `DECISION_LOG.md` + `SERVICE_CATALOG.md` become the operational source of truth

**Impact:** Homepage and service-page implementation reads directly from the catalog's current status column and the decision log's approval events. The 16 approved services (§1.3 of the prior report) become buildable immediately; the 11 structural-only services stay excluded. This is the fastest path to implementation.

**Risks:**
- The evidentiary basis for "approved" sits in a repository (`afaqalhayatae-app`) this knowledge base cannot see. If that content has drifted, contains an error, or was never fully evidence-reviewed, this repository has no mechanism to detect it before it reaches the homepage.
- 4 of the 16 approved services have no per-service package here at all — implementing their homepage entries under Option A means the "single source of truth, write each fact once" principle (`PROJECT_MANIFEST.md`) is not actually satisfied for those 4; the fact lives only in the external repo.
- The 11 pre-existing per-service packages continue silently disagreeing with the catalog (self-reporting Draft while the catalog says Approved) unless separately corrected — a standing readability/trust risk for anyone who opens a service folder directly instead of the catalog.
- Any future agent or reviewer who checks a per-service `README.md`/`CONTENT_EN.md` first (as `CLAUDE.md`'s fact table directs for "per-service operational facts") will see a Draft status that contradicts what actually got implemented, and may either wrongly block further work or wrongly assume the Draft language is stale noise to ignore — both are governance failure modes.

**Required work:** None before implementation can start — this option accepts the catalog/decision-log pair as-is. Optionally (not required to adopt the option, but reduces the risks above): note in each per-service package that its status is superseded by a named decision, without rewriting the package.

### Option B — Individual service knowledge files remain the source of truth until updated

**Impact:** Nothing currently in `04_SERVICE_KNOWLEDGE/<NN_SERVICE>/` is treated as approved for homepage or service-page use until that specific package's own `README.md`/`CONTENT_EN.md` is rewritten to reflect Approved status. This is the most conservative option and matches the letter of `CLAUDE.md`'s existing fact-ownership table.

**Risks:**
- Directly contradicts `SERVICE_CATALOG.md` and `DECISION_LOG.md` #37–#39, which record that the Owner already approved this content and that it is already live on the production website. Treating it as unapproved here would mean this repository's governance state lags behind reality — the website would already be showing content this repository still calls "Draft."
- Blocks homepage implementation for all 16 services the Owner already approved, re-litigating a decision that was already made (`DECISION_LOG.md` #37/#38 are explicit, dated, Owner-approved entries) rather than executing it.
- Does not by itself fix the 4-services-with-no-folder gap — Option B has no path for content that was approved but was never authored into this repository's package structure in the first place.
- Slowest option, with no corresponding safety benefit if the underlying `afaqalhayatae-app` content was, in fact, properly evidence-reviewed at approval time.

**Required work:** Every one of the 11 pre-existing packages' `README.md` and `CONTENT_EN.md` (and `CONTENT_AR.md` where paired) would need a status rewrite to Approved, each citing the specific `DECISION_LOG.md` entry as evidence, before that service could be implemented under this option's own rule — i.e., Option B effectively converges on Option A's end state anyway, just gated behind a rewrite pass first.

### Option C — Create a synchronization/backfill phase before website content implementation

**Impact:** No homepage or service-page implementation begins until a scoped, time-bound backfill closes the specific gaps identified in §1: (a) update the 11 pre-existing per-service packages' status fields to cite their governing `DECISION_LOG.md` decision; (b) create the missing `04_SERVICE_KNOWLEDGE/` folders for the 4 approved Cleaning services with content sourced from `afaqalhayatae-app`, not re-authored; (c) refresh `04_CONTENT_INTEGRATION_PLAN.md` §3 and `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` against the current 27-service catalog schema; (d) establish some form of visibility into `afaqalhayatae-app` (link, mirror, or read access) so this repository's governance claims about "published" content are independently checkable, not taken on faith.

**Risks:**
- Slower than Option A — implementation waits on a backfill pass rather than starting immediately on the 16 already-approved services.
- Backfill work itself needs scoping and, per this repository's own rules, independent QA review before any status is marked Approved (`ENTERPRISE_PUBLICATION_GATE_MODEL.md` §10: "a layer cannot reach Approved without independent `AGT-QA` review; a producing role cannot self-approve").
- If `afaqalhayatae-app` access is not granted or not feasible, item (d) above cannot be completed, and the underlying "unverifiable external evidence" risk from Option A persists regardless — Option C reduces but does not eliminate that specific risk unless (d) is actually achievable.
- Requires Owner time/attention to scope and approve the backfill phase itself, which is additional overhead this option explicitly trades for lower long-term drift risk.

**Required work:** A scoped backfill plan (file list, sourcing rule — copy from `afaqalhayatae-app`, never re-author — and an `AGT-QA` review pass) covering items (a)–(d) above, Owner approval of that plan, then execution before homepage implementation begins.

---

## Summary Comparison

| | Speed to implementation | Governance consistency achieved | External-evidence risk | Owner overhead now |
|---|---|---|---|---|
| **A** | Fastest | Partial — catalog/log align, per-service packages still stale | Unaddressed | Lowest |
| **B** | Slowest (effectively blocks the 16 already-approved services) | Re-derives Option A's end state via rewrite, so ultimately similar | Unaddressed | Low, but re-opens an already-made decision |
| **C** | Slower than A, faster than a full re-litigation under B | Highest — closes the parity gap directly | Reduced, fully addressed only if `afaqalhayatae-app` visibility is granted | Highest (must scope/approve backfill) |

---

## Decision

**Not made by this report.** The Business Owner selects one of Options A, B, or C (or directs a variant). No option above is implemented, no service file is modified, no website file is modified, and no application code is written until that selection is recorded as a new `DECISION_LOG.md` entry.

---

## Related Documents

- `00_GOVERNANCE/DECISION_LOG.md` — decisions #37, #38, #39
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `00_GOVERNANCE/CONTENT_APPROVAL_RESOLUTION_REPORT.md`
- `00_GOVERNANCE/ENTERPRISE_PUBLICATION_GATE_MODEL.md`
- `07_WEBSITE/NAVIGATION_ARCHITECTURE.md`
- `07_WEBSITE/IMPLEMENTATION/04_CONTENT_INTEGRATION_PLAN.md`
- `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md`
