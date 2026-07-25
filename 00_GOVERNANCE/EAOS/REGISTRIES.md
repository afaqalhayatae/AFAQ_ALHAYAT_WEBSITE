# EAOS Registries

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24
- **Program:** `PROG-EAOS-V1`

## Purpose

Single registry document for EAOS v1, holding the Capability Registry,
Program Registry, Job Ledger schema, and Stable ID namespaces. No separate
registry file exists in this version — every EAOS document that needs a
capability, program, ledger field, or identifier format references this one
file instead of restating it.

---

## 1. Capability Registry

Capability classes an agent job may request, bounded by the write scope and
authority level already defined for that role in `AGENT_REGISTRY.md` and
`AUTONOMY_AND_APPROVAL_MATRIX.md`. This registry grants nothing beyond what
those documents already allow — it only names the classes so job envelopes
have a shared vocabulary for `allowed_tools`.

| Capability ID | Meaning | Requestable by |
|---|---|---|
| `CAP-READ` | Read-only access to repository content | All 10 roles |
| `CAP-EDIT-OWN-SCOPE` | Edit within the requesting role's registered write scope only | `AGT-GOV, AGT-SVC, AGT-CX, AGT-WEB, AGT-MKT, AGT-AIX, AGT-DES, AGT-MIG` |
| `CAP-AUDIT` | Produce read-only findings/evidence reports | `AGT-QA` primarily; any role in Audit mode |
| `CAP-COORDINATE` | Create bounded jobs, assign paths, sequence work | `AGT-ORCH` only |
| `CAP-EXTERNAL-FETCH` | Read external sources for research (no publishing) | Granted per job, never by default |

A capability request outside a role's registered scope is refused at the
job-envelope stage, before execution — this is a restatement of the existing
"no two editing agents may own the same file" and default-`A1` rules, not a
new control.

---

## 2. Program Registry

Registers named initiatives. A program entry records what it is, not what it
authorizes — spend, publishing, and scope remain governed entirely by
`AUTONOMY_AND_APPROVAL_MATRIX.md` and `AGENT_APPROVAL_WORKFLOW.md`.

| Program ID | Name | Status | Reference |
|---|---|---|---|
| `PROG-KNOWLEDGE-FOUNDATION` | Program A — Enterprise Knowledge Foundation | Complete | Git tag `repository-stabilized-v1` |
| `PROG-EAOS-V1` | Program B — Enterprise Agent Operating System v1 | Draft | This folder, `00_GOVERNANCE/EAOS/` |
| `PROG-ESF-V1` | Program C — Enterprise Service Framework | Draft (Chartered) | `00_GOVERNANCE/ENTERPRISE_SERVICE_FRAMEWORK_CHARTER.md` |

---

## 3. Job Ledger Schema

Field list a future `JOB-######` record must contain, satisfying the Audit
Trail requirement already stated in `AI_OPERATING_MODEL.md`. This is a schema
only — no ledger entry exists yet. The `LEDGER/` folder is created only when
the Phase 4 pilot produces the first real record, never as an empty
placeholder.

| Field | Description |
|---|---|
| `job_id` | `JOB-######`, assigned sequentially |
| `program_id` | The `PROG-*` this job belongs to |
| `agent_role` | The `AGT-*` role that executed it |
| `objective` | One-line statement of what the job did |
| `authority_level` | `A0`–`A4`, per `AUTONOMY_AND_APPROVAL_MATRIX.md` |
| `sources` | Canonical sources consulted |
| `tools` | Capability IDs used, from §1 |
| `write_paths` | Paths touched, if any |
| `timestamps` | Start and end |
| `qa_verdict` | Pass/fail from `AGT-QA`, with findings if failed |
| `approval_evidence` | Reference to any owner approval, if required |
| `checkpoint_rollback_ref` | Git reference for recovery |

---

## 4. Stable ID Namespaces

Follows the existing pattern in `99_STANDARDS/NAMING_CONVENTIONS.md`
(`SVC-`, `LOC-AE-`, `CMP-`, `ADR-`, `FORM-`, `SOP-`).

| Namespace | Format | Example | Used by |
|---|---|---|---|
| Program | `PROG-<NAME>` | `PROG-EAOS-V1` | §2 above |
| Job | `JOB-######` | `JOB-000001` | §3 above |
| Capability | `CAP-<CLASS>` | `CAP-READ` | §1 above |
| Incident | `INC-####` | `INC-0001` | `DECISION_FLOW.md` §Incident and Stop-Condition Escalation |

## Related Documents

`AGENT_REGISTRY.md`, `AUTONOMY_AND_APPROVAL_MATRIX.md`,
`AI_OPERATING_MODEL.md`, `99_STANDARDS/NAMING_CONVENTIONS.md`,
`AGENT_LIFECYCLE.md`, `COMMUNICATION_PROTOCOL.md`, `DECISION_FLOW.md`.
