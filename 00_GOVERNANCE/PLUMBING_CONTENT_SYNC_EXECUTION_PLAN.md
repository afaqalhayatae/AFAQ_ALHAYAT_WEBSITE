# Plumbing Content Sync Execution Plan (Pilot Extension)

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only; no file has been copied, created, or edited; no publication status changed
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Authorizing decision:** Owner instruction to plan the Plumbing migration, following `00_GOVERNANCE/PLUMBING_CONTENT_SOURCE_REVIEW_PLAN.md`'s "Sync ready" recommendation and the process already proven on AC Maintenance (`AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`, `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md`).
- **Scope:** Plumbing (`SVC-PLUMBING`) only. No file was copied, no service file was edited, no publication status was changed, no website file was modified, nothing staged or committed.

## Purpose

Apply `MAINTENANCE_CONTENT_SYNC_PLAN.md`'s general mapping and the AC Maintenance pilot's proven process to Plumbing — exact source values, exact target changes, and validation already run against this specific content — so the Owner can review precisely what execution would write before authorizing the write itself.

---

## 1. Source File Mapping

- **Repository:** `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app` (read-only reference; not modified).
- **Primary file:** `src/data/SERVICE_DATABASE.json`, record `slug: "plumbing"` (`id: SVC-PLUMBING`).
- **Cross-reference:** `docs/SERVICE_COMPLETION_MATRIX.md` §1 (Maintenance table, Plumbing row — marked `COMPLETE`).
- **Provenance discrepancy carried forward (same as AC Maintenance):** this record's `sourceDocs` field claims `["06_PLUMBING/CONTENT_EN.md", "06_PLUMBING/README.md"]` as origin — those files are the confirmed-empty templates in this repository (`PLUMBING_CONTENT_SOURCE_REVIEW_PLAN.md` §4). Not relied upon; the true source is the JSON record itself.

---

## 2. Target Plumbing Knowledge Files

All under `04_SERVICE_KNOWLEDGE/06_PLUMBING/`:

| File | Action (on execution, not performed by this plan) |
|---|---|
| `CONTENT_EN.md` | Replace the empty content-gate template with real English content |
| `CONTENT_AR.md` | Replace the empty content-gate template with real Arabic content |
| `FAQ.md` | Replace the unanswered "Approved Question Backlog" with 4 real, answered Q&A pairs |
| `SEO_AI.md` | Add real SEO title/meta/keywords, publication-half status only (Live AI Answers gate stays separately closed, per `09_AI_KNOWLEDGE/ANSWER_POLICY.md`) |
| `README.md` | Status banner update — **not performed until §6's checkpoint clears** |
| `CHANGELOG.md` | One appended audit entry recording the sync |

