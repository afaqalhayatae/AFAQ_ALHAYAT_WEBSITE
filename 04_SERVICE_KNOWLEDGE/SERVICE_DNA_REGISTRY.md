# Service DNA Registry

## Document Information

- **Owner:** Business Owner
- **Status:** Draft
- **Version:** 0.1
- **Prepared:** 2026-07-25
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.2 Work Package 4

## What This Is

The canonical Enterprise Service Meta-Model (ESMM) Layer 2 (Service DNA)
registry, per `DECISION_LOG.md` decision 24 and
`ENTERPRISE_SERVICE_META_MODEL.md` §2. It holds the current, resolved value
of each of the twelve catalog services' seven DNA fields — Core Purpose,
Core Promise, Core Risks, Core Constraints, Customer Emotion, Business
Outcome, Brand Position — reshaped from the twelve Owner-confirmed,
`AGT-QA`-reviewed drafts in `00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_*.md`
under Program C Phase C.2 Work Package 4. No new business fact is
introduced here; no field below states anything beyond what those source
drafts already record. This file does not modify
`ENTERPRISE_SERVICE_META_MODEL.md`, `ENTERPRISE_PUBLICATION_GATE_MODEL.md`,
or `SERVICE_CATALOG.md`.

Each source draft's full drafting history — every resolution round,
retracted content, and the reasoning behind each Owner decision — remains
the historical audit trail and is not duplicated here. Each field below
carries a short provenance tag; consult the linked source draft for the
complete record.

**Status caveats carried forward, not resolved by this registry:**

- **Core Risks remains explicitly provisional** for Pest Control, General
  Cleaning, and Water Tank Cleaning, pending a competent safety review
  each source draft itself calls for. This registry does not perform or
  imply that review.
- **Deep Cleaning's Core Purpose, Core Promise, and Core Constraints
  remain deliberately qualitative** — a scope *direction* (task scope,
  distinct from General Cleaning), not a task list. No specific task,
  room, surface, or fixture is named, consistent with the source draft's
  own boundary.
- Per ESMM Layer 2's own validation rule, every field here is qualitative
  and evidence-independent — no number, guarantee, price, or warranty
  term appears anywhere in this file.

This registry's own status is **Draft**, not Approved. Per
`ENTERPRISE_PUBLICATION_GATE_MODEL.md` §7 (Minimum-Status Computation),
object status is the worst status among its constituent layers after
each is capped by its own dependencies — the three provisional Core Risks
entries alone cap this registry below Approved regardless of the other
nine services' completeness.

---

## Index

| ID | Name | Category | DNA status |
|---|---|---|---|
| `SVC-PEST-CONTROL` | Pest Control | Cleaning & Pest Control | Draft — Core Risks provisional |
| `SVC-AC-MAINTENANCE` | AC Maintenance | General Maintenance | Draft — complete |
| `SVC-GENERAL-CLEANING` | General Cleaning | Cleaning & Pest Control | Draft — Core Risks provisional |
| `SVC-DEEP-CLEANING` | Deep Cleaning | Cleaning & Pest Control | Draft — qualitative scope only |
| `SVC-WATER-TANK-CLEANING` | Water Tank Cleaning | Cleaning & Pest Control | Draft — Core Risks provisional |
| `SVC-PLUMBING` | Plumbing | General Maintenance | Draft — complete |
| `SVC-ELECTRICAL-MAINTENANCE` | Electrical Maintenance | General Maintenance | Draft — complete |
| `SVC-PAINTING` | Painting | General Maintenance | Draft — complete |
| `SVC-HANDYMAN` | Handyman Services | General Maintenance | Draft — complete |
| `SVC-DRAIN-UNBLOCKING` | Drain Unblocking | Drainage & Water Protection | Draft — complete |
| `SVC-WATERPROOFING` | Waterproofing | Drainage & Water Protection | Draft — complete |
| `SVC-WATER-LEAK-DETECTION` | Water Leak Detection | Drainage & Water Protection | Draft — complete |

IDs above match `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` exactly — no ID
is invented, renamed, or omitted.

---

## 1. Pest Control (`SVC-PEST-CONTROL`)

