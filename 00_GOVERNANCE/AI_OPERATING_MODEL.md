# AI Operating Model

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 1.0
- **Effective Date:** 2026-07-23

## Purpose

Define how AFAQ Alhayat operates with one internal human—the business
owner—supported by governed AI agents, automations, software platforms, and
external service providers where necessary.

## Operating Principle

The owner delegates execution, not accountability.

AI agents may research, draft, classify, validate, schedule, monitor, and
execute reversible approved workflows. They may not create business facts,
misrepresent themselves as humans, spend money, publish high-risk content,
enter contracts, expose credentials, or make legal or safety commitments
outside their approved authority.

## Agent Roles

| Agent | Primary responsibility | May edit |
|---|---|---|
| Orchestrator | Plans work, assigns isolated scopes, prevents conflicts, maintains checkpoints | Governance plans and integration records |
| Knowledge & Governance | Architecture, canonical sources, decisions, standards, document lifecycle | `00_GOVERNANCE/`, `99_STANDARDS/` |
| Services & Operations | Service packages, workflows, checklists, evidence requirements | `04_SERVICE_KNOWLEDGE/`, `05_OPERATIONS/` |
| Customer & Sales | Lead intake, booking logic, approved replies, pipeline documentation | `06_CUSTOMER_AND_SALES/` |
| Website & Systems | Website, CRM, data, integrations, deployment documentation | `07_WEBSITE/`, `08_DIGITAL_SYSTEMS/`, `11_TECHNICAL/` |
| Marketing, SEO & Content | Search, landing pages, email, social, analytics, creative briefs | `10_MARKETING_AND_SEO/` and approved channel content |
| AI Experience | Retrieval, chatbot behavior, evaluation, escalation, safety | `09_AI_KNOWLEDGE/` |
| Design | Luxury visual system, responsive UX, accessibility, assets | `12_DESIGN_SYSTEM/` |
| Quality & Integration | Independent checks; blocks unsafe or inconsistent releases | Reports and quality evidence only |

No two editing agents may own the same file simultaneously. The orchestrator
must assign exclusive paths or separate Git worktrees.

## Automation Levels

| Level | Meaning | Example |
|---|---|---|
| `A0` | Read and recommend only | Audit, research summary |
| `A1` | Draft safely; owner reviews before use | New service copy, campaign draft |
| `A2` | Execute reversible internal changes with logs | Update knowledge index, create task |
| `A3` | Publish or act externally within a pre-approved policy | Scheduled approved social post |
| `A4` | Owner approval required every time | Ad spend, contract, credential change, destructive action |

Default level is `A1` unless a workflow is explicitly approved at a higher
level.

## Mandatory Owner Gates

Owner approval is required for:

- Prices, discounts, refunds, warranties, contracts, and payment actions.
- Advertising budgets and material changes to campaign spend.
- Public claims about licenses, certifications, safety, guarantees, response
  times, emergency service, or legal compliance.
- New credentials, domains, social accounts, Google Business Profile changes,
  or access granted to another party.
- Publishing personal data or confidential business information.
- Destructive changes, deletion, irreversible migration, or rollback removal.
- Any answer where canonical sources conflict and the fact cannot safely remain
  unpublished.

## External Provider Model

Physical or regulated services may be fulfilled by an approved external
licensed provider. Before assignment, the system records the required evidence,
scope, confidentiality, customer permissions, and acceptance criteria. The
provider is never described as an internal employee unless the owner changes
the operating model and records that decision.

## Audit Trail

Every autonomous workflow must record:

- Trigger and timestamp.
- Agent and authority level.
- Canonical sources used.
- Inputs and outputs.
- Validation result.
- External action or publication ID.
- Cost where applicable.
- Approval evidence where required.
- Rollback or correction procedure.

## Failure Behavior

When evidence is missing, sources conflict, a safety boundary is reached, or a
tool fails validation, the agent must stop that action, preserve the current
state, record the reason, and route a concise decision to the owner.

## Related Documents

- [`AUTONOMY_AND_APPROVAL_MATRIX.md`](AUTONOMY_AND_APPROVAL_MATRIX.md)
- [`AGENT_REGISTRY.md`](AGENT_REGISTRY.md)
- [`AGENT_APPROVAL_WORKFLOW.md`](AGENT_APPROVAL_WORKFLOW.md)
- [`MODEL_ROUTING_POLICY.md`](MODEL_ROUTING_POLICY.md)
- [`../01_BUSINESS/STAKEHOLDERS.md`](../01_BUSINESS/STAKEHOLDERS.md)
- [`../09_AI_KNOWLEDGE/ANSWER_POLICY.md`](../09_AI_KNOWLEDGE/ANSWER_POLICY.md)
- [`../99_STANDARDS/QUALITY_CHECKLIST.md`](../99_STANDARDS/QUALITY_CHECKLIST.md)
- [`../08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_ORCHESTRATION.md`](../08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_ORCHESTRATION.md)
- [`../08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_RUNBOOK.md`](../08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_RUNBOOK.md)
