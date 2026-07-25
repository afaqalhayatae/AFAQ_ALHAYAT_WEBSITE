# Customer Intent Model Draft — Preparatory

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — Preparatory, Owner-Reviewed (Complete)
- **Version:** 0.2
- **Prepared:** 2026-07-24
- **Updated:** 2026-07-25 (Consultation handling shape recorded — last open item resolved)
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.1.c / C.2

## What This Is

A preparatory draft of ESMM Layer 4 (Customer Intent Model), prepared under
Phase C.1.c authorization. It is **not** the canonical Customer Intent
Model file — no such file is created by this draft, and per
`DECISION_LOG.md` decision 30, the canonical file's exact name and path
within `00_GOVERNANCE/` remain **undecided**; this draft's location in
`00_GOVERNANCE/ESF/` is a working location only, not a claim about that
future path. No `SERVICE_RELATIONSHIPS.md` or `SERVICE_DNA_REGISTRY.md` is
touched or created by this draft.

This draft was reviewed by `AGT-QA` (Pass, 0 blocking defects) before
Consultation's handling shape was recorded; it has not been re-reviewed
by `AGT-QA` since. The Business Owner has now confirmed Ownership, the
four consumers, and all eight intent handling shapes, including
Consultation (see Owner Review Resolution below) — no field remains open.
It is still not approved and not canonical, and must not be cited
elsewhere or used to inform publishing, AI answers, or customer-facing
material.

---

## 1. Ownership Model

Per `ENTERPRISE_SERVICE_META_MODEL.md` Layer 4 and `DECISION_LOG.md`
decision 30:

- **Owner: Enterprise Knowledge Governance.**
- **Consumers, not owners: AI, CRM, Booking, and Analytics.** AI Experience
  is explicitly **not** the sole owner, and is not made owner by this
  draft. AI, CRM, Booking, and Analytics each read this model; none of
  them may define their own separate intent list, per ESMM Layer 4's own
  "Forbidden" rule.

This draft does not reassign, dilute, or qualify that ownership. It is
prepared as Knowledge Governance material, for Knowledge Governance
review.

---

## 2. Intent Taxonomy Structure

The eight intent categories are already fixed by `ENTERPRISE_SERVICE_META_MODEL.md`
Layer 4 — this draft does not invent, add, or remove a category. Each
entry below states only the **handling shape** (the pattern of steps a
request of this type follows), never a committed response time, price, or
availability, per Layer 4's own validation rule. Every handling shape
traces to an existing repository source; where no source describes a
category, that is stated rather than invented.

### Emergency

Handling shape: a request flagged as urgent enters owner-review escalation
unless an approved emergency-availability policy and rules already exist.
No emergency response time or availability is stated or implied by any
current source.

