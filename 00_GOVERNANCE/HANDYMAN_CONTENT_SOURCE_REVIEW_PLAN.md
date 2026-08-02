# Handyman Content Source Review Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning and source verification only; no content migrated
- **Version:** 1.0
- **Prepared:** 2026-08-02
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Purpose:** Start the Handyman content governance cycle, following the same process already proven on AC Maintenance, Plumbing, Electrical Maintenance, and Painting — source verification only, no content migrated.
- **Scope:** Planning and review only. No service file, `README.md`, or website file was modified. Nothing staged or committed.

## Target Identification

- **Service:** Handyman Services (`SVC-HANDYMAN`)
- **Category:** General Maintenance
- **Knowledge-base folder:** `04_SERVICE_KNOWLEDGE/09_HANDYMAN/`
- **Application-repository slug:** `handyman` (`afaqalhayatae-app/src/data/SERVICE_DATABASE.json`, confirmed present at `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app`)

---

## 1. Source Verification (afaqalhayatae-app)

- **Does Handyman content exist?** Yes — a complete record exists in `SERVICE_DATABASE.json`, confirmed by direct read this session.
- **Is it bilingual?** Yes — every content field has both `en` and `ar` values.
- **Status fields recorded in the source itself:**
  - `seo`: "Approved — content authored 2026-07-31 per Owner's Service Completion Phase order (general operational knowledge only; no license/warranty/response-time claim)"
  - `pageContent`: "Approved — Owner-directed content build 2026-07-31, see DECISION_LOG #38"
  - `images`: "None — still no real card image; content is complete and ready, but the page stays correctly excluded from every grid/related-link until a real photo exists (no placeholder used)"
  - `packageStatus`: "Content, SEO complete — image gap remains open"
  - `booking`: "Not started"
- **Confirmed against `00_GOVERNANCE/DECISION_LOG.md` #38** (2026-07-31): the Owner authorized authoring Handyman content/SEO from general operational knowledge, explicitly excluding any invented price, discount, warranty, guarantee, license, certification, or exact response-time commitment; the same decision confirms Handyman has no real card image and stays excluded from grids/related-links under the no-placeholder rule.
- **`SERVICE_CATALOG.md` matches:** `SVC-HANDYMAN` row reads "✅ Content approved 2026-07-31; still no real card image (excluded from website grids until one exists)" — consistent with the source record and the Decision Log.
- **Fields present:** `heroTagline`, `overview`, `commonProblems[]` (6), `scope.included[]` (6) / `excluded[]` (4), `process[]` (6 steps), `benefits[]` (5), `safety[]` (3), `faqs[]` (3 pairs), `seoTitle`, `metaDescription`, `keywords[]` (5 EN / 5 AR), `sourceDocs[]`.
- **Same provenance discrepancy as the four prior pilots:** `sourceDocs` claims `["09_HANDYMAN/CONTENT_EN.md", "09_HANDYMAN/README.md"]` as origin — those files, confirmed by fresh read this session, remain empty content-gate templates in this repository. Not relied upon; the true source is the JSON record itself.

---

## 2. Comparison Against `04_SERVICE_KNOWLEDGE/09_HANDYMAN/`

| | Source (`afaqalhayatae-app`) | Current knowledge base (`09_HANDYMAN/`) |
|---|---|---|
| `CONTENT_EN.md` equivalent | Real overview, common problems, scope, process, benefits, safety (English) | Empty content-gate template — "Content Gate," "Content Pending Approval" checklist, no actual description (confirmed by fresh read this session) |
| `CONTENT_AR.md` equivalent | Real Arabic equivalents of all the above | Empty content-gate template, Arabic (same structure, same emptiness) |
| `FAQ.md` | 3 real, answered Q&A pairs | "Draft — Answers Pending Owner Approval," an unanswered 10-item "Approved Question Backlog," no real answers |
| `SEO_AI.md` | Real SEO title, meta description, 5+5 keywords | "Draft — Not Approved for Publication or Live AI Answers," generic Safe Intent Framework only, no actual SEO fields |
| `README.md` | `packageStatus: Content, SEO complete — image gap remains open` | "Structurally Complete Draft — Owner Scope-Boundary Evidence Required," listing "Define permitted tasks and explicit boundaries with licensed trades" as still-required (unchanged, not touched by this review) |

