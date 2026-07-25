# Communication Protocol

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24
- **Program:** `PROG-EAOS-V1`

## Purpose

Defines the concrete message types exchanged around the job envelope already
required by `AGENT_ORCHESTRATION.md`. No existing envelope field is removed
or redefined. Two additive, optional fields are introduced: `program_id` and
`ledger_ref`, both sourced from `REGISTRIES.md`.

## Job Envelope (unchanged, restated for reference only)

`job_id, agent_role, objective, authority_level, allowed_sources,
allowed_tools, allowed_write_paths, forbidden_actions, budget_limit,
validation_checks, approval_required, rollback_reference, deadline`

Additive fields: `program_id` (a `PROG-*` from `REGISTRIES.md` §2),
`ledger_ref` (a `JOB-*` once the ledger exists, per `REGISTRIES.md` §3).

## Message Types

| Message | From → To | Carries |
|---|---|---|
| `JOB_ASSIGNMENT` | `AGT-ORCH` → Specialist | Full job envelope |
| `STATUS_UPDATE` | Specialist → `AGT-ORCH` | `job_id`, progress, blockers |
| `QA_REQUEST` | Specialist → `AGT-QA` | `job_id`, changed paths, acceptance criteria |
| `QA_VERDICT` | `AGT-QA` → `AGT-ORCH` + Specialist | Pass/fail, findings, required fixes |
| `ESCALATION` | Any role → `AGT-ORCH` → Owner | Stop-condition or incident reason, per `DECISION_FLOW.md` |
| `APPROVAL_REQUEST` | `AGT-ORCH` → Owner | Exact format fixed in `AGENT_APPROVAL_WORKFLOW.md` |
| `APPROVAL_RESPONSE` | Owner → `AGT-ORCH` | Decision, scope boundary, conditions |
| `INTEGRATION_RECORD` | `AGT-ORCH` → Job Ledger | Final state, checkpoint, rollback reference |

## Validation

- Every message carries `job_id` and `agent_role` — untraceable messages are
  not valid under `AI_OPERATING_MODEL.md`'s Audit Trail requirement.
- `QA_VERDICT` may only be issued by `AGT-QA`; no producing role may issue
  its own verdict.
- `APPROVAL_REQUEST` content must match the format in
  `AGENT_APPROVAL_WORKFLOW.md` exactly — this protocol does not define a
  second format.

## What This Protocol Is Not

Not a running message bus. Not a technology choice. These are the structured
records (job files, status notes, review summaries) already implied by
`AGENT_RUNBOOK.md`'s standard workflow, named consistently.

## Related Documents

`AGENT_ORCHESTRATION.md`, `AGENT_RUNBOOK.md`, `AGENT_APPROVAL_WORKFLOW.md`,
`REGISTRIES.md`, `DECISION_FLOW.md`.
