# Pest Control Visual Asset Production Brief

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only. No image is generated, sourced, or added by this document; no code is written.
- **Version:** 1.0
- **Prepared:** 2026-07-28
- **Package:** `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/`
- **Depends on:** `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`, `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` §5, `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/WEB_CONTENT_PRODUCTION_PLAN.md`, `02_BRAND/BRAND_IMAGES.md`, `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §4.

## Note on scope and the evidence gate

This package's `README.md` status is still **"Review Required — Not Approved for Publication or Field Execution."** Every image concept below inherits that gate: nothing here may be photographed, generated, or published as depicting a specific treatment method until `OPERATIONS.md` clears its own "Draft — Not Approved for Field Execution" status. This brief plans *what a shoot/illustration set would need to cover*, gated exactly like the written content in `WEB_CONTENT_PRODUCTION_PLAN.md` — it does not pre-approve any of it.

---

## 1. Hero Image Concept

**Interim (today):** the existing `BrandPanel` line-art illustration (category "pest-control," already live in the app) remains the correct placeholder — no real photo replaces it until the items below are ready.

**Target real-photo concept, once ready:**
- A technician arriving at or inspecting a UAE residential/commercial property — calm, professional framing, natural or controlled lighting.
- Shows **inspection**, not a specific treatment application — inspection is safe to depict today (it's a general, undisputed part of the process); a specific method (gel, fogging) is not, until `OPERATIONS.md` clears.
- Wide environmental frame consistent with `LUXURY_DESIGN_DIRECTION.md` §5's Hero Sections guidance: one clear scene, no competing elements, generous negative space for the overlaid headline.
- Color grading consistent with the Primary Blue (`#0F4C81`)-led palette already used site-wide — not a separate "pest control brand" look.

## 2. Service Section Images

Per `MEDIA.md`'s existing inventory (Technician at Work, Pest Inspection, Equipment):
- **Inspection detail** — close-up of a technician examining a likely entry point (skirting board, drain, doorframe) — safe today, no method claim.
- **Equipment detail** — clean, organized tools (sprayer, inspection mirror, flashlight) laid out or in use generically — safe, communicates professionalism without claiming a specific approved method.
- **Pest-type icon set** — `MEDIA.md` calls for Cockroach/Ant/Rodent/Termite/Mosquito icons; **these do not exist yet** in the app's current icon set (`src/components/icons.tsx` has only generic category icons, no per-pest glyphs). Flagged here as a real gap for a future, separately-approved icon-design pass — not created by this document.

## 3. Process Images

Mapped to `OPERATIONS.md`'s workflow, split by what's safe to depict today vs. gated:

| Workflow step | Depictable today? |
|---|---|
| Site visit / inspection | ✅ Safe — general, undisputed |
| Pest identification | ✅ Safe — technician examining evidence (droppings, damage), no chemical/method shown |
| Risk assessment / treatment planning | ✅ Safe if shown as technician-customer conversation, not a specific product/method |
| Customer approval | ✅ Safe — signing/reviewing a document, generic |
| **Treatment execution** | ❌ Gated — depicts a specific method; wait for `OPERATIONS.md` approval |
| Customer education | ✅ Safe — technician explaining aftercare, matches `CUSTOMER_GUIDE.md` |
| Follow-up | ✅ Safe — generic revisit/check-in framing |

## 4. Trust-Building Images