**Category:** Cleaning & Pest Control. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_PILOT_PEST_CONTROL.md`.

### Core Purpose

To inspect, identify, treat, eliminate, and prevent pest infestations
across residential, commercial, industrial, and governmental facilities.

*Source: `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/BUSINESS.md` § Description.*

### Core Promise

Protection of customer health and property from pest infestation,
delivered through treatment intended to be safe and to prevent
recurrence. "Fast response" and "municipality-compliant service" remain
excluded pending owner-approved response-time and municipality-compliance
evidence.

*Source: `BUSINESS.md` § Business Objectives; Owner-confirmed 2026-07-24.*

### Core Risks

**Provisional — pending a competent safety review.** Risks may relate to
chemical handling, storage, and exposure during treatment. Risks may
relate to incorrect or missing personal protective equipment. Risks may
relate to contamination of food, sensitive items, or occupied areas if
containment is inadequate. Risks may relate to exposure of children,
pets, or bystanders during or after treatment. Risks may relate to
improper waste or chemical disposal after service.

*Source: `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/SAFETY.md` § PPE, Before/During/After
Service, Emergency Procedures, § Safety Rules; Owner-confirmed wording
refinement, 2026-07-26 — remains provisional pending `SAFETY.md`'s own
required competent safety review.*

### Core Constraints

- Cannot state or imply a specific response time.
- Cannot claim a specific certification, license, or technician
  qualification.
- Cannot claim municipality compliance or use of specific approved
  products without supporting evidence.
- Cannot state a price, discount, or warranty term.
- Cannot state a specific chemical, product, or method without a
  competent safety and operational review.

*Source: `BUSINESS.md` § Evidence Required Before Approval; `README.md` §
Evidence Gate; `SAFETY.md` § Status.*

### Customer Emotion

Relief from the anxiety and discomfort of an active pest problem, and
reassurance that the treatment is being handled safely and will not
recur.

*Source: interpreted from `BUSINESS.md` § Customer Problems and § Customer
Benefits; Owner-confirmed 2026-07-24 as accepted judgment — remains
labeled interpretation, not sourced fact.*

### Business Outcome

Maintain a safer and more comfortable environment and reduce
pest-related problems.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A trusted pest control service helping customers protect their spaces.

*Source: Owner decision, 2026-07-25. "Certified technicians" and
"approved materials" remain excluded pending supporting evidence.*

---

## 2. AC Maintenance (`SVC-AC-MAINTENANCE`)

**Category:** General Maintenance. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_AC_MAINTENANCE.md`.

### Core Purpose

Covers inspection, routine maintenance, cleaning of relevant components,
addressing basic operating issues, and improving system performance.

*Source: `SERVICE_CATALOG.md`; Owner decision, 2026-07-25.*

### Core Promise

Improved cooling performance, equipment maintenance, reduced failures,
and improved comfort.

*Source: Owner decision, 2026-07-25.*

### Core Risks

Risks may relate to handling AC components and related electrical parts.
Work may involve access to elevated locations or AC units requiring
attention. Some faults may require technical assessment before action.

*Source: Owner decision, 2026-07-25 — risk categories only, no control
measure, PPE, or method specified.*

### Core Constraints

- **Boundary vs. Electrical Maintenance:** AC system operation and
  AC-related issues belong to AC Maintenance; general electrical faults
  or power supply issues outside the AC system route to Electrical
  Maintenance.
- General electrical work outside the AC system is excluded, including
  general electrical supply/installation work.
- Work outside AC specialization must not be performed as AC Maintenance.
- Cannot claim technician qualifications, diagnostic process, safety
  controls, or escalation rules beyond what is stated above.
- Cannot state service deliverables, parts policy, warranty terms, or
  emergency availability.
- Cannot make geographic, response-time, or marketing claims without
  substantiation.

*Source: `BUSINESS.md` § Evidence Gate; Owner decision, 2026-07-25.*

### Customer Emotion

Concern about cooling performance or equipment reliability, and the need
for a well-maintained, comfortable environment.

*Source: interpreted from Owner-stated customer problems, 2026-07-25;
Owner-confirmed 2026-07-25 as accepted judgment — remains labeled
interpretation, not sourced fact.*