*Source: `06_CUSTOMER_AND_SALES/CUSTOMER_SUPPORT/CUSTOMER_SUPPORT_DRAFT.md`
§ Support Availability ("Urgent requests must enter owner-review escalation
unless approved emergency availability and rules exist in a canonical
source"); `06_CUSTOMER_AND_SALES/CUSTOMER_SUPPORT/GENERAL_SERVICE_FAQ_DRAFT.md`
Q3 ("Owner Input Required. No emergency availability or response
commitment is approved by this draft.").*

### Scheduled

Handling shape: customer submits preferred date/time and service details;
request is reviewed, availability is retrieved or escalated, the
appointment is confirmed, delivered, and followed up.

*Source: `06_CUSTOMER_AND_SALES/BOOKING/BOOKING_PROCESS_DRAFT.md` §
Booking Workflow, Steps 1–2 and 4–5 (the standard, non-emergency path
through the booking process).*

### Inspection

Handling shape: a site visit is performed to assess scope, hazards, or
feasibility before a quotation or commitment is finalized; inspection
findings may affect the eventual quotation.

*Source: `BOOKING_PROCESS_DRAFT.md` § Booking Workflow, Step 2 ("Determine
if a site inspection is required") and Step 3 ("Schedule an inspection...
prepare a quotation"); `06_CUSTOMER_AND_SALES/POLICIES/SERVICE_POLICIES_DRAFT.md`
§ Inspection Policy ("Some services require an on-site inspection before
providing a final quotation. Inspection findings may affect pricing...").*

### Consultation

**Owner-confirmed (2026-07-25): an independent intent**, distinct from
Inspection and Quote Request, not an alias or subset of either.

Handling shape: a customer seeks guidance, understanding, or advice
before deciding the appropriate service or next step. It can exist as a
standalone intent and may later lead to Inspection or Quote Request
depending on the customer's situation, but does not require either.

*Source: Owner decision, 2026-07-25. No specific channel, duration,
staffing, or outcome commitment is stated or implied.*

**Boundary vs. Inspection** (Owner-confirmed 2026-07-25): Inspection is a
site assessment or evaluation of an existing condition; Consultation is
guidance or discussion to help understand the customer's need and
possible direction, not a site assessment itself.

**Boundary vs. Quote Request** (Owner-confirmed 2026-07-25): Quote
Request is when the customer seeks pricing for a defined service;
Consultation is when the customer needs guidance before the exact service
request is defined.

### Warranty

Handling shape: customer reports an issue tied to prior completed work;
the service record is verified; an inspection is scheduled if required;
eligibility is evaluated against stated conditions and exclusions; if
eligible, corrective work is scheduled; customer confirmation is obtained
after completion.

*Source: `06_CUSTOMER_AND_SALES/POLICIES/WARRANTY_POLICY_DRAFT.md` §
Warranty Claim Process (six-step sequence).*

### Complaint

Handling shape: an issue or dissatisfaction is reported (not necessarily
tied to a specific prior warrantable defect); it is logged, investigated,
addressed with a practical solution, followed up, and documented for
future improvement.

*Source: `06_CUSTOMER_AND_SALES/CUSTOMER_SUPPORT/CUSTOMER_SUPPORT_DRAFT.md`
§ Complaint Handling; `06_CUSTOMER_AND_SALES/POLICIES/SERVICE_POLICIES_DRAFT.md`
§ Complaint Resolution.*

### Follow-up

Handling shape: after service completion (or after a complaint's
resolution), AFAQ Alhayat initiates contact to confirm customer
satisfaction, request a review, record feedback, and — where applicable —
raise the possibility of future scheduled maintenance. This is
company-initiated outreach, distinct from a customer-initiated request.

*Source: `BOOKING_PROCESS_DRAFT.md` § Booking Workflow, Step 7;
`CUSTOMER_SUPPORT_DRAFT.md` § Complaint Handling, step 5 ("Follow up after
resolution").*

### Quote Request

Handling shape: customer requests pricing for a service before committing
to a booking; where required, an inspection precedes the quotation;
pricing is explained clearly and customer approval is obtained before any
work or additional charge proceeds.

*Source: `BOOKING_PROCESS_DRAFT.md` § Booking Workflow, Step 3;
`06_CUSTOMER_AND_SALES/POLICIES/SERVICE_POLICIES_DRAFT.md` § Pricing
Policy; `06_CUSTOMER_AND_SALES/CUSTOMER_SUPPORT/GENERAL_SERVICE_FAQ_DRAFT.md`
Q7 ("Yes. Where required, an inspection is performed and an official
quotation is provided before work begins.").*

---

## 3. Inheritance Rule (Stated, Not Applied)

Per ESMM Layer 4: "every service inherits the full set by default;
suppression requires a stated reason." This draft does not apply or
attempt this rule against any of the 12 catalog services — no service's
intents are suppressed here. Any future per-service suppression is a
separate exercise requiring its own stated reason and Owner review, out of
scope for this preparatory draft.

## 4. Consumer Notes (Descriptive Only)

Restating decision 30's consumer list with the source basis for each
consumer's stake, without granting any of them ownership or a separate
intent list:

- **AI** — would use this model to route or shape conversational answers;
  per Layer 4 and decision 30, is a consumer only.
- **CRM** — would use this model to classify inbound requests; no CRM
  system or field mapping exists yet to consume it.
- **Booking** — the richest sourced consumer today; `BOOKING_PROCESS_DRAFT.md`'s
  workflow already implicitly distinguishes several of these intents
  (Scheduled, Inspection, Quote Request, Follow-up) without naming them as
  such.
- **Analytics** — would use this model to categorize request volume by
  intent; no analytics event schema referencing intent exists yet.

None of these four consumers is treated as owner. This section is
descriptive only — it does not authorize any integration.

---

## Owner Review Resolution (2026-07-25)

Recorded under Program C Phase C.2, Work Package 1:

1. **Ownership:** confirmed as drafted — Enterprise Knowledge Governance.
2. **Consumers:** confirmed as drafted — AI, CRM, Booking, and Analytics;
   none is owner.
3. **Consultation:** confirmed as an **independent intent**, not an alias
   or subset of Inspection or Quote Request (see § 2 above). Its handling
   shape remained unsourced and Pending Owner Input at this point — this
   resolution settled the taxonomic question only, not the content.

## Owner Review Resolution — Round 2 (2026-07-25, Consultation Handling Shape)

1. **Definition:** Consultation represents a customer seeking guidance,
   understanding, or advice before deciding the appropriate service or
   next step.
2. **Boundary vs. Inspection:** Inspection is a site assessment/evaluation
   of an existing condition; Consultation is guidance or discussion to
   help understand the customer's need and possible direction.
3. **Boundary vs. Quote Request:** Quote Request is when the customer
   seeks pricing for a defined service; Consultation is when the customer
   needs guidance before defining the exact service request.
4. **Standalone status:** Consultation can exist as a standalone intent
   and may later lead to Inspection or Quote Request depending on the
   customer's situation, but does not require either.
5. Recorded into the Consultation entry in § 2 only. No channel,
   duration, staffing, or outcome commitment was added beyond what is
   stated above; no operational workflow was invented.

This resolution completes the last open item in this draft. It does not
create the canonical Customer Intent Model file, does not modify any
Service DNA draft, and does not modify `SERVICE_RELATIONSHIPS_DRAFT.md`,
ESMM, or EPGM.

## Validation Performed

- All eight intent categories match `ENTERPRISE_SERVICE_META_MODEL.md`
  Layer 4 exactly — none invented, added, or removed.
- Every handling shape, including Consultation's, now traces to either a
  specific cited section of an existing `06_CUSTOMER_AND_SALES/` document
  or an explicit 2026-07-25 Owner decision — none is filled by inference.
- No response time, price, warranty duration, staffing, or availability
  commitment appears in any handling shape, consistent with Layer 4's
  validation rule and with the cited source documents' own explicit
  disclaimers (e.g., `CUSTOMER_SUPPORT_DRAFT.md`: "This draft does not
  establish support hours, emergency availability, or response-time
  commitments"; `BOOKING_PROCESS_DRAFT.md`: "This draft does not promise
  availability... response time...").
- Ownership is stated exactly as decision 30 and ESMM Layer 4 define it:
  Enterprise Knowledge Governance owns it; AI is explicitly not owner.
- The inheritance rule is stated but not exercised against any service —
  no suppression decision was made.
- This file does not modify `ENTERPRISE_SERVICE_META_MODEL.md`,
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`, `SERVICE_DNA_DRAFT_*.md`,
  `SERVICE_RELATIONSHIPS_DRAFT.md`, or any file under
  `06_CUSTOMER_AND_SALES/` or `04_SERVICE_KNOWLEDGE/`.
- No canonical Customer Intent Model file or registry was created.

## Status

Draft — Preparatory, Owner-Reviewed (Complete). Ownership, the four
consumers, and all eight intent handling shapes — including Consultation,
resolved in Round 2 above — are now Owner-confirmed or source-traced. No
field in this draft remains open. Not approved, not canonical — every
populated handling shape still originates from either a source document
that is itself Draft/`Publication: Blocked` or a direct Owner decision not
yet separately confirmed through the underlying policy documents; none
may be treated as an approved fact until that confirmation happens, and
this draft has not been re-reviewed by `AGT-QA` since Round 2.
