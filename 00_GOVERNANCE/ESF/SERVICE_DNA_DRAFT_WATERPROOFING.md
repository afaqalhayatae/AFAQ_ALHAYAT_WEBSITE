# Service DNA Draft — Waterproofing

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — Expansion, Owner-Reviewed (Partial)
- **Version:** 0.3
- **Prepared:** 2026-07-24
- **Updated:** 2026-07-25 (Phase C.2 — Owner confirmed scope, promise, boundaries vs. Water Leak Detection and Plumbing, and customer problems; Business Outcome, Brand Position, and specific Core Risks remain Pending)
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.1.a / C.2
- **Service:** `SVC-WATERPROOFING`

## What This Is

An ESMM Layer 2 (Service DNA) draft for Waterproofing, prepared under Phase
C.1.a expansion authorization. Not `SERVICE_DNA_REGISTRY.md`; creates no
registry. Reshaped entirely from
`04_SERVICE_KNOWLEDGE/11_WATERPROOFING/BUSINESS.md`, `SAFETY.md`,
`README.md`, and `DECISION_LOG.md` decision 19 — no fact invented.
`BUSINESS.md` and `SAFETY.md` are deliberately fact-free governance
scaffolds, so fields below without an Owner decision are marked Pending
Owner Input rather than inferred from the service name. This draft's
structure was reviewed by `AGT-QA` (Pass, one defect corrected) as part
of the Phase C.1.a expansion batch. Following Phase C.2 Owner Knowledge
Capture, the Owner confirmed this service's scope, promise, customer
problems, boundaries against Water Leak Detection and Plumbing, and a
general safety principle (see Owner Review Resolution below); specific
Core Risks content, Business Outcome, and Brand Position remain Pending
Owner Input. Its content has not been reviewed by `AGT-QA` since this
update and must not be cited elsewhere or used to inform publishing, AI
answers, or customer-facing material.

---

## 1. Core Purpose

AFAQ Alhayat's waterproofing service, confirmed by the Owner as offered
across the approved UAE coverage (Decision 19). **Owner-confirmed
2026-07-25:** covers protection against water ingress and
waterproofing-related treatment; thermal insulation remains excluded
unless separately confirmed.

*Source: `README.md` § Purpose; `DECISION_LOG.md` decision 19; Owner
decision, 2026-07-25 (see Owner Review Resolution below).*

## 2. Core Promise

Protection of the property from water entry and related moisture
problems.

