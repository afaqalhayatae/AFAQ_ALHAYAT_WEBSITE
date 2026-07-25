# Service DNA Draft — Water Leak Detection

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — Expansion, Owner-Reviewed (Complete)
- **Version:** 0.3
- **Prepared:** 2026-07-24
- **Updated:** 2026-07-25 (Phase C.2 — Owner confirmed purpose, scope, exclusion, detection/repair boundary, Customer Emotion, Business Outcome, Brand Position, and Core Risks; all seven fields are now populated)
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.1.a / C.2
- **Service:** `SVC-WATER-LEAK-DETECTION`

## What This Is

An ESMM Layer 2 (Service DNA) draft for Water Leak Detection, prepared
under Phase C.1.a expansion authorization. Not `SERVICE_DNA_REGISTRY.md`;
creates no registry. Reshaped entirely from
`04_SERVICE_KNOWLEDGE/12_WATER_LEAK_DETECTION/BUSINESS.md`, `SAFETY.md`,
`README.md`, and `DECISION_LOG.md` decision 19 — no fact invented.
`BUSINESS.md` and `SAFETY.md` are deliberately fact-free governance
scaffolds, so most fields below are marked Pending Owner Input rather than
inferred from the service name. This draft's structure was reviewed by
`AGT-QA` (Pass, one defect corrected) as part of the Phase C.1.a expansion
batch, and re-checked in Phase C.2. Following Phase C.2 Owner Knowledge
Capture, the Owner confirmed this service's purpose, scope, its exclusion
of repair work, its boundary against Plumbing and Waterproofing, Customer
Emotion, Business Outcome, Brand Position, and Core Risks (see Owner
Review Resolution below). All seven fields are now populated. Its content
has not been reviewed by `AGT-QA` since these updates and must not be
cited elsewhere or used to inform publishing, AI answers, or customer-facing
material.

---

## 1. Core Purpose

AFAQ Alhayat's water leak detection service, confirmed by the Owner as
offered across the approved UAE coverage (Decision 19). **Owner-confirmed
2026-07-25:** the service identifies and locates suspected water leaks —
detection and identification of the possible leak source or location.
Repair work is a separate, excluded scope unless separately defined. The
specific diagnostic methods used remain undefined.

*Source: `README.md` § Purpose; `DECISION_LOG.md` decision 19; Owner
decision, 2026-07-25 (see Owner Review Resolution below).*

## 2. Core Promise

Identification and location of a suspected water leak's source.

