# Enterprise Service Meta-Model (ESMM)

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24

## Purpose

Defines what a Service **is**, as a single abstract enterprise object, before
any document, page, record, or workflow represents it. Every service
package, website page, CRM record, AI knowledge object, booking flow,
automation workflow, and analytics event is a **projection** of this one
object — never a second definition of it. This document is technology
independent: no database, schema, or programming concept appears here.

## Position in the Architecture

```text
Business Owner
     |
Enterprise Constitution        (why anything must be true — Draft, unratified)
     |
SYSTEM_ARCHITECTURE.md          (how the repository is structured)  }  parallel
Enterprise Service Meta-Model   (what a Service fundamentally is)   }  authorities
     |
     +-- Enterprise Publication Gate Model — separate document, cross-referenced
     |   only (see "Relationship to the Publication Gate Model" below).
     +-- Enterprise Agent Operating System (EAOS, Approved v1) — a compatible
         operating system this model's Automation Layer and Publication
         Lifecycle attach to. ESMM does not replace EAOS, and EAOS does not
         redefine ESMM.
```

- **Below the Enterprise Constitution.** No layer or validation rule here
  overrides a Constitution principle; where either appears to conflict, this
  model is corrected, not the Constitution.
- **Parallel in scope with `SYSTEM_ARCHITECTURE.md`.** That document governs
  where files live and how they are named; this document governs what a
  Service Object is. Neither is subordinate to the other.
- **Not an implementation document.** No layer below prescribes a
  technology, storage mechanism, or programming construct.
- **Not a replacement for EAOS.** EAOS governs how agents work; ESMM governs
  what a service is. Layer 11 (Automation) and Layer 12 (Publication
  Lifecycle) are the two points where this model's concepts attach to EAOS's
  job envelope and phase gates, defined in `00_GOVERNANCE/EAOS/`.

## The Service Object — Core Definition

A Service is one abstract object made of four **invariant** parts and a set
of **governed layers**:

- **Identity** — what makes this service this service, and no other.
- **DNA** — its unchanging nature: why it exists, what it promises, what it
  risks, what it cannot do.
- **Relationships** — how it connects to every other service.
- **Intent Model** — the shapes of need a customer can bring to it.

These four are constant — every projection traces back to them and none may
fork a private version. Layers 5–11 are governed lenses through which the
core becomes visible to a specific audience or system, each bound to a
canonical owner. Layers 12–16 are meta-rules governing the object's
lifecycle, integrity, inheritance, evolution, and growth.

## The Sixteen Layers

Each layer states: purpose, owner, canonical source, dependencies,
validation, allowed inheritance, and forbidden duplication.

### 1. Service Identity Model
Root of the object; nothing attaches until identity exists. **Owner:**
Knowledge & Governance. **Canonical source:** `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`
(assignment mechanism; this model defines only the shape). **Dependencies:**
none. **Validation:** unique, immutable, bilingual, never inferred.
**Inheritance:** a variant references a parent identity, never mints a new
one. **Forbidden:** no projection may assign its own identity.

### 2. Service DNA
The unchanging nature: Core Purpose, Core Promise, Core Risks, Core
Constraints, Customer Emotion, Business Outcome, Brand Position. **Owner:**
Business Owner (highest judgment layer). **Canonical source:** future
`SERVICE_DNA_REGISTRY` — approved in concept per `DECISION_LOG.md` decision
24, placed in `04_SERVICE_KNOWLEDGE`, not yet built. **Dependencies:**
Identity. **Validation:** qualitative and evidence-independent only — no
number, guarantee, or price. **Inheritance:** a child inherits parent DNA,
overrides only genuine differences. **Forbidden:** DNA is never restated
inside Business Rules, Knowledge, or AI Behavior — those layers reference it.

### 3. Service Relationships
Parent, Children, Related, Alternatives, Upsell, Cross-sell, Dependencies.
**Owner:** Knowledge & Governance; Market & Sales for upsell/cross-sell
judgment. **Canonical source:** future `SERVICE_RELATIONSHIPS` registry —
approved in concept per decision 25, placed in `04_SERVICE_KNOWLEDGE`, not
yet built. **Dependencies:** Identity. **Validation:** both ends of a
relationship must exist in the catalog; no cycles. **Inheritance:** a child
inherits parent Related/Alternatives unless overridden. **Forbidden:** no
channel may run independent "recommended services" logic outside this graph.

