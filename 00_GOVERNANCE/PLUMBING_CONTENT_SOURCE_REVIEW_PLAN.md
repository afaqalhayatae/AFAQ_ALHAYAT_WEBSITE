# Plumbing Content Source Review Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning and source verification only; no migration performed
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Purpose:** Extend the AC Maintenance pilot process (`AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`, `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md`) to Plumbing — source verification only, no content migrated.
- **Scope:** Planning and review only. No service file, website file, or `README.md` status was modified. Nothing staged or committed.

## Target Identification

- **Service:** Plumbing (`SVC-PLUMBING`)
- **Knowledge-base folder:** `04_SERVICE_KNOWLEDGE/06_PLUMBING/`
- **Application-repository slug:** `plumbing` (`src/data/SERVICE_DATABASE.json`)

---

## 1. Source Availability

- **Does Plumbing content exist?** Yes — a complete record exists in `afaqalhayatae-app/src/data/SERVICE_DATABASE.json`, confirmed by direct read this session.
- **Is it bilingual?** Yes — every content field has both `en` and `ar` values.
- **Is it complete?** Yes, by the same measure applied to AC Maintenance: `status.packageStatus` reads "Complete — content, SEO, and image all approved," and every content field used for AC Maintenance is present here too.
- **Which fields exist?** `name`, `status`, `content.{en,ar}.{heroTagline, overview, commonProblems[], scope.{included[],excluded[]}, process[], benefits[], safety[]}`, `faqs[]` (4 pairs), `images`, `cardImage`, `seoTitle`, `metaDescription`, `keywords`, `sourceDocs`.
- **Same provenance discrepancy as AC Maintenance:** `sourceDocs` claims `["06_PLUMBING/CONTENT_EN.md", "06_PLUMBING/README.md"]` as origin — those files, in this repository, are confirmed-empty templates (see §4). Not relied upon here, consistent with the same finding already recorded for AC Maintenance.

---

## 2. Content Mapping

| Field | Available? | Notes |
|---|---|---|
| Overview | ✅ | "Our plumbing service covers everyday repairs and maintenance for the pipes, fittings, and fixtures found in UAE homes and businesses..." |
| Common problems | ✅ | 6 items (leaking taps, low pressure, running toilets, slow drains, visible pipe leaks, water heater connection issues) |
| Scope — Included | ✅ | 6 items (tap/mixer/fixture leak repair, pipe joint/fitting inspection and repair, cistern repair, water heater connection checks, drain/trap inspection, general fault diagnosis) |
| Scope — Excluded | ✅ | 4 items (major re-piping/full bathroom re-plumbing, main water-line/municipal connection work, manufacturer warranty claims, structural access work) |
| Process | ✅ | 6 steps, same shape as AC Maintenance's (consultation → inspection → diagnosis → agreed work → test → summary) |
| Benefits | ✅ | 5 items, non-numeric, hedged language throughout |
| Safety notes | ✅ | 3 items (water isolation before repair, checking for related issues like water damage, flagging out-of-scope issues) |
| FAQ | ✅ | 4 pairs — response/same-day, warranty, low-pressure cause, cost |
| SEO title | ✅ | Bilingual, present |
| Meta description | ✅ | Bilingual, present |
| Keywords | ✅ | 5 EN / 5 AR |
| **CTA availability** | ❌ **Same gap as AC Maintenance** | No per-service CTA field exists in the source record. The already-established resolution (Owner-approved generic "Book Appointment"/"احجز موعد" pattern) applies identically here, pending the same explicit per-service confirmation. |

---

## 3. Claim Safety

| Category | Finding |
|---|---|
| **Price claims** | None found. The cost FAQ ("How much does a plumbing visit cost?") is hedged: "Pricing depends on the fault and the work required. This is subject to company policy — please contact us directly for an accurate quote." No figure stated. |
| **Warranty claims** | None found. The warranty FAQ uses the same standardized hedge as AC Maintenance: "Warranty terms are subject to company policy — please confirm directly with our team before the visit." Scope — Excluded also explicitly disclaims "Manufacturer warranty claims on fixtures or appliances." |
| **Certification claims** | None found. Safety notes describe general professional practice (isolating water supply, flagging out-of-scope issues) without asserting a license or certification. |
| **Response-time claims** | **One item flagged for attention, not a violation.** FAQ #1 asks "Can you fix a leak the same day I contact you?" — this is the first response-time-adjacent question seen in this pilot process (AC Maintenance had no equivalent). The answer is correctly hedged: "Availability depends on scheduling at the time you contact us. Please reach out via WhatsApp or phone and we'll confirm the earliest available appointment." No same-day, fixed-hour, or emergency commitment is made — it defers to real-time scheduling. Assessed as safe on inspection, but flagged explicitly since it is the closest any content in this pilot has come to a response-time topic. |
| **Emergency claims** | None found beyond the item above; no "24/7," "emergency," or "urgent" service claim appears anywhere in the record. |

