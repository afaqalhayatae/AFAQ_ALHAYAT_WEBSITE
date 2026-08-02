# Painting Content Source Review Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning and source verification only; no content migrated
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Purpose:** Start the Painting content governance cycle, following the same process already proven on AC Maintenance, Plumbing, and Electrical Maintenance — source verification only, no content migrated.
- **Scope:** Planning and review only. No service file, `README.md`, or website file was modified. Nothing staged or committed.

## Target Identification

- **Service:** Painting (`SVC-PAINTING`)
- **Knowledge-base folder:** `04_SERVICE_KNOWLEDGE/08_PAINTING/`
- **Application-repository slug:** `painting` (`src/data/SERVICE_DATABASE.json`)

---

## 1. Source Verification (afaqalhayatae-app)

- **Does Painting content exist?** Yes — a complete record exists in `afaqalhayatae-app/src/data/SERVICE_DATABASE.json`, confirmed by direct read this session.
- **Is it bilingual?** Yes — every content field has both `en` and `ar` values.
- **Is it complete?** Yes — `status.packageStatus` reads "Complete — content, SEO, and image all approved," consistent with the same measure applied to the three prior pilots.
- **Fields present:** `heroTagline`, `overview`, `commonProblems[]` (6), `scope.included[]` (6) / `excluded[]` (4), `process[]` (6 steps), `benefits[]` (5), `safety[]` (3), `faqs[]` (4 pairs), `seoTitle`, `metaDescription`, `keywords[]` (5 EN / 5 AR), `sourceDocs[]`.
- **Same provenance discrepancy as the three prior pilots:** `sourceDocs` claims `["08_PAINTING/CONTENT_EN.md", "08_PAINTING/README.md"]` as origin — those files, confirmed by fresh read this session, remain empty content-gate templates in this repository. Not relied upon; the true source is the JSON record itself.

---

## 2. Comparison Against `04_SERVICE_KNOWLEDGE/08_PAINTING/`

| | Source (`afaqalhayatae-app`) | Current knowledge base (`08_PAINTING/`) |
|---|---|---|
| `CONTENT_EN.md` equivalent | Real overview, common problems, scope, process, benefits, safety (English) | Empty content-gate template — "Content Gate," "Content Pending Approval" checklist, no actual description (confirmed by fresh read this session) |
| `CONTENT_AR.md` equivalent | Real Arabic equivalents of all the above | Empty content-gate template, Arabic (same structure, same emptiness) |
| `FAQ.md` | 4 real, answered Q&A pairs | "Draft — Answers Pending Owner Approval," an unanswered 10-item "Approved Question Backlog," no real answers |
| `SEO_AI.md` | Real SEO title, meta description, 5+5 keywords | "Draft — Not Approved for Publication or Live AI Answers," generic Safe Intent Framework only, no actual SEO fields |
| `README.md` | `packageStatus: Complete — content, SEO, and image all approved` | "Structurally Complete Draft — Owner and Operations Evidence Required" (unchanged, not touched by this review) |

**Conclusion:** the gap is identical in shape to the three prior pilots — real, complete, bilingual content exists only in the application repository; the knowledge-base files remain unpopulated templates.

---

## 3. Gaps or Conflicts Identified

- **CTA gap (same as all three prior pilots):** no per-service CTA field exists in the source record. The already-established resolution (Owner-approved "Book Appointment"/"احجز موعد" pattern) applies identically here.
- **No missing source content** relative to the established field set — every field used successfully in the three prior pilots is present here too.
- **No conflict between the catalog-level approval and the source content** — consistent with the pattern already established for the other Maintenance-category services.

---

## 4. Claim Safety Review