### 4. Customer Intent Model
Emergency, Scheduled, Inspection, Consultation, Warranty, Complaint,
Follow-up, Quote Request. **Owner:** Enterprise Knowledge Governance, per
`DECISION_LOG.md` decision 30 — AI, CRM, Booking, and Analytics are
consumers, not owners; AI Experience is explicitly not the sole owner.
**Canonical source:** future enterprise-wide model, exact file not yet
placed. **Dependencies:** Identity. **Validation:** an intent describes
handling shape, never a committed response time. **Inheritance:** every
service inherits the full set by default; suppression requires a stated
reason. **Forbidden:** no channel invents its own separate intent list.

### 5. Business Rules Layer
Conditions, never facts. **Owner:** Customer & Sales; Business Owner for any
change. **Canonical source:** `06_CUSTOMER_AND_SALES/PRICING/*`,
`WARRANTY/*`, `POLICIES/*`. **Dependencies:** DNA. **Validation:** no
literal price, discount, or warranty duration — reference and conditions
only. **Inheritance:** children inherit parent rules unless overridden with
evidence. **Forbidden:** never restate a commercial fact owned in
`06_CUSTOMER_AND_SALES/*`.

### 6. Knowledge Layer
What a human must know to deliver, sell, or explain this correctly.
**Owner:** Services & Operations. **Canonical source:**
`04_SERVICE_KNOWLEDGE/<SERVICE>/*`, `05_OPERATIONS/*`. **Dependencies:**
Identity, DNA. **Validation:** references operational/safety content, never
restates it; bilingual parity mandatory. **Inheritance:** children inherit
shared knowledge, add only genuine service-specific detail. **Forbidden:**
operational/safety facts stay owned once.

### 7. AI Behavior Layer
How AI systems may talk about, recommend, and answer questions on this
service. **Owner:** AI Experience. **Canonical source:**
`09_AI_KNOWLEDGE/ANSWER_POLICY.md`, `RETRIEVAL_POLICY.md`,
`ENTITY_REGISTRY.md`. **Dependencies:** DNA, Knowledge, Intent Model.
**Validation:** every answer cites a canonical source; guardrails from DNA
may only be narrowed, never loosened. **Inheritance:** children inherit and
may only narrow parent guardrails. **Forbidden:** does not redefine
retrieval/answer mechanics.

### 8. Website Layer
Presentation, never origination. **Owner:** Website & Systems. **Canonical
source:** `07_WEBSITE/*`. **Dependencies:** Identity, DNA, Business Rules,
Brand/Contact authority. **Validation:** no master fact origin. **Inheritance:**
children inherit parent presentation pattern by default. **Forbidden:** never
re-hosts contact, price, or coverage facts.

### 9. CRM Layer
How the object is represented as a trackable customer-relationship
instance. **Owner:** Website & Systems. **Canonical source:**
`08_DIGITAL_SYSTEMS/CRM_AND_PORTALS.md`, `DATA_MODEL.md`. **Dependencies:**
Identity, Customer Intent Model. **Validation:** no new intent/stage
semantics invented locally. **Inheritance:** children inherit parent
classification unless justified otherwise. **Forbidden:** never redefines
Identity or DNA inside a CRM description.

### 10. Analytics Layer
What "success" and "signal" mean for this service. **Owner:** Marketing,
SEO & Content; Services & Operations for operational KPIs. **Canonical
source:** `04_SERVICE_KNOWLEDGE/SERVICE_KPIS.md`, `10_MARKETING_AND_SEO/ANALYTICS.md`.
**Dependencies:** DNA (Business Outcome), Publication Lifecycle.
**Validation:** no new metric invented per service — selection only; targets
pending until owner-confirmed. **Inheritance:** children inherit parent KPI
set. **Forbidden:** never restates global analytics/consent policy.

### 11. Automation Layer
Which automated behaviors are conceptually eligible, without asserting any
are live. **Owner:** Website & Systems today; **EAOS (`00_GOVERNANCE/EAOS/`,
Approved v1)** for the job/approval mechanics once automation is actually
enabled. **Canonical source:** `08_DIGITAL_SYSTEMS/AUTOMATION/*`; EAOS's
`COMMUNICATION_PROTOCOL.md` and `DECISION_FLOW.md`. **Dependencies:** Intent
Model, Business Rules. **Validation:** status must read "Not Yet
Implemented" until EAOS enables it for this service through its own
approval gate — this model does not enable automation itself. **Inheritance:**
children inherit parent's eligible categories. **Forbidden:** does not
redefine EAOS mechanics — only declares eligibility.

### 12. Publication Lifecycle
The entire object moves through one lifecycle, never per-channel. **Owner:**
Quality & Integration; Business Owner for final approval. **Canonical
source:** the computation defined in `ENTERPRISE_PUBLICATION_GATE_MODEL.md`
— a separate, cross-referenced document (see below), not merged here.
**Dependencies:** every layer above. **Validation:** object status is the
minimum across all layers, never an average. **Inheritance:** a child's
status can never exceed its parent's. **Forbidden:** state is tracked once
per object, never re-declared per channel.

