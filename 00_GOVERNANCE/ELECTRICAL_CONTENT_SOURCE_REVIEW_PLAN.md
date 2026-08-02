# Electrical Maintenance Content Source Review Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning and source verification only; no content migrated
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Purpose:** Start the Electrical Maintenance content governance cycle, following the same process already proven on AC Maintenance and Plumbing (`AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`/`_CONTENT_REVIEW_REPORT.md`, `PLUMBING_CONTENT_SOURCE_REVIEW_PLAN.md`/`_SYNC_EXECUTION_PLAN.md`/`_CONTENT_REVIEW_REPORT.md`) — source verification only, no content migrated.
- **Scope:** Planning and review only. No service file, `README.md`, or website file was modified. Nothing staged or committed.

## Target Identification

- **Service:** Electrical Maintenance (`SVC-ELECTRICAL-MAINTENANCE`)
- **Knowledge-base folder:** `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/`
- **Application-repository slug:** `electrical-maintenance` (`src/data/SERVICE_DATABASE.json`)

---

## 1. Source Availability

- **Does Electrical Maintenance content exist?** Yes — a complete record exists in `afaqalhayatae-app/src/data/SERVICE_DATABASE.json`, confirmed by direct read this session.
- **Is it bilingual?** Yes — every content field has both `en` and `ar` values.
- **Is it complete by the same measure as the two prior pilots?** Yes — `status.packageStatus` reads "Complete — content, SEO, and image all approved," cross-referenced against `docs/SERVICE_COMPLETION_MATRIX.md` §1 (Maintenance table, Electrical Maintenance row — marked `COMPLETE`).
- **Same provenance discrepancy as AC Maintenance and Plumbing:** `sourceDocs` claims `["07_ELECTRICAL_MAINTENANCE/CONTENT_EN.md", "07_ELECTRICAL_MAINTENANCE/README.md"]` as origin — those files, confirmed by fresh read this session, remain empty content-gate templates in this repository. Not relied upon; the true source is the JSON record itself.

---

## 2. Content Completeness

Every field used successfully in the two prior pilots is present here too, in both languages: `heroTagline`, `overview`, `commonProblems[]` (6), `scope.included[]` (6) / `excluded[]` (4), `process[]` (6 steps), `benefits[]` (5), `safety[]` (3), `faqs[]` (4 pairs), `seoTitle`, `metaDescription`, `keywords[]` (5 EN / 5 AR). No field is missing relative to the established pattern.

---

## 3. Fields Available

| Field | Available? | Notes |
|---|---|---|
| Overview | ✅ | "Our electrical maintenance service addresses everyday household and commercial electrical faults — from faulty switches and sockets to lighting and distribution-panel issues..." |
| Common Problems | ✅ | 6 items (sockets/switches not working, flickering lights, repeatedly tripping breaker, buzzing sounds, partial power loss, old/damaged wiring visible) |
| Scope — Included | ✅ | 6 items (switch/socket inspection and repair, lighting fixture troubleshooting/repair, distribution-panel/breaker **inspection**, fault-finding for partial power loss, replacement of damaged fittings, general electrical safety inspection) |
| Scope — Excluded | ✅ | 4 items (full rewiring/new circuit installation, utility-provider meter/main-supply work, manufacturer warranty claims, any work beyond what can be safely assessed **without specialized regulatory sign-off**) |
| Process | ✅ | 6 steps, same shape as the two prior pilots |
| Benefits | ✅ | 5 items, non-numeric, hedged language |
| Safety notes | ✅ | 3 items — notably includes an explicit deferral: "any fault... requiring specialized regulatory sign-off is flagged to the customer rather than attempted" |
| FAQ | ✅ | 4 pairs — breaker-tripping cause, warranty, DIY-safety-advice, cost |
| SEO | ✅ | Title, meta description, keywords, bilingual |
| **CTA availability** | ❌ **Same gap as the two prior pilots** | No per-service CTA field in the source record. The established resolution (Owner-approved "Book Appointment"/"احجز موعد" pattern) applies identically, pending the same per-service confirmation already given directly for Plumbing. |

---

## 4. Claim Safety Review

