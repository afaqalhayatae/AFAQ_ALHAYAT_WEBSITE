# Service Content Production Matrix

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only. No code, content, image, or application change is made by this document.
- **Version:** 1.1 — added the Mandatory SEO Keyword Strategy Framework and Keyword Placement Requirements (§1–2), and reshaped every per-service entry's keyword field into that framework's categories. v1.0 content (page/content/approval/image/blog fields) carried forward unchanged.
- **Prepared:** 2026-07-28
- **Filename note:** requested as `12_SERVICE_CONTENT_PRODUCTION_MATRIX.md`, but `12_SERVICE_EXPANSION_ROADMAP.md` already exists — this remains filed as **`14_...`**, per the note recorded when this document was first created.
- **Depends on:** `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `03_MARKET/SERVICE_AREAS.md`, `05_SEO_IMPLEMENTATION_PLAN.md`, `09_AI_KNOWLEDGE/GEO_STRATEGY.md`, `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`, `07_WEBSITE/IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md`, `07_WEBSITE/IMPLEMENTATION/13_LOCATION_EXPANSION_ROADMAP.md`.

## Note on all keyword content in this document

**No real keyword-volume, ranking, competitor, or search-demand data exists anywhere in this repository, and none is fabricated here or in the update below.** Every keyword shown is an illustrative, structurally-derived candidate — a pattern a UAE home-services keyword would plausibly take — not a validated target. Real keyword research (actual search volume, difficulty, exact phrasing data from a keyword tool) must happen before any of these are locked in as final targets. This caveat applies to every category in §1 and every per-service Keyword Profile below without exception.

---

## 1. Mandatory SEO Keyword Strategy Framework

Every service page and every location page must define keywords across all ten categories below before content production begins. This is a structural requirement, not a suggestion — a page missing a category should be treated as not yet production-ready.

| # | Category | Definition | Illustrative pattern (unresearched) |
|---|---|---|---|
| 1 | **Primary target keyword** | The single main phrase the page is built around — one per page, never split across two competing primary targets on the same page | `[service] [emirate]`, e.g. "AC maintenance Dubai" |
| 2 | **Secondary keywords** | 2–4 closely related phrases the page can also naturally satisfy without diluting the primary | `[service] company`, `[service] service UAE` |
| 3 | **Long-tail keywords** | Longer, more specific phrases with lower competition, usually 4+ words | `best [service] company in [emirate] for villas` |
| 4 | **Search intent keywords** | Phrases that signal *why* someone is searching (informational vs. transactional) | "how to know if I need [service]," "[service] vs [alternative]" |
| 5 | **Local SEO keywords** | `[service] + [emirate/area]` combinations, generated from the same `SERVICE_MATRIX.md`/`SERVICE_AREAS.md` pairing already used for internal links (`04_CONTENT_INTEGRATION_PLAN.md` §5) — never hand-invented per page | `[service] + each of the 7 approved emirates` |
| 6 | **Arabic keywords** | Natural Arabic phrasing of the above — never a mechanical word-for-word translation, per `PROJECT_MANIFEST.md`'s bilingual-equality principle | e.g. "صيانة مكيفات في دبي," phrased as an Arabic speaker would actually search, not transliterated English syntax |
| 7 | **English keywords** | The English equivalents, same non-mechanical-translation rule in reverse | As in the Primary/Secondary rows above |
| 8 | **Commercial keywords** | Phrases signaling price/cost-comparison intent — **these describe what people search for, not what the page may claim.** No price, discount, or cost figure may appear on the page itself without the same `A4` commercial approval any such claim needs elsewhere (`AUTONOMY_AND_APPROVAL_MATRIX.md`) | "[service] cost," "[service] price UAE" — content answers with general guidance ("request a quote"), never a number |
| 9 | **Problem-based keywords** | Phrases describing the customer's problem, not the service name | "AC not cooling," "water leaking from ceiling," "drain smells bad" |
| 10 | **Booking intent keywords** | Phrases signaling readiness to act | "[service] near me," "book [service] today," "[service] appointment" |

### Rules governing every category above

- **Avoid keyword stuffing** — a keyword earns its place by matching real content already on the page; it is never inserted to hit a density target. If a category has no natural fit for a given page, it is left thin rather than forced.
- **Prioritize natural semantic SEO** — write for the topic and the reader first; keyword categories are a coverage checklist for *what to make sure the content addresses*, not a literal-string insertion list. Google's and AI systems' current ranking/answer behavior already rewards topical completeness over exact-match repetition, and `LUXURY_DESIGN_DIRECTION.md` §10 separately prohibits "keyword-stuffed headings and repetitive location copy" regardless of SEO trends.
- **Target both Google Search and AI search visibility** — the same semantic, question-answering, well-structured content that ranks in Google also feeds AI answer engines (per `09_AI_KNOWLEDGE/GEO_STRATEGY.md` and `09_AI_KNOWLEDGE/ANSWER_POLICY.md`'s existing restraint/factuality requirements) — there is no separate "AI-only" content track or looser factual standard for that audience.
- **Maintain content quality and user experience** — every rule above is subordinate to `LUXURY_DESIGN_DIRECTION.md`'s governance order (§12): accessibility/usability over decoration, verified facts over invented ones. A keyword requirement never overrides an approval gate or a truthfulness rule.

---

## 2. Keyword Placement Requirements

| Placement | What belongs there | Anti-stuffing guardrail |
|---|---|---|
| **SEO title** | Primary keyword, naturally phrased, once | Never the primary keyword repeated or force-fit with secondary keywords appended |
| **Meta description** | Primary keyword once + one supporting benefit/intent phrase | Written to earn the click, not to list keywords; no secondary/long-tail stuffing |
| **H1/H2 headings** | H1 carries the primary keyword naturally; H2s carry secondary/search-intent/problem-based phrases where they genuinely match a section's content | One H1 per page (existing `TYPOGRAPHY.md` rule); headings describe the section, keywords fit only where true |
| **Page content** | Primary + secondary + long-tail + problem-based keywords, distributed across genuinely relevant paragraphs | No fixed density target; a paragraph earns a keyword by being about that topic, not the reverse |
| **FAQ** | Search-intent and problem-based keywords as actual question headings, paired 1:1 with FAQ schema (existing rule, `05_SEO_IMPLEMENTATION_PLAN.md` §2) | Questions must be real customer questions, not keyword phrases reformatted with a question mark |
| **Image alt text** | Local/service-specific descriptive terms where they genuinely describe the image | Per `11_VISUAL_ASSET_STRATEGY.md` §6: alt text describes what the image shows — it is not a secondary keyword-insertion slot |
| **Internal links** | Anchor text drawn from secondary/local keywords where it accurately describes the destination | Generated from `SERVICE_MATRIX.md`/`SERVICE_AREAS.md` link data, per the existing anti-drift rule (`04_CONTENT_INTEGRATION_PLAN.md` §5) — never hand-stuffed anchor text |
| **Schema data** | Primary/secondary keywords only insofar as they appear in the real visible name/description fields | Schema must mirror visible content exactly (`05_SEO_IMPLEMENTATION_PLAN.md` §2) — never a keyword-richer "shadow" version of the page for crawlers |
| **Blog linking strategy** | Long-tail and problem-based keywords used as the topic hooks connecting blog posts back to the relevant service/location page | Links must be topically genuine (a post about a real problem linking to the service that solves it), never a keyword-anchor-text link farm |

---

## 3. Location Page Keyword Pattern

Applies the same ten categories to the seven emirate pages in `13_LOCATION_EXPANSION_ROADMAP.md`, combined with each service:

- **Primary:** `[service] [emirate]` per page (a Dubai AC Maintenance page's primary differs from its Sharjah counterpart's).
- **Local SEO:** every one of the 12 services × 7 emirates combination that is actually publishable (per each service's own content-status gate in §4 below) — generated from `SERVICE_MATRIX.md`, never hand-listed as 84 individual rows here.
- **Arabic/English, commercial, problem-based, booking-intent:** same category definitions as §1, applied per emirate rather than re-derived — the pattern doesn't change by location, only the emirate name/context does.
- **Genuine local content requirement is unchanged from `13_LOCATION_EXPANSION_ROADMAP.md` §2** — a keyword profile does not substitute for the real local-relevance content gate; a page with a perfect keyword profile but no genuine local content still should not publish.

---

## 4. Priority Order Used Below

Per the Owner's instruction: (1) Pest Control, (2) Cleaning [General Cleaning, Deep Cleaning, Water Tank Cleaning], (3) AC Maintenance, (4) General Maintenance [Painting, Handyman], (5) Plumbing, (6) Electrical Maintenance, (7) remaining approved services [Drain Unblocking, Waterproofing, Water Leak Detection].

---

## 5. Pest Control

- **Name:** Pest Control (EN) / مكافحة الحشرات (AR)
- **Category:** Cleaning & Pest Control
- **Page requirement:** Live route (`/services/pest-control`); most content-mature service in the catalog
- **SEO intent:** Preventive and treatment-seeking intent; secondary emergency/urgent-infestation intent
- **Keyword profile** (illustrative, per §1 — full 10-category set applied via the framework, unique fields below):
  | Category | Example |
  |---|---|
  | Primary | "pest control Dubai" / "مكافحة حشرات دبي" |
  | Secondary | "pest control company UAE," "cockroach treatment," "termite inspection" |
  | Long-tail | "best pest control company in Dubai for villas" |
  | Search intent | "how often should I get pest control" |
  | Problem-based | "cockroaches in kitchen," "termites in wooden furniture" |
  | Commercial (pattern only, no price on page) | "pest control cost Dubai" |
  | Booking intent | "book pest control near me" |
  | Local / Arabic / English | Per §1/§3 formula — applied across all 7 emirates, both languages |
- **Content status:** Knowledge package marked **Complete** per `SERVICE_CATALOG.md`
- **Approval status:** Structurally complete; still requires the standard evidence review before any new claim is added
- **Required images:** Hero (technician applying approved treatment, PPE visible), equipment detail, before/after only if verified evidence exists
- **Image style direction:** Professional and reassuring, explicitly avoiding "fear-based pest imagery used excessively" per `BRAND_IMAGES.md`
- **Related emirates:** All 7 emirates
- **Blog opportunities:** Seasonal pest patterns (only if a real, verifiable fact), prevention tips, "what to expect during a treatment visit" — each linked back to this page via a problem-based keyword hook per §2's blog-linking rule

## 6. Cleaning

### 6a. General Cleaning
- **Name:** General Cleaning (EN) / التنظيف العام (AR)
- **Category:** Cleaning & Pest Control
- **Page requirement:** Live route; **Review-ready package**
- **SEO intent:** Routine/recurring home or office cleaning intent
- **Keyword profile:**
  | Category | Example |
  |---|---|
  | Primary | "home cleaning service Dubai" / "خدمة تنظيف منازل دبي" |
  | Secondary | "office cleaning company UAE," "recurring cleaning service" |
  | Long-tail | "weekly home cleaning service for apartments in Dubai" |
  | Search intent | "how often should I clean my apartment professionally" |
  | Problem-based | "need deep clean before guests arrive" |
  | Commercial (pattern only) | "home cleaning price Dubai" |
  | Booking intent | "book cleaning service near me" |
  | Local / Arabic / English | Per §1/§3 formula |
- **Content status:** Review-ready
- **Approval status:** Awaiting final owner/technical review before publish
- **Required images:** Hero (cleaning in progress, real equipment/products), detail shots of equipment
- **Image style direction:** Bright, clean, high-key lighting
- **Related emirates:** All 7 emirates
- **Blog opportunities:** Cleaning checklists by room type, how-often guidance (only if a real, non-invented recommendation)

### 6b. Deep Cleaning
- **Name:** Deep Cleaning (EN) / التنظيف العميق (AR)
- **Category:** Cleaning & Pest Control
- **Page requirement:** Live route; **Blocked — no source draft, pending Owner scope**
- **SEO intent:** Move-in/move-out and intensive one-time cleaning intent
- **Keyword profile:** **Deferred — scope not yet approved.** No primary/secondary/long-tail keyword should be locked in for an undefined service; doing so would imply a scope that doesn't exist yet.
- **Content status:** Blocked
- **Approval status:** Cannot proceed to content, keywords, or approval until the Owner defines scope
- **Required images:** None commissioned
- **Image style direction:** N/A until scope exists
- **Related emirates:** All 7 emirates (coverage approved; content is not)
- **Blog opportunities:** None until scope is defined

### 6c. Water Tank Cleaning
- **Name:** Water Tank Cleaning (EN) / تنظيف خزانات المياه (AR)
- **Category:** Cleaning & Pest Control
- **Page requirement:** Live route; **Review-ready package**
- **SEO intent:** Hygiene/inspection-compliance intent
- **Keyword profile:**
  | Category | Example |
  |---|---|
  | Primary | "water tank cleaning Dubai" / "تنظيف خزانات المياه دبي" |
  | Secondary | "tank disinfection service UAE," "water tank inspection" |
  | Long-tail | "how often to clean residential water tank in Dubai" |
  | Search intent | "signs my water tank needs cleaning" |
  | Problem-based | "water tastes/smells bad from tank" |
  | Commercial (pattern only) | "water tank cleaning cost UAE" |
  | Booking intent | "book water tank cleaning near me" |
  | Local / Arabic / English | Per §1/§3 formula |
- **Content status:** Review-ready
- **Approval status:** Awaiting final owner/technical review
- **Required images:** Hero (technician at tank access point, PPE visible), before/after only if verified
- **Image style direction:** Emphasize hygiene/safety visually
- **Related emirates:** All 7 emirates
- **Blog opportunities:** Recommended cleaning frequency (only if a real, sourced recommendation), signs a tank needs cleaning

## 7. AC Maintenance
- **Name:** AC Maintenance (EN) / صيانة المكيفات (AR)
- **Category:** General Maintenance
- **Page requirement:** Live route; **Structurally complete draft**
- **SEO intent:** Routine servicing and cooling-failure/emergency intent — high seasonal relevance
- **Keyword profile:**
  | Category | Example |
  |---|---|
  | Primary | "AC maintenance Dubai" / "صيانة مكيفات دبي" |
  | Secondary | "AC repair near me," "AC service company UAE" |
  | Long-tail | "AC not cooling properly what to do Dubai" |
  | Search intent | "how often should AC be serviced in UAE" |
  | Problem-based | "AC not cooling," "AC making noise," "AC leaking water" |
  | Commercial (pattern only) | "AC maintenance cost Dubai" |
  | Booking intent | "book AC service today" |
  | Local / Arabic / English | Per §1/§3 formula |
- **Content status:** Structurally complete draft
- **Approval status:** Requires owner/technical evidence review before publish
- **Required images:** Hero (technician at AC unit), detail (condenser/filter), before/after only if verified
- **Image style direction:** Technical competence emphasis — clean tools, visible technique
- **Related emirates:** All 7 emirates
- **Blog opportunities:** Seasonal AC-prep guidance (verifiable, general advice only), energy-efficiency tips, signs of common faults (general, not diagnostic claims)

## 8. General Maintenance

### 8a. Painting
- **Name:** Painting (EN) / الدهانات (AR)
- **Category:** General Maintenance
- **Page requirement:** Live route; **Structurally complete draft**
- **SEO intent:** Interior/exterior repaint and refresh intent
- **Keyword profile:**
  | Category | Example |
  |---|---|
  | Primary | "painting service Dubai" / "خدمة دهانات دبي" |
  | Secondary | "villa painting UAE," "exterior painting company" |
  | Long-tail | "best interior painting company for apartments in Dubai" |
  | Search intent | "how long does professional painting take" |
  | Problem-based | "peeling paint," "wall cracks need repainting" |
  | Commercial (pattern only) | "painting service cost Dubai" |
  | Booking intent | "book painting service near me" |
  | Local / Arabic / English | Per §1/§3 formula |
- **Content status:** Structurally complete draft
- **Approval status:** Requires owner/technical evidence review
- **Required images:** Hero (in-progress painting), before/after only if verified, finish/color detail shots
- **Image style direction:** Crisp, well-lit, color-accurate photography
- **Related emirates:** All 7 emirates
- **Blog opportunities:** Color-trend or finish-type explainers (general/editorial), prep-work explainer

### 8b. Handyman Services
- **Name:** Handyman Services (EN) / الصيانة والإصلاحات العامة (AR)
- **Category:** General Maintenance
- **Page requirement:** Live route; **Structurally complete draft**
- **SEO intent:** General small-repair, multi-task intent ("odd jobs")
- **Keyword profile:**
  | Category | Example |
  |---|---|
  | Primary | "handyman service Dubai" / "خدمة صيانة عامة دبي" |
  | Secondary | "home repair service UAE," "furniture assembly service" |
  | Long-tail | "handyman for small repairs in apartment Dubai" |
  | Search intent | "what tasks does a handyman do" |
  | Problem-based | "need furniture mounted," "small repair around the house" |
  | Commercial (pattern only) | "handyman service cost UAE" |
  | Booking intent | "book handyman near me" |
  | Local / Arabic / English | Per §1/§3 formula |
- **Content status:** Structurally complete draft
- **Approval status:** Requires owner/technical evidence review
- **Required images:** Hero (technician with varied tools), detail shots per common task type
- **Image style direction:** Versatile/approachable — several short task vignettes rather than one narrow scene
- **Related emirates:** All 7 emirates
- **Blog opportunities:** "Common small repairs homeowners defer," task-scope explainer distinguishing handyman work from specialist trades

## 9. Plumbing
- **Name:** Plumbing (EN) / السباكة (AR)
- **Category:** General Maintenance
- **Page requirement:** Live route; **Structurally complete draft**
- **SEO intent:** Leak/blockage/fixture-repair intent, meaningful emergency-search component
- **Keyword profile:**
  | Category | Example |
  |---|---|
  | Primary | "plumber Dubai" / "سباك دبي" |
  | Secondary | "emergency plumbing service near me," "leak repair UAE" |
  | Long-tail | "24 hour emergency plumber in Dubai" |
  | Search intent | "what to do before plumber arrives for leak" |
  | Problem-based | "pipe leaking," "toilet blocked," "low water pressure" |
  | Commercial (pattern only) | "plumbing service cost Dubai" |
  | Booking intent | "book plumber near me now" |
  | Local / Arabic / English | Per §1/§3 formula |
- **Content status:** Structurally complete draft
- **Approval status:** Requires owner/technical evidence review
- **Required images:** Hero (technician with tools at fixture), detail (pipe/fitting work)
- **Image style direction:** Clean, controlled water-related imagery — avoid staged "flooding" drama
- **Related emirates:** All 7 emirates
- **Blog opportunities:** Leak-prevention tips (general, verifiable), what-to-do-first guidance before a technician arrives (general safety advice only)

## 10. Electrical Maintenance
- **Name:** Electrical Maintenance (EN) / الصيانة الكهربائية (AR)
- **Category:** General Maintenance
- **Page requirement:** Live route; **Structurally complete draft**
- **SEO intent:** Wiring/fixture repair and safety-inspection intent
- **Keyword profile:**
  | Category | Example |
  |---|---|
  | Primary | "electrician Dubai" / "كهربائي دبي" |
  | Secondary | "electrical safety inspection UAE," "wiring repair near me" |
  | Long-tail | "certified electrician for villa wiring in Dubai" |
  | Search intent | "how to know if wiring is unsafe" |
  | Problem-based | "circuit breaker keeps tripping," "flickering lights" |
  | Commercial (pattern only) | "electrician cost Dubai" |
  | Booking intent | "book electrician near me" |
  | Local / Arabic / English | Per §1/§3 formula |
- **Content status:** Structurally complete draft
- **Approval status:** Requires owner/technical evidence review — safety claims here carry extra weight per `AUTONOMY_AND_APPROVAL_MATRIX.md`'s "legal, licensing, regulatory, or safety claim" `A4` gate
- **Required images:** Hero (technician at panel/fixture, visible PPE), tool/equipment detail
- **Image style direction:** Safety-forward — PPE and correct procedure clearly visible
- **Related emirates:** All 7 emirates
- **Blog opportunities:** General electrical-safety awareness content (verifiable, non-diagnostic), "when to call an electrician vs. handyman"

## 11. Remaining Approved Services

### 11a. Drain Unblocking
- **Name:** Drain Unblocking (EN) / تسليك المجاري (AR)
- **Category:** Drainage & Water Protection
- **Page requirement:** Live route; **Structurally complete draft; technical scope detail still pending owner/technical approval**
- **SEO intent:** Blocked-drain, often emergency-adjacent intent
- **Keyword profile:** **Deferred — technical scope not yet approved for publication.** Pattern reserved: "drain unblocking [emirate]," "blocked drain emergency service UAE" — not actionable until scope clears.
- **Content status:** Structurally complete draft
- **Approval status:** Owner confirmed the service exists; detailed technical scope not yet approved for publication
- **Required images:** None until technical scope clears
- **Image style direction:** Deferred
- **Related emirates:** All 7 emirates
- **Blog opportunities:** Deferred until scope clears

### 11b. Waterproofing
- **Name:** Waterproofing (EN) / العزل المائي (AR)
- **Category:** Drainage & Water Protection
- **Page requirement:** Live route; **Structurally complete draft; technical scope detail still pending**
- **SEO intent:** Water-ingress-protection intent (per `DECISION_LOG.md` decision 19, thermal insulation is explicitly excluded unless separately confirmed — no keyword or content may blur this line)
- **Keyword profile:** **Deferred.** Pattern reserved: "waterproofing service [emirate]," "roof/bathroom waterproofing UAE" — not actionable until scope clears.
- **Content status:** Structurally complete draft
- **Approval status:** Same pending-scope status as Drain Unblocking
- **Required images:** None until technical scope clears
- **Image style direction:** Deferred
- **Related emirates:** All 7 emirates
- **Blog opportunities:** Deferred until scope clears

### 11c. Water Leak Detection
- **Name:** Water Leak Detection (EN) / كشف تسربات المياه (AR)
- **Category:** Drainage & Water Protection
- **Page requirement:** Live route; **Structurally complete draft; technical scope detail still pending**
- **SEO intent:** Hidden/undetected leak intent, often precautionary or damage-driven
- **Keyword profile:** **Deferred.** Pattern reserved: "leak detection service [emirate]," "hidden water leak detection UAE" — not actionable until scope clears.
- **Content status:** Structurally complete draft
- **Approval status:** Same pending-scope status as the two above
- **Required images:** None until technical scope clears
- **Image style direction:** Deferred
- **Related emirates:** All 7 emirates
- **Blog opportunities:** Deferred until scope clears

---

## What This Document Does Not Do

- Does not assert any real keyword-volume, ranking, competitor, or search-demand data — every keyword in §1 through §11 is an illustrative, unresearched pattern.
- Does not commission, generate, or approve any image.
- Does not change any service's status in `SERVICE_CATALOG.md`.
- Does not resolve the pending technical-scope approvals for Drain Unblocking, Waterproofing, or Water Leak Detection, or the blocked status of Deep Cleaning — their keyword profiles remain deferred, not filled in around the gap.
- Does not commit to any specific AI-search/answer-engine optimization tactic beyond the semantic-completeness principle stated in §1 — a dedicated GEO (generative-engine-optimization) implementation plan, if needed, is separate future work.

---

## Related Documents

- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `07_WEBSITE/IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md`
- `07_WEBSITE/IMPLEMENTATION/13_LOCATION_EXPANSION_ROADMAP.md`
- `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`
- `05_SEO_IMPLEMENTATION_PLAN.md`
- `09_AI_KNOWLEDGE/GEO_STRATEGY.md`
- `03_MARKET/SERVICE_AREAS.md`
