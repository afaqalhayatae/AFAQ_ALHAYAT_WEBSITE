# Enterprise Publication Gate Model (EPGM)

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24

## Purpose

Defines how publication readiness is computed for an Enterprise Object
composed of multiple governed layers and multiple physical representations.
This is not a seventeenth layer of the Enterprise Service Meta-Model — it
operationalizes ESMM Layer 12 (Publication Lifecycle) and Layer 13
(Enterprise Validation Rules) into one computation. It has no Identity, DNA,
Relationships, or Intent Model of its own.

## Relationship to ESMM

`ENTERPRISE_SERVICE_META_MODEL.md` is a **separate document**, per
`DECISION_LOG.md` decision 28. This model reads the status of every ESMM
layer and produces one number; it does not redefine any layer's ownership,
canonical source, or validation rule. Cross-referenced, never merged.

## Relationship to EAOS

`00_GOVERNANCE/EAOS/` (Approved v1) is a compatible operating system, not a
replacement for this model. This model reuses, without redefining:

- the job envelope and message types in `EAOS/COMMUNICATION_PROTOCOL.md`;
- the Job Ledger schema in `EAOS/REGISTRIES.md`;
- the Detect → Record → Stop → Escalate flow in `EAOS/DECISION_FLOW.md`'s
  "Incident and Stop-Condition Escalation" section, itself drawn from
  `ENTERPRISE_CONSTITUTION.md`.

No new automation level, agent role, or capability is introduced here.

## The Sixteen Concepts

Each concept states: purpose, authority, canonical source, inputs,
validation, allowed transitions, and forbidden interpretations.

### 1. Object-level Status
The single number every channel may trust. **Authority:** computed, not
authored. **Canonical source:** §7 below. **Inputs:** every Required +
Applicable + Available layer, Hard Publication Blocks, Parent status,
bilingual parity. **Validation:** equals §7's output exactly; no manual
override except Emergency Suspension (§14). **Transitions:** Draft → In
Review → Approved → Deprecated → Archived, plus the cross-cutting **Blocked**
and **Suspended** states. **Forbidden:** treating any single file's or
layer's status as the object's status.

### 2. Layer-level Status
Each ESMM layer's own readiness reading. **Authority:** the domain owner
named for that layer in ESMM. **Canonical source:** the file(s) expressing
that layer, reduced through §3 and §4. **Validation:** cannot exceed the
lowest constituent file status, nor any dependency's status. **Forbidden:**
a layer being well-written is not the same as being Approved.

### 3. File/Document Status
The existing convention, unchanged. **Authority:** the authoring domain
agent; approval per `AUTONOMY_AND_APPROVAL_MATRIX.md`. **Canonical source:**
`99_STANDARDS/NAMING_CONVENTIONS.md` §8.4 (`Draft, In Review, Approved,
Deprecated, Archived`). **Forbidden:** a file's own status carries no
authority over the layer or object it feeds.

### 4. Dependency Status
A layer's local content can be fine while what it depends on is not.
**Authority:** whichever domain owns the depended-upon source. **Validation:**
a layer's status is capped at the lowest status among its dependencies.
**Forbidden:** treating a well-written local reference as sufficient when
its target is unresolved.

### 5. Publication Channels
Website, CRM, AI, Booking, Analytics, Automation, marketing/social.
**Authority:** the domain owning each channel. **Validation:** a channel may
be stricter than the object status, never looser. **Forbidden:** a channel
publishing because its own content looked ready, independent of the
object's computed status.

### 6. Hard Publication Blocks
Absolute rules overriding every computation. **Authority:** Business Owner
(`A4`-class facts). **Canonical source:** `CURRENT_PROJECT_STATUS.md` §Hard
Publication Blocks, `99_STANDARDS/QUALITY_CHECKLIST.md`. **Validation:** any
block condition present caps object status at **Blocked**, regardless of
every layer's independent computation. **Forbidden:** waiving a block
because everything else is Approved.

### 7. Minimum-Status Computation
*Object status = the worst status among every Required, Applicable,
Available layer, after each layer is capped by its own dependencies — then
reduced to Blocked if a Hard Publication Block is present, and overridden
entirely by Suspended if an emergency withdrawal is active.* **Authority:**
Knowledge & Governance owns the rule; no one owns the result. **Forbidden:**
averaging, majority vote, or "most layers passed."

### 8. Required versus Optional Layers
Not every layer matters equally for every service. **Authority:** Knowledge
& Governance sets the default; category exceptions require Owner sign-off.
Identity, DNA, Business Rules, Knowledge, and AI Behavior are Required by
default. **Forbidden:** treating an Optional layer's absence as equivalent
to a Required layer's absence.

