# Pest Control Image Generation Brief

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — **specification only. No image has been generated.** See the note below.
- **Version:** 2.2 — visual direction rewritten from illustration style to Owner-approved realistic professional photography; §7 added for the two remaining `public/brand/images/services/pest-control/` library gaps.
- **Prepared:** 2026-07-28
- **Last Updated:** 2026-08-01 — see Change Log at the end of this document.
- **Package:** `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/`
- **Depends on:** `IMAGE_SEO_LIBRARY.md` (v1.1), `VISUAL_ASSET_BRIEF.md`, `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md` (v2.0), `00_GOVERNANCE/DECISION_LOG.md` (decision 36).

## Important — read before using this document

**No image was generated to produce this brief.** This session has no image-generation tool, model, or API available — nothing equivalent to DALL·E, Midjourney, or Stable Diffusion is present in the toolset used to write this repository's content. Rather than fabricate placeholder files and describe them as "generated assets" (which would misrepresent what happened, and would itself violate this repository's own no-fabrication discipline), this document instead provides a **complete, execution-ready specification** for each requested asset — exact filename, bilingual alt text, usage, keyword target, and a detailed generation prompt — so a human designer, photographer, or a separately-approved image-generation tool can produce the actual files against a precise, pre-agreed spec rather than an ad hoc description.

Every asset below still carries the same Evidence Gate as the rest of this package (`README.md`: "Review Required — Not Approved for Publication or Field Execution") and the same constraints already established in `IMAGE_SEO_LIBRARY.md` §0/§5.

---

## Asset Specifications

Each entry follows the exact fields requested: Asset ID, SEO filename, English Alt Text, Arabic Alt Text, intended page/section usage, keyword target — plus a **Generation Prompt** for whoever/whatever produces the actual file. Asset IDs, SEO filenames, alt text, usage, and keyword targets are unchanged from v1.0 — only the visual direction and each Generation Prompt were rewritten for this v2.0 update.

**Shared prompt suffix (applies to every asset below, per Owner decision 36 and `11_VISUAL_ASSET_STRATEGY.md` v2.0 §3):** *Style: realistic professional photography, luxury corporate UAE service-brand tone — calm, confident, clean, high-resolution. Natural or carefully controlled professional lighting, never harsh flash or over-edited. Official AFAQ AL HAYAT logo only where a logo is visible — no invented, approximated, or AI-fabricated logo marks, no fake company names, no incorrect or invented phone numbers. Same team uniform identity as every other service. Real or realistic UAE residential/commercial setting, never a generic international stock backdrop. No embedded text, no watermarks, no certification badges or seals. Any person shown as a "customer" must be either a real, documented-consent customer or an unbranded professional model presented generically — never captioned or implied as a specific real, named individual or testimonial unless that consent genuinely exists. No before/after or result-implying imagery. Suitable for both desktop and mobile crops; leave clear negative space for RTL/LTR text overlay where the asset is used as a hero.*

### 1. Hero Images

**PC-HERO-01**
- SEO filename: `pest-control-homepage-hero-v1.webp`
- English alt text: "Technician inspecting a UAE home for pest activity"
- Arabic alt text: "فني يفحص منزلاً في الإمارات بحثًا عن الآفات"
- Usage: Homepage (`/`) — Hero section
- Keyword target: pest control UAE (candidate, unresearched)
- Generation prompt: *A wide-format realistic photograph of a uniformed AFAQ AL HAYAT technician carrying an inspection tool, approaching a modern UAE villa exterior, shot in warm natural daylight, professional composition with generous negative space at top-left for headline text.* + shared suffix.

**PC-HERO-02**
- SEO filename: `pest-control-service-hero-v1.webp`
- English alt text: "Technician inspecting a Dubai property for pest activity"
- Arabic alt text: "فني يفحص عقارًا في دبي بحثًا عن نشاط الآفات"
- Usage: `/services/pest-control` — Hero section
- Keyword target: pest control Dubai (candidate, unresearched)
- Generation prompt: *A wide-format realistic photograph of a uniformed technician holding a clipboard and inspection light, examining the exterior entry points of a modern UAE residential building, natural daylight, professional editorial composition.* + shared suffix.

