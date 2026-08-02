# Homepage Content Review Report

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — review and recommendation only; does not itself approve, publish, or implement anything
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, review/recommendation only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Reviews:** `00_GOVERNANCE/HOMEPAGE_CONTENT_DRAFT.md` v1.0, unmodified by this report
- **Scope:** Review only. No draft content was rewritten, no code/component/page/asset/translation was touched, nothing staged or committed.

## Purpose

Prepare `00_GOVERNANCE/HOMEPAGE_CONTENT_DRAFT.md` for Owner review by sorting its 10 sections into what can be approved now, what needs an Owner decision first, where the Arabic needs a closer look, which claims were deliberately left out and why, what business facts are still missing, and in what order approval should happen.

---

## 1. Content Sections Ready for Approval

These sections draw every fact from an already-approved or canonical source; only the exact wording (not the underlying facts) awaits sign-off, and none has an open structural gap:

| Section | Why it's ready |
|---|---|
| **Company Introduction (§2)** facts | Company Overview and Mission Statement both come from canonical, unambiguous sources (`COMPANY_PROFILE.md`, `MISSION.md`); the quotation-before-work line is the one fully-answered fact in `GENERAL_SERVICE_FAQ_DRAFT.md`. |
| **Cleaning category (§3)** | Title, description, and benefit are copied from `03_GENERAL_CLEANING/CONTENT_EN.md`/`CONTENT_AR.md`, which now carries "Approved — General Operational Content" status (`DECISION_LOG.md` #38). |
| **Pest Control category (§3)** | Title, description, and benefit are copied from `01_PEST_CONTROL/06_PAGE_CONTENT.md`, "Approved — General Page Content" (`DECISION_LOG.md` #37) — the single most content-mature service in the catalog. |
| **Emirates Coverage (§4)** | Directly and completely sourced from `03_MARKET/SERVICE_AREAS.md`'s Approved Registry; all 7 emirates, no city/district overreach. |
| **Why Choose Us (§5)** | Every bullet is non-numeric and traceable to an approved source (contact channels, quotation process, property-specific approach already used in the two approved service descriptions). |
| **How It Works (§6)** | Built entirely from approved contact channels and the one approved process fact; no timeframe stated. |
| **Book Appointment CTA wording (§7)** | "Book Appointment"/"احجز موعد" is not new — it is the Owner-fixed pattern already in use in `07_WEBSITE/NAVIGATION_ARCHITECTURE.md`. |
| **3 included FAQ pairs (§8)** | Emirates coverage, booking channels, and quotation-before-work — each traceable to an approved source, not the drafting agent's judgment call. |

**Recommendation:** these can be approved as a block, since none of them depends on a decision that's still open elsewhere in the repository.

---

## 2. Sections Requiring Owner Decision

| Section | Decision needed |
|---|---|
| **Hero headline/subtitle (§1)** | No headline or subtitle has ever been marked Approved anywhere in this repository — the Owner needs to confirm or revise this specific first-draft wording (not the facts behind it, which are already approved: brand positioning, tagline, booking mechanics). |
| **Maintenance category (§3)** | The largest open item. No approved customer-facing description exists for AC Maintenance, Plumbing, Electrical Maintenance, Painting, or Handyman Services — only the service *names* are approved. The Owner must choose one of: (a) publish the Maintenance card with just the category name and no description until real content exists, (b) hold the entire Maintenance card out of the homepage until content is authored, or (c) authorize a content-authoring or import pass (see `SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`'s "Remaining Gaps") before publishing. This draft did not pick one of these for the Owner. |
| **Book Appointment section wording (§7)** | The CTA pattern itself is fixed and approved; the heading/description sentence wording is still first-draft and needs sign-off. |
| **SEO title/meta/keywords (§9)** | Entirely draft direction — no homepage-level SEO copy has ever been approved, and no keyword listed has any real research behind it. The Owner should decide whether to approve this as a starting direction or commission real keyword research first. |
| **6 pending FAQ questions (§8)** | Each requires a separate upstream decision before it can even be drafted: emergency-service policy, AMC packages, payment methods, warranty terms, response-time commitment, rescheduling rules. These are commercial/policy decisions, not wording decisions — no amount of copyediting resolves them. |

---

## 3. Arabic Wording Review Points

- **Company Introduction (§2):** the Arabic paragraph is a first adaptation of the approved English facts — no prior approved Arabic company-introduction text existed anywhere in the repository before this draft. This is the single highest-priority Arabic item: it should get a native/professional Arabic-quality pass (tone, natural phrasing, register) before publication, consistent with the same caution already applied elsewhere in this repository to newly-drafted Arabic (e.g., `SERVICE_MASTER_DATABASE.md`'s treatment of Arabic service names as "accurate-but-unreviewed").
- **Hero headline/subtitle (§1):** also first-draft Arabic, not yet checked by a native speaker beyond the drafting pass itself.
- **Cleaning and Pest Control Arabic (§3):** lower risk — this Arabic text is copied verbatim from already-approved package files, not newly written, so it inherits whatever review those files already received rather than introducing a new unreviewed pass.
- **Why Choose Us, How It Works, FAQ (§§5, 6, 8):** newly composed Arabic, same category as the Hero and Company Introduction — first draft, not yet Arabic-reviewed.
- **General note:** none of the newly-written Arabic in this draft (as opposed to the Arabic copied from already-approved service files) has been through a dedicated linguistic review pass. The Owner should treat "sourced from an approved fact" and "Arabic wording is review-ready" as two separate questions — the draft is clean on the first, open on the second, for every section except Cleaning and Pest Control.

---

## 4. Claims Intentionally Excluded

These were deliberately left out of the draft, not overlooked:

- **Years in business / founding date** — no figure exists anywhere in the repository.
- **Certifications, licenses, or accreditation claims** — none evidenced; every per-service Evidence Gate explicitly withholds these.
- **Awards or recognition** — none exist.
- **Customer counts, completed-job counts, or "trusted by X"** — no figure exists.
- **Reviews, ratings, or testimonials** — none exist anywhere in the repository, with no consent or provenance trail for any; the draft has no testimonials section at all rather than a placeholder.
- **Response-time or emergency-service commitments** — `CONTACT_INFORMATION.md` marks Emergency Service Pending; no claim was made.
- **Warranty or guarantee language** — commercial/warranty facts are `06_CUSTOMER_AND_SALES`-owned and `A4`-gated; none exists to draw from.
- **"Fast Response" / "Guaranteed Quality" as literal claims** — these two phrases appear in `02_BRAND/BRAND_IDENTITY.md`'s "Brand Promise" as tagline/brand-voice language, but the draft deliberately does not reuse them as literal customer commitments anywhere, since doing so would read as an unevidenced response-time or guarantee claim.
- **"Certified," "licensed," "municipality-compliant"** — flagged by `01_PEST_CONTROL/01_SERVICE_PROFILE.md` as not-yet-approved phrasing; none used.

---

## 5. Missing Business Information Required Before Publishing

- **Maintenance-category content** — no description or benefit statement exists for AC Maintenance, Plumbing, Electrical Maintenance, Painting, or Handyman Services (see §2 above). This is the single largest blocker to a complete Services section.
- **Emergency-service policy** — availability, scope, and any response commitment (`CONTACT_INFORMATION.md`: Pending).
- **Annual Maintenance Contract (AMC) terms** — whether this package exists and what it includes.
- **Accepted payment methods.**
- **Warranty/guarantee policy** — what, if anything, is actually offered.
- **Physical/headquarters address** — still under Owner Verification in `COMPANY_PROFILE.md`, separate from the already-approved phone/domain/WhatsApp/email.
- **Real keyword research** — no search-volume, ranking, or competitor data exists for any keyword in §9; needed before the SEO direction becomes a real target rather than a placeholder.
- **Booking-confirmation speed / staff-notification status** — referenced in the draft's Book Appointment section as an open operational question, not just a copywriting one.

None of the above can be resolved by rewording the draft — each requires an Owner or upstream-document decision first.

---

## 6. Recommended Approval Order

1. **Approve the fact-ready block first (§1 of this report)** — Company Introduction facts, Cleaning, Pest Control, Emirates Coverage, Why Choose Us, How It Works, Book Appointment CTA pattern, and the 3 approved FAQ pairs. Nothing here is blocked on a new decision; approving this block unblocks the largest share of homepage content immediately.
2. **Decide the Hero headline/subtitle wording** — highest visibility, no dependency on any other open item, quick to resolve once reviewed.
3. **Decide the Maintenance-category treatment** — the largest structural gap; resolving this (publish name-only, hold the card, or commission real content) determines how much of the Services section can go live at all.
4. **Confirm Book Appointment section wording** (heading/description sentence) — low effort, no dependency, can move alongside step 2.
5. **Decide the SEO direction (§9)** — approve as a starting point or commission keyword research first; does not block any other section's approval.
6. **Address the 6 pending FAQ questions and the "Missing Business Information" list (§5) as separate, slower-moving policy decisions** — these do not need to be resolved before the rest of the homepage launches, since the draft already treats them as absent rather than as blockers to the sections that don't depend on them.

---

## What This Report Does Not Do

- Does not modify `00_GOVERNANCE/HOMEPAGE_CONTENT_DRAFT.md`.
- Does not rewrite, add, or remove any content.
- Does not implement, publish, or approve anything.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/HOMEPAGE_CONTENT_DRAFT.md` — the document under review
- `00_GOVERNANCE/HOMEPAGE_CONTENT_IMPLEMENTATION_PLAN.md`
- `00_GOVERNANCE/SERVICE_KNOWLEDGE_SYNC_EXECUTION_REPORT.md`
- `00_GOVERNANCE/CONTACT_INFORMATION_DECISION_UPDATE.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
- `03_MARKET/SERVICE_AREAS.md`