### Business Outcome

Help maintain AC performance and reduce operational issues.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A reliable AC maintenance service supporting indoor comfort.

*Source: Owner decision, 2026-07-25.*

---

## 3. General Cleaning (`SVC-GENERAL-CLEANING`)

**Category:** Cleaning & Pest Control. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_GENERAL_CLEANING.md`.

### Core Purpose

Routine cleaning of agreed, accessible areas in residential or commercial
premises, with the final task list confirmed before work begins and
recorded in the service order.

*Source: `04_SERVICE_KNOWLEDGE/03_GENERAL_CLEANING/BUSINESS.md` § Service
Definition.*

### Core Promise

Reliable, scheduled, documented cleaning delivered through clear scope,
reliable coordination, professional conduct, safe task execution, and
visible quality checks.

*Source: `BUSINESS.md` § Value Proposition.*

### Core Risks

**Provisional — pending a competent safety review.** Risk of slips,
trips, and wet-floor incidents; chemical exposure from incompatible
products; manual-handling strain; electrical-equipment hazards in wet
environments; contact with sharps, broken glass, or biological material;
unsafe work at height or access; risk arising from customer, child, pet,
or public interaction during service; and damage to sensitive surfaces.

*Source: `SAFETY.md` § Primary Hazards; Owner-confirmed wording
refinement, 2026-07-26 — remains provisional pending a competent safety
review.*

### Core Constraints

- Cannot include deep cleaning, post-construction work, specialist
  fabric cleaning, hazardous materials, work at height, pest control, or
  licensed maintenance unless separately approved.
- Cannot state a final inclusion/exclusion matrix, price, cancellation,
  warranty, or rework term without owner approval.
- Cannot claim specific approved materials, equipment, PPE, or chemical
  handling controls without approval.

*Source: `README.md` § Boundary, § Approval Blockers.*

### Customer Emotion

Confidence that routine cleaning is being handled reliably and safely,
and relief from limited time or internal cleaning capacity.

*Source: interpreted from `BUSINESS.md` § Customer Problems Addressed;
Owner-confirmed 2026-07-25 as accepted judgment — remains labeled
interpretation, not sourced fact.*

### Business Outcome

Maintain ongoing cleanliness and improve the customer's daily
environment experience.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A reliable cleaning service for keeping spaces clean and organized.

*Source: Owner decision, 2026-07-25. Overlaps in substance with Core
Promise — accepted as a source-material limitation, not an invented
differentiation; `BUSINESS.md` contains only one Value Proposition
paragraph, used for both fields.*

---

## 4. Deep Cleaning (`SVC-DEEP-CLEANING`)

**Category:** Cleaning & Pest Control. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_DEEP_CLEANING.md`.

**Qualitative scope direction only — not a task list.** No specific
task, room, surface, or fixture is named in any field below, consistent
with the source draft's own boundary (see that draft's Round 3
governance correction for why).

### Core Purpose

Deep Cleaning is a service distinct from General Cleaning, with Task
Scope as the differentiation basis. Covers detailed cleaning according
to the agreed service scope, focused on deeper cleaning needs beyond
routine cleaning, addressing accumulated dirt and areas requiring
additional effort. General Cleaning is the regular/routine service; Deep
Cleaning is the deeper, more detailed service for situations requiring
enhanced attention.

*Source: `SERVICE_CATALOG.md`; `04_SERVICE_KNOWLEDGE/04_DEEP_CLEANING/README.md`
§ Purpose; Owner decision, 2026-07-25.*

### Core Promise

A higher level of cleanliness and improvement of the property's
cleanliness condition, beyond what routine cleaning addresses.

*Source: Owner decision, 2026-07-25.*

### Core Risks

Risks may relate to handling accumulated dirt or areas requiring
appropriate assessment before cleaning work begins. Work requirements
may vary depending on the property's condition and the agreed cleaning
scope. Some situations may involve needs outside cleaning scope and
require routing to another appropriate service.

*Source: Owner decision, 2026-07-25 — risk categories only, not cleaning
procedures or technical methods.*

