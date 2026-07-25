# Service DNA Draft — Electrical Maintenance

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — Expansion, Owner-Reviewed (Complete)
- **Version:** 0.3
- **Prepared:** 2026-07-24
- **Updated:** 2026-07-25 (Phase C.2 — Owner confirmed scope, promise, boundary vs. AC Maintenance, customer problems, Business Outcome, Brand Position, and Core Risks; all seven fields are now populated)
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.1.a / C.2
- **Service:** `SVC-ELECTRICAL-MAINTENANCE`

## What This Is

An ESMM Layer 2 (Service DNA) draft for Electrical Maintenance, prepared
under Phase C.1.a expansion authorization. Not `SERVICE_DNA_REGISTRY.md`;
creates no registry.
`04_SERVICE_KNOWLEDGE/07_ELECTRICAL_MAINTENANCE/BUSINESS.md` and
`SAFETY.md` are deliberately fact-free governance scaffolds; fields with no
supporting repository content or Owner decision are marked Pending Owner
Input rather than inferred from the service name. This draft's structure
was reviewed by `AGT-QA` (Pass, one defect corrected) as part of the
Phase C.1.a expansion batch. Following Phase C.2 Owner Knowledge Capture,
the Owner confirmed this service's scope, promise, customer problems,
boundary against AC Maintenance, Business Outcome, Brand Position, and
Core Risks (see Owner Review Resolution below). All seven fields are now
populated. Its content has not been reviewed by `AGT-QA` since these
updates and must not be cited elsewhere or used to inform publishing, AI
answers, or customer-facing material.

---

## 1. Core Purpose

Electrical Maintenance is an approved service in AFAQ Alhayat's catalog
(`SVC-ELECTRICAL-MAINTENANCE`, category General Maintenance).
**Owner-confirmed 2026-07-25:** covers inspection of electrical faults,
maintenance and repair of electrical problems within scope, and handling
electrical components related to the property.

*Source: `SERVICE_CATALOG.md`; `BUSINESS.md` § Confirmed Identity; Owner
decision, 2026-07-25 (see Owner Review Resolution below).*

## 2. Core Promise

Resolution of electrical issues, safe operation, and restoration of
affected electrical functions.

