# Service DNA Draft — Pilot — Pest Control

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — Pilot, Owner-Reviewed
- **Version:** 0.2
- **Prepared:** 2026-07-24
- **Reviewed:** 2026-07-24
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.1.a
- **Service:** `SVC-PEST-CONTROL`

## What This Is

A single-service pilot draft of ESMM Layer 2 (Service DNA) for Pest Control
only, prepared under Phase C.1.a preparatory-drafting authorization. It is
**not** `SERVICE_DNA_REGISTRY.md` and creates no registry. It is reshaped
entirely from existing repository content (`04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/BUSINESS.md`,
`SAFETY.md`, `README.md`) — no business fact is invented. Per ESMM Layer 2,
DNA is qualitative and evidence-independent: no number, guarantee, or price
appears below, consistent with the source documents' own evidence gates.

This draft has been reviewed by the Business Owner (see Owner Review
Resolution below) and by `AGT-QA` (Pass, one minor defect corrected), but it
is still not approved DNA content. It must not be cited by any other
document or used to inform publishing, AI answers, or customer-facing
material.

---

## 1. Core Purpose

To inspect, identify, treat, eliminate, and prevent pest infestations across
residential, commercial, industrial, and governmental facilities.

*Source: `BUSINESS.md` § Description.*

## 2. Core Promise

Protection of customer health and property from pest infestation, delivered
through treatment intended to be safe and to prevent recurrence.

*Source: `BUSINESS.md` § Business Objectives ("Protect customer health,"
"Protect property," "Prevent pest recurrence," "Deliver safe and effective
treatments").*

**Requires Owner input:** `BUSINESS.md` § Customer Benefits also lists "Fast
response" and "Municipality-compliant service." Both are excluded from this
Core Promise draft because `README.md`'s Evidence Gate and `BUSINESS.md`'s
own Evidence Required section state these may not be published or asserted
without owner-approved response-time policy and municipality-compliance
evidence. Restating them here as "promise" would contradict that existing
gate.

## 3. Core Risks

Risk of harm to customer health, property, or the environment if treatment
is performed without correct chemical handling, protective equipment, or
containment of treated areas.

*Source: `SAFETY.md` § PPE, Before/During/After Service, Emergency
Procedures — reshaped as risk statements, not as approved control
instructions.*

**Requires Owner input:** `SAFETY.md` itself states it is "a legacy draft
control list, not an approved risk assessment" and requires "a competent
safety review" before its hazards, exposure routes, and controls can be
treated as confirmed. This Core Risks entry is therefore provisional pending
that review.

## 4. Core Constraints

- Cannot state or imply a specific response time.
- Cannot claim a specific certification, license, or technician
  qualification.
- Cannot claim municipality compliance or use of specific approved products
  without supporting evidence.
- Cannot state a price, discount, or warranty term.
- Cannot state a specific chemical, product, or method without a competent
  safety and operational review.

*Source: `BUSINESS.md` § Evidence Required Before Approval;
`README.md` § Evidence Gate; `SAFETY.md` § Status.*

## 5. Customer Emotion

Relief from the anxiety and discomfort of an active pest problem (e.g.,
cockroaches, rodents, bed bugs, termites), and reassurance that the
treatment is being handled safely and will not recur.

*Source: inferred from `BUSINESS.md` § Customer Problems (the conditions
customers are experiencing) and § Customer Benefits ("Safe treatments,"
"Long-term protection"). This field is interpretive rather than a direct
restatement.*

**Requires Owner input:** No source document states a customer emotion
directly. This entry should be confirmed or corrected by the Business Owner
before it is treated as settled DNA content.

## 6. Business Outcome

Maintain a safer and more comfortable environment and reduce
pest-related problems.

*Source: Owner decision, 2026-07-25. Supersedes the prior
`BUSINESS.md`-derived entry ("Repeat business and recurring service
contracts...") with a direct Owner statement — see Owner Review
Resolution below for both versions.*

## 7. Brand Position

A trusted pest control service helping customers protect their spaces.

*Source: Owner decision, 2026-07-25. Supersedes the prior
`BUSINESS.md`-derived entry ("A quality-assured provider distinguished
by scheduled maintenance programs...") with a direct Owner statement —
see Owner Review Resolution below. The prior entry's excluded items
("Certified technicians," "Approved materials," pending evidence) are
not restated here and remain unapproved.*

---

## Owner Review Resolution (2026-07-24)

1. **Core Promise exclusion** — Owner-confirmed: "fast response" and
   "municipality-compliant service" remain excluded until response-time and
   municipality-compliance evidence is approved. No change to field 2.
2. **Core Risks** — Owner-confirmed: accepted as provisional draft content
   pending a competent Safety validation of `SAFETY.md`. No change to
   field 3. The underlying safety review remains a separate, open
   prerequisite.
3. **Customer Emotion** — Owner-confirmed: remains interpretive content, not
   a factual claim. No change to field 5.
4. **Brand Position exclusion** — Owner-confirmed: "Certified technicians"
   and "Approved materials" remain excluded until supporting evidence is
   approved. No change to field 7.

This resolution confirms the pilot draft's existing treatment of all four
flagged items. It does not approve any underlying fact (response time,
municipality compliance, safety controls, certification, or product
approval) — those evidence gates remain separately open and unresolved.

## Owner Review Resolution — Round 2 (2026-07-25, Business Outcome & Brand Position)

1. **Business Outcome superseded:** prior entry ("Repeat business and
   recurring service contracts, built on customer satisfaction and
   long-term relationships") replaced with Owner-supplied "Maintain a
   safer and more comfortable environment and reduce pest-related
   problems."
2. **Brand Position superseded:** prior entry ("A quality-assured
   provider distinguished by scheduled maintenance programs and ongoing
   customer support...") replaced with Owner-supplied "A trusted pest
   control service helping customers protect their spaces." The
   previously-excluded items (certified technicians, approved materials)
   remain excluded and unapproved.
3. No claim of being the best, largest, or otherwise unsupported market
   position was added, per instruction.

## Validation Performed

- Every stated field traces to specific sections of `BUSINESS.md`,
  `SAFETY.md`, or `README.md` for `SVC-PEST-CONTROL` — no fact outside those
  three files was used.
- No number, guarantee, price, warranty, or specific product/certification
  claim appears in any field, consistent with ESMM Layer 2's validation
  rule and with the source documents' own unresolved evidence gates.
- Every place where source material was interpreted (Customer Emotion) or
  deliberately excluded (Core Promise, Brand Position) is marked above
  rather than silently resolved.
- This file does not modify `ENTERPRISE_SERVICE_META_MODEL.md`,
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`, or any file under
  `04_SERVICE_KNOWLEDGE/`.

## Status

Draft — Pilot, Owner-Reviewed. Business Outcome and Brand Position were
updated 2026-07-25 with direct Owner statements superseding their prior
`BUSINESS.md`-derived content. This draft is still not approved, not
QA-reviewed against this update, and not canonical.