| Category | Finding |
|---|---|
| **Prices** | None found. Cost FAQ hedged: "Pricing depends on the area size, surface condition, and paint chosen. This is subject to company policy — please contact us directly for an accurate quote." |
| **Warranty** | None found. Warranty FAQ uses the same standardized hedge as the three prior pilots: "Warranty terms are subject to company policy — please confirm directly with our team before the visit." |
| **Certifications** | None found anywhere in overview, scope, process, benefits, safety, or FAQ. |
| **Licenses** | None found. No "licensed painter" or equivalent claim anywhere. |
| **Response-time promises** | **One item requires a careful distinction, not a violation.** The drying-time FAQ ("How long does paint take to dry before the room can be used?") is about a physical/product characteristic (paint drying time), not a service response-time commitment — the answer correctly hedges: "Drying time depends on the paint type, number of coats, and ventilation. Your technician will advise the expected drying time for your specific job before finishing." This is a different category from the "same day" service-arrival questions seen in Plumbing and Electrical Maintenance and should not be conflated with them; it is assessed as safe. |
| **Marketing promises (وعود تسويقية)** | None found beyond ordinary, hedged descriptive language. Benefits use phrases like "Refreshed, consistent appearance," "Help covering stains... evenly," and "Color guidance" — no absolute outcome ("flawless," "guaranteed," "perfect finish") is asserted as a company promise. (Note: the `heroTagline` itself contains the phrase "flawless finish" as a tagline-style hook, not a body-content claim — flagged below in §5, since it is the one piece of language in this record closest to an absolute-outcome promise.) |
| **Emergency claims** | None found. No "24/7," "urgent," or "emergency service" claim anywhere. |

**One additional item flagged for Owner awareness (not a blocker):** the `heroTagline` — "Fresh walls, flawless finish — professional painting for homes and businesses across the UAE" — uses "flawless finish" as marketing language. This is tagline-style phrasing, analogous to the already-accepted "Brand Promise" tagline treatment (`HOMEPAGE_CONTENT_IMPLEMENTATION_PLAN.md` §5), not a literal quality guarantee stated as a company commitment elsewhere in the record. Surfaced here for the Owner's awareness before migration, consistent with the level of scrutiny already applied to similar language in other pilots (e.g., AC Maintenance/Plumbing's benefit phrasing).

---

## 5. SEO Keywords vs. Scope Check

Keywords: Painting Services UAE, House Painter Dubai, Wall Painting, Interior Painting UAE, Villa Painting (English); five Arabic equivalents.

- **"Wall Painting," "Interior Painting UAE"** — checked against Scope — Included ("Interior wall and ceiling painting," "Exterior wall painting where accessible"). **Compatible.**
- **"House Painter Dubai"** — generic occupational search term, treated as safe by the same reasoning already applied to "Plumber Dubai" and "Electrician Dubai."
- **"Villa Painting" — flagged, not cleared.** Scope — Included covers exterior painting only "where accessible," and Scope — Excluded separately disclaims "work at heights requiring specialized access equipment beyond standard reach." Villas commonly include multi-story exterior facades that may fall outside standard-reach access. This keyword risks implying full villa exterior-painting capability (including height-access work) that the scope does not unconditionally support. This is the same class of finding already raised for AC Maintenance ("AC Repair UAE") and Electrical Maintenance ("Distribution Panel Repair") — **surfaced here for Owner/reviewer decision before sync, not resolved by this document.** Unlike those two cases, this one is softer/contextual (many villas are within standard reach), so it is flagged as a judgment call rather than a clear-cut mismatch.

---

## 6. Recommendation

**Needs decision** (not "Ready for sync," not "Blocked").

- **"Villa Painting"** (§5) needs an explicit Owner/reviewer decision — drop the keyword, keep it as-is (if villa painting in practice stays within standard-reach access), or qualify the Scope — Included wording — before a sync execution plan is written and executed.
- **The `heroTagline` "flawless finish" phrasing** (§4) is flagged for awareness; recommended to keep as tagline-style language (consistent with existing brand-tagline precedent) rather than as a body-content claim, but this is the Owner's call, not decided here.
- **The CTA gap** (§3) is the same already-precedented item resolved identically for the three prior pilots — a quick confirmation to reuse the same pattern is expected, not a substantive open question.

No missing source content and no other unresolved claim-safety issue was found.

---

## What This Document Does Not Do

- Does not migrate, copy, or write any content into `04_SERVICE_KNOWLEDGE/08_PAINTING/`.
- Does not modify `README.md` or any publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`, `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md`
- `00_GOVERNANCE/PLUMBING_CONTENT_SOURCE_REVIEW_PLAN.md` through `PLUMBING_CONTENT_APPROVAL_APPLIED.md`
- `00_GOVERNANCE/ELECTRICAL_CONTENT_SOURCE_REVIEW_PLAN.md` through `ELECTRICAL_CONTENT_APPROVAL_APPLIED.md` — process precedent, including the keyword-flagging pattern this review reuses
- `00_GOVERNANCE/MAINTENANCE_CONTENT_SYNC_PLAN.md`
- `04_SERVICE_KNOWLEDGE/08_PAINTING/`
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` — external repository, read-only reference
