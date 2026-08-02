# Painting Content Sync Execution Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only; no file has been copied, created, or edited; no publication status changed
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Authorizing sources:** `00_GOVERNANCE/PAINTING_CONTENT_SOURCE_REVIEW_PLAN.md`, `00_GOVERNANCE/PAINTING_SEO_DECISION_PLAN.md`, `00_GOVERNANCE/PAINTING_SEO_DECISION_APPLIED.md`
- **Scope:** Painting (`SVC-PAINTING`) only. Planning only — no content migrated, no service file edited, no `README.md` or publication status changed, no website file modified, nothing staged or committed.

## Purpose

Prepare the Painting Maintenance content migration following the same process already proven on AC Maintenance, Plumbing, and Electrical Maintenance — exact source values, exact target changes, and all four previously-recorded decisions applied — so the Owner can review precisely what execution would write before authorizing the write itself.

---

## 1. Source Mapping

- **Repository:** `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app` (read-only reference; not modified).
- **Primary file:** `src/data/SERVICE_DATABASE.json`, record `slug: "painting"` (`id: SVC-PAINTING`).
- **Related documentation sources:** `docs/SERVICE_COMPLETION_MATRIX.md` §1 (Maintenance table, Painting row — marked `COMPLETE`).
- **Provenance discrepancy carried forward (same as the three prior pilots):** this record's `sourceDocs` field claims `["08_PAINTING/CONTENT_EN.md", "08_PAINTING/README.md"]` as origin — those files are the confirmed-empty templates in this repository (`PAINTING_CONTENT_SOURCE_REVIEW_PLAN.md` §1–§2). Not relied upon; the true source is the JSON record itself.

---

## 2. Target Files

All under `04_SERVICE_KNOWLEDGE/08_PAINTING/`:

| File | Action (on execution, not performed by this plan) |
|---|---|
| `CONTENT_EN.md` | Replace the empty content-gate template with real English content |
| `CONTENT_AR.md` | Replace the empty content-gate template with real Arabic content |
| `FAQ.md` | Replace the unanswered "Approved Question Backlog" with 4 real, answered Q&A pairs |
| `SEO_AI.md` | Add real SEO title/meta/keywords (with the Villa Painting exclusion applied), publication-half status only |
| `CHANGELOG.md` | One appended audit entry recording the sync |

**`README.md` must remain unchanged** — not touched by this plan or by its eventual execution until the approval gates in §6 clear.

