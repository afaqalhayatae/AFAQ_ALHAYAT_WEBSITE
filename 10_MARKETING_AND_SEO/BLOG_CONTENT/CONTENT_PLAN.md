# AFAQ AL HAYAT — 30-Article SEO Content Plan

## Document Information

- **Owner:** Business Owner / Marketing
- **Status:** Draft — plan and scaffolding only; no article is published or wired into the live site by this document
- **Prepared:** 2026-08-05
- **Scope:** Content and SEO only. No app code, routing, or design was touched to produce this plan (per explicit instruction). Nothing here goes live until reviewed and wired into `afaqalhayatae-app/src/lib/catalog/blog.ts`, the same "empty registry until approved" pattern the live site already uses.

## Relationship to existing content work (read this first)

Before drafting anything, this plan was checked against work that already exists in this repo, to avoid duplicating it:

- **21 articles are already live** on the site today (verified in `CONTENT_FACTORY_LIVE_BLOG_RECONCILIATION.md`), covering AC Maintenance, Electrical, Painting, general Pest Control, Plumbing, Handyman, Deep/General Cleaning, and Water Leak Detection.
- **56 more articles are already drafted but unpublished** across `10_MARKETING_AND_SEO/BLOG/` (33) and `10_MARKETING_AND_SEO/CONTENT_FACTORY/` (23), already classified GAP / OVERLAP / PARTIAL OVERLAP against the live set.
- This plan's 30 topics are deliberately weighted toward the **confirmed real gaps** that reconciliation already surfaced — services and pest sub-types with **zero live coverage at all** (Termite Control, Rodent Control, Villa/Office/Post-Construction/Carpet Cleaning, Water Tank Cleaning, Drain Unblocking, Waterproofing) — plus local-SEO and trust pillars nothing else covers, rather than re-covering ground the 21 live articles already hold.
- Where a topic below is adjacent to an existing draft in `BLOG/` or `CONTENT_FACTORY/`, that draft is noted as reference material, not duplicated verbatim — this plan's articles are written fresh, longer (1500+ words), bilingual, and structured to the full SEO spec below, which the existing shorter English-only drafts don't carry.

## Global rules applied to every article (Claim-Safety, inherited from `CONTENT_STRATEGY.md`)

- No invented prices, discounts, guarantees, warranty terms, licenses, certifications, reviews, or statistics.
- No unapproved location/coverage claims — only the 7 approved emirates (`03_MARKET/SERVICE_AREAS.md`) and, where named, only communities in that file's Priority Community Registry.
- No unsafe DIY technical instructions for hazardous tasks (live electrical work, pesticide mixing/application, gas/refrigerant handling) — these are framed as "what a professional does," never as home-owner instructions.
- Cost content discusses the *factors* that affect price, never a specific AED figure — matching the same hedged language the live FAQ already uses ("contact us for an accurate quote").
- Pest sub-type articles (cockroach, ant, termite, bed bug, rodent) are content topics under the existing `SVC-PEST-CONTROL` catalog service, not implied as separate services — consistent with the Option A decision already recorded in `BLOG_MASTER_PLAN.md` §5.
- Every article links to a real, live URL only — verified against the actual app routes, including the service×city pest-control pages that now exist live (`/services/pest-control/{subService}/{city}`).

## Company facts used (all approved, none invented)

- Brand: AFAQ AL HAYAT / آفاق الحياة — maintenance, cleaning, and pest control across all 7 UAE emirates.
- Phone: `+971 58 543 1766`. WhatsApp: `https://wa.me/message/JMZVJDFDQL3VD1`. Domain: `afaqalhayatae.com`.
- Approved catalog services referenced: AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman Services, General Cleaning, Deep Cleaning, Water Tank Cleaning, Pest Control, Drain Unblocking, Waterproofing, Water Leak Detection.
- Bilingual (Arabic first, English second), 24/7 availability, all 7 emirates — all already-approved facts used sitewide.

---

## Article Index