### 2. Service Images

**PC-SVC-02 — Residential pest control**
- SEO filename: `pest-control-residential-villa-v1.webp`
- English alt text: "Technician providing pest control at a residential villa"
- Arabic alt text: "فني يقدم خدمة مكافحة حشرات في فيلا سكنية"
- Usage: `/services/pest-control` — Services overview (card)
- Keyword target: residential pest control Dubai (candidate)
- Generation prompt: *A realistic photograph of a uniformed technician with an inspection kit at the entrance of a residential villa, warm domestic setting, natural light, card-format 4:3 composition.* + shared suffix.

**PC-SVC-03 — Commercial pest control**
- SEO filename: `pest-control-commercial-office-v1.webp`
- English alt text: "Technician providing pest control at a commercial premises"
- Arabic alt text: "فني يقدم خدمة مكافحة حشرات في منشأة تجارية"
- Usage: `/services/pest-control` — Services overview (card)
- Keyword target: commercial pest control UAE (candidate)
- Generation prompt: *A realistic photograph of a uniformed technician with equipment in a clean, modern office/commercial corridor setting, professional tone, card-format 4:3 composition.* + shared suffix.

**PC-SVC-04 — Pest inspection**
- SEO filename: `pest-control-inspection-detail-v1.webp`
- English alt text: "Technician examining a skirting board for signs of pest entry"
- Arabic alt text: "فني يفحص حافة الجدار بحثًا عن علامات دخول الآفات"
- Usage: `/services/pest-control` — Services overview (card)
- Keyword target: pest inspection service (candidate)
- Generation prompt: *A close-up realistic photograph of a uniformed technician's gloved hand holding an inspection light, examining a skirting board / entry point, detail-focused, shallow depth of field, card-format 4:3 composition.* + shared suffix.

**PC-SVC-05 — Prevention and protection concept** *(added to the library in v1.1; see `IMAGE_SEO_LIBRARY.md`)*
- SEO filename: `pest-control-prevention-protection-v1.webp`
- English alt text: "Visual concept representing pest prevention and protection"
- Arabic alt text: "مفهوم بصري للوقاية والحماية من الآفات"
- Usage: `/services/pest-control` — Services overview (card)
- Keyword target: pest prevention Dubai (candidate)
- **Reinterpretation note (v2.0):** the v1.0 prompt was an abstract/graphic concept (a "shield or perimeter line motif"), which does not translate literally into a photograph. It is reinterpreted below as a real preventive action rather than a graphic symbol — see the Review section for why.
- Generation prompt: *A realistic photograph of a uniformed technician conducting a visible preventive perimeter check around a home's exterior — inspecting the foundation line, door seals, and vents — communicating proactive protection rather than an active infestation. No literal pest imagery, no fear-based tone. Card-format 4:3.* + shared suffix.

### 3. Process Images (non-technical only, per the explicit exclusions in this request)

**PC-PROC-01 — Customer assessment**
- SEO filename: `pest-control-assessment-step-v1.webp`
- English alt text: "Technician assessing the property before treatment"
- Arabic alt text: "فني يقيّم حالة العقار قبل العلاج"
- Usage: `/services/pest-control` — How it works
- Keyword target: pest control process (candidate)
- Generation prompt: *A realistic photograph of a uniformed technician walking through a property holding a tablet/clipboard, visibly observing and assessing rather than treating — communicates evaluation, not action on a specific method.* + shared suffix.

**PC-PROC-05 — Professional consultation** *(added to the library in v1.0 of this brief)*
- SEO filename: `pest-control-consultation-step-v1.webp`
- English alt text: "Technician consulting with a customer about their needs"
- Arabic alt text: "فني يستشير العميل حول احتياجاته"
- Usage: `/services/pest-control` — How it works
- Keyword target: pest control consultation (candidate)
- Generation prompt: *A realistic photograph of a uniformed technician in conversation with a customer (an unbranded professional model presented generically, not as a specific real customer or testimonial, unless genuine documented consent exists) at a doorway or table — communicating dialogue and explanation. No product, chemical, or equipment shown in use.* + shared suffix.

