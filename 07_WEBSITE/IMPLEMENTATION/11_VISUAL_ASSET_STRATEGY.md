# Visual Asset Strategy

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only for asset production; the image style **direction** in §3 is Owner-Approved (2026-07-28). No image is generated, sourced, or added by this document.
- **Version:** 2.0
- **Prepared:** 2026-07-28
- **Last Updated:** 2026-07-28 — §3 changed from illustration-only to Owner-approved realistic professional photography direction. See Change Log at the end of this document and `00_GOVERNANCE/DECISION_LOG.md`.
- **Scope:** All visual assets for `afaqalhayatae-app` and its social presence.
- **Depends on:** `02_BRAND/BRAND_IMAGES.md`, `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §4, `99_STANDARDS/NAMING_CONVENTIONS.md`, `05_SEO_IMPLEMENTATION_PLAN.md`, `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `03_MARKET/SERVICE_AREAS.md`, `02_BRAND/LOCAL_SEO_PROFILE.md`.

## Note on scope

This document plans standards only. It does not generate, commission, purchase, or add any image; it does not change `brand-panel.tsx`, `demo-visuals.ts`, or any other code; it does not create an image folder or asset pipeline. No code or application change is made.

---

## 0. Current State (verified, not assumed)

The app already has a working, deliberate placeholder strategy: `BrandPanel` renders line-art illustrations (`brand-scenes.tsx`) in place of real photography, with a documented swap-in path (add a file to `public/brand/images/`, pass `src`+`alt`, the illustration is replaced automatically). A `SHOW_DEMO_VISUALS` flag exists specifically for visual-QA placeholder images, explicitly labeled "DEMO PLACEHOLDER — NOT REAL COMPANY MEDIA" and shipped `false` by default. This strategy extends that existing pattern — it does not replace it.

This section describes the app's current, unchanged code. The v2.0 direction change in §3 is a forward-looking production standard for future real photography and any future AI-generated placeholder imagery — it does not, by itself, modify `brand-panel.tsx`, `brand-scenes.tsx`, or `demo-visuals.ts`. The existing line-art illustrations remain live until real assets are actually produced and wired in under a separate, approved implementation step.

---

## 1. Image Style Guidelines

Per `BRAND_IMAGES.md` and `LUXURY_DESIGN_DIRECTION.md` §4, every real photograph used anywhere on the platform must be:

- High-resolution (1920×1080px minimum), bright, clean, and professional — never blurry, watermarked, or over-edited.
- Naturally or carefully controlled lighting — not harsh flash or artificial staging.
- Consistently color-graded across the site, so services/locations/blog don't feel like they were sourced from different shoots.
- Composed for both hero (wide environmental frame) and card (detail/close-up) uses — the same shoot should be able to serve multiple placements, per `LUXURY_DESIGN_DIRECTION.md`'s "generous whitespace" and "consistent card padding" principles.

## 2. Photography Direction

Per `BRAND_IMAGES.md`'s "Preferred Photography" list and `LUXURY_DESIGN_DIRECTION.md` §4, prioritize:

- Real technicians in approved uniforms, following approved safety procedures.
- Clean, organized equipment and well-maintained vehicles.
- Real UAE residential/commercial environments (not generic international stock settings).
- Customers only with explicit, documented permission — never a photo implying an endorsement that hasn't been separately verified per `LUXURY_DESIGN_DIRECTION.md`'s "Evidence Before Claims" principle.

**Explicitly reject** (same source): generic stock photos unrelated to the actual company, visibly staged/fake people or tools, fear-based pest imagery used excessively, misleading before/after comparisons, images exposing a private customer's identity/location without permission, and low-resolution/oversaturated/distorted assets.

## 3. Image Generation Direction (Owner-Approved Realistic Photography — v2.0)

**Owner decision (2026-07-28):** the platform's image direction for service pages, hero images, service cards, process images, trust images, and marketing assets is **realistic professional photography style** — luxury corporate, UAE-appropriate — superseding this section's prior illustration-only rule (v1.0, preserved in Change Log below). Recorded in `00_GOVERNANCE/DECISION_LOG.md`.

