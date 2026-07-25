# Service DNA Draft — Painting

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — Expansion, Owner-Reviewed (Partial)
- **Version:** 0.3
- **Prepared:** 2026-07-24
- **Updated:** 2026-07-25 (Phase C.2 — Owner confirmed scope, promise, boundary vs. Handyman, and customer problems; Business Outcome, Brand Position, and specific Core Risks remain Pending)
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.1.a / C.2
- **Service:** `SVC-PAINTING`

## What This Is

An ESMM Layer 2 (Service DNA) draft for Painting, prepared under Phase
C.1.a expansion authorization. Not `SERVICE_DNA_REGISTRY.md`; creates no
registry. `04_SERVICE_KNOWLEDGE/08_PAINTING/BUSINESS.md` and `SAFETY.md`
are deliberately fact-free governance scaffolds; fields with no
supporting repository content or Owner decision are marked Pending Owner
Input rather than inferred from the service name. This draft's structure
was reviewed by `AGT-QA` (Pass, one defect corrected) as part of the
Phase C.1.a expansion batch. Following Phase C.2 Owner Knowledge Capture,
the Owner confirmed this service's scope, promise, customer problems,
boundary against Handyman, and general safety guidance (see Owner Review
Resolution below); specific Core Risks content, Business Outcome, and
Brand Position remain Pending Owner Input. Its content has not been
reviewed by `AGT-QA` since this update and must not be cited elsewhere or
used to inform publishing, AI answers, or customer-facing material.

---

## 1. Core Purpose

Painting is an approved service in AFAQ Alhayat's catalog (`SVC-PAINTING`,
category General Maintenance). **Owner-confirmed 2026-07-25:** covers
interior and exterior painting within scope, including surface
preparation when required, paint application, and related finishing
work.

*Source: `SERVICE_CATALOG.md`; `BUSINESS.md` § Confirmed Identity; Owner
decision, 2026-07-25 (see Owner Review Resolution below).*

## 2. Core Promise

Improved appearance, renewed finishes, and improved surface condition.

*Source: Owner decision, 2026-07-25 ("Customers choose Painting to
improve appearance, renew finishes, and improve surface condition"). No
specific product, color, durability, timeframe, or price is stated or
implied.*

## 3. Core Risks

**Partially addressed, not a specific hazard list.** Owner-confirmed
2026-07-25: "Prepare work areas safely," "Consider ladder and
height-related safety where applicable," and "Use suitable materials and
tools." Ladder/height work is named as a relevant category, but no
specific control, fall-protection measure, or material hazard is
identified — `SAFETY.md` still contains no hazard list for this service.
Specific Core Risks content remains Pending Owner Input pending a
competent safety review.

## 4. Core Constraints

- **Boundary vs. Handyman** (Owner-confirmed 2026-07-25): Painting applies
  when the customer needs painting or surface finishing work. The
  Handyman boundary remains separately defined elsewhere; Painting must
  not expand into general handyman tasks.
- Plumbing, electrical work, AC Maintenance, and general unrelated work
  are excluded; Waterproofing is excluded unless separately defined.
- Cannot define finish acceptance criteria beyond what is stated above.
- Cannot state product-selection responsibility, ventilation, PPE,
  protection, or waste controls.
- Cannot state color confirmation, change handling, completion evidence, or
  rework policy.
- Cannot claim durability, warranty, safety, or timing without evidence.

*Source: `BUSINESS.md` § Evidence Gate; `README.md` § Required Before
Approval; Owner decision, 2026-07-25.*

## 5. Customer Emotion

Desire for a renewed, improved appearance, and satisfaction with a
refreshed space.

*Source: interpreted from the Owner's 2026-07-25 statement of customer
problems ("renewing appearance, addressing faded or damaged paint,
changing colors, improving walls/surfaces appearance, and finishing after
repairs or preparation"). Interpretive, not a direct restatement — this
names the given problem, not a stated emotion.*

**Requires Owner input:** this interpretation should be confirmed or
corrected — the Owner described the customer's problem, not explicitly
the emotion behind it; this entry infers desire/satisfaction from that
problem description.

## 6. Business Outcome

Improve property appearance and renew finishes.

*Source: Owner decision, 2026-07-25. No number, price, or metric is
stated or implied.*

## 7. Brand Position

A painting service helping refresh and improve spaces.

*Source: Owner decision, 2026-07-25. No claim of being the best or
largest is stated or implied.*

---

## Owner Review Resolution (2026-07-25)

1. **Customer problems:** renewing appearance, addressing faded or
   damaged paint, changing colors, improving walls/surfaces appearance,
   and finishing after repairs or preparation.
2. **Scope:** interior and exterior painting within scope, including
   surface preparation when required, paint application, and related
   finishing work.
3. **Exclusions:** Plumbing, electrical work, AC Maintenance, and general
   unrelated work; Waterproofing excluded unless separately defined.
4. **Boundary vs. Handyman:** Painting applies to painting or surface
   finishing work; the Handyman boundary is separately defined elsewhere,
   and Painting must not expand into general handyman tasks.
5. **Customer reason:** improved appearance, renewed finishes, and
   improved surface condition — recorded as Core Promise.
6. **Safety:** three general points ("prepare work areas safely,"
   "consider ladder and height-related safety where applicable," "use
   suitable materials and tools") were given, with ladder/height work
   named as a relevant category but no specific control or hazard
   detailed — recorded in Core Risks with that distinction made explicit.
   Specific hazards remain Pending Owner Input.
7. Recorded into Core Purpose, Core Promise, Core Risks (partially), Core
   Constraints, and Customer Emotion (interpreted, flagged for
   confirmation). No product, color, duration, price, or warranty was
   added beyond what is stated above.
8. **Remaining undefined, kept Pending Owner Input:** specific Core Risks
   content.

## Owner Review Resolution — Round 2 (2026-07-25, Business Outcome & Brand Position)

1. **Business Outcome:** "Improve property appearance and renew
   finishes."
2. **Brand Position:** "A painting service helping refresh and improve
   spaces."
3. No claim of being the best, largest, or otherwise unsupported market
   position was added.

This resolution also explains, but does not modify, the confirmed
Cross-sell relationships already recorded in `SERVICE_RELATIONSHIPS_DRAFT.md`
(`SVC-PAINTING` → `SVC-HANDYMAN`, `SVC-PAINTING` → `SVC-ELECTRICAL-MAINTENANCE`)
— that file is unchanged, per instruction. This resolution creates no new
business fact beyond what is stated above, does not create
`SERVICE_DNA_REGISTRY.md`, and does not touch ESMM or EPGM.

## Validation Performed

- Every field traces to `BUSINESS.md`, `SAFETY.md`, `README.md`,
  `SERVICE_CATALOG.md`, or the 2026-07-25 Owner decision for
  `SVC-PAINTING` only.
- No claim was inferred from the service name or expanded beyond the
  points the Owner confirmed.
- Customer Emotion is explicitly marked interpretive, not a direct
  restatement, and flagged for confirmation.
- Core Risks is explicitly distinguished as general guidance, not a full
  hazard list — not silently treated as resolved.
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
Core Risks carries general safety guidance but no full hazard list — the
sole remaining Pending item. Not approved, not QA-reviewed
against this update, not canonical.
