# Enterprise Agent Operating System (EAOS)

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24
- **Updated:** 2026-07-24
- **Program:** `PROG-EAOS-V1` (Program B)

## What This Is

EAOS is the operable layer instrumenting the agent control plane already
defined in `AGENT_ORCHESTRATION.md`. It extends the existing governance
foundation — `AI_OPERATING_MODEL.md`, `AUTONOMY_AND_APPROVAL_MATRIX.md`,
`AGENT_REGISTRY.md`, `AGENT_APPROVAL_WORKFLOW.md`, `MODEL_ROUTING_POLICY.md`,
`AGENT_ORCHESTRATION.md`, `AGENT_RUNBOOK.md` — and replaces none of it.

## Contents

| File | Purpose |
|---|---|
| `EAOS_CHARTER.md` | Purpose, scope, non-replacement declaration |
| `EAOS_ARCHITECTURE.md` | The six-layer control plane, instrumented |
| `REGISTRIES.md` | Capability Registry, Program Registry, Job Ledger schema, Stable ID namespaces |
| `AGENT_LIFECYCLE.md` | Propose → Provision → Active → Suspend → Deprecate → Retire, for the 10 existing roles only |
| `COMMUNICATION_PROTOCOL.md` | Concrete message types built on the existing job envelope |
| `DECISION_FLOW.md` | The unified decision path, including Incident and Stop-Condition Escalation |
| `QUALITY_GATES.md` | Six gates wrapping `99_STANDARDS/QUALITY_CHECKLIST.md` |

## Status

Every file above is `Status: Approved`, `Version: 0.1`, following independent
QA pass, a successful Phase 4 pilot, Business Owner review, and approval
recorded in `DECISION_LOG.md` decision 23. No cross-links have been added
from outside this folder in this phase — `README.md` (repository root),
`CLAUDE.md`, `SYSTEM_ARCHITECTURE.md`, `AI_OPERATING_MODEL.md`,
`AGENT_REGISTRY.md`, and `DECISION_LOG.md` remain untouched.

## Compliance

EAOS introduces zero new agent roles (only the 10 already in
`AGENT_REGISTRY.md`), zero new automation levels (only `A0`–`A4`), and zero
new architectural layers beyond the six in `AGENT_ORCHESTRATION.md`. It
complies with the Enterprise Constitution (`ENTERPRISE_CONSTITUTION.md`,
Approved, v1.0), ratified retroactively to 2026-07-24 per `DECISION_LOG.md`
decision 32, which confirms this approval remains valid without reopening
decision 23.
