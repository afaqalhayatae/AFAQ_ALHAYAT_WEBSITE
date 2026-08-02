# Homepage Content Approval Decision

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — presents open decisions only; no option is selected by this document
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning/recommendation only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Source:** `00_GOVERNANCE/HOMEPAGE_CONTENT_DRAFT.md` v1.0 and `00_GOVERNANCE/HOMEPAGE_CONTENT_REVIEW_REPORT.md` v1.0 — neither modified by this document.
- **Scope:** Decision document only. No homepage draft, website code, translation, or content file was modified. Nothing staged or committed.

## Purpose

Isolate the four unresolved decisions the review report identified as blocking full sign-off of `HOMEPAGE_CONTENT_DRAFT.md`, state the current situation and real options for each without picking one, and record exactly what the Owner needs to choose. Per this repository's own conflict-handling rule (`00_GOVERNANCE/ENTERPRISE_PUBLICATION_GATE_MODEL.md` §15), an agent does not resolve an open Owner-level decision on its own authority — it records it.

---

## Decision 1 — Hero Headline and Subtitle Approval

### Current situation

`HOMEPAGE_CONTENT_DRAFT.md` §1 proposes a first-draft Arabic headline and subtitle, with an English adaptation, built from already-approved facts (brand positioning and tagline in `02_BRAND/BRAND_IDENTITY.md`, the booking-mechanic subtitle framing already used in `HOMEPAGE_CONTENT_IMPLEMENTATION_PLAN.md` §2). No headline or subtitle of any kind has ever been marked Approved anywhere in this repository — this is the first time exact wording has been drafted for Owner review.

### Available options

- **Approve as drafted** — use the proposed Arabic/English headline and subtitle exactly as written in the draft.
- **Approve with edits** — keep the same underlying facts (positioning, tagline, booking mechanic) but request specific wording changes.
- **Reject and request a new draft** — the facts stand, but none of the proposed phrasing is acceptable; a new wording pass is needed.

### Impact

- Approving as drafted or with minor edits unblocks the single most visible piece of homepage content with no dependency on any other open item.
- Requesting a new draft delays the Hero section specifically but does not block any other section's approval — the other three decisions in this document are independent of this one.
- No option here changes what facts may be claimed; all three options operate strictly within the already-approved positioning/tagline material.

### Required Owner choice

Approve as drafted, approve with specific edits, or reject and request a new draft — and if edits or rejection, what direction the new wording should take.

---

## Decision 2 — Maintenance Section Treatment

### Current situation

Per `HOMEPAGE_CONTENT_DRAFT.md` §3 and `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`, the Maintenance category (AC Maintenance, Plumbing, Electrical Maintenance, Painting, Handyman Services) is catalog-approved as a category, but none of the five services has any approved customer-facing description or benefit statement anywhere in this repository — their in-repo package files are empty governance templates, not populated content. This is the largest structural gap in the draft.

### Available options

