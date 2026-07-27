# Announcement / News Bar Architecture Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — architecture plan only. No code or design change is made by this document.
- **Version:** 1.2 — Owner-approved decisions recorded (dismiss behavior, priority order, display rules); §3 type taxonomy and priority order updated to match. v1.1 extended to a 15-section outline; content carried forward from v1.0 (§1–11, and §12 renumbered to §13), plus §12 (Analytics Tracking), §14 (AI Content Integration Possibility), and §15 (Scalability Considerations).
- **Prepared:** 2026-07-28
- **Scope:** `afaqalhayatae-app` — a site-wide announcement/news bar component.
- **Depends on:** `12_DESIGN_SYSTEM/{COMPONENTS,ACCESSIBILITY,LUXURY_DESIGN_DIRECTION}.md`, `05_SEO_IMPLEMENTATION_PLAN.md`, `04_CONTENT_INTEGRATION_PLAN.md`, `08_DIGITAL_SYSTEMS/DATA_MODEL.md`, `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`, `00_GOVERNANCE/TECH_STACK.md`.

## Note on scope

This document plans the architecture only. It does not add a component, write a route, change `src/app/[locale]/layout.tsx`, add a Prisma model, or select a visual treatment beyond citing the already-approved design tokens. No code or design change is made.

---

## Owner-Approved Decisions (2026-07-28)

The following are ratified and are now binding on this plan, superseding the corresponding provisional recommendations in v1.0/v1.1:

1. **Dismiss behavior:** if a user dismisses an announcement, it stays hidden for that user until the announcement's *content* changes — a dismissed announcement is never shown again to that user in its current form. See §1 and §6 for the content-identity mechanism this implies.
2. **Priority order** (highest to lowest): (1) Important service notices, (2) Limited-time offers, (3) New articles, (4) General announcements. See §3 and §7 for the updated type taxonomy and scheduling rules.
3. **Display rules:** exactly one active announcement at a time; no automatic rotation; no fixed positioning; Core Web Vitals must be preserved. All four were already this plan's v1.0 recommendation (§2, §7, §9) — they are now Owner-ratified requirements, not proposals.

---

## 0. Governing Constraint (read first)

`12_DESIGN_SYSTEM/COMPONENTS.md`'s 13-component inventory (Header, Navigation, Hero, CTA, Service Grid, Location, Booking Widget, Review, FAQ, Gallery, Map, Contact, Footer) **does not include an announcement/news bar.** This plan proposes it as a new, 14th component — the design system itself needs a small registration update once this architecture is approved, not a silent addition.

`08_DIGITAL_SYSTEMS/DATA_MODEL.md`'s Core Entities list has no `Announcement`/`Notice` entity. Exactly as with the authentication plan (`08_AUTHENTICATION_ARCHITECTURE.md` §12), **any database-backed, admin-manageable version of this component requires a `DATA_MODEL.md` governance amendment first.** This plan is structured (§7) so a lightweight, no-schema-change v1 is possible without that amendment, deferring the database-backed version to a later, separately approved phase.

**Commercial content constraint — the most important content-policy rule in this plan:** an "Offers" announcement that names a discount, price, or promotional term is a commercial claim. Per `AUTONOMY_AND_APPROVAL_MATRIX.md`, "Quote a price or warranty" is `A4` — owner approval every time, no template exception. This bar is a *placement* mechanism, not a new approval bypass — every Offer message still needs the same commercial sign-off any price/discount would need anywhere else on the site.

---

## 1. Purpose and UX Goals

- Give the site one clear, consistent place to surface time-relevant, site-wide messages (a new article, a service-availability note, an approved offer, a genuinely important notice) without editing page content or redeploying for every message change.
- **Calm, not urgent** — per `LUXURY_DESIGN_DIRECTION.md`'s "Quiet Luxury" principle, this is an information surface, not an attention-grabbing device. One message at a time, no flashing, no auto-rotating carousel of competing claims (§10 of that document explicitly prohibits "carousels for critical information" and "fake urgency, countdown timers, or misleading scarcity").
- **Dismissible and unobtrusive** — **(Owner-approved, 2026-07-28)** once a user dismisses an announcement, it stays hidden for that user until the announcement's content changes; the same dismissed announcement is never shown again in its unchanged form. Mechanically, this means dismissal is tracked against a content-identity key (announcement id **plus** a content version/hash), not just the id alone — editing an announcement's text produces a new key and makes it eligible to show again, exactly as intended. It must also never block or delay access to the page's actual content (`LUXURY_DESIGN_DIRECTION.md` §7: "no animation may delay access to essential content").
- **Truthful by construction** — the content types in §3 are deliberately narrow so the bar cannot become a place where an unapproved claim slips onto every page at once; a site-wide surface is exactly where a Hard Publication Block violation would have the widest blast radius.

