# EAOS Charter

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24
- **Program:** `PROG-EAOS-V1` (Program B)

## Purpose

This charter defines the Enterprise Agent Operating System (EAOS) — the
operable layer that instruments the existing agent control plane so that
jobs, roles, and approvals are traceable in practice, not only described in
policy. EAOS extends the repository's existing operating model. It replaces
none of it.

## Non-Replacement Declaration

EAOS does not redefine, and has no authority to redefine:

- the automation levels (`A0`–`A4`) in `AI_OPERATING_MODEL.md`;
- the specialist agent roster or write scopes in `AGENT_REGISTRY.md`;
- the decision matrix in `AUTONOMY_AND_APPROVAL_MATRIX.md`;
- the owner-approval process in `AGENT_APPROVAL_WORKFLOW.md`;
- the model routing rules in `MODEL_ROUTING_POLICY.md`;
- the control-plane concept or job-envelope fields in `AGENT_ORCHESTRATION.md`;
- the standard operating sequence in `AGENT_RUNBOOK.md`.

Where any EAOS document appears to conflict with one of the above, the
existing document prevails and the conflict is escalated to the Owner, not
resolved locally.

## Scope

EAOS defines, within `00_GOVERNANCE/EAOS/`:

- how the existing 10 specialist agent roles move through a lifecycle
  (`AGENT_LIFECYCLE.md`);
- how those agents exchange concrete messages built on the existing job
  envelope (`COMMUNICATION_PROTOCOL.md`);
- how a single decision flow chains the existing matrix, workflow, and
  runbook together, including incident escalation
  (`DECISION_FLOW.md`);
- how work is gated stage by stage (`QUALITY_GATES.md`);
- the capability, program, ledger, and identifier registries all of the
  above depend on (`REGISTRIES.md`).

## Relationship to the Enterprise Constitution

The Enterprise Constitution (`ENTERPRISE_CONSTITUTION.md`) is Draft and not
yet ratified. EAOS is designed to comply with it once ratified and contains
nothing that anticipates a principle beyond what that draft already states.
Until ratification, EAOS itself remains provisional in the same way.

## Program Identity

This work is registered as `PROG-EAOS-V1` in the Program Registry section of
`REGISTRIES.md`.

## Status

Draft. No EAOS document may be treated as approved authority until:

1. independent QA (`AGT-QA`) has reviewed it;
2. the Phase 4 pilot has succeeded;
3. the Business Owner has reviewed it; and
4. the approval is recorded in `DECISION_LOG.md`.

## Related Documents

`AI_OPERATING_MODEL.md`, `AUTONOMY_AND_APPROVAL_MATRIX.md`,
`AGENT_REGISTRY.md`, `AGENT_APPROVAL_WORKFLOW.md`, `MODEL_ROUTING_POLICY.md`,
`AGENT_ORCHESTRATION.md`, `AGENT_RUNBOOK.md`, `ENTERPRISE_CONSTITUTION.md`.