- Real photography remains the preferred, primary source for every service marketing image — §2's photography direction is unchanged and still governs what gets shot and how.
- Where an image cannot yet be real photography (e.g., produced ahead of an actual shoot for a given service or location), it must now target the same **realistic, professional, luxury-corporate photographic look** as real photography — not the illustration/line-art style previously required.
- Every image, real or generated, must follow these brand safety rules without exception:
  - Official AFAQ AL HAYAT logo only — no invented, approximated, or AI-generated logo marks.
  - No fake company names or invented brand marks.
  - No incorrect or invented phone numbers — any visible contact detail must match `02_BRAND/CONTACT_INFORMATION.md` exactly.
  - Same team uniform identity across every service — no per-image variation in uniform style or color.
  - UAE professional environment — recognizable UAE residential/commercial context, consistent with §2's rejection of generic international stock settings.
  - Luxury corporate photography style, consistent with `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md`.
- **Unchanged hard rules — this decision does not touch these:**
  - Any image implying an endorsement, before/after result, or testimonial still requires real, verified evidence by definition (`LUXURY_DESIGN_DIRECTION.md` §4/§10) — a realistic style does not substitute for that evidence.
  - No image, generated or real, may be presented as a specific, identifiable real customer's or technician's genuine identity or testimonial unless that identity and consent are actually real and documented — fabricated identities remain a Hard Publication Block regardless of visual style.
  - §7's gating rule is unchanged: no image may depict a method, equipment, or scope not yet confirmed in that service's own canonical package.
