# Electrical Maintenance Content Sync Execution Plan

## 1. Document Information

- **Owner:** Business Owner
- **Version:** 1.0
- **Status:** Draft — planning only; no file has been copied, created, or edited; no publication status changed
- **Scope:** Electrical Maintenance (`SVC-ELECTRICAL-MAINTENANCE`) only. No file was copied, no service file was edited, no `README.md` or publication status was changed, no website file was modified, nothing staged or committed.
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Authorizing sources:** `00_GOVERNANCE/ELECTRICAL_CONTENT_SOURCE_REVIEW_PLAN.md` (source verification, "Needs decision" recommendation) and `00_GOVERNANCE/ELECTRICAL_SEO_DECISION_APPLIED.md` (Owner decision resolving that finding)

---

## 2. Source Mapping

- **Primary source file:** `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` (read-only reference; not modified)
- **Record name:** `slug: "electrical-maintenance"` (`id: SVC-ELECTRICAL-MAINTENANCE`)
- **Cross-reference:** `docs/SERVICE_COMPLETION_MATRIX.md` §1 (Maintenance table, Electrical Maintenance row — marked `COMPLETE`)
- **Available fields:** `name.{en,ar}`, `status`, `content.{en,ar}.{heroTagline, overview, commonProblems[], scope.{included[],excluded[]}, process[], benefits[], safety[]}`, `faqs[]` (4 pairs), `seoTitle.{en,ar}`, `metaDescription.{en,ar}`, `keywords.{en,ar}[]`, `sourceDocs[]`
- **Provenance discrepancy carried forward (same as AC Maintenance and Plumbing):** `sourceDocs` claims `["07_ELECTRICAL_MAINTENANCE/CONTENT_EN.md", "07_ELECTRICAL_MAINTENANCE/README.md"]` as origin — those files are confirmed-empty templates in this repository (`ELECTRICAL_CONTENT_SOURCE_REVIEW_PLAN.md` §1). Not relied upon; the true source is the JSON record itself.

---

## 3. Migration Mapping

Source values (as they exist today), mapped to target sections — presented here for review; **not yet written to any file**.

