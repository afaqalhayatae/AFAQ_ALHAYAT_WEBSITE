# Agent Registry

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 1.0
- **Effective Date:** 2026-07-24

## Purpose

Define the specialist agents that may work in this repository, their authority,
their exclusive write scopes, and the evidence required before their work can
be integrated.

## Operating Rules

- The Business Owner is the only human approval authority.
- The Orchestrator creates bounded jobs and assigns one writer per path.
- Every agent defaults to `A1` unless a job explicitly grants a higher level.
- Agents may not invent business facts or treat Draft, HOLD, or Unverified
  content as approved.
- Destructive work, external publishing, credentials, money, legal claims, and
  safety commitments always require the owner gate defined in
  `AUTONOMY_AND_APPROVAL_MATRIX.md`.
- A producing agent may not approve its own work. Quality & Integration performs
  the independent review.

## Specialist Agents

| Agent ID | Role | Default authority | Primary write scope | Required validation |
|---|---|---:|---|---|
| `AGT-ORCH` | Orchestrator | A1 | Governance plans and job records only | Scope, dependencies, conflict check |
| `AGT-GOV` | Knowledge & Governance | A1 | `00_GOVERNANCE/`, `99_STANDARDS/` | SSOT, metadata, links, decision alignment |
| `AGT-SVC` | Services & Operations | A1 | `04_SERVICE_KNOWLEDGE/`, `05_OPERATIONS/` | Service template, evidence, safety gate |
| `AGT-CX` | Customer & Sales | A1 | `06_CUSTOMER_AND_SALES/` | Canonical facts, consent, owner gates |
| `AGT-WEB` | Website & Systems | A1 | `07_WEBSITE/`, `08_DIGITAL_SYSTEMS/`, `11_TECHNICAL/` | Architecture, security, accessibility |
| `AGT-MKT` | Marketing, SEO & Content | A1 | `10_MARKETING_AND_SEO/` | Brand, SEO/GEO, claims, publication gate |
| `AGT-AIX` | AI Experience | A1 | `09_AI_KNOWLEDGE/` | Answer policy, retrieval, evaluations |
| `AGT-DES` | Design | A1 | `12_DESIGN_SYSTEM/` | Brand consistency, RTL/LTR, accessibility |
| `AGT-QA` | Quality & Integration | A0 | Audit reports only | Independent checks; no source edits |
| `AGT-MIG` | Migration Engineer | A1 | Approved migration paths only | Checkpoint, manifest, checksums, rollback |

## Job Assignment

Every job must use the envelope defined in
`../08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_ORCHESTRATION.md` and must state:

- Exact objective and deliverables.
- Authority level.
- Allowed sources and write paths.
- Forbidden actions.
- Validation and acceptance criteria.
- Approval requirement.
- Git checkpoint or rollback reference.

## Integration Gate

Work may be integrated only when:

1. The producing agent reports the changed paths.
2. `AGT-QA` independently validates the acceptance criteria.
3. No canonical-source conflict remains.
4. Required owner approvals are recorded.
5. Git diff and recovery evidence are available.

## Related Documents

- [`AI_OPERATING_MODEL.md`](AI_OPERATING_MODEL.md)
- [`AUTONOMY_AND_APPROVAL_MATRIX.md`](AUTONOMY_AND_APPROVAL_MATRIX.md)
- [`AGENT_APPROVAL_WORKFLOW.md`](AGENT_APPROVAL_WORKFLOW.md)
- [`MODEL_ROUTING_POLICY.md`](MODEL_ROUTING_POLICY.md)
- [`../08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_RUNBOOK.md`](../08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_RUNBOOK.md)
