# Handyman Content Sync Execution Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only; no file has been copied, created, or edited; no publication status changed
- **Version:** 1.0
- **Prepared:** 2026-08-02
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Authorizing source:** `00_GOVERNANCE/HANDYMAN_CONTENT_SOURCE_REVIEW_PLAN.md`
- **Scope:** Handyman (`SVC-HANDYMAN`) only. Planning only — no content migrated, no service file edited, no `README.md` or publication status changed, no website file modified, nothing staged or committed.

## Purpose

Prepare the Handyman content migration following the same process already proven on AC Maintenance, Plumbing, Electrical Maintenance, and Painting — exact source values, exact target changes, and the source review's decisions applied — so the Owner can review precisely what execution would write before authorizing the write itself.

---

## 1. Source Mapping

- **Repository:** `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app` (read-only reference; not modified).
- **Primary file:** `src/data/SERVICE_DATABASE.json`, record `slug: "handyman"` (`id: SVC-HANDYMAN`).
- **Related documentation sources:** `docs/SERVICE_COMPLETION_MATRIX.md` — Maintenance table, Handyman row: `CONTENT COMPLETE — awaiting a real photo (never had one)`.
- **Provenance discrepancy carried forward (same as the four prior pilots):** this record's `sourceDocs` field claims `["09_HANDYMAN/CONTENT_EN.md", "09_HANDYMAN/README.md"]` as origin — those files are the confirmed-empty templates in this repository (`HANDYMAN_CONTENT_SOURCE_REVIEW_PLAN.md` §1–§2). Not relied upon; the true source is the JSON record itself.

---

## 2. Target Files

All under `04_SERVICE_KNOWLEDGE/09_HANDYMAN/`:

| File | Action (on execution, not performed by this plan) |
|---|---|
| `CONTENT_EN.md` | Replace the empty content-gate template with real English content |
| `CONTENT_AR.md` | Replace the empty content-gate template with real Arabic content |
| `FAQ.md` | Replace the unanswered "Approved Question Backlog" with 3 real, answered Q&A pairs |
| `SEO_AI.md` | Add real SEO title/meta/keywords, publication-half status only |
| `CHANGELOG.md` | One appended audit entry recording the sync |

**`README.md` must remain unchanged** — not touched by this plan or by its eventual execution until the approval gates in §6 clear. It currently lists "Define permitted tasks and explicit boundaries with licensed trades" as still required; `HANDYMAN_CONTENT_SOURCE_REVIEW_PLAN.md` §3 flags that this may already be satisfied by the source's `scope.excluded`/`safety` fields, but resolving that reading is an Owner decision, not something this plan or its execution performs.