### Core Constraints

- Does not include maintenance or repair work; does not include
  painting, restoration, or specialized non-cleaning services; does not
  expand into Handyman or other specialist services.
- **Boundary vs. General Cleaning:** routine/regular cleaning stays
  General Cleaning; Deep Cleaning applies only to situations requiring
  enhanced attention beyond that routine scope.
- Cannot state a specific task, room, surface, fixture, item type,
  frequency, or occasion.
- Cannot state team, equipment, materials, PPE, or duration rules.
- Cannot state customer preparation or acceptance criteria.
- Cannot state pricing, warranty, rework, cancellation, or availability.

*Source: `README.md` § Owner Input Required, § Purpose; Owner decision,
2026-07-25.*

### Customer Emotion

Satisfaction from having accumulated dirt and neglected areas thoroughly
addressed, beyond what routine cleaning reaches.

*Source: interpreted from Owner-stated customer need, 2026-07-25;
Owner-confirmed 2026-07-25 as accepted judgment — remains labeled
interpretation, not sourced fact.*

### Business Outcome

Improve overall cleanliness and address cleaning needs requiring
additional attention.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A deeper cleaning solution for spaces requiring detailed care.

*Source: Owner decision, 2026-07-25.*

---

## 5. Water Tank Cleaning (`SVC-WATER-TANK-CLEANING`)

**Category:** Cleaning & Pest Control. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_WATER_TANK_CLEANING.md`.

### Core Purpose

Controlled cleaning of an approved water-storage tank through an
assessed scope, safe isolation, removal of accessible deposits, an
approved hygiene method, inspection, documentation, and release criteria.

*Source: `04_SERVICE_KNOWLEDGE/05_WATER_TANK_CLEANING/BUSINESS.md` §
Service Definition.*

### Core Promise

Documented inspection, controlled execution, traceability, and
responsible hygiene practice.

*Source: `BUSINESS.md` § Value.*

### Core Risks

**Provisional — pending a competent confined-space entry assessment.**
Risk of confined-space hazards (oxygen deficiency, engulfment,
restricted entry), falls from ladder, roof, or tank-opening access,
drowning or unexpected inflow, electrical and pump hazards, chemical
exposure, biological contamination, slips and manual handling, and
unintended use of the tank before release.

*Source: `SAFETY.md` § Critical Hazards; Owner-confirmed wording
refinement, 2026-07-26 — remains provisional pending a competent
confined-space entry assessment. `SAFETY.md` states no person may enter
a tank without one and an approved entry system.*

### Core Constraints

- Cannot approve tank entry, a product, a concentration, or a
  disinfection/regulatory claim.
- Cannot state supported tank types/sizes/access, the isolation,
  drainage, cleaning, disinfection, waste, or release method, product
  approvals, or water-quality testing responsibility without
  owner/technical approval.
- Cannot claim water is safe to drink or free of microorganisms.
- Coverage remains emirate-level only; no city, district, or community
  claim.

*Source: `SAFETY.md`; `README.md` § Approval Blockers; `BUSINESS.md` §
Value.*

### Customer Emotion

Reassurance that stored water is being inspected and maintained
responsibly, within stated limitations.

*Source: interpreted from `BUSINESS.md` § Service Definition and §
Value; Owner-confirmed 2026-07-25 as accepted judgment — remains labeled
interpretation, not sourced fact.*

### Business Outcome

Support clean water tank conditions and better water usage quality.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A specialized service focused on maintaining water source cleanliness.

*Source: Owner decision, 2026-07-25. Overlaps in substance with Core
Promise — accepted as a source-material limitation, not an invented
differentiation.*

---

## 6. Plumbing (`SVC-PLUMBING`)

**Category:** General Maintenance. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_PLUMBING.md`.

### Core Purpose

Covers water supply issues, pipe-related issues, plumbing fixtures,
repairs, replacements, and plumbing system problems.

*Source: `SERVICE_CATALOG.md`; Owner decision, 2026-07-25.*

### Core Promise

Resolution of water supply, pipe, fixture, and plumbing system problems
through repair or replacement.

*Source: Owner decision, 2026-07-25.*

### Core Risks

