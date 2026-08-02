# Electrical Arabic SEO Decision Applied

## Document Information

- **Owner:** Business Owner
- **Version:** 1.0
- **Status:** Decision recorded — governance/documentation only; no content migrated, no file in `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/` modified
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, governance recording only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Source:** `00_GOVERNANCE/ELECTRICAL_CONTENT_SYNC_EXECUTION_PLAN.md` §4 (asymmetry flagged, not resolved) and this Owner instruction resolving it
- **Scope:** Governance decision record only. No service file, `README.md`, or website file was modified. Nothing staged, committed, or pushed.

## Note on the Exact Keyword Text

The source record (`afaqalhayatae-app/src/data/SERVICE_DATABASE.json`, `electrical-maintenance.keywords.ar`) contains this keyword as **"إصلاح لوحة توزيع"** (without the definite article). The Owner's instruction names it **"إصلاح لوحة التوزيع"** (with the definite article "ال"). These refer to the same keyword — a minor definite-article variation, not two different terms — and this decision applies to that one Arabic keyword as it exists in the source record, regardless of which exact form is referenced. No content file exists yet to check this against, since Electrical Maintenance is still unmigrated (`ELECTRICAL_CONTENT_SOURCE_REVIEW_PLAN.md` §1).

---

## 1. Decision Applied

- **Arabic keyword removed from future migration:** "إصلاح لوحة توزيع" / "إصلاح لوحة التوزيع" will **not** be included when the Electrical Maintenance SEO fields are migrated.
- **English and Arabic SEO scope now aligned:** combined with the prior removal of "Distribution Panel Repair" (English) per `00_GOVERNANCE/ELECTRICAL_SEO_DECISION_APPLIED.md`, both language versions of the future keyword list now exclude the same unsupported repair claim. The asymmetry flagged in `ELECTRICAL_CONTENT_SYNC_EXECUTION_PLAN.md` §4 is resolved — neither language will carry a panel-repair keyword the approved scope does not support.

**Resulting future keyword lists (both now 4 of the original 5, aligned):**
- **English:** Electrical Maintenance UAE; Electrician Dubai; Electrical Repair; Home Electrical Service.
- **Arabic:** صيانة كهربائية الإمارات؛ كهربائي دبي؛ إصلاح كهرباء؛ كهرباء منزلية.

---

## 2. Reason

Prevents an unsupported expansion from inspection into a repair claim. The approved scope (per `afaqalhayatae-app`'s `electrical-maintenance` record, Scope — Included) supports only "Distribution-panel and breaker **inspection**" — not repair — and Scope — Excluded separately disclaims "any work beyond what can be safely assessed without specialized regulatory sign-off," a category panel-level repair plausibly falls into. The Arabic keyword carried the identical claim the English keyword did; removing only one language would have left the same unsupported claim live in the other, contrary to `PROJECT_MANIFEST.md`'s bilingual-equality principle (facts must not diverge between languages).

---

## 3. Validation

- **No content files modified:** `CONTENT_EN.md`, `CONTENT_AR.md`, and `FAQ.md` in `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/` remain exactly as they were — unmigrated, empty content-gate templates.
- **No SEO file modified yet:** `SEO_AI.md` is unchanged — still the empty template; there is no keyword list in this repository yet to edit. This decision is recorded as a constraint on the future migration, the same treatment already applied to the English keyword removal.
- **No publication status changed:** `README.md` and this package's publication approval status are unchanged.

---

## 4. Next Step

Proceed with the **Electrical Maintenance content migration** per `00_GOVERNANCE/ELECTRICAL_CONTENT_SYNC_EXECUTION_PLAN.md`, which will apply both keyword exclusions (English "Distribution Panel Repair" and Arabic "إصلاح لوحة توزيع"/"إصلاح لوحة التوزيع") in its SEO field mapping when execution is separately authorized.

---

## What This Document Does Not Do

- Does not migrate any content into `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/`.
- Does not modify `README.md` or any publication status.
- Does not modify any website file in either repository.
- Does not stage, commit, or push anything.

---

## Related Documents

- `00_GOVERNANCE/ELECTRICAL_CONTENT_SOURCE_REVIEW_PLAN.md`
- `00_GOVERNANCE/ELECTRICAL_SEO_DECISION_APPLIED.md` — the English-side counterpart to this decision
- `00_GOVERNANCE/ELECTRICAL_CONTENT_SYNC_EXECUTION_PLAN.md` — where this decision resolves the §4 asymmetry
- `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/`
