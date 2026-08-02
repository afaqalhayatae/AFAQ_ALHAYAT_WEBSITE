# Service Master Matrix

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — index only; does not itself approve any service for publication, booking, or field execution. Each service's own `README.md`/`CONTENT_EN.md` Evidence Gate remains the governing status for that package.
- **Version:** 1.0
- **Prepared:** 2026-08-02
- **Source of truth:** `afaqalhayatae-app/src/data/SERVICE_DATABASE.json` (live field-by-field read, this session) and `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`. Where the two agree, the JSON is cited as primary since it is what the live site actually reads.
- **Relationship to existing documents:** `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md` already exists as a service index but lists only the original 12 services with "Not started" SEO/content status (dated 2026-07-29, pre-dates `DECISION_LOG` #38/#39). This document is not a duplicate — it is the current, full 27-service count with columns (FAQ, City page, Website readiness) the older index does not carry. Reconciling or retiring the older index is an Owner decision, not performed here.
- **Scope:** Governance document only. No service file, `README.md`, `SERVICE_CATALOG.md`, or website file was modified.

---

## Category Mapping

Per this directive's requested three-group structure (Maintenance / Cleaning / Pest Control), mapped explicitly against the catalog's own three category labels so nothing is silently reclassified:

- **Maintenance** = catalog's "General Maintenance" (16) + "Drainage & Water Protection" (3) = **19 services**
- **Cleaning** = catalog's "Cleaning & Pest Control" minus Pest Control itself = **7 services**
- **Pest Control** = the single Pest Control service = **1 service**

**Total: 27 services** (confirmed by direct count of `SVC-*` records in `SERVICE_DATABASE.json` this session — matches `SERVICE_CATALOG.md`'s own stated count).

---

## Maintenance (19 services)

| Service EN | Service AR | Service ID | Content status | SEO status | FAQ status | Image status | City page readiness | Website readiness |
|---|---|---|---|---|---|---|---|---|
| AC Maintenance | صيانة التكييف | `SVC-AC-MAINTENANCE` | Complete | Complete | 4 pairs | 1 real image, live | Not started | Live, indexed |
| Plumbing | السباكة | `SVC-PLUMBING` | Complete | Complete | 4 pairs | 1 real image, live | Not started | Live, indexed |
| Electrical Maintenance | الصيانة الكهربائية | `SVC-ELECTRICAL-MAINTENANCE` | Complete | Complete | 4 pairs | 1 real image, live | Not started | Live, indexed |
| Painting | الدهانات | `SVC-PAINTING` | Complete | Complete | 4 pairs | 1 real image, live | Not started | Live, indexed |
| Handyman Services | خدمات الصيانة العامة (هاندي مان) | `SVC-HANDYMAN` | Complete | Complete | 3 pairs | **None — never had one** | Not started | Content complete, **excluded from grids/related-links** (no-placeholder rule) |
| CCTV Installation | تركيب كاميرات المراقبة | `SVC-CCTV-INSTALLATION` | **Not started** | Complete (metadata only) | 0 | **None — requested asset never located** | Not started | `noindex`, not live |
| Smart Home Installation | تركيب أنظمة المنزل الذكي | `SVC-SMART-HOME-INSTALLATION` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Swimming Pool Maintenance | صيانة حمامات السباحة | `SVC-SWIMMING-POOL-MAINTENANCE` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Kitchen Installation | تركيب المطابخ | `SVC-KITCHEN-INSTALLATION` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Interior Decoration | الديكور الداخلي | `SVC-INTERIOR-DECORATION` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Interlock Installation | تركيب الإنترلوك | `SVC-INTERLOCK-INSTALLATION` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Lighting Maintenance | صيانة الإضاءة | `SVC-LIGHTING-MAINTENANCE` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Wood Alternative Installation | تركيب بدائل الخشب | `SVC-WOOD-ALTERNATIVE-INSTALLATION` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Wallpaper Installation | تركيب ورق الجدران | `SVC-WALLPAPER-INSTALLATION` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Thermal Insulation | العزل الحراري | `SVC-THERMAL-INSULATION` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Rooftop Space Utilization | استغلال مساحات الأسطح | `SVC-ROOFTOP-SPACE-UTILIZATION` | Not started | Complete (metadata only) | 0 | 1 real image, staged | Not started | `noindex`, not live (content pending) |
| Drain Unblocking | تسليك المجاري | `SVC-DRAIN-UNBLOCKING` | Complete | Complete | 3 pairs | 1 real image, live | Not started | Live, indexed |
| Waterproofing | العزل المائي | `SVC-WATERPROOFING` | Complete | Complete | 3 pairs | **Rejected (AI-render typo) — none live** | Not started | Content complete, **excluded from grids/related-links** (no-placeholder rule) |
| Water Leak Detection | كشف تسربات المياه | `SVC-WATER-LEAK-DETECTION` | Complete | Complete | 3 pairs | 1 real image, live | Not started | Live, indexed |

## Cleaning (7 services)

| Service EN | Service AR | Service ID | Content status | SEO status | FAQ status | Image status | City page readiness | Website readiness |
|---|---|---|---|---|---|---|---|---|
| General Cleaning | التنظيف العام | `SVC-GENERAL-CLEANING` | Complete | Complete | 3 pairs | 1 real image, live | Not started | Live, indexed |
| Deep Cleaning | التنظيف العميق | `SVC-DEEP-CLEANING` | Complete | Complete | 3 pairs | 1 real image, live | Not started | Live, indexed |
| Water Tank Cleaning | تنظيف خزانات المياه | `SVC-WATER-TANK-CLEANING` | Complete | Complete | 3 pairs | 1 real image, live | Not started | Live, indexed |
| Villa Cleaning | تنظيف الفلل | `SVC-VILLA-CLEANING` | Complete | Complete | 2 pairs | 1 real image, live | Not started | Live, indexed |
| Office Cleaning | تنظيف المكاتب | `SVC-OFFICE-CLEANING` | Complete | Complete | 2 pairs | 1 real image, live | Not started | Live, indexed |
| Post-Construction Cleaning | تنظيف ما بعد البناء | `SVC-POST-CONSTRUCTION-CLEANING` | Complete | Complete | 2 pairs | 1 real image, live | Not started | Live, indexed |
| Carpet & Upholstery Cleaning | تنظيف السجاد والمفروشات | `SVC-CARPET-UPHOLSTERY-CLEANING` | Complete | Complete | 3 pairs | 1 real image, live | Not started | Live, indexed |

## Pest Control (1 service)

| Service EN | Service AR | Service ID | Content status | SEO status | FAQ status | Image status | City page readiness | Website readiness |
|---|---|---|---|---|---|---|---|---|
| Pest Control | مكافحة الحشرات | `SVC-PEST-CONTROL` | Complete | Complete | 10 pairs | 2 real images, live | Not started | Live, indexed |

**Note on Pest Control's granularity:** the source content and website copy address the service generally (with an internal `commonProblems` list mentioning cockroaches, ants, bed bugs, termites, rodents, mosquitoes, and flies) rather than as separate pest-type sub-services. There is currently **no separate catalog ID per pest type** — "Cockroach Control," "Bed Bug Control," etc. do not exist as distinct services today. Phase 3 (`LOCAL_SEO_MASTER_PLAN.md`) treats pest-type + city as a **future page-architecture pattern under the single Pest Control service**, not as new catalog entries — creating new pest-type service IDs would be a separate, explicit Owner decision, not made by this document.

---

## Column Definitions (for consistent future use)

- **Content status:** "Complete" = `content.en/ar.overview` and all standard fields populated in `SERVICE_DATABASE.json`. "Not started" = `content` field is `null`.
- **SEO status:** "Complete" = `seoTitle`, `metaDescription`, and `keywords` populated for both languages. All 27 services currently have this — even the 11 content-pending Maintenance-expansion services, which is why their row is marked "Complete (metadata only)" to avoid implying page content also exists.
- **FAQ status:** count of `faqs[]` entries in the source record. 0 = no FAQ authored yet.
- **Image status:** as recorded in `status.images` per record, verified this session; not inferred from category defaults.
- **City page readiness:** uniformly "Not started" for all 27 — no city- or community-level page exists for any service today. Only Dubai has a live **emirate**-level page; city/community tier is a distinct, later tier per `03_MARKET/SERVICE_AREAS.md`, not yet begun for any service.
- **Website readiness:** "Live, indexed" = in `APPROVED_SERVICE_CONTENT_SLUGS` and included in grids/related-links. "Excluded from grids" = content approved but held back solely by the no-placeholder image rule. "`noindex`, not live" = per `DECISION_LOG` #39, structural-only entries stay `noindex` until a future content phase.

---

## Confirmed Service Count

**27 services total** — 19 Maintenance, 7 Cleaning, 1 Pest Control. This is a direct count against the live source database, not an estimate. It matches `SERVICE_CATALOG.md`'s own stated total but **exceeds** the 12-service count still recorded in `00_GOVERNANCE/CURRENT_PROJECT_STATUS.md` (v1.1, 2026-07-24) and `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md` (2026-07-29) — both pre-date `DECISION_LOG` #38/#39 and are flagged, not corrected, by this document (see `PROJECT_EXECUTION_STATUS_REPORT.md` §3).

**Content/SEO-complete and live: 16 of 27** (all of Cleaning, Pest Control, and 5 of Maintenance's original 8, plus Drain Unblocking/Water Leak Detection but excluding Waterproofing/Handyman's image gap). **Structural-only, no content: 11 of 27** (all in Maintenance, all from the Service Expansion Phase).

---

## What This Document Does Not Do

- Does not modify `SERVICE_CATALOG.md`, `SERVICE_MASTER_DATABASE.md`, any `04_SERVICE_KNOWLEDGE/` service file, or any website file.
- Does not create any new service ID, including any pest-type sub-service.
- Does not approve, publish, or change the status of any service.
- Does not stage, commit, or push anything.

---

## Related Documents

- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `SERVICE_MASTER_DATABASE.md`, `SERVICE_MATRIX.md`
- `00_GOVERNANCE/PROJECT_EXECUTION_STATUS_REPORT.md` — Phase 1 audit this matrix supports
- `00_GOVERNANCE/DECISION_LOG.md` — decisions #38, #39 (the 15 services this matrix adds beyond the original 12)
- `afaqalhayatae-app/src/data/SERVICE_DATABASE.json`, `docs/SERVICE_COMPLETION_MATRIX.md`, `docs/VISUAL_ASSET_MASTER_PLAN.md` — external repository, read-only source