### 13. Enterprise Validation Rules
The invariants every Service Object must satisfy. **Owner:** Knowledge &
Governance, bound by the Enterprise Constitution. **Canonical source:** this
model, plus `SYSTEM_ARCHITECTURE.md` §7. **Dependencies:** the Enterprise
Constitution. **Rules:** one identity per real-world service; no fact
duplicated across layers; every layer traces to a canonical owner; no layer
claims a lifecycle state its dependencies haven't reached; every
price/warranty/safety/license claim traces to an owner-gated source.
**Inheritance:** applies uniformly, without exception. **Forbidden:** none —
this is the layer preventing duplication elsewhere.

### 14. Object Inheritance Rules
How a child/variant inherits from and overrides a parent. **Owner:**
Knowledge & Governance. **Canonical source:** this model. **Dependencies:**
DNA, Relationships. **Validation:** additive-by-default,
overriding-by-exception; every override states a reason. **Inheritance:**
multi-level inheritance permitted; multiple-parent inheritance requires
explicit resolution. **Forbidden:** an override states only the delta.

**Note:** per `DECISION_LOG.md` decision 27, `SERVICE_CATALOG.md` categories
remain classification labels only — no Parent Service Object exists yet, so
this layer is currently dormant for every service in the catalog.

### 15. Versioning Rules
Distinguishes a clarification from a redefinition. **Owner:** Knowledge &
Governance (the model); Services & Operations (instances). **Canonical
source:** `99_STANDARDS/NAMING_CONVENTIONS.md` semantic versioning,
extended here. **Dependencies:** Object Inheritance Rules. **Validation:** a
Major version changes DNA or Identity (escalated per the Constitution's
Detect → Record → Stop → Escalate flow); a Minor version updates a layer
without changing what the service fundamentally is. **Inheritance:** a
child's version is independent of its parent's, but a parent Major change
forces re-review of children. **Forbidden:** version history lives once per
object.

### 16. Extension Rules
How the model absorbs growth without redesign. **Owner:** Knowledge &
Governance; Owner approval required for structural extension. **Canonical
source:** this model. **Dependencies:** Enterprise Validation Rules.
**Validation:** a new layer needs a distinct owner and canonical source,
must not duplicate an existing layer, is optional until adopted, and is
itself a Major model version. **Inheritance:** existing services do not
retroactively acquire a new layer's obligations. **Forbidden:** an extension
may never redefine Identity, DNA, Relationships, or Intent — those four are
constant; layers are the variable, extensible surface.

## Relationship to the Enterprise Publication Gate Model

`ENTERPRISE_PUBLICATION_GATE_MODEL.md` is a **separate document**. It
operationalizes Layer 12 and Layer 13 into a computation. It is
cross-referenced from this model and cross-references back; it is never
merged into this file, per `DECISION_LOG.md` decision 28.

## Relationship to EAOS

`00_GOVERNANCE/EAOS/` (Approved v1) is a compatible operating system, not a
replacement for this model and not replaced by it. Layer 11 and Layer 12
are the only points of contact: EAOS's job envelope, message types, and
phase gates are the mechanism; this model's Automation Layer and Publication
Lifecycle are the concepts those mechanisms act on. Neither document
redefines the other's rules.

## Governance Decisions Already Recorded

- Decision 24 — future `SERVICE_DNA_REGISTRY`, placement `04_SERVICE_KNOWLEDGE`, not yet built.
- Decision 25 — future `SERVICE_RELATIONSHIPS` registry, placement `04_SERVICE_KNOWLEDGE`, not yet built.
- Decision 26/30 — Customer Intent Model ownership is Enterprise Knowledge Governance; AI, CRM, Booking, Analytics are consumers; exact file path still undecided.
- Decision 27 — `SERVICE_CATALOG.md` categories remain labels only; no Parent Service Object yet.
- Decision 28 — Publication Gate Model stays separate from this model.
- Decision 29 — future ESMM/EPGM documents placed under `00_GOVERNANCE/`.

## Ratification Status

Approved. Ratified following independent QA review (0 defects, Pass) and
Owner review, recorded in `DECISION_LOG.md` decision 31. Ratification
covers this model as a governed conceptual framework only — it does not by
itself create `SERVICE_DNA_REGISTRY`, `SERVICE_RELATIONSHIPS`, or a Customer
Intent Model file, and does not start Program C.