*Source: Owner decision, 2026-07-25 ("Customers choose Waterproofing to
protect the property from water entry and related moisture problems").
No method, material, lifespan, guarantee, or price is stated or implied.*

## 3. Core Risks

**Partially addressed, not a specific hazard list.** Owner-confirmed
2026-07-25: "Apply appropriate safety considerations based on work
location and conditions." This is a general principle, not an identified
hazard — `SAFETY.md` still contains no hazard list for this service, and
no specific risk (chemical, fall, structural, or otherwise) has been
named. Specific Core Risks content remains Pending Owner Input pending a
competent safety review.

## 4. Core Constraints

- **Boundary vs. Water Leak Detection** (Owner-confirmed 2026-07-25): Water
  Leak Detection identifies and locates the leak or problem source;
  Waterproofing addresses protection against water ingress and
  waterproofing-related causes once identified.
- **Boundary vs. Plumbing** (Owner-confirmed 2026-07-25): Plumbing applies
  when the cause is pipes, fixtures, or plumbing systems; Waterproofing
  applies when the issue is water ingress protection or
  waterproofing-related.
- Thermal insulation remains excluded unless separately confirmed.
- Cannot name membrane types, coatings, injection systems, brands, or
  application methods until approved.
- Cannot promise a lifespan, watertight guarantee, fixed warranty, or
  permanent repair without a verified system and site-specific terms.
- Cannot imply structural engineering, authority approval, or licensed work
  without evidence.

*Source: `README.md` § Publication Guardrails; Owner decision,
2026-07-25.*

## 5. Customer Emotion

Concern about water ingress or moisture affecting the property, and the
need for protection against water entry.

*Source: interpreted from the Owner's 2026-07-25 statement of customer
problems ("water ingress protection problems, moisture concerns, and
situations requiring protection against water entry"). Interpretive, not
a direct restatement — this names the given problem, not a stated
emotion.*

**Requires Owner input:** this interpretation should be confirmed or
corrected — the Owner described the customer's problem, not explicitly
the emotion behind it; this entry infers concern/need from that problem
description.

## 6. Business Outcome

Help protect properties from water ingress and related moisture
problems.

*Source: Owner decision, 2026-07-25. No number, price, or metric is
stated or implied.*

## 7. Brand Position

A specialized solution for property water protection.

*Source: Owner decision, 2026-07-25. No claim of being the best or
largest is stated or implied.*

---

## Owner Review Resolution (2026-07-25)

1. **Customer problems:** water ingress protection problems, moisture
   concerns, and situations requiring protection against water entry.
2. **Scope:** protection against water ingress and waterproofing-related
   treatment; thermal insulation remains excluded unless separately
   confirmed.
3. **Exclusions:** Water Leak Detection remains responsible for
   identifying and locating suspected leaks; Plumbing remains responsible
   for pipe-related faults, repairs, and plumbing system issues; thermal
   insulation is excluded.
4. **Boundary vs. Water Leak Detection:** Water Leak Detection identifies
   and locates the source; Waterproofing addresses ingress protection and
   waterproofing-related causes.
5. **Boundary vs. Plumbing:** Plumbing applies to pipes/fixtures/systems;
   Waterproofing applies to ingress protection or waterproofing-related
   issues.
6. **Customer reason:** protecting the property from water entry and
   related moisture problems — recorded as Core Promise.
7. **Safety:** a general principle ("apply appropriate safety
   considerations based on work location and conditions") was given, not
   a specific hazard — recorded in Core Risks with that distinction made
   explicit; specific hazards remain Pending Owner Input.
8. Recorded into Core Purpose, Core Promise, Core Risks (partially),
   Core Constraints, and Customer Emotion (interpreted, flagged for
   confirmation). No task, material, method, price, or warranty was added
   beyond what is stated above.
9. **Remaining undefined, kept Pending Owner Input:** specific Core Risks
   content.

## Owner Review Resolution — Round 2 (2026-07-25, Business Outcome & Brand Position)

1. **Business Outcome:** "Help protect properties from water ingress and
   related moisture problems."
2. **Brand Position:** "A specialized solution for property water
   protection."
3. No claim of being the best, largest, or otherwise unsupported market
   position was added.

This resolution also explains, but does not modify, the confirmed
Dependency relationship already recorded in `SERVICE_RELATIONSHIPS_DRAFT.md`
(`SVC-WATER-LEAK-DETECTION` → `SVC-WATERPROOFING`) — that file is
unchanged, per instruction. This resolution creates no new business fact
beyond what is stated above, does not create `SERVICE_DNA_REGISTRY.md`,
and does not touch ESMM or EPGM.

## Validation Performed

- Every field traces to `BUSINESS.md`, `SAFETY.md`, `README.md`,
  `DECISION_LOG.md` decision 19, or the 2026-07-25 Owner decision for
  `SVC-WATERPROOFING` only.
- No claim was inferred from the service name or expanded beyond the
  points the Owner confirmed.
- Customer Emotion is explicitly marked interpretive, not a direct
  restatement, and flagged for confirmation.
- Core Risks is explicitly distinguished as a general principle, not a
  specific hazard list — not silently treated as resolved.
- Six of seven fields are populated from Owner-confirmed facts. Core
  Risks carries a general safety principle but no specific hazard list —
  the sole remaining partial item, not a blank Pending field.
- No number, guarantee, price, or warranty claim appears in any field.
- `SERVICE_RELATIONSHIPS_DRAFT.md` was not modified.
- This file does not modify `ENTERPRISE_SERVICE_META_MODEL.md`,
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`, or any file under
  `04_SERVICE_KNOWLEDGE/`.
- No `SERVICE_DNA_REGISTRY.md` was created.

## Status

Draft — Expansion, Owner-Reviewed (Partial). Core Purpose, Core Promise,
Core Constraints, Customer Emotion (interpreted), Business Outcome, and
Brand Position are now populated from Owner-confirmed facts (2026-07-25);
Core Risks carries a general safety principle but no specific hazard —
the sole remaining Pending item. Not approved, not QA-reviewed
against this update, not canonical.