**PC-PROC-02 — Service preparation**
- SEO filename: `pest-control-preparation-step-v1.webp`
- English alt text: "Technician preparing equipment before starting the service"
- Arabic alt text: "فني يستعد بالمعدات قبل بدء الخدمة"
- Usage: `/services/pest-control` — How it works
- Keyword target: pest control preparation (candidate)
- Generation prompt: *A realistic photograph of a uniformed technician organizing and checking generic equipment cases before starting work — no specific chemical, product label, or application method depicted or implied.* + shared suffix.

**Explicitly excluded from this brief, per the original request's own instruction:** `PC-PROC-03` (service/treatment-process image) remains blocked pending `OPERATIONS.md` method approval, and `PC-PROC-04` (follow-up) was not requested — neither is specified here. Unchanged by this v2.0 update.

### 4. Trust Images

**PC-TRUST-01 — Professional service environment**
- SEO filename: `pest-control-professional-environment-v1.webp`
- English alt text: "Professional pest control team in an organized work setting"
- Arabic alt text: "فريق مكافحة حشرات محترف في بيئة عمل منظمة"
- Usage: `/services/pest-control`, `/about` — Trust section
- Keyword target: professional pest control company (candidate)
- Generation prompt: *A realistic photograph of a small team of uniformed AFAQ AL HAYAT technicians in a clean, organized workspace or vehicle-adjacent setting — official logo visible only where it is the real, approved brand mark on genuine uniforms/vehicles, no other badges, no certification imagery.* + shared suffix.

**PC-TRUST-02 — Clean equipment**
- SEO filename: `pest-control-equipment-detail-v1.webp`
- English alt text: "Organized, professional pest control equipment"
- Arabic alt text: "معدات مكافحة حشرات احترافية منظمة"
- Usage: `/services/pest-control` — Trust section
- Keyword target: pest control equipment (candidate)
- Generation prompt: *A realistic flat-lay or shelf photograph of neatly arranged, generic inspection/service equipment (cases, tools, PPE) — no chemical product labels, no brand logos beyond the official AFAQ AL HAYAT mark where naturally present on the equipment itself.* + shared suffix.

**PC-TRUST-03 — Customer support concept**
- SEO filename: `pest-control-customer-support-v1.webp`
- English alt text: "Technician reviewing an inspection report with a customer"
- Arabic alt text: "فني يستعرض تقرير المعاينة مع العميل"
- Usage: `/services/pest-control`, `/about` — Trust section
- Keyword target: pest control customer service (candidate)
- **Note carried over from `VISUAL_ASSET_BRIEF.md`, now more important under realistic photography than it was under illustration:** a photograph of a "customer" is far closer to implying a real testimonial than a line-art figure ever was. This image requires either (a) a real customer with documented consent, or (b) an unbranded professional model, never captioned or implied as a specific real customer. It is not a stand-in for real photography/testimony without consent.
- Generation prompt: *A realistic photograph of a uniformed technician and a customer (per the note above) reviewing a document/report together — communicating transparency and follow-through.* + shared suffix.

### 5. Blog Images

**PC-BLOG-01 — Prevention tips**
- SEO filename: `pest-prevention-tips-v1.webp`
- English alt text: "Illustration of home pest-prevention tips"
- Arabic alt text: "رسم توضيحي لنصائح الوقاية من الآفات في المنزل"
- Usage: `/blog/[future-post]` — Article hero/inline
- Keyword target: pest prevention tips UAE (candidate)
- **Reinterpretation note (v2.0):** the v1.0 concept was an "icon-style vignette set" (a graphic format). Reinterpreted below as a small set of real close-up photographs with the same subject matter. If a graphic/icon treatment is still wanted for this specific asset, that is a separate design-format decision, not a photography-style one, and is not resolved by this brief.
- Generation prompt: *A set of realistic, well-lit close-up photographs of everyday prevention actions (sealing a gap around a pipe, storing food in a sealed container), styled as a clean, coordinated set for blog use — no embedded text, natural lighting throughout.*
- Note: alt text above ("Illustration of...") describes the v1.0 concept and should be revised to describe the actual photograph once produced, per §6's rule that alt text must describe what the image actually shows — flagged here rather than guessed, since the real photograph doesn't exist yet.