| Source field | Target | English (source) | Arabic (source) |
|---|---|---|---|
| `name` | Service Title (`CONTENT_EN.md`/`CONTENT_AR.md`) | Electrical Maintenance | الصيانة الكهربائية |
| `heroTagline` | Short Description (`CONTENT_EN.md`/`CONTENT_AR.md`) | Safe, reliable electrical repairs for your home or business, wherever you are in the UAE. | إصلاحات كهربائية آمنة وموثوقة لمنزلك أو منشأتك، أينما كنت في الإمارات. |
| `overview` | Overview (`CONTENT_EN.md`/`CONTENT_AR.md`) | Our electrical maintenance service addresses everyday household and commercial electrical faults — from faulty switches and sockets to lighting and distribution-panel issues — across UAE properties. | تعالج خدمة الصيانة الكهربائية لدينا الأعطال الكهربائية اليومية في المنازل والمنشآت التجارية — من المفاتيح والمقابس المعطلة إلى مشاكل الإضاءة ولوحات التوزيع — في جميع أنحاء الإمارات. |
| `commonProblems[]` (6) | Common Problems section | Sockets/switches not working or loose; flickering/dimming/non-working lights; breaker tripping repeatedly; buzzing/unusual sounds from panel or fixture; partial power loss to a room; old or damaged wiring visible | مقابس أو مفاتيح لا تعمل؛ إضاءة تومض أو تخفت؛ قاطع يفصل بشكل متكرر؛ أصوات طنين؛ فقدان جزئي للتيار؛ أسلاك قديمة أو تالفة ظاهرة |
| `scope.included[]` (6) | Scope — Included | Switch/socket inspection and repair; lighting fixture troubleshooting and repair; distribution-panel and breaker **inspection**; fault-finding for partial power loss; replacement of damaged fittings/accessories; general electrical safety inspection | فحص وإصلاح المفاتيح والمقابس؛ تشخيص وإصلاح تجهيزات الإضاءة؛ فحص لوحة التوزيع والقواطع؛ تشخيص أعطال فقدان التيار الجزئي؛ استبدال التجهيزات التالفة؛ فحص عام للسلامة الكهربائية |
| `scope.excluded[]` (4) | Scope — Excluded | Full property rewiring/new circuit installation; utility-provider meter/main-supply work; manufacturer warranty claims on appliances; any work beyond what can be safely assessed **without specialized regulatory sign-off** | إعادة تمديد كهربائي كامل أو دوائر جديدة؛ أعمال عداد مزود الخدمة؛ مطالبات ضمان الشركة المصنعة؛ أي عمل يتجاوز ما يمكن تقييمه بأمان دون موافقة تنظيمية متخصصة |
| `process[]` (6 steps) | Process Summary | Initial WhatsApp/phone consultation; on-site inspection; diagnosis explained before work begins; agreed repair or maintenance work carried out; circuit/fixture tested; final walkthrough with safety recommendations | استشارة أولية؛ معاينة ميدانية؛ مشاركة التشخيص قبل البدء؛ تنفيذ الأعمال المتفق عليها؛ اختبار الدائرة/التجهيز؛ جولة ختامية مع توصيات السلامة |
| `benefits[]` (5) | Why Choose Us | Faster, more accurate diagnosis; reduced risk from unresolved wiring issues over time; support for minor repairs and routine upkeep; scheduling across all 7 emirates; clear explanation before work starts | تشخيص أسرع وأدق؛ تقليل المخاطر؛ دعم الإصلاحات البسيطة والصيانة الروتينية؛ الجدولة في 7 إمارات؛ شرح واضح قبل البدء |
| `safety[]` (3) | General Safety Notes | Power isolated before inspection/repair; technicians follow standard electrical safety practice; faults requiring specialized regulatory sign-off flagged rather than attempted | فصل التيار قبل الفحص/الإصلاح؛ اتباع ممارسات السلامة الكهربائية المعتادة؛ إبلاغ العميل بالأعطال التي تتطلب موافقة تنظيمية متخصصة بدل التعامل معها |
| `faqs[]` (4 pairs) | `FAQ.md` | Breaker-tripping cause; warranty; DIY-safety-advice; cost — see §6/§7 below for validation | Same 4, Arabic |
| `seoTitle` | `SEO_AI.md` | Electrical Maintenance Services in the UAE \| AFAQ AL HAYAT | خدمات الصيانة الكهربائية في الإمارات \| آفاق الحياة |
| `metaDescription` | `SEO_AI.md` | Professional electrical maintenance across the UAE from AFAQ AL HAYAT — switch, socket, lighting, and distribution-panel troubleshooting for homes and businesses. | صيانة كهربائية احترافية في جميع أنحاء الإمارات من آفاق الحياة — تشخيص المفاتيح والمقابس والإضاءة ولوحات التوزيع للمنازل والمنشآت. |
| `keywords[]` | `SEO_AI.md` | See §4 — one keyword excluded per Owner decision | See §4 |

---

## 4. Apply Owner SEO Decision

Per `00_GOVERNANCE/ELECTRICAL_SEO_DECISION_APPLIED.md`:

- **Explicitly excluded:** "Distribution Panel Repair" — **not** included in the migrated English keyword list.
- **Reason:** Scope — Included supports only "Distribution-panel and breaker inspection," not repair; Scope — Excluded separately disclaims work requiring specialized regulatory sign-off, a category panel-level repair plausibly falls into. The keyword's implied repair capability is not supported by the approved scope.
- **Keywords to migrate (English, 4 of the original 5):** Electrical Maintenance UAE; Electrician Dubai; Electrical Repair; Home Electrical Service.
- **Keywords to migrate (Arabic, unchanged, 5 of 5 — no Arabic equivalent of "لوحة توزيع" + "إصلاح" existed as a standalone term to remove):** صيانة كهربائية الإمارات؛ كهربائي دبي؛ إصلاح كهرباء؛ إصلاح لوحة توزيع؛ كهرباء منزلية.

**Note carried forward, not newly decided here:** the Arabic keyword list still contains "إصلاح لوحة توزيع" (the direct Arabic equivalent of "Distribution Panel Repair"), which was not explicitly named in the Owner's removal instruction (English only). This asymmetry is flagged for Owner confirmation before execution — per `PROJECT_MANIFEST.md`'s bilingual-equality principle, if the English keyword is unsupported by scope, its Arabic equivalent likely is too, and removing only one language would reintroduce the same tension in Arabic. **This plan does not resolve it — surfaced for explicit Owner instruction before the actual write.**

- **All other SEO fields unchanged:** SEO title, meta description, and the remaining 4 EN / 4-or-5 AR keywords (pending the note above) migrate exactly as sourced.

