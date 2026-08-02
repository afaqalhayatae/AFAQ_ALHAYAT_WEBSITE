# Web Content Production Plan — Pest Control

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only. Inherits this package's own `README.md` gate: **"Review Required — Not Approved for Publication or Field Execution."** Organizing existing draft knowledge into a web-content shape does not resolve that gate.
- **Version:** 1.1 — the 4 fixes flagged in v1.0 (stale internal link, both "Why Choose Us" sections, the warranty FAQ answer, the missing Arabic FAQ) have since been applied to the underlying files; this document is updated to mark them resolved rather than pending.
- **Prepared:** 2026-07-28
- **Package:** `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/`
- **Depends on:** every file in this folder (`BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `CUSTOMER_GUIDE.md`, `FAQ.md`, `SEO_AI.md`, `CONTENT_AR.md`, `CONTENT_EN.md`, `MEDIA.md`), `05_SEO_IMPLEMENTATION_PLAN.md`, `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`, `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` §5, `07_WEBSITE/IMPLEMENTATION/13_LOCATION_EXPANSION_ROADMAP.md`.

## Note on scope

This document organizes existing package knowledge into the specific shape a web page needs (outline, SEO title, meta description, FAQ structure, internal links, visual plan, location mapping). It creates no code, no image, and publishes nothing. Every claim carried forward from a still-hedged source file is marked as such below — this plan does not launder a "pending evidence" statement into confident marketing copy anywhere.

---

## 0. Governing Constraint — What Is and Isn't Usable Today

This package's `README.md` Evidence Gate is explicit: *"no certification, municipality-compliance, approved-product, child/pet-safety, fast-response, or warranty claim may be published solely because it appears in this package."* Reviewing every file:

- **Safe to use as-is (no unverified claim):** the pest-type list, the general service process/steps, `CUSTOMER_GUIDE.md` in full (already marked "Approved Customer Guide" and contains only generic, non-claim guidance), and the FAQ answers that are already honestly hedged rather than asserting something unverified (see §3).
- **Not safe to use as customer-facing copy, even though it exists in a draft file:** `BUSINESS.md`'s "Customer Benefits" (safe treatments, fast response, municipality-compliant service — all explicitly listed under that same file's own "Evidence Required Before Approval") remains unfixed and out of this plan's original scope. `CONTENT_AR.md`/`CONTENT_EN.md`'s "Why Choose Us" sections, which were internal placeholders ("Competency evidence to be confirmed," "كفاءة الفريق تنتظر التحقق بالأدلة"), **have since been rewritten** (2026-07-28) as real customer-facing copy focused on process/tailored-assessment/communication/follow-up — see §1a/§1b, updated below.
- **Operationally unresolved:** `OPERATIONS.md`'s treatment methods (gel treatment, ULV fogging, fumigation) are themselves still "Draft — Not Approved for Field Execution." This matters for imagery too (§2) — a photo of a specific treatment method is itself an implicit claim that this is the company's approved method, which isn't true yet.

---

## 1. Complete Service Content Structure

### 1a. Arabic Content Outline

Building on `CONTENT_AR.md` (currently "Review Draft"):

1. **H1** — عنوان الخدمة: "خدمات مكافحة الحشرات" (already drafted, safe).
2. **Intro** — the existing short description paragraph; already generic and safe (no unverified claim present in that specific paragraph).
3. **الخدمات (services list)** — the existing pest-type list (صراصير، نمل، بق فراش، فئران، نمل أبيض، بعوض، ذباب) — factual, safe.
4. **لماذا تختارنا (Why Choose Us)** — ✅ **Fixed (2026-07-28).** Rewritten as real customer-facing copy (documented process, tailored assessment, clear guidance, maintenance programs, follow-up support) with no certification, guarantee, or response-time claim.
5. **خطوات الخدمة (process)** — existing 6-step list; procedural, no claims, safe.
6. **الأسئلة الشائعة (FAQ)** — ✅ **Fixed (2026-07-28).** `FAQ_AR.md` now exists, mirroring `FAQ.md`'s facts in natural Arabic phrasing, including the reworded warranty answer.
7. **دعوة للتواصل (CTA)** — existing line is generic and safe, no change needed.

### 1b. English Content Outline

Mirroring `CONTENT_EN.md`'s structure with the same gating:

1. **Title** — "Professional Pest Control Services" (existing, safe).
2. **Intro** — existing short description; safe as written.
3. **Our Services** — existing pest-type list; safe.
4. **Why Choose Us** — ✅ **Fixed (2026-07-28).** Rewritten as real customer-facing copy, matching the Arabic version's content exactly per bilingual-parity rules.
5. **Service Process** — existing 6-step list; safe.
6. **FAQ** — see §3 for the per-question publish-readiness map (now fully resolved, including the warranty answer and the new Arabic FAQ).
7. **Call to Action** — existing line is safe.

### 1c. SEO Title (new — none exists in `SEO_AI.md` today)

- **Base service page (EN):** "Pest Control Services in the UAE | AFAQ Alhayat"
- **Base service page (AR):** "خدمات مكافحة الحشرات في الإمارات | آفاق الحياة"
- **Dubai combo page (EN)**, using the app's existing `services/[slug]/[location]` route: "Pest Control Services in Dubai | AFAQ Alhayat"
- **Dubai combo page (AR):** "خدمات مكافحة الحشرات في دبي | آفاق الحياة"

No certification/safety/speed claim is included in any title — titles describe the service and coverage only.

### 1d. Meta Description (new)

- **EN:** "Professional pest control across the UAE from AFAQ Alhayat — inspection, treatment, and prevention for homes and businesses. Contact us to book a visit." (153 characters)
- **AR:** "خدمات مكافحة حشرات احترافية في جميع أنحاء الإمارات من آفاق الحياة — معاينة وعلاج ووقاية للمنازل والمنشآت. تواصل معنا لحجز موعد."

Neither asserts safety, certification, or response-time — consistent with §0's gate.

### 1e. Keywords

Single source of truth: `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` §5's Pest Control Keyword Profile — not redefined here to avoid two divergent keyword lists for the same service. Cross-checked against this package's own `SEO_AI.md` Primary/Secondary Keywords: both lists already agree (Pest Control, Cockroach/Termite/Rodent Control as primary/secondary) — no conflict found.

### 1f. FAQ Structure

Per-question publish-readiness, reviewing every entry in `FAQ.md`:

| Question | Status | Note |
|---|---|---|
| Is the treatment safe? | **Publish as-is** | Already honestly hedged ("depends on...") rather than overclaiming — this is good, truthful copy, not a gap. |
| Is it safe for children and pets? | **Publish as-is** | Same reasoning — correctly avoids an unconditional assurance. |
| How long does the treatment take? | **Publish as-is** | No unverified claim; correctly defers to the technician's on-site estimate. |
| When can I return to the treated area? | **Publish as-is** | Same. |
| Will one treatment solve the problem? | **Publish as-is** | Same. |
| What pests do you treat? | **Publish as-is** | Factual list, matches the catalog. |
| Do you offer warranty? | ✅ **Fixed (2026-07-28)** | Reworded to "Warranty details are confirmed in your written quotation or service order, so you always know exactly what's covered before work begins" — describes the mechanism without promising a warranty or its terms, and removes the internal-note phrasing. |
| How can I prevent pests from returning? | **Publish as-is** | General, verifiable prevention advice. |

**Arabic FAQ:** ✅ **Fixed (2026-07-28).** `FAQ_AR.md` now exists, mirroring this same table's facts and publish-readiness per question in natural Arabic phrasing, not a mechanical translation.

### 1g. Internal Linking Plan

✅ **Fixed (2026-07-28).** `SEO_AI.md`'s "Internal Links" section previously listed "Disinfection," which is not one of the 12 approved services in `SERVICE_CATALOG.md` and had no linkable page — it has been removed, leaving only real catalog services.

Corrected internal-link plan:
- **Related services:** General Cleaning, Deep Cleaning, Water Tank Cleaning (all in the same "Cleaning & Pest Control" category) — generated from `SERVICE_MATRIX.md`, not hand-authored, per the app's existing anti-drift pattern.
- **Location pages:** link to the Dubai (and later, each additional emirate's) pest-control combo page once it exists.
- **Blog:** once pest-prevention/seasonal-pattern posts exist (per `14_SERVICE_CONTENT_PRODUCTION_MATRIX.md` §5's blog opportunities), link them back here using a problem-based keyword anchor ("cockroaches in kitchen" → this page), per that document's blog-linking rule.

---

## 2. Visual Asset Plan

Building on `MEDIA.md`'s existing (approved-as-a-requirements-list) inventory and `11_VISUAL_ASSET_STRATEGY.md`'s rules.

### 2a. Hero Image Direction

Real technician applying an approved treatment, PPE clearly visible, calm/professional framing — explicitly **not** fear-based pest imagery, per `BRAND_IMAGES.md`'s direct warning and this package's own restraint in its FAQ answers. **Gated:** cannot be photographed as depicting a *specific* treatment method (gel, fogging, etc.) until `OPERATIONS.md`'s methods clear their own "Draft — Not Approved for Field Execution" status — a photo of a specific method is an implicit operational claim.

### 2b. Service Images

From `MEDIA.md`'s list — Technician at Work, Pest Inspection, Treatment Process, Equipment, Customer Interaction:
- Inspection and equipment shots carry the least evidence risk (they show tools/process generally, not a specific unapproved method) — reasonable candidates to prioritize once real photography begins.
- "Treatment Process" and "Before & After" are gated behind `OPERATIONS.md`'s method approval and real verified evidence respectively — do not stage a generic "spraying" photo as if it depicts the company's actual approved method.

### 2c. Blog Images

Lower evidence risk than service-page imagery, since blog content is educational (pest identification, prevention) rather than "our specific service" claims — but still no staged photo presented as if it were a real customer's home/infestation without genuine evidence and permission.

### 2d. Alt Text Requirements

Per `11_VISUAL_ASSET_STRATEGY.md` §6: descriptive and specific ("Technician inspecting for termite activity along a skirting board," not "pest control service"). **Alt text is subject to the same evidence gate as visible copy** — alt text reading "Certified technician safely treating your home" would embed two unverified claims (certification, safety assurance) inside accessibility metadata, which is just as much a publication as visible text.

---

## 3. UAE Location Expansion Mapping

### Dubai (first)

The app's `services/[slug]/[location]` route already generates a Dubai + Pest Control combo page technically (per the existing app audit) — the open work is **content**, not routing: per `13_LOCATION_EXPANSION_ROADMAP.md` §2, this page needs genuine Dubai-specific context (not the base service page with "Dubai" inserted) before it can honestly publish, on top of clearing the same §0 evidence gate as the base page.

### Remaining Six Emirates (preparation)

Once Dubai's combo page pattern is proven, the same Pest Control content package (outline, FAQ, images, keywords) extends to Abu Dhabi, Sharjah, Ajman, Umm Al Quwain, Ras Al Khaimah, and Fujairah — each still needing its own genuine local-relevance content per `13_LOCATION_EXPANSION_ROADMAP.md` §2, not a mechanical copy. No emirate is prioritized over another here beyond Dubai-first, per the roadmap's own sequencing note that ranking should follow real local insight, not an unverified assumption about relative size/demand.

---

## What This Document Does Not Do

- Does not change this package's `README.md` status or resolve its Evidence Gate.
- Does not write or publish any page, FAQ, or Arabic FAQ translation.
- Does not commission or approve any image.
- Does not touch `BUSINESS.md`'s still-unfixed "Customer Benefits" section — out of this update's scope, remains a separate future fix.
- Does not add or generate application code.

---

## Related Documents

- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/README.md`
- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/SEO_AI.md`
- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/MEDIA.md`
- `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`
- `07_WEBSITE/IMPLEMENTATION/13_LOCATION_EXPANSION_ROADMAP.md`
- `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`
