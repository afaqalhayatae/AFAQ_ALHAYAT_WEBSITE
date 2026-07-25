# Enterprise Service Framework Charter

## Document Information

- **Owner:** Business Owner
- **Status:** Draft (Chartered)
- **Version:** 0.1
- **Prepared:** 2026-07-24
- **Program:** `PROG-ESF-V1` (Program C)

## What This Is

This charter records the existence, purpose, scope, and boundaries of
Program C — the Enterprise Service Framework. It is a charter record only.
It authorizes no work beyond the act of chartering itself: no file under its
initial scope is created by this document, no capability is granted beyond
what already exists, and no execution has begun.

## Purpose

Build the governed enterprise service knowledge foundation using the
Enterprise Service Meta-Model (ESMM) and the Enterprise Publication Gate
Model (EPGM).

## Initial Scope

- Prepare future canonical service knowledge structures.
- Prepare future `SERVICE_DNA_REGISTRY`.
- Prepare future `SERVICE_RELATIONSHIPS` registry.
- Prepare future Customer Intent Model foundation.

"Prepare" means design and readiness work only, within the execution ceiling
below — it does not mean any of these registries or the Customer Intent
Model file exist yet. They do not.

## Execution Ceiling

- `A0`–`A2` only, per `AUTONOMY_AND_APPROVAL_MATRIX.md`.
- All work QA-gated by `AGT-QA` before integration.
- Reversible work only.

## Explicit Exclusions

- No EAOS live automation.
- No new capabilities beyond `00_GOVERNANCE/EAOS/REGISTRIES.md` §1.
- No publishing.
- No customer-facing actions.
- No registry files created yet (`SERVICE_DNA_REGISTRY`,
  `SERVICE_RELATIONSHIPS`, or any other).