| # | Category | Arabic Title | Primary Keyword (AR) | Status |
|---|---|---|---|---|
| 01 | Pest Control | مكافحة الصراصير في دبي: الدليل الشامل | مكافحة الصراصير في دبي | Full article written |
| 02 | Pest Control | علامات بق الفراش وكيفية التخلص منه نهائيًا | علاج بق الفراش | Full article written |
| 03 | Pest Control | مكافحة النمل في المنزل: الأسباب والحلول الاحترافية | مكافحة النمل | Full article written |
| 04 | Pest Control | النمل الأبيض: أخطر آفة تهدد منزلك في الإمارات | مكافحة النمل الأبيض | Full article written |
| 05 | Pest Control | دليلك الشامل للتخلص من الحشرات المنزلية في الإمارات | مكافحة الحشرات المنزلية | Full article written |
| 06 | Pest Control | أفضل طرق مكافحة الحشرات الاحترافية | أفضل طرق مكافحة الحشرات | Full article written |
| 07 | Cleaning | تنظيف المنازل في الإمارات: دليلك لمنزل نظيف طوال العام | تنظيف المنازل | Full article written |
| 08 | Cleaning | تنظيف الفلل الفاخرة: خدمة احترافية لكل تفاصيل منزلك | تنظيف الفلل | Full article written |
| 09 | Cleaning | التنظيف العميق: متى تحتاجه وماذا يشمل؟ | التنظيف العميق | Full article written |
| 10 | Cleaning | تنظيف ما بعد البناء والتشطيب: خطوات احترافية | تنظيف ما بعد البناء | Full article written |
| 11 | Cleaning | تنظيف السجاد والمفروشات: حماية استثمارك في الأثاث | تنظيف السجاد | Full article written |
| 12 | Cleaning | تنظيف خزانات المياه: لماذا هو ضروري لصحة عائلتك؟ | تنظيف خزانات المياه | Full article written |
| 13 | Cleaning | كيف تختار أفضل شركة تنظيف في دبي والإمارات؟ | شركات التنظيف في دبي | Full article written |
| 14 | Maintenance | صيانة المكيفات في الإمارات: دليلك لصيف بارد بلا أعطال | صيانة المكيفات | Full article written |
| 15 | Maintenance | كشف تسربات المياه: تقنيات حديثة لحماية منزلك | كشف تسربات المياه | Full article written |
| 16 | Maintenance | أعطال السباكة الشائعة وكيفية التعامل معها باحترافية | أعطال السباكة | Full article written |
| 17 | Maintenance | الأعطال الكهربائية في المنزل: متى تستدعي فنيًا فورًا؟ | صيانة كهربائية | Full article written |
| 18 | Maintenance | دليل صيانة المنزل الشامل: كل ما تحتاج معرفته | خدمات الصيانة الشاملة | Full article written |
| 19 | Maintenance | تسليك المجاري والصرف الصحي: حلول احترافية | تسليك المجاري | Full article written |
| 20 | Maintenance | العزل المائي: حماية منزلك من تسربات المياه والرطوبة | العزل المائي | Full article written |
| 21 | Local SEO | خدمات منزلية احترافية في دبي: كل ما تحتاجه في مكان واحد | خدمات منزلية في دبي | Full article written |
| 22 | Local SEO | خدمات الصيانة والتنظيف في أبوظبي: دليلك الكامل | خدمات منزلية في أبوظبي | Full article written |
| 23 | Local SEO | أفضل خدمات منزلية في الشارقة | خدمات منزلية في الشارقة | Full article written |
| 24 | Local SEO | خدمات منزلية في جميع إمارات الدولة السبع | خدمات منزلية في الإمارات | Full article written |
| 25 | Trust | كيف تختار شركة صيانة وتنظيف موثوقة في الإمارات؟ | كيف تختار شركة صيانة | Full article written |
| 26 | Trust | ما الذي يحدد تكلفة خدمات الصيانة والتنظيف في الإمارات؟ | تكلفة خدمات الصيانة | Full article written |
| 27 | Trust | 10 نصائح للحفاظ على منزلك في أفضل حالة على مدار العام | نصائح صيانة المنزل | Full article written |
| 28 | Pest Control | مكافحة القوارض: كيف تحمي منزلك من الفئران والجرذان؟ | مكافحة القوارض | Full article written |
| 29 | Cleaning | تنظيف المكاتب والمنشآت التجارية | تنظيف المكاتب | Full article written |
| 30 | Maintenance | الفرق بين الصيانة الدورية والصيانة الطارئة | الصيانة الدورية والطارئة | Full article written |

**Status (updated 2026-08-06): all 30 articles have complete bilingual `ARTICLE.md` prose.** Depth varies by design, not by finish state: the 8 single-topic articles drafted first (01, 02, 04, 08, 12, 18, 21, 25) and the deep-dive service/pest articles added after (03, 06, 09-11, 14-17, 19-20, 26-30) run 1200-2700+ combined words — the standalone pages meant to rank for their own commercial keyword. The pillar/index articles (05, 07, 18 doubles as both, 21-24) are intentionally more concise (roughly 500-900 combined words) — they're navigational hubs linking out to the deeper single-topic articles, not meant to duplicate that depth themselves, the same pattern major sites use for category/hub pages. If a specific article needs more depth for a competitive keyword, expanding it further is a straightforward next pass using the same template.

See each `ARTICLE_NN/` folder for the complete SEO package. Full field definitions and shared conventions:

- **Search Intent**: Informational, Commercial, or Local — per Google's standard intent categories, drives the H1/structure choice.
- **FAQ Schema Questions**: written to map directly onto `FAQPage` JSON-LD, same pattern the live site's `ServiceFaqSection` component already emits.
- **CTA**: every article ends with a WhatsApp + phone CTA and a link to the relevant `/book` flow (pre-filled with `?service=` where the article maps to one real catalog service).
- **Internal Links**: only to real, live URLs on `afaqalhayatae.com` — verified against the app's actual route structure this session.
- **External Authority References**: category of source only (e.g., "UAE government pest/health advisory," "DEWA energy-efficiency guidance") — no specific URL is asserted unless it is a well-known, stable government/utility domain; never a fabricated or unverified source.