Untouched: `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `TRAINING.md`, `MEDIA.md`, `CUSTOMER_GUIDE.md`, `SOURCE_DRAFT.md`, `IMAGE_SEO_LIBRARY.md`, `IMAGE_GENERATION_BRIEF.md`, `assets/`.

---

## 3. Migration Mapping

Source values (as they exist today), mapped to target sections — presented here for review; **not yet written to any file**.

| Source field | Target | English (source) | Arabic (source) |
|---|---|---|---|
| `name` | Service Title | Handyman Services | خدمات الصيانة العامة (هاندي مان) |
| `heroTagline` | Short Description | One call for the small jobs that pile up — general handyman service across the UAE. | اتصال واحد للمهام الصغيرة المتراكمة — خدمة صيانة عامة (هاندي مان) في جميع أنحاء الإمارات. |
| `overview` | Overview | Our handyman service covers small, general repair and installation tasks around the home or office that don't need a dedicated trade specialist — the kind of everyday jobs that can otherwise sit unresolved on a to-do list. | تغطي خدمة الصيانة العامة (هاندي مان) لدينا مهام الإصلاح والتركيب الصغيرة والعامة في المنزل أو المكتب التي لا تحتاج إلى أخصائي حرفة مخصصة — المهام اليومية التي قد تبقى دون حل في قائمة المهام. |
| `commonProblems[]` (6) | Common Problems | Door/cabinet not closing properly; loose hinges/handles/fittings; furniture assembly or minor repair; small wall-mounting jobs; minor carpentry touch-ups; general small repairs that don't fit a single trade category | باب أو خزانة لا يُغلق؛ مفصلات أو مقابض غير محكمة؛ تجميع أثاث أو إصلاح بسيط؛ تركيب بسيط على الجدران؛ رتوش نجارة بسيطة؛ إصلاحات صغيرة عامة |
| `scope.included[]` (6) | Scope — Included | Door, cabinet, and hinge adjustment; furniture assembly and minor repair; wall-mounting of shelves/mirrors/fixtures; minor carpentry and fitting repairs; general small-item installation; multi-task visits combining several small jobs in one call-out | ضبط الأبواب والخزائن والمفصلات؛ تجميع الأثاث وإصلاحه البسيط؛ تركيب الأرفف والمرايا والتجهيزات؛ إصلاحات نجارة وتركيبات بسيطة؛ تركيب عام للأغراض الصغيرة؛ زيارات متعددة المهام |
| `scope.excluded[]` (4) | Scope — Excluded | Specialized trade work (major electrical, plumbing, or AC repair — see dedicated services); structural carpentry or renovation-scale work; manufacturer warranty claims on furniture/fittings; any job requiring a licensed trade specialist beyond general handyman scope | الأعمال الحرفية المتخصصة؛ أعمال نجارة إنشائية أو بحجم التجديد؛ مطالبات ضمان الشركة المصنعة؛ أي عمل يتطلب أخصائي حرفة مرخصًا |
| `process[]` (6 steps) | Process Summary | Initial WhatsApp/phone consultation; on-site assessment; scope confirmation with customer; work carried out (often multi-task); quality check with customer; work area left clean | استشارة أولية عبر واتساب أو الهاتف؛ معاينة ميدانية؛ تأكيد النطاق مع العميل؛ تنفيذ العمل؛ فحص الجودة مع العميل؛ ترك مكان العمل نظيفًا |
| `benefits[]` (5) | Why Choose Us | One visit can cover several small jobs at once; useful for tasks too small for a dedicated trade call-out; convenient for tenants/homeowners clearing a maintenance backlog; scheduling across all seven UAE emirates; clear scope agreed before work starts | يمكن لزيارة واحدة تغطية عدة مهام؛ مفيدة للمهام الصغيرة جدًا؛ مريحة للمستأجرين وأصحاب المنازل؛ إمكانية الجدولة في سبع إمارات؛ نطاق عمل واضح متفق عليه |
| `safety[]` (3) | General Safety Notes | Any task requiring a licensed trade specialist is flagged to the customer rather than attempted outside scope; tools/materials handled per standard safe-practice; work areas left tidy and hazard-free | أي مهمة تتطلب أخصائي حرفة مرخص يتم إبلاغ العميل بها؛ التعامل مع الأدوات والمواد وفق ممارسات السلامة؛ ترك مكان العمل مرتبًا وخاليًا من المخاطر |
| `faqs[]` (3 pairs) | `FAQ.md` | Multi-task visits; handyman-vs-trade guidance; cost | نفس الثلاثة، عربي |
| `seoTitle` | `SEO_AI.md` | Handyman Services in the UAE \| AFAQ AL HAYAT | خدمات الصيانة العامة (هاندي مان) في الإمارات \| آفاق الحياة |
| `metaDescription` | `SEO_AI.md` | General handyman services across the UAE from AFAQ AL HAYAT — furniture assembly, wall-mounting, minor carpentry, and small repairs for homes and offices. | خدمات صيانة عامة (هاندي مان) في جميع أنحاء الإمارات من آفاق الحياة — تجميع الأثاث والتركيب على الجدران والنجارة البسيطة والإصلاحات الصغيرة للمنازل والمكاتب. |
| `keywords[]` (5 EN / 5 AR) | `SEO_AI.md` | Handyman UAE; Handyman Dubai; Furniture Assembly; Small Repairs; General Maintenance UAE — all 5 migrate, none excluded (§4) | هاندي مان الإمارات؛ صيانة عامة دبي؛ تجميع أثاث؛ إصلاحات صغيرة؛ صيانة منزلية عامة |
| — (no source field) | Call to Action | **Book Appointment** | **احجز موعد** *(per §4 — see CTA note below)* |

---

## 4. Apply Previous Decisions

Per `00_GOVERNANCE/HANDYMAN_CONTENT_SOURCE_REVIEW_PLAN.md`:

1. **No keyword exclusion required** — unlike Painting's "Villa Painting," the source review found no keyword in this record reaching toward excluded scope (specialized/licensed-trade or structural work). All 5 English and 5 Arabic keywords migrate unchanged.
2. **No tagline-language flag required** — unlike Painting's "flawless finish," the `heroTagline` here ("One call for the small jobs that pile up") contains no absolute-outcome phrasing; it migrates unchanged with no annotation needed.
3. **Cost FAQ kept as hedged, policy-deferred language** — migrates unchanged: "Pricing depends on the number and type of tasks... please contact us directly for an accurate quote."

**CTA — resolved, not re-opened:** this instruction's own text again listed the Arabic CTA as "دعوم زجحا." That exact discrepancy was already raised and resolved for Painting (`PAINTING_CONTENT_SYNC_EXECUTION_PLAN.md` §4) via the Owner's direct confirmation that the correct, intended phrase is **"احجز موعد"** — the same phrase used identically for AC Maintenance, Plumbing, Electrical Maintenance, and Painting. This plan applies that already-confirmed resolution rather than re-litigating it: **English — Book Appointment; Arabic — احجز موعد.** "دعوم زجحا" is not applied anywhere.

---

## 5. Validation Rules

| Check | Assessment (against the mapped content in §3) |
|---|---|
| No price claims | None present. Cost FAQ hedged: "Pricing depends on the number and type of tasks... subject to company policy." |
| No warranty guarantees | None present — and self-limiting: `scope.excluded` explicitly disclaims manufacturer warranty claims on furniture/fittings as out of scope. |
| No certification/license claims | None present anywhere in overview, scope, process, benefits, safety, or FAQ — and self-limiting: content explicitly states any task requiring a licensed trade specialist is flagged to the customer rather than attempted. |
| No response-time promises | None present. No "same day" or time-to-arrival commitment anywhere. |
| No emergency claims | None present. No "24/7," "urgent," or "emergency service" claim anywhere. |
| No unsupported quality guarantees | None present. Benefits use hedged, functional language ("often cover," "convenient for," "clear scope agreed") — no absolute-outcome word ("guaranteed," "flawless," "perfect") anywhere in this record. |
| Scope consistency with exclusions | Confirmed — Scope — Included's general/small-task items and Scope — Excluded's licensed-trade/structural/warranty items are mutually consistent; the FAQ ("How do I know if my task needs a handyman or a specialist trade?") reinforces the same boundary directly to the customer. |
| SEO keyword consistency with scope | Confirmed — none of the 5 keywords (§4) implies licensed-trade capability or overlaps with Electrical/Plumbing/AC Maintenance's included scope. |
| Bilingual parity | Confirmed — every field in §3 has matching EN/AR content expressing the same facts; both keyword lists carry the same 5 items each. |

**No blocking finding.**

---

## 6. Approval Gates

- **Migration only after plan approval** — no file listed in §2 is written until this plan itself is explicitly authorized.
- **Independent review required** — a separate check against this plan's §5 validation, mirroring `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md`, `PLUMBING_CONTENT_REVIEW_REPORT.md`, `ELECTRICAL_CONTENT_REVIEW_REPORT.md` (and the equivalent Painting review), confirming nothing drifted between plan and execution — including a direct check that "دعوم زجحا" does not appear in any migrated field.
- **`README.md` status remains unchanged** — no change to `README.md` occurs as part of migration execution itself; status synchronization, and the separate scope-boundary reading flagged in §2, are later, explicitly authorized steps.
- **Image gap remains open and separate** — Handyman has no real card image; per the Owner's no-placeholder rule (Decision Log #37–#39) the page stays excluded from website grids/related-links regardless of this content sync. This is a website asset/photography issue tracked independently of the knowledge-base sync and is not resolved, and not claimed to be resolved, by this plan or its eventual execution.
- **No website integration** — no website file, in either repository, is touched at any point in this plan or its eventual execution.

---

## What This Document Does Not Do

- Does not copy, create, or edit any file in `04_SERVICE_KNOWLEDGE/09_HANDYMAN/`.
- Does not modify `README.md` or any publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/HANDYMAN_CONTENT_SOURCE_REVIEW_PLAN.md`
- `00_GOVERNANCE/AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`, `PLUMBING_CONTENT_SYNC_EXECUTION_PLAN.md`, `ELECTRICAL_CONTENT_SYNC_EXECUTION_PLAN.md`, `PAINTING_CONTENT_SYNC_EXECUTION_PLAN.md` — process/format precedent
- `00_GOVERNANCE/DECISION_LOG.md` — decision #38 (content authorization) and #37/#39 (no-placeholder image rule)
- `04_SERVICE_KNOWLEDGE/09_HANDYMAN/`
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` — external repository, read-only source
- `afaqalhayatae-app/docs/SERVICE_COMPLETION_MATRIX.md` — Handyman row
