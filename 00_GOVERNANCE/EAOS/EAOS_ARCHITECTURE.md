# EAOS Architecture

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24
- **Program:** `PROG-EAOS-V1`

## Purpose

Describes how EAOS instruments the six-layer control plane already defined in
`AGENT_ORCHESTRATION.md`. EAOS adds no seventh layer and changes no existing
layer's authority — it makes the existing six operable and traceable.

## The Six Layers, Instrumented

```text
1. Knowledge layer          — unchanged: canonical facts across all domains.
2. Orchestration layer      — unchanged rules; instrumented by the Program
                               Registry section of REGISTRIES.md.
3. Execution layer          — unchanged AGT-* roles and write scopes;
                               instrumented by AGENT_LIFECYCLE.md and the
                               Capability Registry section of REGISTRIES.md.
4. Quality layer            — unchanged AGT-QA authority; instrumented by
                               QUALITY_GATES.md.
5. Approval layer           — unchanged owner gates; instrumented by
                               DECISION_FLOW.md, which chains the existing
                               matrix, workflow, and runbook into one path.
6. Observability layer      — previously conceptual only; instrumented by
                               the Job Ledger schema in REGISTRIES.md and
                               the message types in COMMUNICATION_PROTOCOL.md.
```

## Design Constraints (unchanged, carried forward without exception)

- One human approval authority — the Business Owner.
- Automation levels `A0`–`A4` keep their existing meaning exactly.
- `AGT-QA` remains read-only and independent; EAOS grants it no new power.
- EAOS is documentation only in this version — no running scheduler, no
  credentials, no live automation.

## What EAOS Does Not Introduce

- No new architectural layer beyond the six above.
- No new agent role beyond the 10 already registered in `AGENT_REGISTRY.md`.
- No new automation level beyond `A0`–`A4`.
- No parallel approval authority to the Business Owner.

## Related Documents

`AGENT_ORCHESTRATION.md`, `EAOS_CHARTER.md`, `REGISTRIES.md`,
`AGENT_LIFECYCLE.md`, `QUALITY_GATES.md`, `DECISION_FLOW.md`,
`COMMUNICATION_PROTOCOL.md`.