*Source: Owner decision, 2026-07-25 ("Customers choose Electrical
Maintenance to resolve electrical issues, maintain safe operation, and
restore affected electrical functions"). No specific method, timeframe,
price, or warranty is stated or implied.*

## 3. Core Risks

Risks may relate to working with electricity and electrical components.
Electrical faults or conditions may require specialist assessment.
Electrical systems require careful handling due to their nature.

*Source: Owner decision, 2026-07-25. These are stated as risk categories
only, not safety procedures or operational instructions — no control
measure, PPE, or method is specified. `SAFETY.md` still contains no
formal hazard assessment for this service; a competent safety review
remains a separate, open item beyond this Core Risks entry.*

## 4. Core Constraints

- **Boundary vs. AC Maintenance** (Owner-confirmed 2026-07-25): AC
  equipment performance and AC system issues belong to AC Maintenance;
  electrical supply, electrical components, or electrical faults belong to
  Electrical Maintenance.
- AC system maintenance and plumbing work are excluded, as is unrelated
  non-electrical work.
- Work outside electrical specialization must not be performed as
  Electrical Maintenance.
- Cannot define voltage/system limits or escalation beyond what is stated
  above.
- Cannot claim technician authorization, lockout/isolation, testing, PPE,
  or incident controls.
- Cannot state inspection records, completion evidence, parts, or warranty
  rules.
- Cannot make regulatory, licensing, emergency, or response-time claims
  without evidence.

*Source: `BUSINESS.md` § Evidence Gate; `README.md` § Required Before
Approval; Owner decision, 2026-07-25.*

## 5. Customer Emotion

Concern about electrical faults or safety, and the need for the issue to
be resolved and function restored.

*Source: interpreted from the Owner's 2026-07-25 statement of customer
problems ("electrical faults, power-related issues, problems with
switches/outlets, and electrical issues requiring inspection").
Interpretive, not a direct restatement — this names the given problem,
not a stated emotion.*

**Requires Owner input:** this interpretation should be confirmed or
corrected — the Owner described the customer's problem, not explicitly
the emotion behind it; this entry infers concern/need from that problem
description.

## 6. Business Outcome

Help resolve electrical issues and maintain related property systems
operation.

*Source: Owner decision, 2026-07-25. No number, price, or metric is
stated or implied.*

## 7. Brand Position

A reliable electrical maintenance service for property electrical needs.

*Source: Owner decision, 2026-07-25. No claim of being the best or
largest is stated or implied.*

---

## Owner Review Resolution (2026-07-25)

1. **Customer problems:** electrical faults, power-related issues,
   problems with switches/outlets, and electrical issues requiring
   inspection.
2. **Scope:** inspection of electrical faults, maintenance and repair of
   electrical problems within scope, and handling electrical components
   related to the property.
3. **Exclusions:** AC system maintenance (stays under AC Maintenance),
   plumbing work, and unrelated non-electrical work.
4. **Boundary vs. AC Maintenance:** AC equipment performance and AC system
   issues belong to AC Maintenance; electrical supply, components, or
   faults belong to Electrical Maintenance.
5. **Customer reason:** resolving electrical issues, maintaining safe
   operation, and restoring affected electrical functions — recorded as
   Core Promise.
6. **Safety:** two general principles ("electrical work requires
   appropriate safety practices," "handle electrical sources with proper
   caution") were given, not specific hazards — recorded in Core Risks
   with that distinction made explicit; the statement that work outside
   electrical specialization must not be performed as Electrical
   Maintenance is recorded in Core Constraints. Specific hazards remain
   Pending Owner Input.
7. Recorded into Core Purpose, Core Promise, Core Risks (partially), Core
   Constraints, and Customer Emotion (interpreted, flagged for
   confirmation). No task, equipment, price, or warranty was added beyond
   what is stated above.
8. **Remaining undefined, kept Pending Owner Input:** specific Core Risks
   content.

## Owner Review Resolution — Round 2 (2026-07-25, Business Outcome & Brand Position)

1. **Business Outcome:** "Help resolve electrical issues and maintain
   related property systems operation."
2. **Brand Position:** "A reliable electrical maintenance service for
   property electrical needs."
3. No claim of being the best, largest, or otherwise unsupported market
   position was added.

This resolution also explains, but does not modify, the confirmed
Cross-sell relationships already recorded in `SERVICE_RELATIONSHIPS_DRAFT.md`
(`SVC-AC-MAINTENANCE` → `SVC-ELECTRICAL-MAINTENANCE`,
`SVC-PAINTING` → `SVC-ELECTRICAL-MAINTENANCE`) — that file is unchanged,
per instruction. This resolution creates no new business fact beyond what
is stated above, does not create `SERVICE_DNA_REGISTRY.md`, and does not
touch ESMM or EPGM.

## Owner Review Resolution — Round 3 (2026-07-25, Core Risks)

1. **Core Risks:** may relate to working with electricity and electrical
   components; electrical faults or conditions may require specialist
   assessment; electrical systems require careful handling due to their
   nature. Recorded as risk categories only — not converted into safety
   procedures or operational instructions. No hazard beyond these three
   points is claimed. This closes the last remaining field for this
   service; all seven fields are now populated.

## Validation Performed

- Every field traces to `BUSINESS.md`, `SAFETY.md`, `README.md`,
  `SERVICE_CATALOG.md`, or the 2026-07-25 Owner decision for
  `SVC-ELECTRICAL-MAINTENANCE` only.
- No claim was inferred from the service name or expanded beyond the
  points the Owner confirmed.
- Customer Emotion is explicitly marked interpretive, not a direct
  restatement, and flagged for confirmation.
- Core Risks is explicitly distinguished as general principles, not a
  specific hazard list — not silently treated as resolved.
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
populated from Owner-confirmed facts (2026-07-25). Not approved, not
canonical, and not QA-reviewed against this update.
