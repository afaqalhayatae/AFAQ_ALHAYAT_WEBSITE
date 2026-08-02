# Painting SEO Decision Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only; presents decision options, does not select or apply any of them; no content migrated
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Prepared by:** AI Agent (A1, planning only — see `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`)
- **Source:** `00_GOVERNANCE/PAINTING_CONTENT_SOURCE_REVIEW_PLAN.md` (§4 hero-tagline note, §5 "Villa Painting" finding, §4 drying-time FAQ distinction)
- **Purpose:** Resolve the Painting content governance cycle's open decisions before a Sync Execution Plan is written — Villa Painting keyword, hero tagline handling, paint-drying FAQ handling rules, and CTA pattern confirmation.
- **Scope:** Planning only. No service file, `README.md`, or website file was modified. No content was migrated. Nothing staged or committed.

---

## 1. Villa Painting Keyword Decision

**Finding restated (`PAINTING_CONTENT_SOURCE_REVIEW_PLAN.md` §5):** the English keyword "Villa Painting" risks implying full villa exterior-painting capability, including height-access work, while Scope — Excluded disclaims "work at heights requiring specialized access equipment beyond standard reach." Scope — Included covers exterior painting only "where accessible."

**No option is selected here.** Options for the Owner's decision:

### Option A: Remove the keyword
Drop "Villa Painting" (and its Arabic equivalent, "دهان فلل") from the migrated keyword list, mirroring the resolution already applied to AC Maintenance's "AC Repair UAE" and Electrical Maintenance's "Distribution Panel Repair"/Arabic equivalent.

### Option B: Keep the keyword as-is
Accept that most villas' exterior surfaces fall within standard-reach access in practice, and that the Scope — Excluded wording already qualifies the claim ("beyond standard reach," not an absolute prohibition on villa exteriors). No change to the keyword list.

### Option C: Qualify the scope wording instead of removing the keyword
Adjust `CONTENT_EN.md`/`CONTENT_AR.md`'s Scope — Included wording to explicitly state that exterior painting (including typical villa exteriors) is covered within standard reach, making the keyword's implied claim and the documented scope explicitly consistent, without removing a keyword that may have real SEO value.

---

## 2. Hero Tagline Handling Decision

**Finding restated (`PAINTING_CONTENT_SOURCE_REVIEW_PLAN.md` §4):** the source `heroTagline` — "Fresh walls, flawless finish — professional painting for homes and businesses across the UAE" — uses "flawless finish," the closest language in this record to an absolute-outcome claim, though it appears in a tagline/hook position rather than as a body-content commitment.

**No option is selected here.** Options for the Owner's decision:

### Option A: Migrate as-is
Treat "flawless finish" as brand-tagline/hook language, analogous to the already-accepted treatment of `02_BRAND/BRAND_IDENTITY.md`'s "Brand Promise" tagline wording (`HOMEPAGE_CONTENT_IMPLEMENTATION_PLAN.md` §5) — a hook phrase, not a literal quality guarantee, and migrate the Short Description field unchanged.

### Option B: Reword before migration
Replace "flawless finish" with hedged language consistent with the rest of the record's tone (e.g., "a clean, refreshed finish"), removing even the tagline-level absolute-outcome word before it enters the knowledge base.

### Option C: Migrate as-is now, flag for a later company-wide tagline review
Accept the wording for this pilot without change, but note it as an input to any future company-wide review of tagline/hook language across all service short descriptions (not just Painting), since this is the first time this specific pattern has appeared in the pilot series.

---

## 3. Paint Drying Duration FAQ — Handling Rules

This item does not require an Owner decision between options — it is a factual distinction already established in `PAINTING_CONTENT_SOURCE_REVIEW_PLAN.md` §4, restated here as the binding handling rule for migration and for future review documents:

- The FAQ "How long does paint take to dry before the room can be used?" concerns a **physical/product characteristic** (paint drying time, dependent on paint type, coats, and ventilation), **not a service response-time or arrival-time commitment**.
- It is categorically distinct from the "same day" / urgency-adjacent FAQs already reviewed for Plumbing and Electrical Maintenance, and must not be flagged, counted, or reported as a "response-time promise" in any future validation or review document for this service.
- The answer already correctly hedges ("Drying time depends on... Your technician will advise the expected drying time for your specific job before finishing") and requires no change — it migrates as-is under this rule.
- Future independent review of this service's FAQ section should note this distinction explicitly, the same way this plan does, so the item is not mistakenly re-flagged as a claim-safety issue during later review passes.

---

## 4. CTA Pattern Confirmation

**Established, Owner-approved pattern (used identically for AC Maintenance, Plumbing, and Electrical Maintenance):**

- **English:** Book Appointment
- **Arabic:** احجز موعد

**Discrepancy flagged, not silently resolved:** this instruction's Arabic text read **"دعوم زجحا"** — this is not a valid Arabic phrase and appears to be the established phrase **"احجز موعد"** with its character order fully reversed (a common copy/paste or text-direction rendering artifact, not a new phrase). Applying "دعوم زجحا" literally would introduce meaningless Arabic text into the knowledge base, breaking both linguistic correctness and consistency with the three already-approved services.

**This plan does not silently substitute one for the other.** Recorded for explicit Owner confirmation before the Sync Execution Plan is written:

- **Recommended:** confirm the CTA remains **"احجز موعد"** (the already-established, correctly-formed phrase), treating "دعوم زجحا" as a rendering/input artifact rather than a new instruction.
- **Alternative:** if a different Arabic CTA phrase was genuinely intended, the Owner should supply it explicitly and correctly, and this plan's confirmation would be superseded before migration proceeds.

No CTA is applied by this document — this is a planning-stage confirmation request, not an execution step.

---

## Summary of What Needs Owner Input Before Sync Execution

| # | Item | Type | Status |
|---|---|---|---|
| 1 | Villa Painting keyword | Decision (3 options) | Open |
| 2 | Hero tagline "flawless finish" | Decision (3 options) | Open |
| 3 | Paint drying duration FAQ | Handling rule (no decision needed) | Resolved by this plan |
| 4 | CTA Arabic text | Confirmation (likely input artifact) | Open |

---

## What This Document Does Not Do

- Does not select an option for §1 or §2.
- Does not migrate, copy, or write any content into `04_SERVICE_KNOWLEDGE/08_PAINTING/`.
- Does not modify `README.md` or any publication status.
- Does not modify any website file in either repository.
- Does not commit or push anything.

---

## Related Documents

- `00_GOVERNANCE/PAINTING_CONTENT_SOURCE_REVIEW_PLAN.md` — the findings this plan resolves
- `00_GOVERNANCE/ELECTRICAL_SEO_DECISION_APPLIED.md`, `ELECTRICAL_ARABIC_SEO_DECISION_APPLIED.md` — decision-recording precedent
- `00_GOVERNANCE/HOMEPAGE_CONTENT_APPROVAL_DECISION.md` — options-without-selection format precedent
- `07_WEBSITE/NAVIGATION_ARCHITECTURE.md`, `00_GOVERNANCE/HOMEPAGE_CONTENT_DECISION_APPLIED.md` — established CTA pattern source
- `04_SERVICE_KNOWLEDGE/08_PAINTING/`
