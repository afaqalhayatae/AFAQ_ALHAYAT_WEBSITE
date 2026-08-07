# Post Design and Engagement Playbook

## Document Information

- **Owner:** Business Owner / Marketing
- **Status:** Draft — extends Approved architecture; authorizes no live posting, live replying, tool purchase, or account connection
- **Version:** 0.1
- **Prepared:** 2026-08-07 (Owner-requested: "تصميم بوستا لكل منصه ووضع عناوين مع رقم الموبايل في وسائل التواصل الاجتماعي كلها لكل الخدمات... مع الالتزام بالمعايير لكل منصه والردود علي التعليقات باحترافيه")

## Purpose

`AUTOMATION_AND_PUBLISHING.md` (Approved Architecture) and
`MULTI_PLATFORM_AUTOMATION_ARCHITECTURE.md` already define the pipeline,
the AI sub-stages, and the Fast-Track Classes. `CONTENT_CALENDAR_STRUCTURE.md`
already maps categories to platform *formats*. **None of them specify what
a post actually looks like, what a title/caption pattern is, per-platform
technical limits, or how comment replies concretely get drafted and
released.** This document is that missing layer — sitting on top of all
of the above, not re-deriving any of it. It is the design spec the n8n
drafting workflow (`MULTI_PLATFORM_AUTOMATION_ARCHITECTURE.md`'s
Copywriting/Captions/Image-prompts sub-stages) is built against.

It covers every service in `afaqalhayatae-app`'s
`APPROVED_SERVICE_CONTENT_SLUGS` (`src/lib/catalog/service-content.ts`,
26 services as of 2026-08-07) — not a hand-picked subset. That list, not
a copy of it here, is the source of truth; the new
`GET /api/social-content/facts` endpoint (noted in
`MULTI_PLATFORM_AUTOMATION_ARCHITECTURE.md`'s 2026-08-07 update) is how
the drafting workflow reads it.

---

## 1. Post template system (per platform)

One underlying template, four platform variants — same brand system
already live on the website (`12_DESIGN_SYSTEM/COLORS.md` navy/white,
approved logo, real service photography from
`afaqalhayatae-app/public/brand/images/`), not a new visual identity.

**Fixed elements on every post image, every platform, every service:**

- Approved logo mark (top corner, safe-area padding).
- The service's real photo — one already approved and in use on that
  service's own landing page (`src/lib/catalog/landing-pages.ts`) or
  `SERVICE_DATABASE.json` card image. Never a stock photo presented as
  AFAQ's own work, never an AI-generated "customer result" (`MEDIA_STANDARDS.md`,
  unchanged).
- The service name, bilingual (Arabic primary per `CONTENT_STRATEGY.md`'s
  lifecycle step 4, English secondary) as the headline.
