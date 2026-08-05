# Deep Cleaning — Landing Page Structure

## Document Information

- **Owner:** Business Owner / Marketing
- **Status:** Published — implemented via the shared `GoogleAdsLandingPage` component (`afaqalhayatae-app/src/components/google-ads-landing-page.tsx`) and the dynamic `/[locale]/lp/[slug]` route. Every landing page in this system uses the same section order — this document records this page's specific content within that fixed structure.
- **Prepared:** 2026-08-06
- **Relationship to existing standards:** Follows `10_MARKETING_AND_SEO/LANDING_PAGE_STANDARD.md`'s general landing-page principles (message-match, one clear intent, verified contact path, no fabricated trust evidence) and is a distinct page type from `07_WEBSITE/LANDING_PAGE_SYSTEM/` (which governs the informational `/services/{section}/{slug}` pages) — this system is built specifically for paid Google Ads traffic.

## Section Order (render order, fixed across all 10 landing pages)

1. **Hero** — headline, subheadline, primary CTA (Request Service), secondary CTAs (Call, WhatsApp), real photo.
2. **Trust Badges** (4) — UAE-wide service, Trained cleaning teams, Flexible scheduling, Quality-focused
3. **Problem / Pain Point** — Regular Cleaning Keeps Up — It Doesn't Reset / التنظيف المعتاد يحافظ على النظافة — لكنه لا يعيد الضبط من الصفر
4. **Why Choose AFAQ AL HAYAT** — Why UAE Homeowners Choose AFAQ AL HAYAT / لماذا يختار أصحاب المنازل في الإمارات آفاق الحياة
5. **Service Details** — What Our Deep Cleaning Service Covers / ما الذي تشمله خدمة التنظيف العميق
6. **Our Process** (4 steps) — How It Works / كيف تسير الخدمة
7. **Standard of Work** — The Standard You Can Expect / المستوى الذي يمكنك توقعه (real photo, no fabricated before/after)
8. **Pricing Guidance** — What Does It Cost? / كم التكلفة؟ (no fixed price, "Get a Free Quote" CTA — matches the site's existing claim-safety convention)
9. **Reviews** — honest placeholder ("Customer reviews will appear here as they come in.") — no invented testimonials, per Claim-Safety Rule.
10. **FAQ** (10 questions) — with `FAQPage` JSON-LD schema.
11. **Final CTA** — Give Your Home a Genuine Reset / امنح منزلك إعادة ضبط حقيقية

The page also inherits the site's shared header, footer, and sticky mobile CTA bar from the root layout — not a separate design system.