Risks may relate to water leaks and plumbing systems. Water-related
issues may cause property impact if not properly addressed. Conditions
may require assessment before repair work.

*Source: Owner decision, 2026-07-25 — risk categories only.*

### Core Constraints

- **Not a substitute for a simple blockage-only service.** Routes to
  Drain Unblocking when the issue is only blockage removal; Plumbing
  applies when pipe faults, plumbing repairs, fixtures, or broader
  plumbing system work is involved.
- Cannot define supported jobs, exclusions, emergency classification, or
  escalation beyond the scope stated in Core Purpose.
- Cannot claim technician competency, isolation, testing, safety, or
  documentation practices.
- Cannot state materials, customer-supplied-parts handling, damage
  handling, or warranty terms.
- Cannot make legal, licensing, response-time, or availability claims
  without evidence.

*Source: `BUSINESS.md` § Evidence Gate; Owner decision, 2026-07-25.*

### Customer Emotion

Concern about water-related problems and their impact on the property;
relief after the issue is resolved and normal use is restored;
confidence when the problem is handled by an appropriate specialist
service.

*Source: Owner decision, 2026-07-25 — expressed as customer perspective,
not a guaranteed outcome.*

### Business Outcome

Help customers resolve plumbing problems and maintain the operation of
water systems within the property.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A reliable plumbing service for handling water-related problems and
plumbing system needs.

*Source: Owner decision, 2026-07-25.*

---

## 7. Electrical Maintenance (`SVC-ELECTRICAL-MAINTENANCE`)

**Category:** General Maintenance. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_ELECTRICAL_MAINTENANCE.md`.

### Core Purpose

Covers inspection of electrical faults, maintenance and repair of
electrical problems within scope, and handling electrical components
related to the property.

*Source: `SERVICE_CATALOG.md`; Owner decision, 2026-07-25.*

### Core Promise

Resolution of electrical issues, safe operation, and restoration of
affected electrical functions.

*Source: Owner decision, 2026-07-25.*

### Core Risks

Risks may relate to working with electricity and electrical components.
Electrical faults or conditions may require specialist assessment.
Electrical systems require careful handling due to their nature.

*Source: Owner decision, 2026-07-25 — risk categories only.*

### Core Constraints

- **Boundary vs. AC Maintenance:** AC equipment performance and AC
  system issues belong to AC Maintenance; electrical supply, electrical
  components, or electrical faults belong to Electrical Maintenance.
- AC system maintenance and plumbing work are excluded, as is unrelated
  non-electrical work.
- Work outside electrical specialization must not be performed as
  Electrical Maintenance.
- Cannot define voltage/system limits or escalation beyond what is
  stated above.
- Cannot claim technician authorization, lockout/isolation, testing,
  PPE, or incident controls.
- Cannot state inspection records, completion evidence, parts, or
  warranty rules.
- Cannot make regulatory, licensing, emergency, or response-time claims
  without evidence.

*Source: `BUSINESS.md` § Evidence Gate; Owner decision, 2026-07-25.*

### Customer Emotion

Concern about electrical faults or safety, and the need for the issue to
be resolved and function restored.

*Source: interpreted from Owner-stated customer problems, 2026-07-25;
Owner-confirmed 2026-07-25 as accepted judgment — remains labeled
interpretation, not sourced fact.*

### Business Outcome

Help resolve electrical issues and maintain related property systems
operation.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A reliable electrical maintenance service for property electrical needs.

*Source: Owner decision, 2026-07-25.*

---

## 8. Painting (`SVC-PAINTING`)

**Category:** General Maintenance. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_PAINTING.md`.

### Core Purpose

Covers interior and exterior painting within scope, including surface
preparation when required, paint application, and related finishing
work.

*Source: `SERVICE_CATALOG.md`; Owner decision, 2026-07-25.*

### Core Promise

Improved appearance, renewed finishes, and improved surface condition.

*Source: Owner decision, 2026-07-25.*

### Core Risks

Risks may relate to working at height and ladder use. Risks may relate
to exposure to paint, coatings, and materials. Risks may relate to
surface preparation and work-area conditions.