**Additional check specific to this service (learned from the AC Maintenance review):** the AC Maintenance pilot found one keyword ("AC Repair UAE") in tension with its own excluded scope. The same check was run here: Plumbing's keyword "Pipe Repair UAE" was checked against Scope — Excluded's "Major re-piping or full bathroom re-plumbing projects." **No tension found** — Scope — Included explicitly names "Pipe joint and fitting inspection and repair" as in-scope, so "pipe repair" as a keyword is consistent with what's actually included, unlike the AC Maintenance case where "repair" wasn't a scoped-in activity. Similarly, Process step 4 ("Agreed repair or maintenance work carried out" / "تنفيذ أعمال الإصلاح أو الصيانة المتفق عليها") uses "repair" deliberately and consistently with the included scope — this does **not** carry the same ambiguity flagged and refined for AC Maintenance, because repair work is a core included activity for Plumbing, not an excluded one.

---

## 4. Compare: Source Content vs. Current Knowledge-Base Files

| | Source (`afaqalhayatae-app`) | Current knowledge base (`06_PLUMBING/`) |
|---|---|---|
| `CONTENT_EN.md` equivalent | Real overview, common problems, scope, process, benefits, safety (English) | Empty content-gate template — "Content Gate," "Content Pending Approval" checklist, no actual description (confirmed by fresh read this session) |
| `CONTENT_AR.md` equivalent | Real Arabic equivalents of all the above | Empty content-gate template, Arabic (same structure, same emptiness) |
| `FAQ.md` | 4 real, answered Q&A pairs | "Draft — Answers Pending Owner Approval," an unanswered 10-item "Approved Question Backlog," no real answers |
| `SEO_AI.md` | Real SEO title, meta description, 5+5 keywords | "Draft — Not Approved for Publication or Live AI Answers," generic Safe Intent Framework only, no actual SEO fields |
| `README.md` | `packageStatus: Complete — content, SEO, and image all approved` | "Structurally Complete Draft — Owner and Licensed-Trade Evidence Required" (unchanged, not touched by this review) |

**Conclusion:** the gap is identical in shape to what was found and resolved for AC Maintenance — real, complete, bilingual, claim-safe content exists only in the application repository; the knowledge-base files remain unpopulated templates.

---

## 5. Recommendation

**Sync ready**, with one already-precedented decision to confirm before execution:

- The CTA gap (§2) is the same gap already resolved for AC Maintenance — reusing the same Owner-approved "Book Appointment"/"احجز موعد" pattern is the expected resolution, pending the Owner's explicit per-service confirmation (the same procedural step already followed for AC Maintenance, not a new open question).
- The response-time-adjacent FAQ (§3) is assessed as safe as written and does not block sync, but is surfaced for Owner awareness since it is a new pattern not seen in the AC Maintenance pilot.
- No missing source content, no unresolved claim-safety violation, and no scope/keyword tension were found — Plumbing's source record is at least as clean as AC Maintenance's was going into its own pilot.

This plan does not itself migrate any content — a `PLUMBING_SYNC_EXECUTION_PLAN.md` (mirroring `AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`'s exact-field-mapping format) would be the next step, upon Owner authorization.

---

## What This Document Does Not Do

- Does not migrate, copy, or write any content into `04_SERVICE_KNOWLEDGE/06_PLUMBING/`.
- Does not modify `README.md` or any publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md` — process template this review follows
- `00_GOVERNANCE/AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md` — comparison basis for the "repair wording" check in §3
- `00_GOVERNANCE/MAINTENANCE_CONTENT_SYNC_PLAN.md`
- `00_GOVERNANCE/MAINTENANCE_CONTENT_SOURCE_DECISION.md`
- `04_SERVICE_KNOWLEDGE/06_PLUMBING/`
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` — external repository, read-only reference