---

## 5. CTA

Per the already-established, Owner-approved generic pattern (same as AC Maintenance and Plumbing):

- **English:** Book Appointment
- **Arabic:** احجز موعد

No service-specific CTA wording is invented — the source record has no per-service CTA field, the same gap already resolved identically for the two prior pilots.

---

## 6. Claim Safety Validation

| Category | Check result |
|---|---|
| Pricing claims | None. Cost FAQ hedged: "Pricing depends on the fault and the work required... subject to company policy." |
| Warranty promises | None. Warranty FAQ uses the standardized hedge; Scope — Excluded independently disclaims manufacturer warranty claims. |
| Certification claims | None found anywhere in overview, scope, process, benefits, safety, or FAQ. |
| Licensing claims | None found. No "licensed electrician" or equivalent claim anywhere in the record. |
| Response-time guarantees | None. No FAQ in this batch addresses same-day/urgency (unlike Plumbing); no fixed turnaround stated anywhere. |
| Emergency promises | None. No "24/7," "urgent," or "emergency service" claim anywhere. |
| **Unsupported electrical authority claims** | **None — specifically checked given the trade.** The content is self-limiting on this point: both Scope — Excluded and the safety notes explicitly defer any work "requiring specialized regulatory sign-off" to the customer rather than implying the company holds that authority. This is a stronger safety boundary than a generic disclaimer. |

**No blocking finding.**

---

## 7. Scope Validation

- **Electrical inspection wording:** confirmed present and accurate — "Switch and socket inspection and repair," "General electrical safety inspection" both correctly use "inspection" alongside repair only where the source scope supports repair (switches, sockets, lighting fixtures, fittings).
- **Breaker/panel inspection wording:** confirmed the source scope says "Distribution-panel and breaker **inspection**" only — this plan's migration mapping (§3) preserves that exact word choice and does **not** upgrade it to "repair" anywhere in `CONTENT_EN.md`/`CONTENT_AR.md`'s Scope — Included. This is the same distinction that justified excluding the "Distribution Panel Repair" keyword (§4) — the body content and the keyword list are being kept consistent with each other.
- **Excluded specialized regulatory work:** confirmed present and will migrate verbatim — "any work beyond what can be safely assessed without specialized regulatory sign-off."
- **Avoid expanding inspection into repair claims:** confirmed as a rule for execution — when this plan is executed, "inspection" must not be silently reworded to "repair" anywhere in the panel/breaker context, consistent with §4's keyword exclusion and this section's check.

---

## 8. Target Files

Intended future migration files only — **none written by this plan**:

- `CONTENT_EN.md`
- `CONTENT_AR.md`
- `FAQ.md`
- `SEO_AI.md`
- `CHANGELOG.md` (one appended audit entry, per the established pattern)

**Held:** `README.md` — not modified by this plan or by its eventual execution until the approval gates in §9 clear.

---

## 9. Approval Gates

Before actual migration is executed:

1. **Content verification** — Owner review of §3's exact mapped content and §4's keyword-exclusion asymmetry note (Arabic "إصلاح لوحة توزيع").
2. **Independent review** — a separate check against this plan's §6–7 validations, mirroring `AC_MAINTENANCE_CONTENT_REVIEW_REPORT.md` and `PLUMBING_CONTENT_REVIEW_REPORT.md`, confirming nothing drifted between plan and execution.
3. **Owner approval** — explicit sign-off to proceed, following the same decision pattern as `PLUMBING_CONTENT_APPROVAL_DECISION.md`/`_APPLIED.md`.
4. **Status synchronization** — only after 1–3 clear does `README.md`'s status banner and this package's publication approval status change, as a separate, explicitly authorized step — not automatically triggered by this plan.

**Publication status for Electrical Maintenance remains unchanged by this document.**

---

## What This Document Does Not Do

- Does not copy, create, or edit any file in `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/`.
- Does not modify `README.md` or any publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/ELECTRICAL_CONTENT_SOURCE_REVIEW_PLAN.md`
- `00_GOVERNANCE/ELECTRICAL_SEO_DECISION_APPLIED.md`
- `00_GOVERNANCE/AC_MAINTENANCE_SYNC_EXECUTION_PLAN.md`, `PLUMBING_CONTENT_SYNC_EXECUTION_PLAN.md` — process/format precedent
- `04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/`
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` — external repository, read-only source