**PC-BLOG-02 — Pest identification reference**
- SEO filename: `termite-damage-identification-v1.webp`
- English alt text: "Reference image showing signs of termite damage"
- Arabic alt text: "صورة مرجعية توضح علامات أضرار النمل الأبيض"
- Usage: `/blog/[future-post]` — Article inline
- Keyword target: termite damage identification (candidate)
- Generation prompt: *An educational, realistic close-up/macro photograph of generic wood damage patterns for identification purposes — informational tone, not alarming, sharp focus, well-lit.* + shared suffix.

**PC-BLOG-03 — Process explainer**
- SEO filename: `pest-control-process-explainer-v1.webp`
- English alt text: "Illustration explaining the steps of a pest control visit"
- Arabic alt text: "رسم توضيحي يشرح خطوات زيارة مكافحة الحشرات"
- Usage: `/blog/[future-post]` — Article inline
- Keyword target: what to expect pest control visit (candidate)
- **Reinterpretation note (v2.0):** the v1.0 concept was a "numbered-step icon illustration" (a graphic format), which — like `PC-BLOG-01` — does not translate literally into a single photograph. Reinterpreted below as a coordinated sequence of realistic photographs, one per step, rather than an icon graphic. If an icon/graphic step diagram is still wanted, that is a separate design-format decision.
- Generation prompt: *A coordinated sequence of 3–4 realistic photographs representing each stage of a visit (booking call, technician arriving/inspecting, technician discussing findings with the customer per the `PC-PROC-05`/`PC-TRUST-03` consent rule, follow-up report handoff) — generic process only, no specific treatment method shown, consistent lighting and tone across the sequence.*
- Note: alt text above describes the v1.0 illustration concept and should be revised to describe the actual photograph sequence once produced, for the same reason noted under `PC-BLOG-01`.

### 6. Pest-Type Service Cards (Batch 2 — 2026-07-28)

**No image-generation tool is available in this session — none of the 6 assets below were generated. This section is a specification only, prepared so a human designer/photographer or a separately-approved generation tool can produce them against a precise, pre-agreed spec**, matching the identity established by the two Owner-approved reference assets already in `assets/hero/` and `assets/service-cards/` (`pest-control-homepage-hero-v1.webp`, `cockroach-control-service-card-v2.webp`): same AFAQ AL HAYAT logo, same technician uniform, same branded equipment (backpack sprayer, toolbox), same navy/green/light-blue palette, same "professional UAE service" photographic tone.

**Format note:** the reference service card is a composite (photo + headline + trust-badge row + footer bar), not a plain photograph — if this composite format is reused for these 6, the badge row must draw only from claim types already verified compliant on the corrected reference card ("long-lasting effectiveness," "complete home protection," "specialized team / excellent customer service" — no certification, no guarantee, no "100%," no eco/product claims without an approved-product source). This brief does not resolve that badge-copy decision itself; it flags the constraint for whoever executes it.

**Shared prompt suffix for this batch (in addition to the standing shared suffix in the Important section above):** *No fake certifications or seals. No guarantee or "guaranteed results" language, implied or written. No absolute claims ("100% safe," "completely eliminates"). No invented trust badges beyond the three claim types named above. No AI-fabricated or garbled text of any kind, in either language — every character of visible text must be a deliberate, correctly-spelled, human-verified string, not model-rendered lettering. Visible text limited to: the service name, AFAQ AL HAYAT branding, the phone number `+971 58 543 1766` / `058 543 1766` (no other number), and the "All 7 Emirates" coverage statement — nothing else. Arabic and English text must express the same facts and must each be checked by a fluent reader before delivery, not assumed correct because a diffusion model produced legible-looking script.*

**PC-SVC-ANT-01 — Ant Control**
- SEO filename: `ant-control-service-card-v1.webp`
- English alt text: "Technician from AFAQ AL HAYAT treating an ant infestation in a modern UAE home"
- Arabic alt text: "فني من آفاق الحياة يعالج انتشار النمل داخل منزل حديث في الإمارات"
- Usage: `/services/pest-control` — Services overview (pest-type card)
- Keyword target: ant control UAE (candidate, unresearched)
- Generation prompt: *A realistic photograph of a uniformed AFAQ AL HAYAT technician applying a professional ant-control treatment along a kitchen or entryway baseboard in a modern UAE home, gloved hands, branded backpack sprayer visible, clean bright interior, card-format composition matching the cockroach-control reference card's framing.* + shared suffix + batch suffix above.