- No Customer Intent Model file created.
- No modification to `ENTERPRISE_SERVICE_META_MODEL.md` or
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`.
- No implementation started.

## Relationship to ESMM, EPGM, and EAOS

This charter creates no new authority over any of the three. ESMM remains
the sole definition of what a Service is (Layers 1–4) and the owner of the
future registries this program will eventually build. EPGM remains the sole
computation for publication readiness. EAOS remains the sole mechanism for
agent job structure, lifecycle, and communication; this program's work, once
executed, is carried out as EAOS-governed jobs — it does not create a
parallel execution mechanism. Program C does not redefine any rule in any of
the three.

## Relationship to the Enterprise Constitution

This charter complies with `ENTERPRISE_CONSTITUTION.md` (Approved, v1.0,
ratified retroactively to 2026-07-24 per `DECISION_LOG.md` decision 32). It
introduces no principle, no fact, and no authority beyond what that
Constitution and the documents subordinate to it already permit.

## Program Identity

This program is registered as `PROG-ESF-V1` in the Program Registry section
of `00_GOVERNANCE/EAOS/REGISTRIES.md` §2.

## Status

Draft (Chartered). This charter itself requires no further approval to
exist as a record. Execution of any item in the Initial Scope — including
Phase C.1 — requires a separate, later Owner authorization, following the
same independent-QA and approval practice already used for EAOS, ESMM, and
EPGM. Nothing in this charter should be read as that authorization.

## Phase Progress Log

### Phase C.1.a — Service DNA (2026-07-24)

A Service DNA pilot (`00_GOVERNANCE/ESF/SERVICE_DNA_DRAFT_PILOT_PEST_CONTROL.md`)
and an 11-service expansion (one `SERVICE_DNA_DRAFT_*.md` file per remaining
catalog service, same folder) were prepared, independently reviewed by
`AGT-QA`, corrected, and reviewed by the Business Owner. Owner review
decision, recorded here as the single reference for this milestone rather
than repeated across 12 files:

1. The seven-field ESMM Layer 2 drafting structure demonstrated across all
   12 drafts is approved as the working pattern for the remainder of
   Phase C.1.
2. No unsupported claim may be added to any draft. Fields marked Pending
   Owner Input remain unresolved until the Business Owner supplies the
   underlying source decision — this review does not resolve any of them.
   The Core Promise / Brand Position overlap flagged in the General
   Cleaning and Water Tank Cleaning drafts remains flagged, for the same
   reason.
3. `SERVICE_DNA_REGISTRY.md` is not created by this review.
4. Service Relationships drafting (Phase C.1.b) does not begin from this
   review.
5. All 12 Service DNA drafts remain Draft, non-canonical.

### Phase C.1.b — Service Relationships (2026-07-24)

A Service Relationships preparatory draft
(`00_GOVERNANCE/ESF/SERVICE_RELATIONSHIPS_DRAFT.md`) was prepared,
independently reviewed by `AGT-QA`, reviewed and partially resolved by the
Business Owner (10 candidates confirmed/rejected; 5 source terms and 2
services' zero-coverage status left open), and re-reviewed by `AGT-QA`.

**Standing policy decision — rejected-candidate retention.** The Business
Owner has decided: rejected relationship candidates are retained in their
originating table with status "Rejected," not physically removed. This
applies to `SERVICE_RELATIONSHIPS_DRAFT.md` and to future Program C
artifacts facing the same choice. Reason, as stated by the Owner: rejected
candidates remain historical decision records only. A rejected entry is
not a valid relationship, not canonical data, and must not be used for AI,
automation, publishing, or any downstream consumption — retention records
that a candidate was considered and declined, nothing more.

This entry approves the *pattern*, not any individual service's field
content — each draft's own Pending Owner Input items and flags stand as
written until separately addressed.

### Phase C.1.c — Customer Intent Model (2026-07-24)

A Customer Intent Model preparatory draft
(`00_GOVERNANCE/ESF/CUSTOMER_INTENT_MODEL_DRAFT.md`) was prepared,
independently reviewed by `AGT-QA` (pass, no blocking defects), and
reviewed by the Business Owner. Ownership (Enterprise Knowledge
Governance) and the AI/CRM/Booking/Analytics consumer-only status were
confirmed as drafted. The Owner has since decided Consultation is an
**independent intent** (not an alias or subset of Inspection or Quote
Request) — noted here for the record; this decision has not yet been
written into the draft file itself and remains a tracked open item (see
Phase C.2 § Required Inputs below). No canonical Customer Intent Model
file was created.

### Phase C.1 — Completion Review (2026-07-24)

All three Phase C.1 preparatory drafts (Service DNA — 12 files, Service
Relationships — 1 file, Customer Intent Model — 1 file) completed their
drafting → QA → Owner review cycle. Phase C.1 is complete as chartered
("prepare," not "finalize"). Confirmed still open at completion: most
Service DNA Pending Owner Input fields, the 5 Service Relationships
unresolved terms and 2 zero-coverage services, and recording the
Consultation decision above. None of the three future artifacts
(`SERVICE_DNA_REGISTRY.md`, `SERVICE_RELATIONSHIPS.md`, canonical Customer
Intent Model file) exists.

## Phase C.2 Charter

### 1. Name and Objective

**Phase C.2 — Resolution and Canonical Readiness Assessment.** Resolve the
outstanding per-item Owner decisions left open across the three Phase C.1
preparatory drafts, run one consolidated `AGT-QA` review across the
resolved set, and produce a canonical-readiness assessment for the Owner —
without creating any canonical artifact.

### 2. Scope Boundaries

**In scope:** resolving Pending Owner Input fields across the 12 Service
DNA drafts; resolving the 5 unresolved Service Relationships terms and the
2 zero-coverage services; recording the Consultation = independent-intent
decision (and any further Customer Intent Model gaps) into
`CUSTOMER_INTENT_MODEL_DRAFT.md`; one consolidated `AGT-QA` pass over all
three resolved artifacts together, including cross-artifact consistency
(e.g., do confirmed Relationships align with DNA Core Constraints); a
written canonical-readiness assessment per artifact.

**Out of scope:** creating any canonical file or registry; enabling
automation; publishing; customer-facing action; starting Phase C.3 or any
implementation.

### 3. Required Inputs from C.1 Outputs

- The 12 Service DNA drafts, their Pending Owner Input lists, and the
  Core Promise / Brand Position overlap flag (General Cleaning, Water Tank
  Cleaning).
- `SERVICE_RELATIONSHIPS_DRAFT.md`'s 5 unresolved terms and 2
  zero-coverage services (`SVC-AC-MAINTENANCE`, `SVC-ELECTRICAL-MAINTENANCE`).
- `CUSTOMER_INTENT_MODEL_DRAFT.md` and the Consultation decision recorded
  above, not yet written into that file.
- This charter's Phase Progress Log (C.1.a, C.1.b, C.1.c, and the C.1
  Completion Review entries).

### 4. Work Packages

1. **Resolve remaining Owner decisions** — bring each open item (DNA
   Pending fields, Relationships unresolved terms/coverage, the
   Consultation recording and any other Intent Model gaps) to the Owner
   individually, recording each decision as it is made, using the same
   per-item, no-guessing discipline used throughout Phase C.1.
2. **Consolidated QA review** — one `AGT-QA` pass across all three
   resolved artifacts together, checking both per-artifact criteria
   (already exercised in C.1) and cross-artifact consistency not
   previously tested.
3. **Canonical readiness assessment** — a report, not an action: for each
   of the three future artifacts, state whether the resolved content is
   sufficient and QA-clean to support canonical creation, and what
   remains missing if not.
4. **Future Owner authorization gate** — a distinct, later decision point
   at which the Owner would separately authorize actual canonical artifact
   creation. This gate is defined by Phase C.2 but not opened by it.

### 5. Explicit Exclusions

- No `SERVICE_DNA_REGISTRY.md`, `SERVICE_RELATIONSHIPS.md`, or canonical
  Customer Intent Model file created.
- No modification to `ENTERPRISE_SERVICE_META_MODEL.md` or
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`.
- No EAOS live automation, no new capabilities, no publishing, no
  customer-facing action.
