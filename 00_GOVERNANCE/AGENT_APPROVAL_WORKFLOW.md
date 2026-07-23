# Agent Approval Workflow

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 1.0
- **Effective Date:** 2026-07-24

## Purpose

Reduce owner interruption while preserving explicit approval for material,
external, destructive, financial, credential, legal, and safety decisions.

## Owner Notification Policy

The owner should see only:

- A decision that changes business direction or an approved fact.
- An `A4` action.
- A conflict between canonical sources.
- A blocked workflow that cannot continue safely.
- A final acceptance summary for a completed phase.

Routine read-only checks, draft creation, formatting, link repair, and internal
validation should be completed by agents within their approved scope without
interrupting the owner.

## Approval Request Format

Every owner request must contain:

1. **Decision:** the exact approval needed.
2. **Recommendation:** one preferred option.
3. **Evidence:** canonical sources and validation results.
4. **Impact:** customer, legal, cost, security, and reputation impact.
5. **Recovery:** checkpoint and rollback.
6. **Safe continuation:** what proceeds if no approval is given.

## Phase Gates

| Gate | Required evidence | Approver |
|---|---|---|
| Start | Objective, scope, authority, paths, checkpoint | Orchestrator; owner only if A4 |
| Edit | Proposed diff or bounded write scope | Policy; owner only if meaning/A4 changes |
| Integrate | QA report, clean checks, changed paths | Orchestrator; owner for canonical approval |
| Publish | Approved content, channel policy, rollback | Owner or certified A3 policy |
| Delete | Itemized target, classification, backup, rollback | Owner every time |

## Approval Semantics

- Silence is not approval.
- Approval is limited to the exact scope shown.
- Approval of a plan is not approval of later destructive execution.
- A new high-risk fact resets the action to `A4`.
- Agents cannot broaden their own authority.

## Related Documents

- [`AI_OPERATING_MODEL.md`](AI_OPERATING_MODEL.md)
- [`AUTONOMY_AND_APPROVAL_MATRIX.md`](AUTONOMY_AND_APPROVAL_MATRIX.md)
- [`AGENT_REGISTRY.md`](AGENT_REGISTRY.md)