**PC-SVC-BEDBUG-01 — Bed Bug Control**
- SEO filename: `bed-bug-control-service-card-v1.webp`
- English alt text: "Technician from AFAQ AL HAYAT treating a bed bug infestation in a UAE home"
- Arabic alt text: "فني من آفاق الحياة يعالج انتشار بق الفراش داخل منزل في الإمارات"
- Usage: `/services/pest-control` — Services overview (pest-type card)
- Keyword target: bed bug control UAE (candidate, unresearched)
- Generation prompt: *A realistic photograph of a uniformed AFAQ AL HAYAT technician inspecting/treating a bedroom mattress seam with professional equipment, gloved hands, branded toolbox visible, tidy bedroom setting, card-format composition matching the cockroach-control reference card's framing.* + shared suffix + batch suffix above.

**PC-SVC-MOSQUITO-01 — Mosquito Control**
- SEO filename: `mosquito-control-service-card-v1.webp`
- English alt text: "Technician from AFAQ AL HAYAT applying mosquito control treatment at a modern UAE property"
- Arabic alt text: "فني من آفاق الحياة يطبق معالجة مكافحة البعوض في عقار حديث بالإمارات"
- Usage: `/services/pest-control` — Services overview (pest-type card)
- Keyword target: mosquito control UAE (candidate, unresearched)
- Generation prompt: *A realistic photograph of a uniformed AFAQ AL HAYAT technician treating standing-water/garden areas around a UAE villa exterior with a branded backpack sprayer, outdoor daylight setting, card-format composition matching the cockroach-control reference card's framing.* + shared suffix + batch suffix above.

**PC-SVC-FLY-01 — Fly Control**
- SEO filename: `fly-control-service-card-v1.webp`
- English alt text: "Technician from AFAQ AL HAYAT applying fly control treatment at a modern UAE property"
- Arabic alt text: "فني من آفاق الحياة يطبق معالجة مكافحة الذباب في عقار حديث بالإمارات"
- Usage: `/services/pest-control` — Services overview (pest-type card)
- Keyword target: fly control UAE (candidate, unresearched)
- Generation prompt: *A realistic photograph of a uniformed AFAQ AL HAYAT technician treating a kitchen or waste-area zone with professional equipment, branded toolbox visible, clean commercial or residential UAE setting, card-format composition matching the cockroach-control reference card's framing.* + shared suffix + batch suffix above.

**PC-SVC-RODENT-01 — Rodent Control**
- SEO filename: `rodent-control-service-card-v1.webp`
- English alt text: "Technician from AFAQ AL HAYAT conducting rodent control at a modern UAE property"
- Arabic alt text: "فني من آفاق الحياة يقوم بمكافحة القوارض في عقار حديث بالإمارات"
- Usage: `/services/pest-control` — Services overview (pest-type card)
- Keyword target: rodent control UAE (candidate, unresearched)
- Generation prompt: *A realistic photograph of a uniformed AFAQ AL HAYAT technician placing/inspecting a professional bait station near a UAE property's exterior wall, branded equipment visible, no specific rodenticide brand or product shown, card-format composition matching the cockroach-control reference card's framing.* + shared suffix + batch suffix above.

**PC-SVC-TERMITE-01 — Termite Control**
- SEO filename: `termite-control-service-card-v1.webp`
- English alt text: "Technician from AFAQ AL HAYAT conducting termite control at a modern UAE property"
- Arabic alt text: "فني من آفاق الحياة يقوم بمكافحة النمل الأبيض في عقار حديث بالإمارات"
- Usage: `/services/pest-control` — Services overview (pest-type card)
- Keyword target: termite control UAE (candidate, unresearched)
- Generation prompt: *A realistic photograph of a uniformed AFAQ AL HAYAT technician inspecting a wooden structural element or foundation line with a professional inspection tool, branded equipment visible, no specific treatment method or chemical depicted (same gate as `PC-PROC-03`), card-format composition matching the cockroach-control reference card's framing.* + shared suffix + batch suffix above.