*Source: Owner decision, 2026-07-25 — risk categories only.*

### Core Constraints

- **Boundary vs. Handyman:** Painting applies when the customer needs
  painting or surface finishing work; Painting must not expand into
  general handyman tasks.
- Plumbing, electrical work, AC Maintenance, and general unrelated work
  are excluded; Waterproofing is excluded unless separately defined.
- Cannot define finish acceptance criteria beyond what is stated above.
- Cannot state product-selection responsibility, ventilation, PPE,
  protection, or waste controls.
- Cannot state color confirmation, change handling, completion evidence,
  or rework policy.
- Cannot claim durability, warranty, safety, or timing without evidence.

*Source: `BUSINESS.md` § Evidence Gate; Owner decision, 2026-07-25.*

### Customer Emotion

Desire for a renewed, improved appearance, and satisfaction with a
refreshed space.

*Source: interpreted from Owner-stated customer problems, 2026-07-25;
Owner-confirmed 2026-07-25 as accepted judgment — remains labeled
interpretation, not sourced fact.*

### Business Outcome

Improve property appearance and renew finishes.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A painting service helping refresh and improve spaces.

*Source: Owner decision, 2026-07-25.*

---

## 9. Handyman Services (`SVC-HANDYMAN`)

**Category:** General Maintenance. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_HANDYMAN.md`.

### Core Purpose

Covers general light tasks that do not require a separate specialist
service — simple installation, assembly, fixing, basic adjustments, and
minor non-specialized repairs. Borderline examples: shelf installation,
hanging items/accessories, door handle adjustments, simple assembly
tasks, and minor non-specialized repairs. Must not be used as an
unrestricted catch-all category.

*Source: `SERVICE_CATALOG.md`; `04_SERVICE_KNOWLEDGE/09_HANDYMAN/README.md`
§ Purpose; Owner decision, 2026-07-25.*

### Core Promise

Help customers complete light general tasks and simple repairs that do
not require a specialist service; a flexible solution for small property
tasks within clearly defined boundaries.

*Source: Owner decision, 2026-07-25 — stays within the scope and four
boundaries confirmed under Core Constraints.*

### Core Risks

Risks may vary depending on the type of general task and the location
where the work is performed. Some tasks may require assessment before
execution to confirm whether they remain within Handyman scope or
require a specialist service. Some requests may fall outside Handyman
boundaries and require routing to Plumbing, Electrical Maintenance, AC
Maintenance, or Painting.

*Source: Owner decision, 2026-07-25 — risk categories only.*

### Core Constraints

- **Boundary vs. Plumbing:** pipe repairs, water leaks, drainage
  problems, and plumbing installations route to Plumbing.
- **Boundary vs. Electrical Maintenance:** electrical wiring, faults,
  circuits, and component repairs route to Electrical Maintenance.
- **Boundary vs. AC Maintenance:** AC repair, servicing, units, and
  cooling-system problems route to AC Maintenance.
- **Boundary vs. Painting:** full painting and surface finishing routes
  to Painting; minor preparation or small adjustments may remain
  Handyman where applicable.
- Handyman is not a substitute for Plumbing, Electrical Maintenance, AC
  Maintenance, or specialized Painting.
- Cannot state job-triage, competency, escalation, safety, or refusal
  criteria beyond what is stated above.
- Cannot state materials, access, customer authorization, documentation,
  or warranty rules.
- Cannot make availability, timing, pricing, or capability claims
  without evidence.
- Must not expand into licensed or otherwise unapproved work.

*Source: `BUSINESS.md` § Evidence Gate; `README.md` § Required Before
Approval; Owner decision, 2026-07-25.*

### Customer Emotion

Relief from resolving accumulated small tasks; satisfaction after
completing minor works that improve use of the space; confidence when a
task is correctly routed to Handyman instead of requiring multiple
specialists.

*Source: Owner decision, 2026-07-25.*

### Business Outcome

Help customers with light general tasks that do not require specialist
services.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A flexible support service for simple general maintenance tasks within
clear boundaries.

*Source: Owner decision, 2026-07-25.*

---

## 10. Drain Unblocking (`SVC-DRAIN-UNBLOCKING`)

**Category:** Drainage & Water Protection. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_DRAIN_UNBLOCKING.md`.