Untouched: `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `TRAINING.md`, `MEDIA.md`, `CUSTOMER_GUIDE.md`, `SOURCE_DRAFT.md`, `IMAGE_SEO_LIBRARY.md`, `IMAGE_GENERATION_BRIEF.md`, `assets/`.

---

## 3. Migration Mapping

Source values (as they exist today), mapped to target sections — presented here for review; **not yet written to any file**.

| Source field | Target | English (source) | Arabic (source) |
|---|---|---|---|
| `name` | Service Title | Painting | الدهانات |
| `heroTagline` | Short Description | Fresh walls, flawless finish — professional painting for homes and businesses across the UAE. *(kept as tagline language, per decision §4 below)* | جدران منعشة وتشطيب مثالي — دهانات احترافية للمنازل والمنشآت في جميع أنحاء الإمارات. |
| `overview` | Overview | Our painting service covers interior and exterior wall painting and touch-up work for homes and businesses across the UAE, from single-room refreshes to full-property repainting. | تغطي خدمة الدهانات لدينا طلاء الجدران الداخلية والخارجية وأعمال الرتوش للمنازل والمنشآت في جميع أنحاء الإمارات، من تجديد غرفة واحدة إلى إعادة طلاء العقار بالكامل. |
| `commonProblems[]` (6) | Common Problems | Faded/chipped/peeling paint; visible stains/cracks/patch marks; color mismatch after prior repair; damp/moisture marks; outdated color schemes; uneven/poor-quality previous work | طلاء باهت أو مقشر؛ بقع أو تشققات؛ عدم تطابق اللون؛ آثار رطوبة؛ أنظمة ألوان قديمة؛ أعمال طلاء غير متساوية |
| `scope.included[]` (6) | Scope — Included | Surface preparation (cleaning, minor filling, sanding); interior wall/ceiling painting; exterior wall painting where accessible; primer application; color consultation; final cleanup | تحضير السطح؛ طلاء الجدران والأسقف الداخلية؛ طلاء الجدران الخارجية حيث يمكن الوصول؛ تطبيق البرايمر؛ استشارة الألوان؛ تنظيف نهائي |
| `scope.excluded[]` (4) | Scope — Excluded | Structural repair of walls/ceilings; waterproofing/damp-proofing (separate service); specialist finishes requiring imported/custom materials; work at heights requiring specialized access equipment beyond standard reach | الإصلاح الإنشائي؛ العزل المائي (خدمة منفصلة)؛ التشطيبات المتخصصة؛ العمل على ارتفاعات تتطلب معدات وصول متخصصة |
| `process[]` (6 steps) | Process Summary | Initial consultation; on-site assessment; color/finish discussion; surface prep then primer/paint; quality check with customer; final cleanup | استشارة أولية؛ معاينة ميدانية؛ مناقشة الألوان؛ تحضير السطح ثم الطلاء؛ فحص الجودة؛ تنظيف نهائي |
| `benefits[]` (5) | Why Choose Us | Refreshed, consistent appearance; help covering stains/cracks evenly; color guidance; scheduling across 7 emirates; clear explanation before work starts | مظهر منعش ومتسق؛ المساعدة في تغطية العيوب؛ إرشاد الألوان؛ الجدولة في 7 إمارات؛ شرح واضح قبل البدء |
| `safety[]` (3) | General Safety Notes | Furniture/flooring protected before painting; work areas kept ventilated; work requiring specialized access equipment flagged rather than attempted | حماية الأثاث والأرضيات؛ الحفاظ على التهوية؛ إبلاغ العميل بالأعمال التي تتطلب معدات وصول متخصصة |
| `faqs[]` (4 pairs) | `FAQ.md` | Drying time (informational only, per decision §4); warranty; color-choice help; cost | نفس الأربعة، عربي |
| `seoTitle` | `SEO_AI.md` | Painting Services in the UAE \| AFAQ AL HAYAT | خدمات الدهانات في الإمارات \| آفاق الحياة |
| `metaDescription` | `SEO_AI.md` | Professional interior and exterior painting across the UAE from AFAQ AL HAYAT — surface preparation, color consultation, and clean finishing for homes and businesses. | طلاء داخلي وخارجي احترافي في جميع أنحاء الإمارات من آفاق الحياة — تحضير الأسطح واستشارة الألوان وتشطيب نظيف للمنازل والمنشآت. |
| `keywords[]` | `SEO_AI.md` | See §4 — one keyword excluded per decision | See §4 |
| — (no source field) | Call to Action | **Book Appointment** | **احجز موعد** *(per §4 — see CTA note below)* |

---

## 4. Apply Previous Decisions

Per `00_GOVERNANCE/PAINTING_SEO_DECISION_APPLIED.md`:

1. **"Villa Painting" removed** from the English keyword list.
2. **Arabic equivalent "دهان فلل" removed** alongside it, keeping both language lists aligned (4 of the original 5 each).
   - **Keywords to migrate (English):** Painting Services UAE; House Painter Dubai; Wall Painting; Interior Painting UAE.
   - **Keywords to migrate (Arabic):** دهانات الإمارات؛ دهان دبي؛ طلاء جدران؛ دهانات داخلية.
3. **"Fresh walls, flawless finish" kept as tagline-only language** — migrates unchanged in the Short Description field, explicitly annotated (in the target file, per §3 above) as marketing/hook language, not a performance guarantee.
4. **Paint drying duration FAQ kept as informational content only** — migrates unchanged, explicitly annotated as a physical/product characteristic, not a response-time promise, so it is never mis-flagged in future review.

**CTA — resolved, not re-opened:** this instruction's own text again listed the Arabic CTA as "دعوم زجحا." That exact discrepancy was already raised in `PAINTING_SEO_DECISION_PLAN.md` §4 and explicitly resolved by the Owner's direct confirmation (this session) that the correct, intended phrase is **"احجز موعد"** — the same phrase already recorded in `PAINTING_SEO_DECISION_APPLIED.md` §4 and used identically for AC Maintenance, Plumbing, and Electrical Maintenance. This plan applies that already-confirmed resolution rather than re-litigating it: **English — Book Appointment; Arabic — احجز موعد.** "دعوم زجحا" is not applied anywhere.

---

## 5. Validation Rules

| Check | Assessment (against the mapped content in §3) |
|---|---|
| No price claims | None present. Cost FAQ hedged: "Pricing depends on the area size, surface condition, and paint chosen... subject to company policy." |
| No warranty guarantees | None present. Warranty FAQ uses the standardized hedge; no guarantee language elsewhere. |
| No certification/license claims | None present anywhere in overview, scope, process, benefits, safety, or FAQ. |
| No response-time promises | None present. The drying-time FAQ is explicitly classified as informational/product-characteristic, not a response-time claim, per decision §4. |
| No unsupported quality guarantees | "Flawless finish" is the one item of note — classified as tagline/hook language per decision §4, not a body-content quality guarantee; no other absolute-outcome language found. |
| Scope consistency with exclusions | Confirmed — Scope — Included's "exterior wall painting where accessible" and Scope — Excluded's "work at heights requiring specialized access equipment beyond standard reach" are consistent with each other; the Villa Painting keyword exclusion (§4) keeps the SEO layer consistent with this same boundary. |
| Bilingual parity | Confirmed — every field in §3 has matching EN/AR content expressing the same facts; both keyword lists reduced identically (4 of 5 each) so no language carries a claim the other doesn't. |

**No blocking finding.**

---

## 6. Approval Gates

- **Migration only after plan approval** — no file listed in §2 is written until this plan itself is explicitly authorized.
- **Independent review required** — a separate check against this plan's §5 validation, mirroring `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md`, `PLUMBING_CONTENT_REVIEW_REPORT.md`, and `ELECTRICAL_CONTENT_REVIEW_REPORT.md`, confirming nothing drifted between plan and execution — including a direct check that neither "Villa Painting"/"دهان فلل" nor "دعوم زجحا" appear in any migrated field.
- **`README.md` status remains unchanged** — no change to `README.md` occurs as part of migration execution itself; status synchronization is a separate, later, explicitly authorized step.
- **No website integration** — no website file, in either repository, is touched at any point in this plan or its eventual execution.

---

## What This Document Does Not Do

- Does not copy, create, or edit any file in `04_SERVICE_KNOWLEDGE/08_PAINTING/`.
- Does not modify `README.md` or any publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/PAINTING_CONTENT_SOURCE_REVIEW_PLAN.md`
- `00_GOVERNANCE/PAINTING_SEO_DECISION_PLAN.md`, `PAINTING_SEO_DECISION_APPLIED.md`
- `00_GOVERNANCE/AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`, `PLUMBING_CONTENT_SYNC_EXECUTION_PLAN.md`, `ELECTRICAL_CONTENT_SYNC_EXECUTION_PLAN.md` — process/format precedent
- `04_SERVICE_KNOWLEDGE/08_PAINTING/`
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` — external repository, read-only source