### 9. Not-Applicable Layers
"Genuinely doesn't apply" versus "not built yet" — both excluded from
computation, for different reasons. **Authority:** the domain agent
proposes; `AGT-QA` validates; Owner confirms for commercial/safety layers.
**Validation:** requires an explicit, evidenced justification — an empty
section is never silently read as Not Applicable. A companion state,
**Deferred / Not Yet Available**, covers layers unbuilt for systemic reasons
(e.g., Automation while live automation is not yet enabled) — excluded from
computation the same way, but re-evaluated once the underlying system
exists; never a permanent exemption. **Forbidden:** using Not Applicable to
avoid building a layer that is actually just unfinished.

### 10. Evidence and Approval Requirements
Ties every status transition to authority that already exists. **Authority:**
exactly the roles and gates in `AGENT_REGISTRY.md`, `AUTONOMY_AND_APPROVAL_MATRIX.md`,
`AGENT_APPROVAL_WORKFLOW.md` — reused verbatim. **Validation:** a layer
cannot reach Approved without independent `AGT-QA` review; a producing role
cannot self-approve. **Forbidden:** this model creating a parallel or
shortcut approval path.

### 11. Deprecation and Archival Behavior
An object's end-of-life is as governed as its launch. **Authority:**
Business Owner. **Canonical source:** `98_LEGACY_ARCHIVE/` convention.
**Validation:** Deprecated means no longer promoted, still referenceable;
Archived means frozen and historical. **Transitions:** Approved/Published →
Deprecated → Archived only; never Archived directly from Draft. **Forbidden:**
deleting content on deprecation.

### 12. Parent-Child Lifecycle Constraints
Prevents a child appearing more ready than its parent, per ESMM Layer 14.
**Authority:** Knowledge & Governance. **Validation:** a child's status is
capped at its parent's. **Forbidden:** treating an informal category label
as an activating Parent — per `DECISION_LOG.md` decision 27, no formal
Parent Service Object currently exists, so this constraint is presently
dormant for every service.

### 13. Bilingual Readiness
Prevents English publishing meaningfully ahead of Arabic. **Authority:**
Business Owner is the only party who may authorize an exception. **Canonical
source:** Constitution Principle 9 (Draft). **Validation:** publishable
status is capped at the lower of the two language statuses, unless an
explicit, recorded, time-bound Owner exception exists. **Forbidden:**
treating "Arabic will follow later" as a standing default.

### 14. Emergency Withdrawal or Suspension
Instant pull for safety or legal reasons. **Authority:** Business Owner;
`AGT-QA` may trigger a provisional Suspension pending immediate Owner
confirmation, never a permanent one alone. **Validation:** Suspended
overrides every other computed status immediately. **Forbidden:** requiring
a full re-approval cycle before the suspension itself can take effect.

### 15. Conflict Handling
Two canonical-ish sources disagreeing. **Authority:** no agent or automated
process resolves this alone. **Canonical source:** the same flow already
ratified for the Constitution and reused in EAOS's `DECISION_FLOW.md` —
**Detect → Record evidence → Stop → Escalate to Owner.** No new mechanism
is introduced. **Validation:** an unresolved conflict forces the affected
layer, and therefore the object, to **Blocked**. **Forbidden:** an agent
picking "the more recent" or "the more complete" source on its own
authority.

### 16. Auditability
Every computed status must be explainable after the fact. **Authority:**
Knowledge & Governance maintains the record; Quality & Integration
validates it. **Canonical source:** none dedicated yet — once used, the Job
Ledger in `00_GOVERNANCE/EAOS/REGISTRIES.md` §3 is the natural home for
status-computation events, but this is not assumed to exist for any object
until actually recorded there. **Forbidden:** a status change with no
traceable cause being treated as valid.

## Compatibility with Existing Status Vocabulary

File-level `Draft / In Review / Approved / Deprecated / Archived`
(`99_STANDARDS/NAMING_CONVENTIONS.md`) needs no change. Layer-level and
Object-level status reuse the same five values, plus two cross-cutting
states now **formally adopted** per `DECISION_LOG.md` decision 31:
**Blocked** and **Suspended**. `Suspended` may be set only by the Business
Owner, or provisionally by `AGT-QA` pending immediate Owner confirmation,
exactly as defined in §14 above — this adoption grants no new authority
beyond what §14 and §6 already specify.

## Ratification Status

Approved. Ratified following independent QA review (0 defects, Pass) and
Owner review, recorded in `DECISION_LOG.md` decision 31, including formal
adoption of the `Blocked`/`Suspended` status modifiers. Ratification covers
this model as a governed computation only — it does not by itself create
any registry, start Program C, or enable live automation.
