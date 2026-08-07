# Content Calendar Structure

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — structure only; no fixed date or campaign is scheduled by this document (§5 sets a cadence *formula*, not dated entries)
- **Version:** 0.2
- **Prepared:** 2026-08-04
- **Updated:** 2026-08-07 — added §5, the Owner-requested 6-month
  continuous rotation engine ("خطه لمده ٦ شهور متتاليه لاتقف")

## Purpose

Deliverable 2 of 5. `CONTENT_CALENDAR.md` already defines the calendar's
**data model** — required fields per item and the exact status flow
(`Idea → Briefed → Drafted → In Review → Changes Required → Approved →
Scheduled → Published → Measured → Updated/Archived`) — "without inventing
campaigns or dates." This document is the missing layer above that: the
actual **structure** (categories, rotation logic, platform-format mapping)
a real calendar would be organized by, sitting on top of that existing
schema and status flow unchanged. It does not add a 9th field, a new
status, or a cadence number.

## 1. Category rotation (maps onto the 6 root pillars — `SOCIAL_MEDIA_GROWTH_STRATEGY.md` §3)

| Category | Root pillar | Notes |
|---|---|---|
| Maintenance tips | Maintenance and prevention | General, cross-service |
| AC maintenance | Service education and scope | UAE-climate relevant year-round, especially pre-summer |
| Cleaning before/after | Business trust and process transparency | Only real, consented customer work — never staged/stock presented as real (`MEDIA_STANDARDS.md`) |
| Pest control education | Service education and scope | Reuse real facts already in `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/` — no invented pest-specific claims |
| UAE seasonal problems | Maintenance and prevention | Framed by season/climate, never by unapproved location/community facts |
| Customer trust content | Business trust and process transparency | Team, process, standards — not reviews unless sourced per `ACCOUNT_VERIFICATION_AND_SECURITY.md`/real Google Business Profile reviews with provenance |
| Company updates | Business trust and process transparency | Real milestones only, never fabricated |
| Offers (approved only) | — | Not a rotation category — every instance is a one-off High/Class-D item, never batch-scheduled |
| FAQ answers | Decision support | Reuse `04_SERVICE_KNOWLEDGE/*/04_FAQ.md` / `APPROVED_FAQS` verbatim — never rephrase in a way that changes the approved fact |

## 2. Weekly rotation logic (structure, not a fixed schedule)

A weekly cycle spreads the 8 real categories (excluding Offers) so no
single pillar dominates and no platform receives only one content type.
This is a **rotation pattern**, not a cadence commitment — how many days
per week actually publish is exactly what `TIKTOK_AND_SNAPCHAT_STRATEGY.md`
and `PINTEREST_GROWTH_STRATEGY.md` both already defer to a production-
capacity pilot, unchanged here:

1. Education (Maintenance tips / AC maintenance / Pest control education) — rotate weekly
2. Trust (Customer trust content / Company updates) — rotate weekly
3. Decision support (FAQ answers) — steady presence, not a burst
4. Seasonal (UAE seasonal problems) — weighted up during the relevant season (e.g., AC content pre-summer), not evenly spread year-round
5. Process (Cleaning before/after) — only when real, consented material exists that week — never manufactured to fill a slot

## 3. Platform-format mapping (the concrete table this folder didn't have yet)

`CHANNEL_STRATEGY.md` already states the *principle* — reuse one
underlying idea, adapt hook/length/format/caption/accessibility/thumbnail/
CTA per channel — but no concrete per-platform breakdown existed. This is
that breakdown, feeding directly into `CONTENT_PRODUCTION_WORKFLOW.md`
stages 3–4 (draft copy / produce channel-specific variants):

| Platform | Primary formats | Notes |
|---|---|---|
| Instagram | Carousel, Reel script, Story | Carousel for education/FAQ, Reel for process/trust, Story for timely/seasonal |
| Facebook | Community-friendly post | Warmer, longer-form caption than Instagram; same underlying fact, different voice |
| LinkedIn | Professional company update | Company/trust category only — not consumer education content |
| Pinterest | SEO image pin | Already fully specified in `PINTEREST_GROWTH_STRATEGY.md`'s own creative system — this row just confirms it fits the same category rotation |
| YouTube Shorts | Short educational video script | Education and process categories primarily |
| TikTok | Vertical video, native pacing | Already fully specified in `TIKTOK_AND_SNAPCHAT_STRATEGY.md` |
| X | Short-form text, single image | Company updates and FAQ answers fit best; least suited to Cleaning before/after (needs visual depth) |

