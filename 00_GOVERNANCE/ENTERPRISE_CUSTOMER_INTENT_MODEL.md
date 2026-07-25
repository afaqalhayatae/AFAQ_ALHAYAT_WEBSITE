# Enterprise Customer Intent Model

## Document Information

- **Owner:** Business Owner
- **Status:** Draft
- **Version:** 0.1
- **Prepared:** 2026-07-25
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.2 Work Package 4

## What This Is

The canonical Enterprise Service Meta-Model (ESMM) Layer 4 (Customer
Intent Model), per `DECISION_LOG.md` decisions 26 and 30 and
`ENTERPRISE_SERVICE_META_MODEL.md` §4. It resolves decision 30's open
placement item: the canonical file's name and path within
`00_GOVERNANCE/` were previously undecided; this file, at this path, is
that resolution, per Program C Phase C.2 Work Package 4 (approved
proposal: `00_GOVERNANCE/ENTERPRISE_CUSTOMER_INTENT_MODEL.md`, naming
consistent with its sibling foundational models —
`ENTERPRISE_CONSTITUTION.md`, `ENTERPRISE_SERVICE_META_MODEL.md`,
`ENTERPRISE_PUBLICATION_GATE_MODEL.md`).

It is reshaped from `00_GOVERNANCE/ESF/CUSTOMER_INTENT_MODEL_DRAFT.md` —
Owner-reviewed across two resolution rounds and independently reviewed
by `AGT-QA` — under Work Package 4. No new intent category, handling
shape, or commitment is introduced here beyond what that source draft
already records. This file does not modify
`ENTERPRISE_SERVICE_META_MODEL.md`, `ENTERPRISE_PUBLICATION_GATE_MODEL.md`,
`SERVICE_DNA_REGISTRY.md`, or `SERVICE_RELATIONSHIPS.md`.

The source draft's full drafting history — the taxonomic resolution of
Consultation as an independent intent, and the reasoning behind each
Owner decision — remains the historical audit trail and is not
duplicated here.

This model's own status is **Draft**, not Approved. Every handling shape
below still originates from either a source document that is itself
`Draft`/`Publication: Blocked`, or a direct Owner decision not yet
separately confirmed through the underlying policy documents — neither
is elevated to approved fact by this file's creation.

---

## 1. Ownership Model

Per `ENTERPRISE_SERVICE_META_MODEL.md` Layer 4 and `DECISION_LOG.md`
decision 30:

- **Owner: Enterprise Knowledge Governance.**
- **Consumers, not owners: AI, CRM, Booking, and Analytics.** AI
  Experience is explicitly **not** the sole owner. Each of the four
  consumers reads this model; none may define its own separate intent
  list, per ESMM Layer 4's own "Forbidden" rule.

---

## 2. Intent Taxonomy

The eight intent categories are fixed by `ENTERPRISE_SERVICE_META_MODEL.md`
Layer 4 — this model does not add, remove, or rename any category. Each
entry states only the **handling shape** — the pattern of steps a
request of this type follows — never a committed response time, price,
or availability, per Layer 4's own validation rule.

### Emergency

A request flagged as urgent enters owner-review escalation unless an
approved emergency-availability policy and rules already exist. No
emergency response time or availability is stated or implied by any
current source.

*Source: `06_CUSTOMER_AND_SALES/CUSTOMER_SUPPORT/CUSTOMER_SUPPORT_DRAFT.md`
§ Support Availability; `GENERAL_SERVICE_FAQ_DRAFT.md` Q3.*

### Scheduled

Customer submits preferred date/time and service details; the request is
reviewed, availability is retrieved or escalated, the appointment is
confirmed, delivered, and followed up.

*Source: `06_CUSTOMER_AND_SALES/BOOKING/BOOKING_PROCESS_DRAFT.md` §
Booking Workflow, Steps 1–2 and 4–5.*

### Inspection

A site visit is performed to assess scope, hazards, or feasibility
before a quotation or commitment is finalized; inspection findings may
affect the eventual quotation.

*Source: `BOOKING_PROCESS_DRAFT.md` § Booking Workflow, Steps 2–3;
`06_CUSTOMER_AND_SALES/POLICIES/SERVICE_POLICIES_DRAFT.md` § Inspection
Policy.*

### Consultation

**An independent intent**, distinct from Inspection and Quote Request —
not an alias or subset of either.

A customer seeks guidance, understanding, or advice before deciding the
appropriate service or next step. It can exist as a standalone intent
and may later lead to Inspection or Quote Request depending on the
customer's situation, but does not require either.