**Generated Assets List for this batch:**

| Asset ID | SEO Filename | Status |
|---|---|---|
| PC-SVC-ANT-01 | `ant-control-service-card-v1.webp` | Not generated — spec only |
| PC-SVC-BEDBUG-01 | `bed-bug-control-service-card-v1.webp` | Not generated — spec only |
| PC-SVC-MOSQUITO-01 | `mosquito-control-service-card-v1.webp` | Not generated — spec only |
| PC-SVC-FLY-01 | `fly-control-service-card-v1.webp` | Not generated — spec only |
| PC-SVC-RODENT-01 | `rodent-control-service-card-v1.webp` | Not generated — spec only |
| PC-SVC-TERMITE-01 | `termite-control-service-card-v1.webp` | Not generated — spec only |

None of these 6 filenames exist yet under `assets/service-cards/`. No file was created, copied, or renamed to stand in for them.

### 7. Service Library Cards — `public/brand/images/services/pest-control/` (Batch 3 — 2026-08-01)

**No image-generation tool is available in this session — neither of the 2 assets below was generated.** This section is a specification only, requested to fill the two remaining gaps in `public/brand/images/services/pest-control/` (the other four service images in that folder — `service-home-cleaning.webp`, `service-deep-cleaning.webp`, `service-office-cleaning.webp` under `services/cleaning/`, and `service-termite-control.webp` under `services/pest-control/` — are real Owner-approved photographs already copied into that library, not generated in this session).

**Filename convention note:** these two use the plain `service-<name>.webp` convention already established in `public/brand/images/services/`, not this document's `<slug>-v1.webp` SEO convention used in §1–§6 — kept exactly as the Owner specified, since these files map directly to that image library folder rather than to a future website route's SEO asset set.

**Shared style constraints for this batch (Owner-specified, 2026-08-01):** photorealistic, high resolution, web-optimized WEBP, 16:9 or 4:3 composition suitable for service cards. No text inside the image, no phone numbers, no banners, no watermarks, no marketing-graphic/composite-card layout (plain photograph only — same format as `service-home-cleaning.webp` / `service-deep-cleaning.webp` / `service-termite-control.webp`, not the composite-layout `cockroach-control-service-card-v2.webp`). No competitor logos. AFAQ AL HAYAT logo appears only naturally on uniform/equipment, not exaggerated. Luxury UAE professional home-service brand tone, matching the visual quality of the three reference images named above.

**PC-LIB-PEST-01 — General pest control**
- Filename: `service-pest-control.webp`
- Target path: `public/brand/images/services/pest-control/service-pest-control.webp`
- Scene: a professional AFAQ AL HAYAT pest control technician inside a luxury UAE villa, wearing uniform and safety equipment, using professional pest control equipment, clean modern interior, premium realistic photography, trustworthy and professional feeling.
- Generation prompt: *A photorealistic photograph of a uniformed AFAQ AL HAYAT pest control technician working inside a luxury UAE villa interior, wearing full uniform and safety equipment (gloves, mask as appropriate), holding professional pest control equipment (e.g. sprayer or inspection tool), clean modern high-end interior setting, natural or controlled professional lighting, calm and trustworthy composition, 16:9 or 4:3 framing suitable for a service card. AFAQ AL HAYAT logo visible only where naturally present on uniform or equipment, not exaggerated.* + shared prompt suffix (Important section, above) + this batch's shared style constraints.

**PC-LIB-COCKROACH-01 — Cockroach control**
- Filename: `service-cockroach-control.webp`
- Target path: `public/brand/images/services/pest-control/service-cockroach-control.webp`
- Scene: a professional AFAQ AL HAYAT technician treating a modern kitchen area for cockroach control, technician in branded uniform, using professional spray equipment, luxury UAE home environment, realistic photography, clean composition, no visible insects at unrealistic large size.
- Generation prompt: *A photorealistic photograph of a uniformed AFAQ AL HAYAT technician treating a modern, high-end kitchen area for cockroach control, using professional spray equipment, luxury UAE home environment, clean and realistic composition, natural or controlled professional lighting, 16:9 or 4:3 framing suitable for a service card. If any insect is depicted it must be realistically small-scaled and not the visual focus of the image. AFAQ AL HAYAT logo visible only where naturally present on uniform or equipment, not exaggerated.* + shared prompt suffix (Important section, above) + this batch's shared style constraints.