- No Phase C.3 or implementation start.
- `A0`–`A2` only, QA-gated, reversible work only — same ceiling as Phase
  C.1.

### 6. Success Criteria

- Every currently open item across the three C.1 drafts has an explicit
  Owner decision on record — confirmed, rejected, or deferred with a
  stated reason, never silently dropped.
- The consolidated QA pass reaches a clean verdict, or all defects found
  are corrected.
- A canonical-readiness assessment exists for each of the three future
  artifacts.
- No canonical file or registry exists as a byproduct of this phase.

### 7. Risks

- **Fabrication pressure:** resolving roughly twenty discrete open items
  may tempt filling gaps with plausible inference instead of genuine
  Owner input. Mitigation: continue the "stop and ask" discipline used
  throughout Phase C.1.
- **Uneven input burden:** most of the nine thin-source Service DNA
  services have no underlying business fact at all beyond catalog
  identity — the Owner may need to supply substantial new information,
  not just confirm or reject existing candidates, a larger lift than
  Phase C.1.a/C.1.b's confirm/reject pattern.
- **Untested check type:** cross-artifact consistency QA has not run
  before in this program; its defect surface is unknown.
- **Readiness/authorization conflation:** the canonical-readiness
  assessment could be misread as authorization to create. Work package 4
  exists specifically to keep these separate.

### 8. Required Owner Decision Before Starting C.2 Execution

A single authorization: does the Owner approve this Phase C.2 charter —
name, objective, scope, work packages, and exclusions — as the basis for
beginning C.2 execution, starting with Work Package 1 (resolving remaining
Owner decisions), mirroring how Phase C.1 itself began?

## Related Documents

`ENTERPRISE_CONSTITUTION.md`, `ENTERPRISE_SERVICE_META_MODEL.md`,
`ENTERPRISE_PUBLICATION_GATE_MODEL.md`, `00_GOVERNANCE/EAOS/` (all files),
`AUTONOMY_AND_APPROVAL_MATRIX.md`, `AGENT_REGISTRY.md`, `DECISION_LOG.md`.
