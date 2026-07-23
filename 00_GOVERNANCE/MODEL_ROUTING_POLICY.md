# Model Routing Policy

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 1.0
- **Effective Date:** 2026-07-24

## Purpose

Route each agent job to an appropriate current model based on risk, complexity,
latency, and verification needs without coupling the operating system to a
model version that will become obsolete.

## Core Rule

Use the strongest currently available model for high-impact architecture,
governance, safety, migration, and final review. Use a balanced current model
for routine implementation. Use an efficient current model only for bounded,
high-volume, easily verified tasks.

Model freshness never overrides evidence requirements, canonical-source rules,
owner approval gates, independent review, Git checkpoints, or rollback.

## OpenAI Routing

| Work class | Preferred route | Typical reasoning |
|---|---|---|
| Architecture, difficult diagnosis, migration design, final acceptance | `gpt-5.6-sol` or the current flagship successor | High to max |
| Routine repository implementation, structured content, bounded analysis | `gpt-5.6-terra` or the current balanced successor | Medium to high |
| High-volume mechanical classification with deterministic validation | `gpt-5.6-luna` or the current efficient successor | Low to medium |

Before programmatic use, verify model availability for the active account and
confirm that the documented successor has not changed.

## Claude Routing

| Work class | Preferred route |
|---|---|
| Architecture, difficult multi-file reasoning, migration, final review | Current `opus` alias |
| Routine implementation, audits, document generation, validation | Current `sonnet` alias |

Prefer current aliases over hard-coded dated model identifiers unless a
reproducible evaluation or regulated workflow requires a pinned snapshot.

## Dual-Model Review

Use independent model review when work affects repository architecture,
migration, governance, canonical facts, safety, legal or regulatory content,
public claims, publication readiness, or AI answer policy.

The producing model supplies proposed work and evidence. A different model or
independent QA context evaluates it against explicit acceptance criteria.
Unresolved disagreement stops integration.

## Quality Controls

- Never assume the newest model is automatically better for every workload.
- Validate representative tasks before changing a production route.
- Record provider, route, reasoning level, date, and evaluation result for
  material jobs.
- Preserve a fallback route when availability changes.
- Do not send credentials or private customer or owner data unless the approved
  security design explicitly permits it.

## Related Documents

- [`AI_OPERATING_MODEL.md`](AI_OPERATING_MODEL.md)
- [`AGENT_REGISTRY.md`](AGENT_REGISTRY.md)
- [`AUTONOMY_AND_APPROVAL_MATRIX.md`](AUTONOMY_AND_APPROVAL_MATRIX.md)
- [`../08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_RUNBOOK.md`](../08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_RUNBOOK.md)