### Core Purpose

AFAQ Alhayat's drain unblocking service, confirmed by the Owner as
offered across the approved UAE coverage. Covers blockages, slow
drainage, blocked sinks, blocked toilets, blocked drains, and removal of
drainage obstructions — within the property's internal drainage scope.

*Source: `04_SERVICE_KNOWLEDGE/10_DRAIN_UNBLOCKING/README.md` § Purpose;
`DECISION_LOG.md` decision 19; Owner decision, 2026-07-25.*

### Core Promise

Removal of blockages and restoration of normal drainage.

*Source: Owner decision, 2026-07-25.*

### Core Risks

Risks may relate to drainage blockages affecting property use or normal
drainage flow. Some cases may require assessment to determine the cause
of the blockage and the appropriate service boundary. Some drainage
issues may relate to concealed areas or external lines outside the
property scope, requiring appropriate routing.

*Source: Owner decision, 2026-07-25 — risk categories only.*

### Core Constraints

- **Does not expand into general plumbing repairs.** Routes to Plumbing
  when pipe faults, plumbing repairs, fixtures, or broader plumbing
  system work is involved.
- **Boundary vs. sewer-line/external-authority work:** scope is limited
  to blockages within the property's drainage scope. External drainage
  problems, main sewer-line issues, or issues involving public networks
  or external responsible authorities are not automatically included and
  require separate evaluation. Does not expand into large external
  infrastructure drainage work.
- **Routing rule:** blockage within the property's drainage scope →
  Drain Unblocking; issue involving external main lines or an outside
  responsible authority → route to the appropriate responsible party.
- Cannot claim hydro-jetting, CCTV inspection, vacuum equipment,
  chemicals, or any other method until confirmed.
- Cannot promise 24/7 attendance, response time, fixed price, guaranteed
  clearance, or warranty until approved.
- Cannot publish licensing or regulatory claims without evidence.

*Source: `README.md` § Publication Guardrails; Owner decision,
2026-07-25.*

### Customer Emotion

Frustration or concern due to disrupted drainage use; need for a
solution that restores normal property use; relief after the blockage
issue is addressed and the appropriate solution path is clear.

*Source: Owner decision, 2026-07-25 — expressed as customer perspective,
not a guaranteed outcome.*

### Business Outcome

Help restore drainage flow and reduce blockage problems affecting
property use.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A specialized service for resolving drainage blockage problems.

*Source: Owner decision, 2026-07-25.*

---

## 11. Waterproofing (`SVC-WATERPROOFING`)