- **Open conflict flagged, not resolved here:** `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §10 states an absolute prohibition on "AI-generated media presented as real company evidence." A photorealistic AI-generated image of a "technician," "vehicle," or "premises," used without disclosure, is difficult to distinguish from that prohibited case. This document's Owner-approved change is a *style* decision (realistic vs. illustration) — it does not, by itself, amend `LUXURY_DESIGN_DIRECTION.md` §10. Until that document is explicitly reconciled or the Owner confirms this decision also covers it, any AI-generated realistic-style image used before real photography exists should be treated as provisional and kept out of trust/testimonial contexts where it could be mistaken for verified real evidence.
- No AI image-generation tool, API, or credential is selected or added by this document — unchanged from v1.0.
- **No image is generated, sourced, or added by this update.** This is a direction/policy change only, per explicit Owner instruction.

## 4. Image Naming Convention

Per `99_STANDARDS/NAMING_CONVENTIONS.md`'s existing, approved "Image Naming" rule — this strategy adopts it exactly, not a new scheme:

```
<service-or-purpose>-<context>-v<N>.<ext>
```

Examples already given in that standard: `pest-control-homepage-v1.webp`, `cockroach-treatment-v2.jpg`, `technician-ppe-v1.png`. Extensions are limited to `.webp` (preferred), `.png`, `.jpg` per the same document. Version numbers increment on any meaningful re-shoot/re-edit, never reused for a different image.

## 5. Image SEO Requirements

Per `BRAND_IMAGES.md`'s "SEO Guidelines" and `05_SEO_IMPLEMENTATION_PLAN.md` §1/§2:

- Every image ships with a descriptive filename (§4), real alt text (§6), and an optimized/compressed file size — `next/image` (already the app's standard, per `LUXURY_DESIGN_DIRECTION.md` §9 and existing `BrandPanel` usage) handles format negotiation and lazy-loading by default; no separate image CDN/pipeline is proposed here.
- Where an image illustrates a publishable service or location page, it should be eligible for inclusion in that page's `Service`/`ImageObject` structured data per `10_MARKETING_AND_SEO/SCHEMA_STRATEGY.md` — schema and visible image must reference the same file, never a different "SEO-only" image swapped in for crawlers.
- No image may be the *only* place a fact appears — a "before/after" claim illustrated only in an image with no text equivalent is inaccessible and unverifiable; the same fact must exist in real page text too.

## 6. Alt Text Rules

Per `12_DESIGN_SYSTEM/ACCESSIBILITY.md` and `BrandPanel`'s own enforced contract (passing `src` without `alt` is already a TypeScript error in the app — this strategy is consistent with, not overriding, that):

- Alt text describes what the image actually shows, specific to context ("Technician inspecting AC unit condenser coil in Dubai villa," not "AC service") — never keyword-stuffed, never identical across many images.
- Decorative/illustrative images (the current line-art scenes) are `aria-hidden` and need no alt text, exactly as implemented today — this rule does not change once real photography is introduced; real photos get real alt text, decorative art stays decorative.
- No alt text may assert a fact the image doesn't support (a stock-adjacent "after" shot captioned as if from a specific real job) — alt text is subject to the same truthfulness rule as any other on-page claim.

## 7. Service Image Requirements

Per service (12 total, per `SERVICE_CATALOG.md`), each publishable service page should eventually have:

- One hero/wide image (real technician + equipment in a real or realistic UAE setting for that service type).
- One or two card/detail images (close-up of the actual work, e.g., the specific equipment used).
- Before/after pairs **only** where real, verified evidence exists for that exact service — never fabricated or generic, per `LUXURY_DESIGN_DIRECTION.md`'s explicit prohibition on misleading before/after comparisons.
- **Gating rule:** no image may depict a method, equipment, or scope not yet confirmed in that service's own canonical package (`04_SERVICE_KNOWLEDGE/<NN_SERVICE>/*`). A structurally-complete-draft service (per `SERVICE_CATALOG.md`'s maturity column) does not get real "in action" photography implying settled methodology until its content package clears the same review gate its text would need — see `12_SERVICE_EXPANSION_ROADMAP.md` for the per-service maturity/image mapping.

## 8. Location Image Requirements

Per emirate (7, all "Active" per `SERVICE_AREAS.md`):

- Generic, recognizable-but-non-specific imagery of the emirate/service context (e.g., a technician working in a residential setting broadly representative of that emirate) is acceptable.
- **Hard constraint:** no location image may depict or imply a specific street address, storefront, or office — `02_BRAND/LOCAL_SEO_PROFILE.md` is explicit that "No branch structure has been defined yet," and `CURRENT_PROJECT_STATUS.md`'s Hard Publication Blocks name "fake branches, virtual offices" directly. An image of a generic office building captioned as if it were "our Abu Dhabi branch" would violate this regardless of how the caption is worded.
- Priority-community pages (Tier 1, e.g. Palm Jumeirah) may use imagery evocative of that community's general character (skyline, architecture style) but — per `03_MARKET/SERVICE_AREAS.md`'s Priority Community Registry — must not imply a physical presence there; these are marketing priorities, not addresses.
- See `13_LOCATION_EXPANSION_ROADMAP.md` for the per-emirate image plan.

## 9. Social Media Asset Requirements

- Every platform-specific asset (per the 8 approved social profiles in `CONTACT_INFORMATION.md`) follows the same style/photography/AI rules above — a promotional graphic for Instagram is not exempt from the "no AI-generated image presented as real evidence" rule just because it's off-site.
- Dimensions follow each platform's current recommended specs at time of publishing (not hard-coded here, since platform specs change independently of this document's approval cycle) — a future, lighter reference table can be added without re-opening this strategy.
- No price, discount, or warranty may appear in a social image caption or overlay without the same `A4` commercial approval any such claim needs anywhere else (`AUTONOMY_AND_APPROVAL_MATRIX.md`) — a graphic is not a lower-scrutiny surface than a web page.
- Brand mark (logo, wordmark, primary color) usage on social assets follows `12_DESIGN_SYSTEM/COLORS.md` (per the already-approved decision that `COLORS.md`, not `BRAND_COLORS.md`, is the implementation source of truth — `00_PHASE1_APPROVAL.md` decision 1).

---

## What This Document Does Not Do

- Does not generate, purchase, license, or add any image.
- Does not select an AI image-generation tool or add any related dependency/credential.
- Does not create an asset-management folder structure or pipeline beyond citing the existing `public/brand/images/` convention already in use.
- Does not approve any specific photo, caption, or social post.

---

## Related Documents

- `02_BRAND/BRAND_IMAGES.md`
- `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md`
- `99_STANDARDS/NAMING_CONVENTIONS.md`
- `05_SEO_IMPLEMENTATION_PLAN.md`
- `10_MARKETING_AND_SEO/SCHEMA_STRATEGY.md`
- `07_WEBSITE/IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md`
- `07_WEBSITE/IMPLEMENTATION/13_LOCATION_EXPANSION_ROADMAP.md`

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-07-28 | Initial strategy. §3 required all AI-generated imagery to remain illustration/line-art style (never photorealistic), per `LUXURY_DESIGN_DIRECTION.md` §10's absolute prohibition on AI-generated media presented as real company evidence. |
| 2.0 | 2026-07-28 | Owner-approved direction change (recorded in `00_GOVERNANCE/DECISION_LOG.md`): §3 rewritten from illustration-only to realistic professional photography style for service pages, hero images, service cards, process images, trust images, and marketing assets — luxury corporate style, official logo only, no invented logos/company names/phone numbers, consistent uniform identity, UAE environment. Brand-safety and evidence-based-claims rules (testimonials, before/after, fake identities, §7's method-gating rule) are explicitly carried forward unchanged. Flags an unresolved conflict with `LUXURY_DESIGN_DIRECTION.md` §10, which this document does not have authority to amend on its own. No image generated by this change; no code changed. |
