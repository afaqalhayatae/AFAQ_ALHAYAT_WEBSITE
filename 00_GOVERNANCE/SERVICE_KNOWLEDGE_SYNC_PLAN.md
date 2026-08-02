# Service Knowledge Sync Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only; no service file has been modified by this document
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Authorizing decision:** Owner approval of Option C, `00_GOVERNANCE/SERVICE_SOURCE_OF_TRUTH_DECISION_REPORT.md`
- **Scope:** Planning document only. No service file, website file, or application code is modified by this document. Nothing is staged or committed.

## Purpose

Define the exact, bounded scope of the synchronization/backfill phase before it is executed: which services, which files, which fields change, which fields stay untouched, what could go wrong, and how the result will be checked. Execution does not begin until this plan itself is reviewed.

---

## 1. Approved Services List to Sync

Per the Owner's scope instruction, only services with a confirmed approval in **both** `SERVICE_CATALOG.md` and `DECISION_LOG.md` are in scope, and only where an existing `04_SERVICE_KNOWLEDGE/` package already exists to update.

| # | Service | Governing decision | In scope? |
|---|---|---|---|
| 1 | Pest Control (`SVC-PEST-CONTROL`) | `DECISION_LOG.md` #37 | **Yes** |
| 2 | AC Maintenance (`SVC-AC-MAINTENANCE`) | `DECISION_LOG.md` #38 | **Yes** |
| 3 | General Cleaning (`SVC-GENERAL-CLEANING`) | #38 | **Yes** |
| 4 | Deep Cleaning (`SVC-DEEP-CLEANING`) | #38 | **Yes** |
| 5 | Water Tank Cleaning (`SVC-WATER-TANK-CLEANING`) | #38 | **Yes** |
| 6 | Plumbing (`SVC-PLUMBING`) | #38 | **Yes** |
| 7 | Electrical Maintenance (`SVC-ELECTRICAL-MAINTENANCE`) | #38 | **Yes** |
| 8 | Painting (`SVC-PAINTING`) | #38 | **Yes** |
| 9 | Handyman Services (`SVC-HANDYMAN`) | #38 | **Yes** (card-image exclusion is a separate, unrelated gate — not a content-status gate) |
| 10 | Drain Unblocking (`SVC-DRAIN-UNBLOCKING`) | #38 | **Yes** |
| 11 | Waterproofing (`SVC-WATERPROOFING`) | #38 | **Yes** (card-image exclusion, same note as Handyman) |
| 12 | Water Leak Detection (`SVC-WATER-LEAK-DETECTION`) | #38 | **Yes** |

**Explicitly excluded from this sync, though approved in `SERVICE_CATALOG.md`:**

- Villa Cleaning, Office Cleaning, Post-Construction Cleaning, Carpet & Upholstery Cleaning (`SVC-VILLA-CLEANING` etc.) — approved per #38, but **no `04_SERVICE_KNOWLEDGE/` folder exists** for any of them. There is nothing to sync — creating a new folder would mean authoring new content, which risks violating "do not invent missing service information" since the only evidence of their approved content sits in `afaqalhayatae-app`, a repository this workspace cannot read. This requires a separate Owner decision (content-import method), not a status-field sync.

**Excluded per the Owner's explicit instruction (not approved):**

- All 11 structural-only Expansion services (CCTV Installation, Smart Home Installation, Swimming Pool Maintenance, Kitchen Installation, Interior Decoration, Interlock Installation, Lighting Maintenance, Wood Alternative Installation, Wallpaper Installation, Thermal Insulation, Rooftop Space Utilization) — no `04_SERVICE_KNOWLEDGE/` folder exists for these either, and they are not approved, so no action of any kind applies to them.

---

## 2. Files Affected

Each of the 12 in-scope services has the same package shape, with one structural exception (Pest Control — see note below). For the 11 services other than Pest Control:

| File | Current status line (representative example, AC Maintenance) | In sync scope? | Rationale |
|---|---|---|---|
| `README.md` | "Structurally Complete Draft — Owner and Technical Evidence Required" | **Yes** | Top-level package status must reflect the approval that already occurred |
| `CONTENT_EN.md` | "Draft — Not Approved for Publication" | **Yes** | Directly the content type decision #38 approved (overview, scope, process, benefits, FAQ) |
| `CONTENT_AR.md` | (no separate status line found; paired with `CONTENT_EN.md`) | **Yes** | Bilingual parity requires the Arabic pairing to move with the English file, per `ENTERPRISE_PUBLICATION_GATE_MODEL.md` §13 |
| `FAQ.md` | "Draft — Answers Pending Owner Approval" | **Yes** | FAQ is explicitly named in decision #38's approved content list |
| `SEO_AI.md` | "Draft — Not Approved for Publication or Live AI Answers" | **Partially** — only the "Not Approved for Publication" (page SEO fields: title, meta description, keywords) half changes. The "...or Live AI Answers" half is a separate gate owned by `09_AI_KNOWLEDGE/ANSWER_POLICY.md`, not touched by decision #38, and must remain |
| `CHANGELOG.md` | (append-only) | **Yes** | One new entry per service recording exactly what changed and citing the governing decision — this is the audit trail (Objective 5) |
| `BUSINESS.md` | "Review Required — Unsupported claims must not be published" | **No** | Contains certification, response-time, and municipality-compliance claims (confirmed by direct inspection of `01_PEST_CONTROL/BUSINESS.md`) — none of these categories were approved by decision #37/#38 |
| `OPERATIONS.md` | "Draft — Not Approved for Field Execution" | **No** | Field-execution SOP; decision #38 approved customer-facing content, not operational authorization |
| `SAFETY.md` | "Draft — Competent Safety Review Required" | **No** | Requires a competent (licensed/professional) safety review, a distinct gate from the customer-facing "safety" content topic decision #38 covers |
| `CUSTOMER_GUIDE.md` | "Draft — Not for Publication" | **No** | Not named in decision #38's approved content list |
| `TRAINING.md` | "Draft — Training Not Authorized" | **No** | Internal training authorization, unrelated to public content approval |
| `MEDIA.md` | "Draft Asset Brief" | **No** | Image/asset approval follows its own separate trail (`IMAGE_SEO_LIBRARY.md`, `DECISION_LOG.md` image-specific entries) — not a general-content decision |
| `SOURCE_DRAFT.md` (where present) | Historical/reference | **No** | Preserved historical source per `SERVICE_CATALOG.md`'s draft package policy — never edited |

**Pest Control note (structural exception):** Pest Control's approval (`DECISION_LOG.md` #37) names a specific set of files — `02_SEO_DATA.md`, `06_PAGE_CONTENT.md`, `04_FAQ.md` — which are the newer numbered files already present in `01_PEST_CONTROL/` (created 2026-07-29, currently still self-marked "Draft" in their own "Document Information" headers). This is **not the same file set** as the legacy `CONTENT_EN.md`, `FAQ.md`, `SEO_AI.md` trio that the other 11 services use. Both sets currently exist side by side in `01_PEST_CONTROL/`. This sync must therefore:
- Update the status fields of the **numbered set** (`01_SERVICE_PROFILE.md` through `06_PAGE_CONTENT.md`) — these are what decision #37 actually names.
- Explicitly flag, rather than silently resolve, whether the **legacy set** (`CONTENT_EN.md`, `FAQ.md`, `SEO_AI.md`, `CONTENT_AR.md`, `FAQ_AR.md`) is (a) also covered by the same approval since it is the same underlying facts restated, (b) superseded and should carry a "superseded by" pointer instead of its own status change, or (c) a genuine duplication needing separate reconciliation. **This is listed as an open question in §4, not decided here.**

---

## 3. Fields Requiring Updates