Untouched: `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `TRAINING.md`, `MEDIA.md`, `CUSTOMER_GUIDE.md`, `SOURCE_DRAFT.md`, `IMAGE_SEO_LIBRARY.md`, `IMAGE_GENERATION_BRIEF.md`, `assets/`.

---

## 3. Fields to Migrate

Source values (as they exist today in `SERVICE_DATABASE.json`), mapped to target sections — presented here for review; **not yet written to any file**.

### → `CONTENT_EN.md` / `CONTENT_AR.md`

| Section | English (source) | Arabic (source) |
|---|---|---|
| Service Title | Plumbing | السباكة |
| Supporting line (`heroTagline`) | From a dripping tap to a stubborn leak — plumbing help across the UAE, done right. | من حنفية تتنقط إلى تسرب عنيد — مساعدة سباكة في جميع أنحاء الإمارات، بالطريقة الصحيحة. |
| Overview | Our plumbing service covers everyday repairs and maintenance for the pipes, fittings, and fixtures found in UAE homes and businesses — from leaking taps to blocked or slow-draining fixtures. | تغطي خدمة السباكة لدينا الإصلاحات والصيانة اليومية للأنابيب والتوصيلات والتجهيزات في المنازل والمنشآت بالإمارات — من الحنفيات المتسربة إلى التجهيزات بطيئة الصرف أو المسدودة. |
| Common Problems (6) | Leaking/dripping taps and mixers; low water pressure; running/noisy toilet cisterns; slow-draining sinks/showers/bathtubs; visible pipe leaks under sinks or exposed piping; water heater connection issues | تسرب الحنفيات؛ ضعف الضغط؛ صندوق مرحاض مستمر التسريب؛ بطء تصريف؛ تسربات ظاهرة؛ مشاكل توصيلات سخان المياه |
| Scope — Included (6) | Tap/mixer/fixture leak repair; pipe joint and fitting inspection/repair; toilet cistern and flush repair; water heater connection checks; drain/trap inspection; general plumbing fault diagnosis | إصلاح تسرب الحنفيات؛ فحص وإصلاح وصلات الأنابيب؛ إصلاح صندوق المرحاض؛ فحص توصيلات السخان؛ فحص الصرف والمصائد؛ تشخيص عام لأعطال السباكة |
| Scope — Excluded (4) | Major re-piping/full bathroom re-plumbing projects; main water-line/municipal connection work; manufacturer warranty claims on fixtures/appliances; structural work to access hidden piping | إعادة تمديد كبرى/إعادة سباكة الحمام بالكامل؛ أعمال خط المياه الرئيسي/التوصيل البلدي؛ مطالبات ضمان الشركة المصنعة؛ أعمال إنشائية للوصول لأنابيب مخفية |
| Process (6 steps) | Initial WhatsApp/phone consultation; on-site inspection; diagnosis explained before work begins; agreed repair or maintenance work carried out; fixture tested for leaks/function; work area left clean with summary | استشارة أولية؛ معاينة ميدانية؛ مشاركة التشخيص قبل البدء؛ تنفيذ أعمال الإصلاح أو الصيانة المتفق عليها؛ اختبار التجهيز؛ ترك مكان العمل نظيفًا مع ملخص |
| Benefits (5) | Faster identification of leak/blockage source; reduced water waste over time; support for minor repairs and routine upkeep; scheduling across all 7 emirates; clear explanation before work starts | تحديد أسرع للمصدر؛ تقليل هدر المياه؛ دعم الإصلاحات البسيطة والصيانة الروتينية؛ الجدولة في 7 إمارات؛ شرح واضح قبل البدء |
| General Safety notes (3) | Water supply isolated before repair where needed; technicians check for related issues (e.g. water damage) while addressing the fault; out-of-scope issues flagged rather than attempted | إغلاق إمداد المياه عند الحاجة؛ التحقق من مشاكل مرتبطة كأضرار المياه؛ إبلاغ العميل بالحالات خارج النطاق |
| CTA | **Book Appointment** *(per §4 below — Owner-approved generic pattern, applied directly)* | **احجز موعد** *(same)* |

### → `FAQ.md` (4 real Q&A pairs)

| Question (EN) | Answer (EN) | Question (AR) | Answer (AR) |
|---|---|---|---|
| Can you fix a leak the same day I contact you? | Availability depends on scheduling at the time you contact us. Please reach out via WhatsApp or phone and we'll confirm the earliest available appointment. | هل يمكن إصلاح التسرب في نفس يوم التواصل؟ | تعتمد الإتاحة على الجدولة وقت التواصل معنا. يُرجى التواصل عبر واتساب أو الهاتف وسنؤكد أقرب موعد متاح. |
| Is plumbing repair work covered by a warranty? | Warranty terms are subject to company policy — please confirm directly with our team before the visit. | هل يشمل إصلاح السباكة ضمانًا؟ | تخضع شروط الضمان لسياسة الشركة — يُرجى التأكيد المباشر مع فريقنا قبل الزيارة. |
| What causes low water pressure? | Low pressure can come from several sources — a partially blocked fixture, a valve issue, or a supply-line problem, among others. A technician needs to inspect the specific fixture to identify the actual cause. | ما الذي يسبب ضعف ضغط المياه؟ | يمكن أن ينتج ضعف الضغط عن عدة أسباب... يحتاج الفني لمعاينة التجهيز تحديدًا لتحديد السبب الفعلي. |
| How much does a plumbing visit cost? | Pricing depends on the fault and the work required. This is subject to company policy — please contact us directly for an accurate quote for your specific issue. | كم تكلفة زيارة السباكة؟ | تعتمد التكلفة على العطل والعمل المطلوب. يخضع ذلك لسياسة الشركة — يُرجى التواصل معنا مباشرة للحصول على عرض سعر دقيق. |

### → `SEO_AI.md`

| Field | English | Arabic |
|---|---|---|
| SEO Title | Plumbing Services in the UAE \| AFAQ AL HAYAT | خدمات السباكة في الإمارات \| آفاق الحياة |
| Meta Description | Professional plumbing repair and maintenance across the UAE from AFAQ AL HAYAT — leak repair, fixture maintenance, and drain checks for homes and businesses. | خدمات إصلاح وصيانة السباكة الاحترافية في جميع أنحاء الإمارات من آفاق الحياة — إصلاح التسربات وصيانة التجهيزات وفحص الصرف للمنازل والمنشآت. |
| Keywords (illustrative/unresearched) | Plumbing UAE; Plumber Dubai; Leak Repair; Pipe Repair UAE; Bathroom Plumbing | سباكة الإمارات؛ سباك دبي؛ إصلاح تسرب؛ إصلاح أنابيب؛ سباكة حمامات |

---

## 4. CTA

Per Owner instruction, applied directly (not left pending as it initially was for AC Maintenance):

- **English:** Book Appointment
- **Arabic:** احجز موعد

Source: the same Owner-approved generic booking CTA pattern already used in `07_WEBSITE/NAVIGATION_ARCHITECTURE.md` and applied to AC Maintenance (`HOMEPAGE_CONTENT_DECISION_APPLIED.md` §1 Decision 3). No service-specific CTA wording is invented — the source record has no per-service CTA field, same gap as AC Maintenance, resolved the same way.

---

## 5. Validation

### Claim safety
- No price, discount, or package figure anywhere in the fields listed in §3 — the cost FAQ explicitly defers to "subject to company policy."
- No warranty/guarantee claim — the warranty FAQ uses the identical standardized hedge already validated for AC Maintenance; Scope — Excluded independently disclaims manufacturer warranty claims.
- No certification/license claim — safety notes describe general professional practice, not credentialed authority.

### No unsupported promises
- Benefits use hedged language ("support for," not "guarantees"); no outcome is promised as certain.
- Process describes steps, not durations.

### No emergency/response-time commitments
- **Specifically checked** (this is the one item `PLUMBING_CONTENT_SOURCE_REVIEW_PLAN.md` §3 flagged as new): FAQ #1, "Can you fix a leak the same day I contact you?" — the answer makes no same-day, fixed-hour, or emergency commitment; it defers entirely to real-time scheduling confirmation ("we'll confirm the earliest available appointment"). Confirmed safe to migrate as-is.
- No "24/7," "urgent," or "emergency service" claim appears anywhere in the record.

### FAQ review
- All 4 questions are genuine, plausible customer questions, not keyword phrases.
- All 4 answers are safe: two properly hedge on price/warranty via company policy, one correctly defers to in-person diagnosis (low pressure), one correctly defers to real-time scheduling (same-day question) rather than promising availability.
- Bilingual pairs express the same facts in both languages.

### SEO review
- Title/meta restate only the transcribed body content — no new claim introduced via SEO fields.
- Keywords carry the standing "illustrative/unresearched" caveat.
- **Scope-tension check (the specific check that caught "AC Repair UAE" for AC Maintenance):** "Pipe Repair UAE" checked against Scope — Excluded's "Major re-piping or full bathroom re-plumbing projects." **No tension found** — Scope — Included explicitly names "Pipe joint and fitting inspection and repair" as in-scope, so this keyword accurately reflects included work rather than overstating it. No keyword requires removal.
- No keyword stuffing — 5 EN / 5 AR keywords, each distinct and topically relevant.

**No blocking finding in this section.**

---

## 6. Approval Checkpoint Before README/Status Changes

This plan stops here. Before any file under `04_SERVICE_KNOWLEDGE/06_PLUMBING/` is actually written:

1. **Owner review of §3's exact content** — confirm the transcribed wording (both languages) is acceptable as-is.
2. **Owner confirmation of the CTA application** (§4) — already directed by the Owner in this instruction; recorded here as applied-by-direction rather than left pending.
3. **Independent review** — per `ENTERPRISE_PUBLICATION_GATE_MODEL.md` §10, the file-write step should not be self-approved by whoever performs it; a separate check against this plan's §5 validation should confirm nothing drifted between plan and execution (the same step already performed for AC Maintenance via `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md`).
4. **Only after 1–3 clear:** the actual file write (`CONTENT_EN.md`, `CONTENT_AR.md`, `FAQ.md`, `SEO_AI.md`) may proceed, followed by the `README.md` status banner update and the `CHANGELOG.md` audit entry — as a separate, explicitly authorized execution step, not automatically triggered by approval of this plan.

**Publication status for Plumbing remains unchanged by this document.** `README.md` still reads its current pre-sync status until step 4 above is separately authorized and performed.

---

## What This Document Does Not Do

- Does not copy, create, or edit any file in `04_SERVICE_KNOWLEDGE/06_PLUMBING/` or anywhere else.
- Does not change Plumbing's (or any service's) publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.
- Does not extend to Electrical Maintenance, Painting, or Handyman — those remain governed by `MAINTENANCE_CONTENT_SYNC_PLAN.md`, pending their own review/execution once this one is validated.

---

## Related Documents

- `00_GOVERNANCE/PLUMBING_CONTENT_SOURCE_REVIEW_PLAN.md` — the source verification this plan applies
- `00_GOVERNANCE/AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`, `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md` — process precedent
- `00_GOVERNANCE/MAINTENANCE_CONTENT_SYNC_PLAN.md`
- `04_SERVICE_KNOWLEDGE/06_PLUMBING/`
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` — external repository, read-only source