**Boundary vs. Inspection:** Inspection is a site assessment or
evaluation of an existing condition; Consultation is guidance or
discussion to help understand the customer's need and possible
direction, not a site assessment itself.

**Boundary vs. Quote Request:** Quote Request is when the customer seeks
pricing for a defined service; Consultation is when the customer needs
guidance before the exact service request is defined.

*Source: Owner decision, 2026-07-25. No specific channel, duration,
staffing, or outcome commitment is stated or implied.*

### Warranty

Customer reports an issue tied to prior completed work; the service
record is verified; an inspection is scheduled if required; eligibility
is evaluated against stated conditions and exclusions; if eligible,
corrective work is scheduled; customer confirmation is obtained after
completion.

*Source: `06_CUSTOMER_AND_SALES/POLICIES/WARRANTY_POLICY_DRAFT.md` §
Warranty Claim Process.*

### Complaint

An issue or dissatisfaction is reported (not necessarily tied to a
specific prior warrantable defect); it is logged, investigated,
addressed with a practical solution, followed up, and documented for
future improvement.

*Source: `CUSTOMER_SUPPORT_DRAFT.md` § Complaint Handling;
`SERVICE_POLICIES_DRAFT.md` § Complaint Resolution.*

### Follow-up

After service completion (or after a complaint's resolution), AFAQ
Alhayat initiates contact to confirm customer satisfaction, request a
review, record feedback, and — where applicable — raise the possibility
of future scheduled maintenance. This is company-initiated outreach,
distinct from a customer-initiated request.

*Source: `BOOKING_PROCESS_DRAFT.md` § Booking Workflow, Step 7;
`CUSTOMER_SUPPORT_DRAFT.md` § Complaint Handling, step 5.*

### Quote Request

Customer requests pricing for a service before committing to a booking;
where required, an inspection precedes the quotation; pricing is
explained clearly and customer approval is obtained before any work or
additional charge proceeds.

*Source: `BOOKING_PROCESS_DRAFT.md` § Booking Workflow, Step 3;
`SERVICE_POLICIES_DRAFT.md` § Pricing Policy; `GENERAL_SERVICE_FAQ_DRAFT.md`
Q7.*

---

## 3. Inheritance Rule (Stated, Not Applied)

Per ESMM Layer 4: every service inherits the full set of eight intents
by default; suppression requires a stated reason. This model does not
apply or exercise this rule against any of the 12 catalog services — no
service's intents are suppressed here. Any future per-service
suppression is a separate exercise requiring its own stated reason and
Owner review.

---

## 4. Consumer Notes (Descriptive Only)

Restating decision 30's consumer list with the source basis for each
consumer's stake, without granting any of them ownership or a separate
intent list:

- **AI** — would use this model to route or shape conversational
  answers; a consumer only.
- **CRM** — would use this model to classify inbound requests; no CRM
  system or field mapping exists yet to consume it.
- **Booking** — the richest sourced consumer today; `BOOKING_PROCESS_DRAFT.md`'s
  workflow already implicitly distinguishes several of these intents
  (Scheduled, Inspection, Quote Request, Follow-up) without naming them
  as such.
- **Analytics** — would use this model to categorize request volume by
  intent; no analytics event schema referencing intent exists yet.

None of these four consumers is treated as owner. This section is
descriptive only — it does not authorize any integration.

---

## Validation Performed

- All eight intent categories match `ENTERPRISE_SERVICE_META_MODEL.md`
  Layer 4 exactly — none invented, added, or removed.
- Every handling shape, including Consultation's, traces to either a
  specific cited section of an existing `06_CUSTOMER_AND_SALES/`
  document or an explicit Owner decision — none filled by inference.
- No response time, price, warranty duration, staffing, or availability
  commitment appears in any handling shape.
- Ownership is stated exactly as decision 30 and ESMM Layer 4 define it:
  Enterprise Knowledge Governance owns it; AI is explicitly not owner.
- The inheritance rule is stated but not exercised against any service —
  no suppression decision was made.
- This file does not modify `ENTERPRISE_SERVICE_META_MODEL.md`,
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`, `SERVICE_DNA_REGISTRY.md`,
  `SERVICE_RELATIONSHIPS.md`, or `CUSTOMER_INTENT_MODEL_DRAFT.md`.

## Status

Draft. Content-complete — ownership, the four consumers, and all eight
intent handling shapes (including Consultation) are populated; no field
remains open. Not Approved — every handling shape still originates from
either a source document that is itself `Draft`/`Publication: Blocked`
or a direct Owner decision not yet separately confirmed through the
underlying policy documents. Created under Program C Phase C.2 Work
Package 4, pending independent `AGT-QA` review.