One idea → one `CONTENT_CALENDAR.md` Content ID → one entry per platform
variant, each carrying its own AR/EN pair, its own asset reference, and
progressing through the same existing status flow independently (a
LinkedIn variant can reach Approved while the matching Reel is still In
Review).

## 4. Bilingual requirement (unchanged, restated for this structure)

Arabic primary, English secondary — matches every other content system in
this repository. `CONTENT_CALENDAR.md`'s field schema already requires an
AR/EN pair per item; this structure does not weaken that. Localized, not
literally translated, per `CONTENT_STRATEGY.md`'s lifecycle step 4.

## 5. Six-month continuous rotation engine (Owner decision, 2026-08-07)

The Owner asked for a cadence that runs for 6 months **without stopping**
("خطه لمده ٦ شهور متتاليه لاتقف"). §2 deliberately left frequency to a
production-capacity pilot — this section is the Owner now making that
call: **daily, one core idea per day, adapted to each connected platform**
(one idea → many variants, per `CHANNEL_STRATEGY.md`'s Content Adaptation
rule — not a separate idea per platform).

This is specified as a **deterministic formula**, not a finite
hand-written list of 182 dated entries — a formula genuinely never stops
(6 months is the Owner's commitment horizon, not a limit the mechanism
hits), and it never invents a date or campaign, since every day's content
is computed fresh from real, current data (`APPROVED_SERVICE_CONTENT_SLUGS`
and `APPROVED_FAQS`), never pre-written against a calendar date that
might drift out of sync with what's actually approved by then.

**Day → pillar (7-day cycle, extends §2's rotation to a full week):**

| Day | Pillar |
|---|---|
| Mon | Education — service spotlight (see service rotation below) |
| Tue | Decision support — FAQ answer, verbatim from `APPROVED_FAQS` |
| Wed | Education — service spotlight (next in rotation) |
| Thu | Trust — company/process, only if real consented material exists that week; otherwise falls back to Education (never manufactured to fill the slot, per §2 rule 5, unchanged) |
| Fri | Seasonal — UAE seasonal problem, weighted by actual current season (e.g. AC content pre-summer), directional only, never a committed date |
| Sat | Education — service spotlight (next in rotation) |
| Sun | Decision support — FAQ answer or Trust, alternating by week number |

**Service rotation (the part that makes it "never repeat the same way"):**
On each Education day, pick the next service in
`APPROVED_SERVICE_CONTENT_SLUGS`'s own array order, wrapping around
(`day_index mod 26`) — 26 real approved services means a full cycle
takes roughly 9 weeks at 3 Education slots/week, so each service is
naturally revisited about 3 times over a 6-month run, each time free to
draw a different real angle (a different `commonProblems` entry, a
different `benefits` entry) from the same `social-content/facts` record
— genuinely fresh without ever inventing a new fact.

**Why this "doesn't stop":** it is pure arithmetic on `day_index` (days
since the Owner-set start date) — no entry ever needs to be pre-authored,
and the rotation naturally continues past 6 months with zero additional
design work if the Owner later chooses to keep it running.

**n8n implementation shape:** a daily Schedule Trigger computes
`day_index`, looks up that day's pillar + (if Education) the next
service slug, calls `GET /api/social-content/facts` (list mode to know
the current 26, detail mode for the picked slug), drafts per
`POST_DESIGN_AND_ENGAGEMENT_PLAYBOOK.md`'s title/caption formula, and
writes the draft to the Class B approval queue — never posts directly,
same unchanged gate as everywhere else in this system.

## What this document explicitly does not do

- Does not add, remove, or rename any `CONTENT_CALENDAR.md` field or status.
- Does not authorize the Offers category to appear on a rotation.
- Does not invent seasonal dates — "pre-summer" etc. are directional, not calendar-committed.
- Does not authorize live posting — §5's engine still stops at the Class B
  approval queue, same as every other automated draft in this system.

## Related Documents

- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/CONTENT_CALENDAR.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/CONTENT_PRODUCTION_WORKFLOW.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/CHANNEL_STRATEGY.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/SOCIAL_MEDIA_GROWTH_STRATEGY.md`
- `10_MARKETING_AND_SEO/CONTENT_STRATEGY.md`