| Category | Finding |
|---|---|
| **Price claims** | None. Cost FAQ hedged: "Pricing depends on the fault and the work required. This is subject to company policy — please contact us directly for an accurate quote." |
| **Warranty claims** | None. Warranty FAQ uses the same standardized hedge as the two prior pilots. Scope — Excluded independently disclaims "manufacturer warranty claims on appliances." |
| **Certification claims** | None. Safety notes describe general professional practice, not a credentialed authority. |
| **Licenses** | **Specifically checked, given this is electrical work — a category where a license claim would be an obvious temptation.** None found. No "licensed electrician," "certified," or regulatory-authority claim appears anywhere in overview, scope, process, benefits, safety, or FAQ. The content is notably self-aware on this point: Scope — Excluded and the safety notes both explicitly draw a line at "specialized regulatory sign-off" and defer rather than imply the company holds that authority — a stronger, more explicit safety boundary than either AC Maintenance or Plumbing's excluded-scope wording. |
| **Response-time promises** | None. Unlike Plumbing, this FAQ batch contains no "same day" or urgency-adjacent question at all — a simpler claim-safety profile in this respect. |
| **Emergency claims** | None. No "24/7," "urgent," or "emergency service" claim anywhere in the record. |

**One additional FAQ worth noting (not a violation):** "Should I try to fix an electrical fault myself?" — answer: "Electrical work carries real safety risk. We recommend having a technician inspect and handle any electrical fault rather than attempting a repair yourself." This is a genuine safety-awareness answer, consistent with the safety notes, and introduces no claim of its own.

---

## 5. Scope vs. Keywords Check

Keywords: Electrical Maintenance UAE, Electrician Dubai, Electrical Repair, Distribution Panel Repair, Home Electrical Service (English); five Arabic equivalents.

- **"Electrical Repair"** — checked against Scope — Included, which explicitly includes "Switch and socket inspection and **repair**," "Lighting fixture troubleshooting and **repair**," and "Replacement of damaged fittings and accessories." **Compatible** — general repair language is supported for these included items, the same conclusion reached for Plumbing.
- **"Electrician Dubai"** — a generic occupational search term, not a specific capability claim; treated as safe by the same reasoning already applied to "Plumber Dubai" for the Plumbing pilot.
- **"Distribution Panel Repair" — flagged, not cleared.** Scope — Included lists only "Distribution-panel and breaker **inspection**" (inspection, not repair), and Scope — Excluded separately disclaims "any work beyond what can be safely assessed without specialized regulatory sign-off." Panel-level work is exactly the category most likely to require that sign-off. This keyword risks implying a repair capability on the distribution panel itself that the scope only supports as far as *inspection*. This is the same class of finding that required a keyword removal for AC Maintenance ("AC Repair UAE") — **surfaced here for Owner/reviewer decision before sync, not resolved by this document.**

---

## 6. Recommendation

**Needs decision.**

Unlike Plumbing (which reached "Sync ready" cleanly), Electrical Maintenance carries one genuine, unresolved item:

- **"Distribution Panel Repair"** (§5) needs an explicit Owner/reviewer decision — drop the keyword, or adjust the Scope — Included wording to explicitly support panel repair (if that is in fact accurate) — before a sync execution plan is written and executed. This is not a Hard Publication Block violation (no claim was actually published), but it is exactly the kind of pre-sync check this governance cycle exists to catch before content moves, not after.
- The CTA gap (§3) is the same already-precedented item resolved directly for Plumbing; a quick confirmation to reuse the same pattern is expected, not a substantive open question.

No missing source content and no other unresolved claim-safety issue was found — once the Distribution Panel Repair keyword question is resolved, this service is otherwise in the same "ready" position Plumbing was in.

---

## What This Document Does Not Do

- Does not migrate, copy, or write any content into `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/`.
- Does not modify `README.md` or any publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`, `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md` — process precedent, including the keyword-flagging pattern this review reuses
- `00_GOVERNANCE/PLUMBING_CONTENT_SOURCE_REVIEW_PLAN.md`, `PLUMBING_CONTENT_SYNC_EXECUTION_PLAN.md`, `PLUMBING_CONTENT_REVIEW_REPORT.md`, `PLUMBING_CONTENT_APPROVAL_DECISION.md`, `PLUMBING_CONTENT_APPROVAL_APPLIED.md`
- `00_GOVERNANCE/MAINTENANCE_CONTENT_SYNC_PLAN.md`
- `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/`
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` — external repository, read-only reference