- **The phone number, always visible on the image itself, not only in the
  caption** — `+971 58 543 1766` (canonical source: `02_BRAND/CONTACT_INFORMATION.md`,
  Owner-approved, safe to publish per this repo's `CLAUDE.md`). Placed in
  a fixed footer band so it survives platform cropping (see safe-area
  table below).
- A single CTA line: "Book now / WhatsApp us" (bilingual), linking to the
  service's real page — never a bare "link in bio" with no real
  destination.

| Platform | Canonical image size (2026 baseline — verify at execution time, platforms change specs) | Safe area for phone number/logo |
|---|---|---|
| Instagram feed | 1080×1080 (1:1) or 1080×1350 (4:5) | Bottom 12% band, centered |
| Instagram Story/Reel cover | 1080×1920 (9:16) | Bottom 20% (below UI overlay zone) |
| Facebook feed | 1200×630 (link) or 1080×1080 (native image) | Bottom 12% band |
| LinkedIn feed | 1200×627 | Bottom 12% band |
| Pinterest pin | 1000×1500 (2:3) | Bottom 15% — already specified in `PINTEREST_GROWTH_STRATEGY.md`'s own creative system; this row only confirms the phone-number placement rule applies there too |
| TikTok/YouTube Shorts cover | 1080×1920 (9:16) | Bottom 20% |
| X (Twitter) | 1200×675 (16:9) | Bottom 12% band |

Exact pixel specs must be re-verified against each platform's current
developer documentation at build time — stated here as a working
baseline, not a guaranteed-current fact, same caution
`SOCIAL_TOOLS_EVALUATION.md` already applies to tool pricing.

## 2. Title/caption formula

One formula, filled from real facts only (the `social-content/facts`
endpoint), never invented:

```
[Hook — real pain point, from `commonProblems`] +
[Service name] +
[One real benefit, from `benefits`] +
[CTA] + [Phone number] + [WhatsApp]
```

**Example shape (illustrative structure only — actual copy is drafted
per-service from real facts, not hardcoded here):**

> AC not cooling like it used to? 🔧 AFAQ AL HAYAT's AC maintenance team
> inspects, cleans, and diagnoses the real cause — across all 7 emirates.
> 📞 +971 58 543 1766 | WhatsApp us — link in bio.

Rules (all restating existing, not new, policy):

- No price, warranty, discount, or urgency ("today only") language unless
  it is a real, Owner-approved, Class-D-reviewed offer
  (`PUBLISHING_APPROVAL_POLICY.md`).
- Hashtags/keywords drawn only from real service/location terms already
  used in `landing-pages.ts`'s `seo.keywords` — never a fabricated
  "trending" tag (`MULTI_PLATFORM_AUTOMATION_ARCHITECTURE.md` §1, unchanged).
- Caption length respects each platform's real norm
  (`CONTENT_CALENDAR_STRUCTURE.md` §3's format table) — Instagram/Facebook
  can run longer, X stays short, LinkedIn stays professional-register.

## 3. Per-service coverage

Every one of the 26 slugs in `APPROVED_SERVICE_CONTENT_SLUGS` is in
rotation — no service is skipped and none is invented beyond that list.
`CONTENT_CALENDAR_STRUCTURE.md` §1–2's category rotation and weekly
pattern already govern *which* service/pillar posts *when*; this
document does not add a second scheduling rule. The n8n workflow simply
iterates `GET /api/social-content/facts` (list mode) to know the full,
current, real set — so a new service added to that list (e.g. once one
of the 11 Service Expansion Phase services activates, per
`00_GOVERNANCE/11_SERVICE_ACTIVATION_REVIEW.md`) is automatically in
rotation with no template change needed here.

## 4. Comment-reply automation

Operationalizes `COMMUNITY_MANAGEMENT.md`'s existing Response Principles,
Escalation list, and AI Boundaries into a concrete drafting workflow —
does not redefine any of them.

**Flow:**

1. New comment arrives (via each platform's official API/webhook, once
   an account is actually connected — connection itself stays Human
   Controlled per `AUTOMATION_AND_PUBLISHING.md`).
2. AI classifies the comment against `COMMUNITY_MANAGEMENT.md`'s
   Escalate-Immediately list (safety/health, threats/abuse/fraud,
   property/payment complaints, legal/regulatory, personal data, media
   inquiries).
3. **If it matches Escalate-Immediately:** AI drafts nothing public. It
   routes the comment to the Owner with a summary only — matches
   `COMMUNITY_MANAGEMENT.md`'s AI Boundaries ("must not resolve
   complaints, confirm bookings, promise compensation, quote unapproved
   prices, or answer emergencies without human oversight").
4. **If it's a general question with a real answer already in
   `APPROVED_FAQS` or the service's own approved content:** AI drafts a
   reply using that real answer, in the commenter's language, warm and
   concise (matches Response Principles: "helpful, concise, respectful,
   privacy-aware, honest about uncertainty"). This is Class B — queued
   for one approval before it posts, same as any other evergreen content,
   until the Owner explicitly approves a lower-risk class for this
   specific case type per `AUTOMATION_AND_PUBLISHING.md`'s own graduation
   rule ("Human approval before public posting until an owner explicitly
   approves a lower-risk automation class" — `README.md`).
5. **If it's a simple positive comment (thanks, praise, emoji) with zero
   claim risk:** AI drafts a short acknowledgment. Still Class B at pilot
   — the Owner can graduate this specific, lowest-risk case type to Class
   A only after real pilot evidence, matching the phased graduation
   pattern `AUTOMATION_AND_PUBLISHING.md`'s Initial Implementation
   Sequence already uses for posts.
6. Every draft reply — regardless of class — never quotes a price,
   promises a timeline, confirms a booking, or offers compensation. Those
   remain Human Controlled without exception (`AUTOMATION_AND_PUBLISHING.md`).

**"Professional, like a human" means:** natural bilingual phrasing (not
a visibly templated bot reply), the business's real warm-but-professional
voice already established in the chat widget's system prompt
(`08_DIGITAL_SYSTEMS/AI_CHATBOT/04_CHATBOT_SYSTEM_PROMPT.md`) — reused
here rather than a second, separately-invented voice — and never a
generic "Thank you for your comment" template repeated verbatim across
every reply.

## 5. n8n job shape

Reuses `AGENT_ORCHESTRATION.md`'s existing Job Envelope schema, per
`MULTI_PLATFORM_AUTOMATION_ARCHITECTURE.md` §3 — not a new schema. Two
job types:

- **Post-draft job:** `allowed_sources` = `GET /api/social-content/facts`
  only; `allowed_tools` = the configured LLM for copy + an image-compose
  step using the real photo + fixed template; `allowed_write_paths` =
  the approval-queue store only (a spreadsheet/DB row, never a live
  platform); `approval_required` = true (Class B minimum).
- **Comment-reply-draft job:** `allowed_sources` = `APPROVED_FAQS` +
  the specific service's `social-content/facts` entry + the incoming
  comment text; same `approval_required` = true; `forbidden_actions`
  explicitly includes "post directly to platform," "quote price,"
  "confirm booking."

## What this document explicitly does not do

- Does not authorize any live posting, live replying, tool purchase, or
  account connection — same standing line as `AUTOMATION_AND_PUBLISHING.md`.
- Does not name or commit to a specific n8n node configuration — that's
  implementation, done once account access exists.
- Does not change any Fast-Track Class, approval tier, or escalation rule
  already defined in `AUTOMATION_AND_PUBLISHING.md`, `PUBLISHING_APPROVAL_POLICY.md`,
  or `COMMUNITY_MANAGEMENT.md`.
- Does not assert current pixel-exact platform specs as permanently fixed
  — verify at execution time, same caution as `SOCIAL_TOOLS_EVALUATION.md`.

## Related Documents

- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/AUTOMATION_AND_PUBLISHING.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/MULTI_PLATFORM_AUTOMATION_ARCHITECTURE.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/CONTENT_CALENDAR_STRUCTURE.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/COMMUNITY_MANAGEMENT.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/MEDIA_STANDARDS.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/PUBLISHING_APPROVAL_POLICY.md`
- `08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_ORCHESTRATION.md`
- `08_DIGITAL_SYSTEMS/AI_CHATBOT/04_CHATBOT_SYSTEM_PROMPT.md`