- **Publish names only** — show the Maintenance card on the homepage with the category title and the five service names, no description or benefit copy, until real content exists.
- **Hide temporarily** — omit the Maintenance card from the homepage entirely until content is authored, showing only Cleaning and Pest Control in the Services section for now.
- **Create a Maintenance content phase first** — commission or import real descriptive content for the five services (see `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`'s "Remaining Gaps" on sourcing this from the external `afaqalhayatae-app` repository or authoring it fresh) before the homepage launches with three complete category cards.

### Impact

- **Publish names only** is fastest to launch but leaves one of three homepage service categories visibly thinner than the other two, which may look incomplete to visitors.
- **Hide temporarily** presents a fully polished two-category homepage sooner, but understates the company's actual service range (Maintenance is a real, approved, larger part of the catalog) until the card is restored.
- **Content phase first** produces the most complete and even homepage but delays the whole homepage launch on new content work, and that work itself would need its own review pass (per `SERVICE_KNOWLEDGE_SYNC_PLAN.md`'s no-fabrication rules) before publication.
- This decision does not affect Decisions 1, 3, or 4 — the homepage can launch with any of these three Maintenance treatments while the other decisions are settled independently.

### Required Owner choice

One of: publish names only, hide temporarily, or create a Maintenance content phase first — and if the third, what scope and timeline that phase should have.

---

## Decision 3 — Book Appointment Section Wording Approval

### Current situation

`HOMEPAGE_CONTENT_DRAFT.md` §7 uses the Owner-fixed CTA pattern "Book Appointment" / "احجز موعد," which is already established elsewhere in this repository (`07_WEBSITE/NAVIGATION_ARCHITECTURE.md`) and is not itself in question. What remains open is the heading and one-sentence description around that CTA — first-draft wording, not yet reviewed.

### Available options

- **Approve as drafted** — use the proposed heading and description sentence exactly as written.
- **Approve with edits** — keep the fixed CTA pattern but adjust the surrounding heading/description wording.
- **Reject and request a new draft** — keep the CTA pattern, discard the surrounding sentence and request new wording.

### Impact

- The CTA wording itself ("Book Appointment"/"احجز موعد") is unaffected by any of these options — it is already settled policy, not part of this decision.
- Approving or lightly editing the surrounding copy is low-effort and has no dependency on Decisions 1, 2, or 4.
- This section's description already notes that booking-confirmation speed is an open operational question (staff-notification automation not yet confirmed live) — none of the three wording options resolves that operational point; it is a separate, non-copywriting item noted in the draft's Content Gaps.

### Required Owner choice

Approve as drafted, approve with specific edits, or reject and request new heading/description wording — the CTA pattern itself does not need re-deciding.

---

## Decision 4 — SEO Direction Approval

### Current situation

`HOMEPAGE_CONTENT_DRAFT.md` §9 proposes a homepage-level SEO title, meta description, and keyword list in both languages. No homepage SEO copy has ever been approved anywhere in this repository, and — consistent with `07_WEBSITE/IMPLEMENTATION/14_SERVICE_CONTENT_PRODUCTION_MATRIX.md`'s own standing caveat — none of the listed keywords have any real search-volume, ranking, or competitor research behind them; they are structurally-derived illustrative candidates only.

### Available options

- **Approve as a starting direction** — accept the drafted title/meta/keywords as a reasonable placeholder direction, to be refined later once real keyword research exists.
- **Commission real keyword research first** — hold SEO copy finalization until actual search-volume/competitor data is available, then revisit this section.
- **Approve title/meta wording now, defer keywords** — treat the customer-facing title and meta description as ready to approve (they read naturally regardless of keyword validity), while explicitly holding the keyword list as unresearched and non-binding until real data exists.

### Impact

- Approving as a starting direction lets implementation proceed sooner but risks the keyword targets needing revision once real research happens — low cost, since keywords are typically easy to update without a full content rewrite.
- Commissioning research first delays any SEO-driven implementation work but avoids optimizing around unvalidated targets.
- The third, split option isolates the lower-risk piece (visible title/description copy) from the higher-risk piece (keyword targeting), letting content work proceed while research runs in parallel.
- None of these options changes any factual claim in the title/meta text itself — all three already exclude price, certification, and other gated claims per the draft.

### Required Owner choice

Approve as a starting direction, commission research first, or approve title/meta now while deferring the keyword list — and if research is commissioned, who performs it and on what timeline.

---

## What This Document Does Not Do

- Does not modify `HOMEPAGE_CONTENT_DRAFT.md` or `HOMEPAGE_CONTENT_REVIEW_REPORT.md`.
- Does not modify any website code, translation file, or content file.
- Does not select an option for any of the four decisions.
- Does not implement, publish, or approve anything.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/HOMEPAGE_CONTENT_DRAFT.md`
- `00_GOVERNANCE/HOMEPAGE_CONTENT_REVIEW_REPORT.md`
- `00_GOVERNANCE/HOMEPAGE_CONTENT_IMPLEMENTATION_PLAN.md`
- `00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`
- `07_WEBSITE/NAVIGATION_ARCHITECTURE.md`
