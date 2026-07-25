# Agent Lifecycle

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24
- **Program:** `PROG-EAOS-V1`

## Purpose

Defines how the 10 agent roles already registered in `AGENT_REGISTRY.md` move
through a lifecycle. This version introduces **zero new roles**. It applies
only to:

`AGT-ORCH, AGT-GOV, AGT-SVC, AGT-CX, AGT-WEB, AGT-MKT, AGT-AIX, AGT-DES,
AGT-MIG, AGT-QA`

## Lifecycle Stages

```text
PROPOSED    — a role or a change to an existing role's scope is drafted
              against a stated business need.
PROVISIONED — the AGENT_REGISTRY.md entry is drafted at A1, capability
              grants from REGISTRIES.md §1 are attached, and a model route
              is selected per MODEL_ROUTING_POLICY.md.
ACTIVE      — the Business Owner approves via a DECISION_LOG.md entry; the
              role or change becomes usable in real jobs.
SUSPENDED   — a temporary hold (e.g., repeated QA rejection, an incident
              per DECISION_FLOW.md); no writes until reinstated.
DEPRECATED  — superseded by a newer version of the same role; still
              referenced in historical job records, not assignable to new
              jobs.
RETIRED     — removed from AGENT_REGISTRY.md; history preserved through Git,
              never deleted.
```

## Versioning

Each role carries a version (for example, `AGT-SVC v1.1`) so a scope change
is traceable, matching the `Version:` field already used across governance
documents. A role's version changes only through the same
`PROPOSED → PROVISIONED → ACTIVE` path above — never silently.

## Validation

- A role change is never active until a `DECISION_LOG.md` entry exists for
  it — this reuses the existing decision log rather than creating a parallel
  one.
- No role may grant itself a capability outside `REGISTRIES.md` §1's table
  for that role.
- `AGT-QA`'s independence (read-only, no source edits) cannot be changed by
  this lifecycle — that authority is fixed in `AGENT_REGISTRY.md`.

## Related Documents

`AGENT_REGISTRY.md`, `MODEL_ROUTING_POLICY.md`, `REGISTRIES.md`,
`DECISION_FLOW.md`.
