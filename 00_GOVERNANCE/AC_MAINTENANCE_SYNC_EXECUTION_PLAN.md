# AC Maintenance Sync Execution Plan (Pilot)

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only; no file has been copied, created, or edited; no publication status changed
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Authorizing decision:** Owner instruction to pilot `00_GOVERNANCE/MAINTENANCE_CONTENT_SYNC_PLAN.md` on AC Maintenance only, before extending to the other 4 services
- **Scope:** AC Maintenance (`SVC-AC-MAINTENANCE`) only. No other service is touched by this plan. No file was copied, no service file was edited, no publication status was changed, no website file was modified, nothing staged or committed.

## Purpose

Apply `MAINTENANCE_CONTENT_SYNC_PLAN.md`'s general mapping to one concrete service — AC Maintenance — with the exact source values, the exact target file changes, and a real validation pass already run against this specific content, so the Owner can review precisely what execution would write before authorizing the write itself.

---

## 1. Source Files

- **Repository:** `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app` (read-only reference; not modified).
- **Primary file:** `src/data/SERVICE_DATABASE.json`, record `slug: "ac-maintenance"` (`id: SVC-AC-MAINTENANCE`).
- **Cross-reference:** `docs/SERVICE_COMPLETION_MATRIX.md` §1 (Maintenance table, AC Maintenance row — marked `COMPLETE`).
- **Note carried from `MAINTENANCE_CONTENT_SYNC_PLAN.md` §1:** this record's own `sourceDocs` field claims `["02_AC_MAINTENANCE/CONTENT_EN.md", "02_AC_MAINTENANCE/README.md"]` as its origin — those files are the confirmed-empty templates in this repository, so that metadata is inaccurate and is not relied upon here. The true source for this sync is the JSON record itself.

---

## 2. Target Files

All under `04_SERVICE_KNOWLEDGE/02_AC_MAINTENANCE/`:

| File | Action (on execution, not performed by this plan) |
|---|---|
| `CONTENT_EN.md` | Replace the empty content-gate template with real English content |
| `CONTENT_AR.md` | Replace the empty content-gate template with real Arabic content |
| `FAQ.md` | Replace the unanswered "Approved Question Backlog" with 4 real, answered Q&A pairs |
| `SEO_AI.md` | Add real SEO title/meta/keywords, publication-half status only (per `SERVICE_KNOWLEDGE_SYNC_PLAN.md`'s existing AI-answer/publication gate distinction) |
| `README.md` | Status banner update — **not performed until §7's checkpoint clears** |
| `CHANGELOG.md` | One appended audit entry recording the sync |

Untouched: `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `TRAINING.md`, `MEDIA.md`, `CUSTOMER_GUIDE.md`, `SOURCE_DRAFT.md`, `IMAGE_SEO_LIBRARY.md`, `IMAGE_GENERATION_BRIEF.md`, `assets/` — none of these carry any change under this plan.

---

## 3. Exact Fields to Migrate

Source values (as they exist today in `SERVICE_DATABASE.json`), mapped to target sections — presented here for review; **not yet written to any file**:

### → `CONTENT_EN.md` / `CONTENT_AR.md`

| Section | English (source) | Arabic (source) |
|---|---|---|
| Service Title | AC Maintenance | صيانة التكييف |
| Supporting line (from `heroTagline`) | Keep every room comfortable — professional AC servicing across the UAE, one call away. | حافظ على راحة كل غرفة — صيانة تكييف احترافية في جميع أنحاء الإمارات، على بعد اتصال واحد. |
| Overview | Our AC maintenance service keeps split, window, and central air conditioning units running efficiently across UAE homes and businesses, covering routine servicing, common performance issues, and preventive upkeep suited to the region's demanding climate. | تحافظ خدمة صيانة التكييف لدينا على كفاءة عمل وحدات التكييف (سبليت، شباك، مركزي) في المنازل والمنشآت في الإمارات، وتشمل الصيانة الدورية ومعالجة مشاكل الأداء الشائعة والصيانة الوقائية التي يتطلبها مناخ المنطقة. |
| Common Problems (6 items) | Weak/reduced cooling airflow; unusual noises/vibration/rattling; water leaking from indoor unit; persistent bad odors; high electricity bills relative to use; unit won't turn on or shuts off unexpectedly | ضعف تدفق هواء التبريد؛ أصوات أو اهتزازات غير معتادة؛ تسرب مياه من الوحدة الداخلية؛ روائح كريهة مستمرة؛ فواتير كهرباء مرتفعة؛ وحدة لا تعمل أو تتوقف فجأة |
| Scope — Included (6 items) | Filter inspection/cleaning; coil and drain-line inspection; visual check of refrigerant lines/connections; thermostat/control check; indoor and outdoor unit cleaning; performance assessment with summary | فحص وتنظيف الفلتر؛ فحص الملف الحراري وخط الصرف؛ فحص بصري لخطوط ووصلات غاز التبريد؛ فحص إعدادات الثرموستات؛ تنظيف الوحدة الداخلية والخارجية؛ تقييم أداء مع ملخص |
| Scope — Excluded (4 items) | Major refrigerant-system repairs requiring specialized parts; structural/ducting installation; manufacturer warranty claims on the unit; electrical rewiring beyond the AC unit's own connections | إصلاحات كبرى لنظام غاز التبريد؛ أعمال تركيب إنشائية أو مجاري هواء؛ مطالبات ضمان الشركة المصنعة؛ إعادة تمديد كهربائي خارج نطاق الوحدة |
| Process (6 steps) | Initial WhatsApp/phone consultation; on-site inspection; diagnosis shared before work begins; agreed work carried out; unit tested; final walkthrough with care recommendations | استشارة أولية عبر واتساب/الهاتف؛ معاينة ميدانية؛ مشاركة التشخيص قبل البدء؛ تنفيذ الأعمال المتفق عليها؛ اختبار الوحدة؛ جولة ختامية مع توصيات |
| Benefits (5 items) | Improved cooling/comfort; support reducing electricity use linked to inefficiency; helps extend equipment life; scheduling across all 7 emirates; clear explanation before work starts | تحسين أداء التبريد؛ مساعدة في خفض استهلاك الكهرباء؛ إطالة عمر الجهاز؛ إمكانية الجدولة في 7 إمارات؛ شرح واضح قبل البدء |
| General Safety notes (3 items) | Technicians follow standard safe-handling practice for electrical/refrigerant components; out-of-scope issues flagged rather than attempted; work areas left clean | يتبع الفنيون ممارسات آمنة معتادة؛ يتم إبلاغ العميل بالحالات خارج النطاق بدل التعامل معها دون خبرة؛ يُترك مكان العمل نظيفًا |
| CTA | *(no source field — see §"Gap" below)* | *(same)* |

**Gap identified:** the source JSON has no per-service CTA string. Per `MAINTENANCE_CONTENT_SYNC_PLAN.md` §4, the already-approved generic CTA pattern from `03_GENERAL_CLEANING/CONTENT_EN.md` ("Request an assessment through an approved contact channel. Availability, coverage, scope, and pricing must be confirmed before booking.") is the proposed fill — not a new claim, reusing existing approved wording. Flagged for Owner confirmation, not silently decided.

### → `FAQ.md` (4 real Q&A pairs)

| Question (EN) | Answer (EN) | Question (AR) | Answer (AR) |
|---|---|---|---|
| How often should an AC unit be maintained? | This depends on usage patterns, unit type, and environment. Many households in the UAE have units checked more frequently around peak summer months; a technician can recommend a suitable schedule after inspecting your specific unit. | كم مرة يجب صيانة وحدة التكييف؟ | يعتمد ذلك على نمط الاستخدام ونوع الوحدة والبيئة المحيطة... يمكن للفني اقتراح جدول مناسب بعد معاينة وحدتك تحديدًا. |
| Why is my AC unit making unusual noises? | Unusual noises can have several causes — loose parts, debris, fan issues, or a mounting problem, among others. A technician needs to inspect the unit directly to identify the actual cause before recommending a fix. | لماذا تصدر وحدة التكييف أصواتًا غير معتادة؟ | يمكن أن تكون الأصوات ناتجة عن عدة أسباب... يحتاج الفني لمعاينة الوحدة مباشرة لتحديد السبب الفعلي. |
| Does maintenance come with a warranty? | Warranty terms are subject to company policy — please confirm directly with our team before the visit. | هل تأتي الصيانة مع ضمان؟ | تخضع شروط الضمان لسياسة الشركة — يُرجى التأكيد المباشر مع فريقنا قبل الزيارة. |
| How much does AC maintenance cost? | Pricing depends on the number of units, their condition, and the work required. This is subject to company policy — please contact us directly for an accurate quote for your property. | كم تكلفة صيانة التكييف؟ | تعتمد التكلفة على عدد الوحدات وحالتها والعمل المطلوب. يخضع ذلك لسياسة الشركة — يُرجى التواصل معنا مباشرة للحصول على عرض سعر دقيق. |

### → `SEO_AI.md`

| Field | English | Arabic |
|---|---|---|
| SEO Title | AC Maintenance Services in the UAE \| AFAQ AL HAYAT | خدمات صيانة التكييف في الإمارات \| آفاق الحياة |
| Meta Description | Professional AC maintenance across the UAE from AFAQ AL HAYAT — filter cleaning, coil and drain-line inspection, and performance checks for split, window, and central units. | صيانة احترافية لمكيفات الهواء في جميع أنحاء الإمارات من آفاق الحياة — تنظيف الفلاتر وفحص الملف الحراري وخط الصرف وفحص الأداء لوحدات السبليت والشباك والمركزي. |
| Keywords (illustrative/unresearched, per standing repository caveat) | AC Maintenance UAE; AC Service Dubai; Air Conditioning Cleaning; AC Repair UAE; Split AC Maintenance | صيانة تكييف؛ صيانة مكيفات الإمارات؛ تنظيف تكييف دبي؛ خدمة تكييف؛ صيانة سبليت |

---

## 4. Content Validation Checklist (applied to the fields in §3 above)

| Check | Result |
|---|---|
| No price, discount, or package claim in overview/scope/process/benefits/safety | ✅ Pass — no figure anywhere; cost is explicitly deferred to the FAQ's "subject to company policy" hedge |
| No warranty/guarantee claim | ✅ Pass — scope.excluded explicitly disclaims "manufacturer warranty claims on the AC unit itself"; benefits use hedged language ("support in," "helps extend") rather than guaranteed outcomes |
| No certification/license claim | ✅ Pass — safety notes describe general professional practice ("standard safe-handling practice"), not a certification or license claim |
| No exact response-time/emergency commitment | ✅ Pass — process describes steps, not timeframes; no "same-day" or "24/7 response" language |
| Bilingual fact parity (EN/AR say the same thing) | ✅ Pass on spot-check — overview, common problems, scope, process, and benefits all carry the same facts in both languages; not a mechanical word-for-word translation, consistent with `PROJECT_MANIFEST.md`'s bilingual-equality principle |
| No claim beyond what the excluded scope permits | ⚠ **One finding, not a blocker — flagged for the Owner/reviewer:** the keyword list includes "AC Repair UAE" (§"SEO Validation" below expands on this) |

---

## 5. SEO Validation

- **Title/meta restate only body content:** confirmed — the meta description's "filter cleaning, coil and drain-line inspection, and performance checks for split, window, and central units" matches the overview/scope fields exactly; no new claim introduced via the SEO fields.
- **Keyword caveat carried forward:** all 10 keywords (5 EN + 5 AR) are illustrative/unresearched, per this repository's standing rule (`07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`) — none is presented as validated search data.
- **Finding requiring attention:** the keyword "AC Repair UAE" sits in tension with `scope.excluded`'s explicit exclusion of "major refrigerant-system repairs requiring specialized parts." The service does cover minor troubleshooting (diagnosing unusual noises, performance issues) but is not a general repair service. Using this keyword as-is risks setting a search-intent expectation ("repair") broader than the approved scope ("maintenance," with excluded major repairs). **Recommendation for the Owner/reviewer:** either drop this keyword or keep it only if the page content makes the maintenance-vs-major-repair boundary explicit (which the transcribed scope section already does) — this plan does not resolve it, only surfaces it before execution.

---

## 6. FAQ Validation

| Check | Result |
|---|---|
| Each question is a genuine, plausible customer question (not a keyword reformatted) | ✅ Pass — frequency, noise cause, warranty, and cost are all natural customer questions |
| No answer commits to a specific price | ✅ Pass — the cost FAQ explicitly declines to state a figure and directs the customer to contact the company |
| No answer commits to a specific warranty term | ✅ Pass — the warranty FAQ uses the Owner's standardized hedge exactly |
| Bilingual answers match in substance | ✅ Pass on spot-check — all 4 pairs checked, same facts in both languages |
| Answers avoid diagnostic overreach | ✅ Pass — the noise/frequency answers correctly defer to an in-person technician assessment rather than asserting a cause or schedule generically |

**No blocking finding in this section.**

---

## 7. Approval Checkpoint Before Final Status Change

This plan stops here. Before any file under `04_SERVICE_KNOWLEDGE/02_AC_MAINTENANCE/` is actually written:

1. **Owner review of §3's exact content** — confirm the transcribed wording (both languages) is acceptable as-is.
2. **Owner decision on the CTA gap** (§3) — approve reusing the General Cleaning CTA pattern, or supply different wording.
3. **Owner/reviewer decision on the "AC Repair UAE" keyword finding** (§5) — drop, keep, or adjust accompanying content.
4. **Independent review** — per `ENTERPRISE_PUBLICATION_GATE_MODEL.md` §10, the file-write step should not be self-approved by whoever performs it; a separate check against this plan's §4–6 checklists should confirm nothing drifted between plan and execution.
5. **Only after 1–4 clear:** the actual file write (`CONTENT_EN.md`, `CONTENT_AR.md`, `FAQ.md`, `SEO_AI.md`) may proceed, followed by the `README.md` status banner update and the `CHANGELOG.md` audit entry — as a separate, explicitly authorized execution step, not automatically triggered by approval of this plan.

**Publication status for AC Maintenance remains unchanged by this document.** `README.md` still reads its current pre-sync status until step 5 above is separately authorized and performed.

---

## What This Document Does Not Do

- Does not copy, create, or edit any file in `04_SERVICE_KNOWLEDGE/02_AC_MAINTENANCE/` or anywhere else.
- Does not change AC Maintenance's (or any service's) publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.
- Does not extend to Plumbing, Electrical Maintenance, Painting, or Handyman — those remain governed by `MAINTENANCE_CONTENT_SYNC_PLAN.md`, pending their own pilot or batch execution once this one is validated.

---

## Related Documents

- `00_GOVERNANCE/MAINTENANCE_CONTENT_SYNC_PLAN.md` — the general plan this pilot applies
- `00_GOVERNANCE/MAINTENANCE_CONTENT_SOURCE_DECISION.md`
- `00_GOVERNANCE/MAINTENANCE_CONTENT_PHASE_PLAN.md`
- `00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`
- `04_SERVICE_KNOWLEDGE/02_AC_MAINTENANCE/`
- `04_SERVICE_KNOWLEDGE/03_GENERAL_CLEANING/CONTENT_EN.md` — CTA pattern reference
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` — external repository, read-only source