## 2. Placement Strategy

- **Position:** **(Owner-approved, 2026-07-28: no fixed positioning)** a single, non-fixed (normal document flow) bar rendered at the very top of `<body>`, above `<Header>`, in `src/app/[locale]/layout.tsx`. The layout already coordinates two independent *fixed*-position elements at the bottom (`MobileCtaBar` and `ConsentBanner`, which already adjust for each other's height via `bottom-20`/`bottom-0`); a fixed top bar was considered and is explicitly rejected by this decision.
- **Scope:** site-wide by default (every locale, every page), since the layout file it lives in wraps all pages. A future per-page or per-section suppression rule (e.g., hide on the checkout/booking flow) is a valid future refinement, not designed in detail here.
- **Stacking order:** renders once, above `Header`, so it never competes with the header's own sticky behavior (`Header` is `sticky top-0` today) — the bar simply scrolls away with the rest of the page content above the sticky header, which then takes over the top of the viewport.
- **One bar, one active announcement, no rotation** — **(Owner-approved, 2026-07-28)** if multiple announcements are active simultaneously, the priority order in §3 decides which single one shows. There is no rotation, carousel, or cycling between them — the others simply wait their turn until they're the highest-priority active item or their window ends.

## 3. Announcement Types

**(Owner-approved priority order, 2026-07-28)** — highest to lowest:

| Priority | Type | Purpose | Content constraint |
|---|---|---|---|
| 1 | **Important Service Notices** | Operational or safety-relevant notices (e.g., temporary unavailability in an area, a schedule change, a holiday closure) | Must reference only approved `SERVICE_CATALOG.md`/`SERVICE_AREAS.md` facts and/or Owner-sourced safety/legal communication — no invented coverage, no unapproved response-time claim. Highest priority; may be open-ended (§7). |
| 2 | **Limited-Time Offers** | An approved, time-bound promotion or discount | Every price/discount/term is `A4` — owner-approved per instance, exactly like any other commercial claim on the site (§0). The bar template must not allow free-text price entry without that approval already having happened elsewhere. `endAt` is mandatory (§7) — "limited-time" is enforced by the schedule, not just the name. |
| 3 | **New Articles** | Surface a newly published blog post | Must link to a real, already-published (non-`isDemo`) post per `src/lib/catalog/blog.ts`'s existing publishability rule — never a post that isn't live yet. |
| 4 | **General Announcements** | Anything else that doesn't fit the three types above (e.g., a general update or non-urgent communication) | Lowest priority; content sourced from the Owner directly, not inferred — this is a catch-all category, not a way to bypass the more specific rules above. |

Every type shares one underlying shape (message, optional CTA, start/end date, priority, locale pair, content-version key for dismissal per §1/§6) — four *content categories*, not four different components.

**Reconciliation note:** this table supersedes v1.0's original four-type list, per the Owner's 2026-07-28 decision. Mapping for traceability: "Service Alerts" → **Important Service Notices**; "Offers" → **Limited-Time Offers**; "Important Notices" → folded into **Important Service Notices** (safety/legal) and **General Announcements** (everything else) depending on content; "New Articles" is unchanged.

## 4. Arabic/English Support

- Every announcement is authored as a **paired** `{ ar: string; en: string }` message (and CTA label, if present) — mirroring the existing bilingual-content discipline already used throughout the app's `i18n/messages/{ar,en}.json` and the blog's `title: { en, ar }` pattern in `src/lib/catalog/blog.ts`.
- No announcement may go live in only one language — per `PROJECT_MANIFEST.md`'s "Arabic and English are equal first-class languages," publishing an English-only offer with no Arabic counterpart (or vice versa) is not an acceptable partial-publish state.
- Phrasing may legitimately differ by language; the underlying fact (the offer, the date, the notice) must not diverge — the same rule already applied to service content in `04_CONTENT_INTEGRATION_PLAN.md` §4.

## 5. RTL Requirements

- The bar's internal layout (message, optional CTA link/button, dismiss control) must use logical properties (`start-`/`end-`), exactly as `BrandPanel` and the header/footer already do — no hardcoded `left`/`right`.
- A CTA arrow icon, if used, follows the same `rtl:rotate-180` pattern already established for `ArrowRightIcon` on service cards (`09_VISUAL_REVIEW_REPORT.md` confirmed this pattern works correctly today) — directional icons mirror, universal icons (the dismiss "×") do not, per `SIDEBAR_NAVIGATION.md`'s existing icon-mirroring rule.
- Dismiss control position (typically the trailing edge) must resolve correctly per locale via `end-` rather than a fixed side.

## 6. Admin Management Requirements

Two viable phases, deliberately separated so a real database/admin UI is not a prerequisite for shipping v1:

- **Phase A (no schema change, no admin UI):** announcements authored as a small, structured array in the codebase (mirroring `BLOG_POSTS`/`SERVICES`'s existing catalog-array pattern) — a content change requires a code review and deploy, same as adding a blog post today. This avoids the `DATA_MODEL.md` blocker entirely and can ship inside the app's existing architecture with no new persistence layer.
- **Phase B (future, requires the `DATA_MODEL.md` amendment from §0):** a real `Announcement` entity manageable from an eventual Owner Dashboard (`CRM_AND_PORTALS.md`'s "content/publication state" minimum), with create/edit/schedule/retire actions and an audit trail consistent with the existing `AuditEvent` pattern (`announcement.created`, `announcement.published`, `announcement.retired`).
- **Either phase:** publishing a new or edited announcement remains a content-governance action under this repository's existing rules — a Limited-Time Offer specifically still needs its commercial approval evidence attached before it can be marked publishable (§0), regardless of which phase built the mechanism.
- **Content-version key (per the Owner's dismiss-behavior decision, §1):** every announcement needs a stable id plus a version/hash that changes whenever its message content is edited. Phase A can derive this from the array entry itself (e.g., a hash of the message text); Phase B would add it as a field on the `Announcement` entity. Either way, editing an announcement's wording is what makes it eligible to reappear for users who previously dismissed the old version — this is the mechanism, not a policy left to the client to interpret.

## 7. Start/End Scheduling

- Every announcement carries `startAt`/`endAt` timestamps; the bar renders the single highest-priority announcement (per §3's Owner-approved order) whose current time falls within its window, or nothing if none is active — never a stale, expired message left visible by omission.
- `endAt` is **mandatory**, not optional, for Limited-Time Offers and New Articles (time-bound by nature); `Important Service Notices` may be open-ended (e.g., a standing safety notice) but should still be reviewed periodically, not left indefinitely without owner reconfirmation. `General Announcements` should generally carry an `endAt` too, being the lowest-priority, most easily forgotten category.
- No countdown timer is rendered against `endAt` — per `LUXURY_DESIGN_DIRECTION.md` §10's explicit prohibition on countdown timers/fake urgency; the end date governs visibility, it is not displayed as a ticking clock.

## 8. CTA Links

- At most one CTA per announcement (consistent with `BUTTONS.md`'s "no more than one Primary button per section" rule, applied here at the bar level).
- CTA target must be an existing, valid internal route (a service page, the specific blog post, the contact page) or a canonical external link already approved elsewhere (e.g., the approved WhatsApp link from `CONTACT_INFORMATION.md`) — never a freshly invented URL.
- CTA label text follows `BUTTONS.md`'s existing rule against vague labels ("Click Here") — a direct action label instead ("Read the Article," "View Offer," "Contact Us").

## 9. SEO Considerations

- The bar is a UI/navigation element, not indexable content in its own right — it should not be the sole place a fact appears (e.g., a "new article" announcement links to the article; the article itself carries the real metadata/schema per `05_SEO_IMPLEMENTATION_PLAN.md`, not the bar).
- No announcement text should be keyword-stuffed or duplicated across pages in a way that reads as manipulative — it's a small, honest notice, consistent with `LUXURY_DESIGN_DIRECTION.md` §10's prohibition on "keyword-stuffed headings and repetitive location copy."
- **(Owner-approved, 2026-07-28: Core Web Vitals must be preserved)** if the bar is ever server-rendered with real content (not a client-only overlay), it must not introduce layout shift that harms Core Web Vitals (`05_SEO_IMPLEMENTATION_PLAN.md` §1's performance requirement) — reserving its height rather than popping in after hydration is a hard requirement for whoever builds this, not a nice-to-have.

## 10. Mobile Behavior

- Sits above `Header` in normal flow on mobile exactly as on desktop — no special fixed/floating mobile treatment, avoiding any new interaction with `MobileCtaBar`'s existing fixed bottom bar.
- Must remain readable and tappable at narrow widths without truncating the message into meaninglessness — a short-message-length constraint is a content-authoring rule (§3's types are inherently short: an offer headline, an article title, a one-line notice), not a layout hack.
- Dismiss control must meet the same 44×44px minimum touch target already established for `MobileCtaBar`'s icon buttons (`BUTTON_ICON_REVIEW.md` precedent).

## 11. Accessibility Requirements

Per `12_DESIGN_SYSTEM/ACCESSIBILITY.md` (WCAG 2.2 AA target) and `LUXURY_DESIGN_DIRECTION.md` §9:

- Semantic markup: an `role="region"` (or `status`/`banner` as appropriate to whether it's purely informational or time-sensitive) with an accessible name, not a bare `<div>`.
- Visible keyboard focus on both the CTA and the dismiss control, reachable and operable via Tab/Enter without a mouse.
- Color is never the only signal — an "Important Notice" must be distinguishable by icon/label text, not red-background alone, per `ACCESSIBILITY.md`'s explicit "red = error only" anti-pattern warning.
- Dismissing the bar must not trap focus or leave a keyboard user stranded — focus should move sensibly to the page content (typically the skip-to-content target or the header) after dismissal.
- Respect reduced-motion preferences for any show/dismiss transition (a simple fade/slide, not a bounce or attention animation) — consistent with `LUXURY_DESIGN_DIRECTION.md` §7.

## 12. Analytics Tracking

- Any tracking is gated by the same consent choice already governing `GoogleTagManager` (`src/components/consent-banner.tsx` → `GoogleTagManager`) — an announcement's impression/click/dismiss events are not a separate bypass of that gate. If consent hasn't been granted, no event fires, exactly like every other tracked interaction on the site today.
- **Events proposed:** `announcement_impression` (bar shown, by type and id), `announcement_cta_click`, `announcement_dismiss` — pushed to the existing `dataLayer` pattern already used by `GoogleTagManager`, not a new analytics mechanism.
- Per `05_SEO_IMPLEMENTATION_PLAN.md` §7's existing rule, event tracking "must not capture more personal data than the `Consent` and `Interaction` entities already permit" — these events carry no personal data at all (announcement id/type only), so they don't raise a new data-minimization question.
- Phase A (§6) can log these client-side to GTM with no backend change; a Phase B, DB-backed version could additionally write to the existing `Interaction` entity for internal reporting (e.g., "which offer got the most clicks") — an additive future option, not required for v1.
- GA4/Search Console/GTM remain in **test mode** until the Owner authorizes live tracking, per `IMPLEMENTATION_READINESS_REPORT.md`'s existing prohibition on live external-channel connections without a confirmed gate — this plan does not change that status.

## 13. Future WordPress/CMS Compatibility

- Per `DECISION_LOG.md`/`TECH_STACK.md`, WordPress remains explicitly non-canonical research (`07_WEBSITE/WORDPRESS/`) and cannot drive implementation without a new Owner decision — this plan does not assume WordPress and is designed entirely around the current Next.js catalog-array pattern (§6 Phase A).
- If a future headless CMS (WordPress-as-API or otherwise) is ever approved, the announcement bar's content shape (message pair, CTA, schedule, priority, type) is intentionally generic enough to be sourced from a CMS API instead of the in-repo array **without changing the rendering component** — the swap would happen at the content-adapter layer (`04_CONTENT_INTEGRATION_PLAN.md`'s existing pattern: adapters read from a source, components stay dumb), not by rewriting the bar itself.
- No CMS integration, credential, or dependency is proposed or added by this document.

## 14. AI Content Integration Possibility

- **Drafting, not publishing:** per `00_GOVERNANCE/AI_OPERATING_MODEL.md`'s `A1` default ("draft only"), a governed agent may propose announcement copy (e.g., summarizing a newly published blog post into a one-line bar message per §3's "New Articles" type) — it may never mark that draft live. Publishing an announcement remains a governed, approved action exactly like publishing any other content, and an Offer-type draft still needs its separate commercial approval (§0) regardless of who wrote the words.
- **Read access for a future customer-facing assistant:** if a future AI assistant (per `09_AI_KNOWLEDGE/ANSWER_POLICY.md`) is asked something like "any current offers?", it should read the same active-announcement source this bar renders from — not a separate, looser index — matching the "no separate AI-only data path" principle already established in `08_AUTHENTICATION_ARCHITECTURE.md` §15 for customer data generally.
- **No autonomous scheduling by AI:** an agent may propose a `startAt`/`endAt` window as part of a draft, but activating it is still the same approval action as activating any other announcement — this plan does not create an AI-specific fast path around §6/§7's approval and scheduling rules.
- This is a forward-looking possibility, not a design commitment — no AI drafting workflow is built by this document.

## 15. Scalability Considerations

- **Phase A array growth:** the in-repo announcement array (§6) will accumulate entries over time exactly like `BLOG_POSTS` does; expired entries should be pruned or archived periodically (a content-hygiene practice, not a technical requirement) rather than left to grow unbounded in the codebase.
- **Query pattern at Phase B:** once a real `Announcement` entity exists (§6 Phase B), selecting "the active, highest-priority announcement" becomes a simple date-range-and-priority query rather than a full-array scan — a natural improvement that falls out of the Phase A→B move already planned, not a separate scaling project.
- **Caching/ISR interaction:** if any page rendering the bar uses Incremental Static Regeneration, the revalidation window must be short enough that an expired `endAt` doesn't linger visibly past its scheduled end on a statically cached page — a concrete implementation constraint to carry into whichever phase actually builds this, not solved here.
- **Priority-conflict volume:** §3's four types plus §2's "one at a time" rule keep the display logic O(1) per page render regardless of how many announcements exist in storage — the array/table can grow without the rendering cost growing with it, provided the "find the active one" query (however implemented) is indexed/bounded by date rather than scanning every historical entry.
- **Multi-locale is already handled**, not a future scaling concern — §4's paired-message shape means adding a locale later (if the site ever did) would extend the message shape, not redesign the scheduling/priority logic.

---

## What This Document Does Not Do

- Does not create the component, add it to `layout.tsx`, or write any code.
- Does not add an `Announcement` entity to `prisma/schema.prisma` or `DATA_MODEL.md`.
- Does not register the component in `12_DESIGN_SYSTEM/COMPONENTS.md` — that update happens if and when this plan is approved.
- Does not approve, draft, or imply any specific offer, discount, or notice content.
- Does not select a WordPress/CMS path — §13 keeps the door open without opening it.
- Does not build any AI drafting workflow — §14 is a possibility, not a commitment.
- Does not add any analytics dependency — §12 reuses the existing GTM/consent mechanism only.

---

## Related Documents

- `12_DESIGN_SYSTEM/COMPONENTS.md`
- `12_DESIGN_SYSTEM/ACCESSIBILITY.md`
- `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md`
- `12_DESIGN_SYSTEM/BUTTONS.md`
- `05_SEO_IMPLEMENTATION_PLAN.md`
- `04_CONTENT_INTEGRATION_PLAN.md`
- `08_DIGITAL_SYSTEMS/DATA_MODEL.md`
- `08_DIGITAL_SYSTEMS/CRM_AND_PORTALS.md`
- `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`
- `00_GOVERNANCE/TECH_STACK.md`
- `07_WEBSITE/IMPLEMENTATION/08_AUTHENTICATION_ARCHITECTURE.md`