For each in-scope file (README.md, CONTENT_EN.md, CONTENT_AR.md, FAQ.md, and the SEO-fields portion of SEO_AI.md — plus Pest Control's numbered-file equivalents):

1. **Status line/banner** — replace "Draft — Not Approved for Publication" (or the service-specific equivalent wording) with an approval statement that:
   - States the content is approved as general operational content.
   - Cites the specific governing decision by number (`DECISION_LOG.md` #37 for Pest Control, #38 for the other 11).
   - Explicitly re-states, in the same line or an adjacent one, that price, discount, warranty, guarantee, license, certification, and exact response-time claims remain excluded and unapproved — this is the language decision #38 itself uses, carried forward rather than dropped.
2. **`README.md` "Evidence Gate" section** — reworded, not deleted, to distinguish "general content: approved" from "specific claim categories (certification, municipality-compliance, product approval, child/pet-safety assurance, fast-response, warranty): still gated." The gate itself must survive the sync intact in substance.
3. **`CHANGELOG.md`** — one new entry appended (never inserted mid-history or backdated) per service, in the same format as existing entries, recording: date of sync, files touched, the governing decision cited, and an explicit statement that no new fact was introduced and no gated claim category was closed.
4. **Body content** — unchanged. No sentence is added, removed, or reworded inside the substantive content of `CONTENT_EN.md`/`CONTENT_AR.md`/`FAQ.md` beyond the status banner itself. Objective 4 ("do not invent missing service information") means this sync is a metadata/status correction, not a content rewrite.

---

## 4. Fields Still Requiring Owner Input (Explicitly Out of Scope)

- Any certification, license, or municipality-compliance claim, in any file, for any of the 12 services.
- Any warranty, guarantee, or "100%"-style assurance claim.
- Any specific response-time or emergency-commitment claim.
- Any price, discount, or package claim.
- `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `TRAINING.md`, `MEDIA.md`, `CUSTOMER_GUIDE.md` for all 12 services — remain Draft, untouched by this sync.
- The Pest Control legacy-vs-numbered file duplication (§2 note) — requires an Owner or follow-up governance decision on which file set is canonical going forward, before or alongside execution.
- Villa Cleaning, Office Cleaning, Post-Construction Cleaning, Carpet & Upholstery Cleaning — approved, but no in-repo package exists; needs an Owner decision on how their content is sourced into this repository (copy from `afaqalhayatae-app`, author fresh under the same #38-style rule, or leave as an acknowledged parity gap).
- Whether/how `afaqalhayatae-app` becomes visible to this repository, so future syncs do not rely on taking `DECISION_LOG.md`'s description of external, unseen content on faith.

---

## 5. Risks

- **Scope creep into gated claims:** the biggest risk is a status-line edit that reads as blanket approval, inadvertently implying certification/warranty/safety-competent sign-off that was never granted. Mitigated by writing an explicit carve-out sentence into every changed status line (§3.1), not just changing the headline word.
- **Pest Control dual-file inconsistency:** updating the numbered set but not the legacy set (or vice versa) leaves two documents in the same folder making different claims about the same service — the exact kind of internal conflict this whole workstream exists to remove. Must be resolved as a named decision before or during execution, not left ambiguous.
- **Bilingual drift:** updating `CONTENT_EN.md`'s status without updating `CONTENT_AR.md` in the same pass would itself recreate an EN/AR parity gap. Both must change together, same wording intent, appropriately translated.
- **SEO_AI.md partial-gate confusion:** because only half of this file's current gate (publication) lifts while the other half (live AI answers) stays closed, an imprecise edit could accidentally lift both. Requires care to keep the two gates visibly distinct in the file itself.
- **Changelog entries misread as new claims:** a changelog entry that summarizes "what's now approved" too loosely could itself become a place where an unapproved claim gets restated as if settled. Entries should cite the decision, not re-describe the service.
- **False sense of external verification:** this sync updates *this repository's* metadata to match what `DECISION_LOG.md` says was approved elsewhere — it does not and cannot verify that the actual live content in `afaqalhayatae-app` still matches those approved facts today. The sync closes the internal documentation-parity gap; it does not close the external-evidence gap flagged in the prior two reports.
- **Version-field drift:** several files carry a `Version` number at the bottom (e.g., `README.md` "Version 1.0"); inconsistent bumping across 12 services would create a new, smaller parity problem. A single fixed version-increment convention should be agreed before execution.

---

## 6. Validation Checklist (to run after execution, before any commit)

- [ ] Every status-line change cites the correct decision number (#37 for Pest Control, #38 for the other 11) — no generic "Approved" with no citation.
- [ ] Every status-line change retains an explicit, un-softened carve-out for price/warranty/license/certification/response-time claims.
- [ ] `README.md` "Evidence Gate" sections still exist in substance in all 12 files — none deleted, only reworded to reflect the split.
- [ ] `CONTENT_EN.md` and `CONTENT_AR.md` changed together per service, expressing the same fact in both languages, per `PROJECT_MANIFEST.md`'s bilingual-equality principle.
- [ ] `SEO_AI.md` shows the publication gate lifted but the live-AI-answer gate still closed, per `09_AI_KNOWLEDGE/ANSWER_POLICY.md`.
- [ ] No edit touches `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `TRAINING.md`, `MEDIA.md`, `CUSTOMER_GUIDE.md`, or `SOURCE_DRAFT.md` in any of the 12 services.
- [ ] No edit touches Villa Cleaning, Office Cleaning, Post-Construction Cleaning, Carpet & Upholstery Cleaning, or any of the 11 structural-only Expansion services.
- [ ] `CHANGELOG.md` in each of the 12 services has exactly one new, appended entry; no existing entry is rewritten, reordered, or removed.
- [ ] Pest Control's legacy-vs-numbered file duplication is either resolved by a named decision before execution, or explicitly logged as a still-open item in both files' changelog entries — not silently left inconsistent.
- [ ] Body/substantive content (beyond the status banner) is byte-for-byte unchanged in `CONTENT_EN.md`, `CONTENT_AR.md`, and `FAQ.md` for all 12 services.
- [ ] A version-number increment convention is applied consistently across all 12 packages.
- [ ] Independent review (`AGT-QA` per `ENTERPRISE_PUBLICATION_GATE_MODEL.md` §10 — "a producing role cannot self-approve") completes before any file reaches a committed state.
- [ ] A full `git diff` of every touched file is reviewed line-by-line before staging, confirming only the fields listed in §3 changed.

---

## What This Plan Does Not Do

- Does not modify any service file, website file, or application code.
- Does not create the missing `04_SERVICE_KNOWLEDGE/` folders for the 4 new Cleaning services.
- Does not touch any of the 11 non-approved structural-only Expansion services.
- Does not resolve the Pest Control legacy-vs-numbered file question — surfaces it for a decision.
- Does not stage or commit anything.

---

## Related Documents

- `00_GOVERNANCE/SERVICE_SOURCE_OF_TRUTH_DECISION_REPORT.md` — the Owner decision authorizing this plan (Option C)
- `00_GOVERNANCE/CONTENT_APPROVAL_RESOLUTION_REPORT.md`
- `00_GOVERNANCE/DECISION_LOG.md` — decisions #37, #38
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `00_GOVERNANCE/ENTERPRISE_PUBLICATION_GATE_MODEL.md`
- `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`