**Generated Assets List for this batch:**

| Asset ID | Filename | Status |
|---|---|---|
| PC-LIB-PEST-01 | `service-pest-control.webp` | Not generated — spec only |
| PC-LIB-COCKROACH-01 | `service-cockroach-control.webp` | Not generated — spec only |

Neither filename exists yet under `public/brand/images/services/pest-control/`. No file was created, copied, or renamed to stand in for them. Once produced against this spec, hand the finished `.webp` files back for copy-in, checksum verification, and placement into that folder — no image-generation tool will be used to fabricate a substitute in the meantime.

---

## Reviews

### 1. Visual Consistency Review

Every prompt above now shares the same realistic-photography suffix (professional UAE luxury-corporate tone, consistent lighting/uniform/brand rules) so that if 15 different shoots or sessions produced these, the outputs would still read as one coherent set — the risk with a spec this long is drift between asset #1 and #15, which the shared-suffix approach is designed to prevent. Three assets (`PC-SVC-05`, `PC-BLOG-01`, `PC-BLOG-03`) were originally written as abstract/iconographic concepts specifically because they don't map onto one literal photographable scene; each has been reinterpreted above as a realistic-photography equivalent (a real preventive action, a small photo set, a photo sequence) rather than forced into an unnatural single photograph. If the original graphic/icon treatment is still preferred for any of these three, that is a separate design-format decision this brief does not make.

### 2. SEO Metadata Review

All 15 filenames and bilingual alt texts are unchanged from v1.0 and still follow `IMAGE_SEO_LIBRARY.md` §3/§4 exactly — lowercase, hyphenated, descriptive, versioned. No keyword target is presented as verified research; each remains explicitly labeled "(candidate)." Three alt texts (`PC-BLOG-01`, `PC-BLOG-03`, and the English alt of `PC-BLOG-03`) still say "Illustration of..." / describe the old graphic concept — flagged individually above rather than guessed, since accurate alt text must describe the real photograph once it exists (§6), not the pre-photography concept.

### 3. Brand Alignment Review

The explicit exclusions from the original request (no unsupported treatment methods, no fake certifications, no fake identities, no guaranteed results) map directly onto rules this package already had in place — `PC-PROC-03` was already blocked for exactly the first reason, and `PC-TRUST-01`/`PC-TRUST-03`'s "no badge"/"requires real consent" notes already covered the second and third. Moving from illustration to realistic photography raises the stakes on the identity/consent point specifically: a silhouette illustration could never be mistaken for a real person, but a realistic photograph of a "customer" or "technician" can be — every prompt above involving a person now explicitly requires either genuine documented consent or an unbranded, non-specific professional model, per decision 36's carried-forward hard rules (`11_VISUAL_ASSET_STRATEGY.md` §3).

### 4. Conversion Impact Review