**Category:** Drainage & Water Protection. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_WATERPROOFING.md`.

### Core Purpose

AFAQ Alhayat's waterproofing service, confirmed by the Owner as offered
across the approved UAE coverage. Covers protection against water
ingress and waterproofing-related treatment; thermal insulation remains
excluded unless separately confirmed.

*Source: `04_SERVICE_KNOWLEDGE/11_WATERPROOFING/README.md` § Purpose;
`DECISION_LOG.md` decision 19; Owner decision, 2026-07-25.*

### Core Promise

Protection of the property from water entry and related moisture
problems.

*Source: Owner decision, 2026-07-25.*

### Core Risks

Risks may relate to roof, elevated-area, and access-related conditions.
Risks may relate to exposure to waterproofing materials and coatings.
Risks may relate to surface condition and structural-area factors.

*Source: Owner decision, 2026-07-25 — risk categories only.*

### Core Constraints

- **Boundary vs. Water Leak Detection:** Water Leak Detection identifies
  and locates the leak or problem source; Waterproofing addresses
  protection against water ingress and waterproofing-related causes once
  identified.
- **Boundary vs. Plumbing:** Plumbing applies when the cause is pipes,
  fixtures, or plumbing systems; Waterproofing applies when the issue is
  water ingress protection or waterproofing-related.
- Thermal insulation remains excluded unless separately confirmed.
- Cannot name membrane types, coatings, injection systems, brands, or
  application methods until approved.
- Cannot promise a lifespan, watertight guarantee, fixed warranty, or
  permanent repair without a verified system and site-specific terms.
- Cannot imply structural engineering, authority approval, or licensed
  work without evidence.

*Source: `README.md` § Publication Guardrails; Owner decision,
2026-07-25.*

### Customer Emotion

Concern about water ingress or moisture affecting the property, and the
need for protection against water entry.

*Source: interpreted from Owner-stated customer problems, 2026-07-25;
Owner-confirmed 2026-07-25 as accepted judgment — remains labeled
interpretation, not sourced fact.*

### Business Outcome

Help protect properties from water ingress and related moisture
problems.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A specialized solution for property water protection.

*Source: Owner decision, 2026-07-25.*

---

## 12. Water Leak Detection (`SVC-WATER-LEAK-DETECTION`)

**Category:** Drainage & Water Protection. **Source draft:**
`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_WATER_LEAK_DETECTION.md`.

### Core Purpose

AFAQ Alhayat's water leak detection service, confirmed by the Owner as
offered across the approved UAE coverage. Identifies and locates
suspected water leaks — detection and identification of the possible
leak source or location. Repair work is a separate, excluded scope
unless separately defined. The specific diagnostic methods used remain
undefined.

*Source: `04_SERVICE_KNOWLEDGE/12_WATER_LEAK_DETECTION/README.md` §
Purpose; `DECISION_LOG.md` decision 19; Owner decision, 2026-07-25.*

### Core Promise

Identification and location of a suspected water leak's source.

*Source: Owner decision, 2026-07-25.*

### Core Risks

Risks may relate to hidden or suspected leaks affecting the property.
Accurate assessment may be required to identify the source of the
issue. Some leak locations may involve concealed areas or access
challenges.

*Source: Owner decision, 2026-07-25 — risk categories only.*

### Core Constraints

- **Repair work is excluded from this service's scope unless separately
  defined.** Suspected plumbing-cause leaks route to Plumbing for
  repair; suspected waterproofing-cause leaks route to Waterproofing for
  repair. This service's role ends at identification.
- Cannot claim thermal imaging, acoustic detection, tracer gas, pressure
  testing, moisture meters, or non-invasive diagnosis until confirmed.
- Cannot promise exact detection, no-damage inspection, fixed price,
  response time, repair inclusion, or warranty until approved.
- Cannot publish licensing, certification, or regulatory claims without
  evidence.

*Source: `README.md` § Publication Guardrails; Owner decision,
2026-07-25.*

### Customer Emotion

Concern due to an unknown or suspected leak; need for clarity and
understanding of the problem source; reassurance after the leak location
is identified.

*Source: Owner decision, 2026-07-25 — expressed as customer perspective,
not a guaranteed outcome.*

### Business Outcome

Help customers identify the source of suspected leaks before deciding
on the appropriate repair direction.

*Source: Owner decision, 2026-07-25.*

### Brand Position

A specialized service for detecting and locating leak-related problems.

*Source: Owner decision, 2026-07-25.*

---

## Validation Performed

- All 12 services present; every ID matches `SERVICE_CATALOG.md` exactly.
- Every field traces to either a cited repository source or a dated
  Owner decision recorded in the corresponding `00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_*.md`
  file — no fact introduced beyond those 12 source drafts.
- The three provisional Core Risks entries (Pest Control, General
  Cleaning, Water Tank Cleaning) and Deep Cleaning's qualitative-only
  scope are preserved as caveats, not silently upgraded to settled fact.
- Interpretive Customer Emotion fields remain labeled as interpretation,
  not elevated to sourced fact, matching each source draft's own
  treatment.
- No number, guarantee, price, warranty, license, or regulatory claim
  appears anywhere in this file.
- This file does not modify `ENTERPRISE_SERVICE_META_MODEL.md`,
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`, `SERVICE_CATALOG.md`, or any of
  the 12 source drafts.

## Status

Draft. Content-complete for all 12 services; not Approved — capped below
Approved by the three provisional Core Risks entries per
`ENTERPRISE_PUBLICATION_GATE_MODEL.md` §7. Created under Program C Phase
C.2 Work Package 4, pending independent `AGT-QA` review.