- Technician reviewing/handing over an inspection report — ties directly to the one already-approved "Why Choose Us" bullet ("thorough, documented process") from the recent content fix.
- Organized, clean equipment and a well-maintained service vehicle, per `BRAND_IMAGES.md`'s preferred-photography list.
- Technician-customer interaction **only with documented permission** (per `BRAND_IMAGES.md` and `LUXURY_DESIGN_DIRECTION.md`'s Evidence Before Claims principle) — never a stock-style staged "happy customer" without real consent on file.
- **Explicitly not included:** certification badges, award graphics, or any "verified/certified" visual seal — none of that evidence exists yet, and a badge graphic is itself an unsupported claim regardless of caption.
- Before/after imagery is **not** planned in this brief — it requires real, verified evidence per `11_VISUAL_ASSET_STRATEGY.md` §2, which doesn't exist yet; a future, separate brief can add it once it does.

## 5. Blog/Article Images

Lower evidence risk than service-page imagery (educational, not "our specific service" claims):
- Pest-identification reference imagery (what does termite damage look like, generically) — informational, not tied to a specific job.
- Prevention-tip illustrations (sealing entry points, food storage) — can be illustration-style rather than photography, appropriate for editorial content.
- Seasonal-pattern imagery — only paired with a real, verifiable seasonal fact per `WEB_CONTENT_PRODUCTION_PLAN.md`'s blog-opportunity notes, never an invented claim illustrated to look authoritative.

## 6. AI Image Generation Prompts

Per `11_VISUAL_ASSET_STRATEGY.md` §3, AI-generated imagery may **only** serve as a clearly-labeled illustrative placeholder in the same line-art style as the existing `brand-scenes.tsx` — never photorealistic, never presented as a real technician, customer, or result. No AI image-generation tool or credential is selected here; the prompts below are prepared for **if and when** such a tool is separately approved, and are illustration-brief text, not a working pipeline.

Every prompt below carries the same mandatory guardrail suffix:

> *Style: flat editorial line-art illustration, single accent color on white/neutral background, no photorealism, no readable text or logos, no depiction of a specific identifiable person, no chemical/product branding, no fear-based or graphic pest imagery.*

Illustrative prompt concepts:
1. "A calm line-art illustration of a technician with an inspection clipboard examining a stylized UAE villa exterior."
2. "A simple line-art icon scene of a magnifying glass over a doorframe, suggesting inspection, no pest depicted graphically."
3. "An editorial line-art illustration of a technician handing a document to a homeowner at a front door, conveying trust and communication."
4. "A minimal line-art illustration of cleaning/inspection equipment arranged neatly, no chemical labels visible."

None of these may be generated by this document — they are prepared text only, pending a separate tooling decision.

## 7. Image Style Rules

Direct application of `BRAND_IMAGES.md` and `LUXURY_DESIGN_DIRECTION.md` §4 to this service specifically:

- **Calm confidence over shock** — per `BRAND_IMAGES.md`'s explicit warning against "fear-based pest imagery used excessively": no macro shots of live pests, no graphic infestation imagery. Lead with the technician's competence and the property's cleanliness, not the pest itself.
- **Quiet Luxury restraint** — one clear subject per image, generous negative space, no cluttered multi-element scenes (`LUXURY_DESIGN_DIRECTION.md` §2/§3).
- **Consistent color grading** matching the site-wide Primary Blue-anchored palette — pest-control imagery should not look like a different brand from the rest of the site.
- **High resolution (1920×1080px minimum), WebP-preferred**, per `BRAND_IMAGES.md`'s Image Quality section.

## 8. SEO File Naming

Per `99_STANDARDS/NAMING_CONVENTIONS.md`'s approved `<service-or-purpose>-<context>-v<N>.<ext>` pattern:

| Asset | Filename |
|---|---|
| Hero | `pest-control-hero-v1.webp` |
| Inspection detail | `pest-control-inspection-detail-v1.webp` |
| Equipment detail | `pest-control-equipment-v1.webp` |
| Customer report handoff | `pest-control-report-handoff-v1.webp` |
| Blog: termite damage reference | `termite-damage-identification-v1.webp` |
| Blog: prevention illustration | `pest-prevention-tips-v1.webp` |

## 9. Alt Text Requirements

Per `11_VISUAL_ASSET_STRATEGY.md` §6 — specific, descriptive, no embedded unverified claim:

| Image | Alt text (EN) | Alt text (AR) |
|---|---|---|
| Hero | "Technician inspecting the exterior of a UAE residential property for pest activity" | "فني يفحص الجزء الخارجي لعقار سكني في الإمارات بحثًا عن نشاط الآفات" |
| Inspection detail | "Technician examining a skirting board for signs of pest entry" | "فني يفحص حافة الجدار بحثًا عن علامات دخول الآفات" |
| Report handoff | "Technician reviewing an inspection report with a customer" | "فني يستعرض تقرير المعاينة مع العميل" |

Neither language's alt text asserts certification, safety guarantees, or a specific treatment method — consistent with the same evidence gate applied to visible copy.

## 10. Arabic/English Usage Mapping

- Per the app's existing `BrandPanel` pattern, **the same image file serves both locales** — images are not language-specific. Only the alt text differs per §9.
- No image may contain embedded text/typography (per §6's prompt guardrail and general accessibility best practice) — this avoids needing separate Arabic/English image variants entirely and keeps RTL/LTR layout unaffected by image content.
- Cultural appropriateness is symmetric: the same restraint/professionalism standard applies regardless of which locale a visitor is browsing in — no version is more "polished" or more "hedged" than the other, consistent with `PROJECT_MANIFEST.md`'s bilingual-equality principle.

---

## What This Document Does Not Do

- Does not generate, commission, or approve any image.
- Does not select or add any AI image-generation tool, API, or credential.
- Does not create the missing pest-type icon set (§2) — flagged for a future, separate design/code task.
- Does not change this package's Evidence Gate or Review-Required status.
- Does not add or generate application code.

---

## Related Documents

- `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`
- `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`
- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/WEB_CONTENT_PRODUCTION_PLAN.md`
- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/MEDIA.md`
- `02_BRAND/BRAND_IMAGES.md`
- `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md`