Unchanged from v1.0: once actually produced, the two most conversion-relevant assets are the two hero images (first impression) and `PC-TRUST-03` (customer support/report handoff, tied to this package's approved "Why Choose Us" copy). `PC-SVC-05` (prevention) and `PC-PROC-05` (consultation) remain lower-urgency but fill the same real gap identified in v1.0.

---

## Generated Assets List (per the requested report format)

**No asset has actually been generated — this is the specification list, ready for execution.**

| Asset ID | SEO Filename | Usage |
|---|---|---|
| PC-HERO-01 | `pest-control-homepage-hero-v1.webp` | Homepage hero |
| PC-HERO-02 | `pest-control-service-hero-v1.webp` | Service page hero |
| PC-SVC-02 | `pest-control-residential-villa-v1.webp` | Services overview card |
| PC-SVC-03 | `pest-control-commercial-office-v1.webp` | Services overview card |
| PC-SVC-04 | `pest-control-inspection-detail-v1.webp` | Services overview card |
| PC-SVC-05 | `pest-control-prevention-protection-v1.webp` | Services overview card |
| PC-PROC-01 | `pest-control-assessment-step-v1.webp` | How it works |
| PC-PROC-05 | `pest-control-consultation-step-v1.webp` | How it works |
| PC-PROC-02 | `pest-control-preparation-step-v1.webp` | How it works |
| PC-TRUST-01 | `pest-control-professional-environment-v1.webp` | Trust section |
| PC-TRUST-02 | `pest-control-equipment-detail-v1.webp` | Trust section |
| PC-TRUST-03 | `pest-control-customer-support-v1.webp` | Trust section |
| PC-BLOG-01 | `pest-prevention-tips-v1.webp` | Future blog article |
| PC-BLOG-02 | `termite-damage-identification-v1.webp` | Future blog article |
| PC-BLOG-03 | `pest-control-process-explainer-v1.webp` | Future blog article |

**Preview URL:** none — no asset exists, so none is integrated into the running application.

---

## What This Document Does Not Do

- Does not generate any image file.
- Does not select or add any AI image-generation tool, API, or credential.
- Does not write or modify any application code.
- Does not resolve `PC-PROC-03`'s block or add `PC-PROC-04` — both intentionally out of scope.
- Does not amend `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §10's prohibition on AI-generated media presented as real company evidence — if any of these prompts are executed by an AI generation tool rather than a real camera, that photorealistic output still needs to be checked against §10 before use in a trust/testimonial context.

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-07-28 | Initial illustration-style generation brief; 15 assets specified. |
| 2.0 | 2026-07-28 | Owner decision 36 approved realistic professional photography as the platform direction. All 15 Generation Prompts rewritten from illustration style to realistic professional photography; shared suffix rewritten accordingly. Asset IDs, SEO filenames, image purposes/usage, keyword targets, and document structure unchanged. Three prompts (`PC-SVC-05`, `PC-BLOG-01`, `PC-BLOG-03`) were originally abstract/iconographic concepts and have been reinterpreted as realistic-photography equivalents rather than forced into an unnatural literal translation — flagged individually. Three alt texts describing the old graphic concept (`PC-BLOG-01`, `PC-BLOG-03`) are flagged as needing revision once the real photograph exists, rather than guessed now. |
| 2.1 | 2026-07-28 | Added §6, a 6-asset "Batch 2" specification for pest-type service cards (ant, bed bug, mosquito, fly, rodent, termite control) requested by the Owner. No image-generation tool is available in this session, so — consistent with this entire document's existing practice — no image was generated for any of the 6; each gets a full execution-ready spec (filename, bilingual alt text, generation prompt) instead, built on the identity established by the two already-approved reference assets (`pest-control-homepage-hero-v1.webp`, `cockroach-control-service-card-v2.webp`). Added a batch-specific prompt suffix encoding the Owner's explicit constraints for this request (no certifications, no guarantees, no "100%," no invented badges beyond the three claim types already verified compliant on the reference card, no AI-fabricated text in either language). `IMAGE_SEO_LIBRARY.md` extended with 6 matching rows (19 → 25). |
| 2.2 | 2026-08-01 | Added §7, a 2-asset "Batch 3" specification for `service-pest-control.webp` and `service-cockroach-control.webp`, the two remaining gaps in the `public/brand/images/services/pest-control/` image library (the other four service images already in that library — `service-home-cleaning.webp`, `service-deep-cleaning.webp`, `service-office-cleaning.webp`, `service-termite-control.webp` — are real Owner-approved photographs, not generated in this session). No image-generation tool is available in this session, so neither asset was generated; each gets a full execution-ready spec (filename, target path, scene description, generation prompt) built from the Owner's own detailed brief, using the plain `service-<name>.webp` filename convention already established in that folder rather than this document's `-v1.webp` SEO convention. |

---

## Related Documents

- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/IMAGE_SEO_LIBRARY.md`
- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/VISUAL_ASSET_BRIEF.md`
- `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`
- `00_GOVERNANCE/DECISION_LOG.md` (decision 36)