*Source: Owner decision, 2026-07-25 ("Service purpose: identify and
locate suspected water leaks"). This is the same statement used for Core
Purpose — the Owner's answer served both what the service exists to do
and what it delivers to the customer; no separate promise language was
given beyond it. No specific method, accuracy claim, timeframe, or price
is stated or implied.*

## 3. Core Risks

Risks may relate to hidden or suspected leaks affecting the property.
Accurate assessment may be required to identify the source of the issue.
Some leak locations may involve concealed areas or access challenges.

*Source: Owner decision, 2026-07-25. These are stated as risk categories
only, not safety procedures or operational instructions — no control
measure, PPE, or method is specified. `SAFETY.md` still contains no
formal hazard assessment for this service; a competent safety review
remains a separate, open item beyond this Core Risks entry.*

## 4. Core Constraints

- **Repair work is excluded from this service's scope unless separately
  defined** (Owner-confirmed 2026-07-25). Suspected plumbing-cause leaks
  route to Plumbing for repair; suspected waterproofing-cause leaks route
  to Waterproofing for repair. This service's role ends at identification.
- Cannot claim thermal imaging, acoustic detection, tracer gas, pressure
  testing, moisture meters, or non-invasive diagnosis until confirmed.
- Cannot promise exact detection, no-damage inspection, fixed price,
  response time, repair inclusion, or warranty until approved.
- Cannot publish licensing, certification, or regulatory claims without
  evidence.

*Source: `README.md` § Publication Guardrails; Owner decision, 2026-07-25.*

## 5. Customer Emotion

Concern due to an unknown or suspected leak; need for clarity and
understanding of the problem source; reassurance after the leak location
is identified.

*Source: Owner decision, 2026-07-25. Expressed as customer perspective,
not a guaranteed outcome. No emotion beyond these three points is
claimed.*

## 6. Business Outcome

Help customers identify the source of suspected leaks before deciding on
the appropriate repair direction.

*Source: Owner decision, 2026-07-25. No number, price, or metric is
stated or implied.*

## 7. Brand Position

A specialized service for detecting and locating leak-related problems.

*Source: Owner decision, 2026-07-25. No claim of being the best or
largest is stated or implied.*

---

## Owner Review Resolution (2026-07-25)

1. **Service purpose:** identify and locate suspected water leaks.
2. **Scope:** detection and identification of the possible leak source or
   location.
3. **Exclusion:** repair work is separate and not included unless
   separately defined.
4. **Detection vs. repair boundary:** Water Leak Detection identifies the
   issue; Plumbing handles plumbing-cause repairs; Waterproofing handles
   waterproofing-cause repairs.
5. Recorded into Core Purpose, Core Promise, and Core Constraints only.
   Scope was not expanded beyond these four confirmed points — no
   diagnostic method, timeframe, price, or warranty was added or implied.
6. **Remaining undefined, kept Pending Owner Input:** Core Risks.

## Owner Review Resolution — Round 3 (2026-07-25, Customer Emotion)

1. **Customer Emotion:** concern due to an unknown or suspected leak;
   need for clarity and understanding of the problem source; reassurance
   after the leak location is identified. Expressed as customer
   perspective, not a guaranteed outcome. Core Risks is now the sole
   remaining Pending Owner Input item.

## Owner Review Resolution — Round 2 (2026-07-25, Business Outcome & Brand Position)

1. **Business Outcome:** "Help customers identify the source of
   suspected leaks before deciding on the appropriate repair direction."
2. **Brand Position:** "A specialized service for detecting and locating
   leak-related problems."
3. No claim of being the best, largest, or otherwise unsupported market
   position was added.

This resolution also explains, but does not modify, the two confirmed
Dependency relationships already recorded in
`SERVICE_RELATIONSHIPS_DRAFT.md` (Water Leak Detection → Plumbing, Water
Leak Detection → Waterproofing) — that file is unchanged by this update,
per instruction. This resolution creates no new business fact beyond what
is stated above, does not create `SERVICE_DNA_REGISTRY.md`, and does not
touch ESMM or EPGM.

## Owner Review Resolution — Round 4 (2026-07-25, Core Risks)

1. **Core Risks:** may relate to hidden or suspected leaks affecting the
   property; accurate assessment may be required to identify the source
   of the issue; some leak locations may involve concealed areas or
   access challenges. Recorded as risk categories only — not converted
   into safety procedures or operational instructions. No hazard beyond
   these three points is claimed. This closes the last remaining field
   for this service; all seven fields are now populated.

## Validation Performed

- Every field traces to `BUSINESS.md`, `SAFETY.md`, `README.md`,
  `DECISION_LOG.md` decision 19, or the 2026-07-25 Owner decision, for
  `SVC-WATER-LEAK-DETECTION` only.
- No claim was inferred from the service name or expanded beyond the four
  points the Owner confirmed.
- All seven fields are populated from Owner-confirmed facts; none remain
  Pending Owner Input.
- No number, guarantee, price, or warranty claim appears in any field.
- `SERVICE_RELATIONSHIPS_DRAFT.md` was not modified.
- This file does not modify `ENTERPRISE_SERVICE_META_MODEL.md`,
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`, or any file under
  `04_SERVICE_KNOWLEDGE/`.
- No `SERVICE_DNA_REGISTRY.md` was created.

## Status

Draft — Expansion, Owner-Reviewed (Complete). All seven fields are now
populated from Owner-confirmed facts (2026-07-25) — none invented. Not
approved, not canonical, and not QA-reviewed against this update.