**Conclusion:** the content gap is identical in shape to the four prior pilots — real, complete, bilingual content exists only in the application repository; the knowledge-base files remain unpopulated templates. One difference from the prior pilots: this service also carries a **separate, non-content publish blocker** — no real card image exists, so the page is excluded from website grids/related-links regardless of any content-sync decision (see §3 and §6).

---

## 3. Gaps, Conflicts, or Blockers Identified

- **CTA gap (same as all four prior pilots):** no per-service CTA field exists in the source record. The already-established resolution (Owner-approved "Book Appointment"/"احجز موعد" pattern) applies identically here.
- **Image gap (blocker, distinct from content sync):** the source record and `SERVICE_CATALOG.md` both confirm no real card image exists for Handyman. Under the Owner's no-placeholder rule (Decision Log #37–#39), the page stays excluded from grids/related-links until a real photo is supplied — this is independent of whether the text/SEO content is synced into the knowledge base, and a content sync alone would not make the service live on the site.
- **`README.md` internal inconsistency worth Owner attention:** the current `09_HANDYMAN/README.md` lists "Define permitted tasks and explicit boundaries with licensed trades" as a still-required item before approval. The source content's `scope.excluded` already does this explicitly — "Specialized trade work (major electrical, plumbing, or AC repair...)," "Any job requiring a licensed trade specialist beyond general handyman scope" — and `safety[]` adds "Any task found to require a licensed trade specialist is flagged to the customer rather than attempted outside scope." This looks like the boundary the README is asking for already exists in the approved source; flagged for Owner confirmation rather than resolved here, since `README.md` is untouched by this review.
- **No missing source content** relative to the established field set — every field used successfully in the four prior pilots is present here too.
- **No conflict between the catalog-level approval and the source content.**

---

## 4. Claim Safety Review

| Category | Finding |
|---|---|
| **Prices** | None found. Cost FAQ hedged: "Pricing depends on the number and type of tasks. This is subject to company policy — please contact us directly for an accurate quote for your specific list of jobs." |
| **Warranty** | None found — and notably self-limiting: `scope.excluded` explicitly disclaims "Manufacturer warranty claims on furniture or fittings" as out of scope, rather than implying any warranty coverage. |
| **Guarantees** | None found anywhere in overview, scope, process, benefits, safety, or FAQ. |
| **Certifications** | None found. |
| **Licenses** | None found — and again self-limiting: content explicitly states any task requiring a licensed trade specialist is flagged to the customer rather than attempted, and is listed under `scope.excluded`. No claim of licensure is made for the handyman service itself. |
| **Response-time promises** | None found. No "same day," no specific time-to-arrival commitment anywhere. |
| **Emergency claims** | None found. No "24/7," "urgent," or "emergency service" claim anywhere. |
| **Unsupported quality claims** | None found. Benefits use hedged, functional language ("One visit can often cover several small, unrelated jobs at once," "Convenient for tenants and homeowners clearing a maintenance backlog," "Clear scope agreed with the customer before work starts") — no absolute outcome ("guaranteed," "perfect," "flawless") is asserted. |

No claim-safety issue was found. This record is, if anything, more conservatively worded than the four prior pilots, since the scope itself is built around explicitly excluding licensed-trade and warranty territory rather than merely omitting it.

---

## 5. Scope Review

- **Included:** door/cabinet/hinge adjustment, furniture assembly and minor repair, wall-mounting (shelves, mirrors, fixtures), minor carpentry and fitting repairs, general small-item installation, multi-task visits combining several small jobs in one call-out.
- **Excluded:** specialized trade work (major electrical, plumbing, or AC repair — explicitly deferred to the dedicated services), structural carpentry or renovation-scale work, manufacturer warranty claims on furniture/fittings, any job requiring a licensed trade specialist beyond general handyman scope.
- **Keyword conflicts:** none found. No keyword in §6 below implies licensed-trade capability or overlaps with the scope of Electrical Maintenance, Plumbing, or AC Maintenance's included lists.
- **Repair-wording conflicts:** none found. "Small repairs," "general small repairs," and "minor carpentry" are consistently hedged against the explicit trade-work exclusion; the FAQ ("How do I know if my task needs a handyman or a specialist trade?") reinforces the same boundary directly to the customer.
- **Cross-check against `SERVICE_CATALOG.md`:** category `General Maintenance` matches the source record's `category: general-maintenance`; no mismatch.

---

## 6. SEO Keywords vs. Scope Check

Keywords: Handyman UAE, Handyman Dubai, Furniture Assembly, Small Repairs, General Maintenance UAE (English); five Arabic equivalents.

- **"Furniture Assembly"** — checked against Scope — Included ("Furniture assembly and minor repair"). **Compatible.**
- **"Small Repairs"** — checked against Scope — Included ("General small-item installation") and the `commonProblems` list ("General small repairs that don't fit a single trade category"). **Compatible**, and already self-bounded by the scope-exclusion of specialized/structural work.
- **"Handyman UAE" / "Handyman Dubai"** — generic occupational search terms, treated as safe by the same reasoning already applied to "Plumber Dubai" and "Electrician Dubai" in the prior pilots.
- **"General Maintenance UAE"** — matches the catalog category name directly. **Compatible.**

No keyword flags a scope mismatch in this record — unlike Painting's "Villa Painting" or AC Maintenance's "AC Repair UAE," none of the five Handyman keywords reach toward territory the scope excludes.

---

## 7. CTA

Established pattern (already applied identically across AC Maintenance, Plumbing, Electrical Maintenance, and Painting):

- **English:** Book Appointment
- **Arabic:** احجز موعد

No per-service CTA field exists in the source record — the same gap already resolved for the four prior pilots. Applying this pattern to Handyman is expected to be a straightforward reuse, not a new decision.

---

## 8. Recommendation

**Needs decision** (not "Ready for sync," not "Blocked").

- **Content and SEO themselves are clean and ready** — no missing field, no claim-safety issue, no scope/keyword mismatch (§4–§6). If the only question were text sync, this would be "Ready for sync."
- **The image gap (§3) is the deciding factor.** Handyman has no real card image and, per the Owner's own no-placeholder rule, stays excluded from website grids and related-links regardless of content-sync status. The Owner should confirm whether to (a) sync the knowledge-base content/SEO now — bringing `09_HANDYMAN/` in line with the already-approved source, while the page remains grid-excluded until a photo exists — or (b) hold the knowledge-base sync until the image is supplied, so content and visibility land together.
- **The `README.md` scope-boundary item (§3)** appears to already be satisfied by the source content's explicit trade/warranty exclusions, but `README.md` still lists it as outstanding. Recommend the Owner confirm this reading before it is updated in a future execution step — not resolved here.
- **The CTA gap (§7)** is the same already-precedented item resolved identically for the four prior pilots — a quick confirmation to reuse the same pattern is expected, not a substantive open question.

No missing source content and no claim-safety issue was found.

---

## What This Document Does Not Do

- Does not migrate, copy, or write any content into `04_SERVICE_KNOWLEDGE/09_HANDYMAN/`.
- Does not modify `README.md` or any publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`, `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md`
- `00_GOVERNANCE/PLUMBING_CONTENT_SOURCE_REVIEW_PLAN.md` through `PLUMBING_CONTENT_APPROVAL_APPLIED.md`
- `00_GOVERNANCE/ELECTRICAL_CONTENT_SOURCE_REVIEW_PLAN.md` through `ELECTRICAL_CONTENT_APPROVAL_APPLIED.md` — process precedent, including the keyword-flagging pattern this review reuses
- `00_GOVERNANCE/PAINTING_CONTENT_SOURCE_REVIEW_PLAN.md`, `PAINTING_CONTENT_REVIEW_REPORT.md`
- `00_GOVERNANCE/DECISION_LOG.md` — decision #38 (content authorization) and #37/#39 (no-placeholder image rule)
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` — `SVC-HANDYMAN` row
- `04_SERVICE_KNOWLEDGE/09_HANDYMAN/`
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` — external repository, read-only reference (`/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app`)
