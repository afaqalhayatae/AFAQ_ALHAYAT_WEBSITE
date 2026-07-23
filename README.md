# AFAQ Alhayat Enterprise Knowledge System

## Purpose

This repository is the governed knowledge foundation for AFAQ Alhayat. It
organizes business, brand, market, service, operational, website, technical,
marketing, and AI knowledge so every future system can use consistent,
traceable information.

It is a knowledge repository, not yet the production website, CRM, publishing
automation, or customer application.

## Current Status

- Architecture migration completed on a protected Git branch with rollback
  points and checksum evidence.
- Pest Control is complete; eleven additional owner-confirmed service packages
  are at controlled stages of completion.
- Operations, sales, marketing, automation, and technical domains are under
  controlled completion.
- Phone, domain, emirate coverage, and the approved priority-community registry
  may be used from their canonical sources. Other contact and operational facts
  remain field-level Pending/Unverified.
- The approved operating model has one internal human: the business owner.
  Governed AI agents and automated systems perform delegated functions.
- Production implementation must not begin from Draft, HOLD, or Unverified
  content.

See `00_GOVERNANCE/CURRENT_PROJECT_STATUS.md` for the latest detailed status and
`00_GOVERNANCE/DECISION_LOG.md` for approved decisions.

## Repository Map

| Directory | Responsibility |
|---|---|
| `00_GOVERNANCE/` | Scope, decisions, roadmap, ownership, and migration evidence |
| `01_BUSINESS/` | Company purpose, business model, goals, and stakeholders |
| `02_BRAND/` | Brand identity and controlled contact facts |
| `03_MARKET/` | Market research, customer evidence, and approved service areas |
| `04_SERVICE_KNOWLEDGE/` | Canonical service definitions and service packages |
| `05_OPERATIONS/` | SOPs, quality, safety, and delivery controls |
| `06_CUSTOMER_AND_SALES/` | Booking, customer support, sales, pricing, and policies |
| `07_WEBSITE/` | Website requirements and content consumption rules |
| `08_DIGITAL_SYSTEMS/` | CRM, booking, API, data, and integration architecture |
| `09_AI_KNOWLEDGE/` | AI retrieval, answer, entity, and evaluation policies |
| `10_MARKETING_AND_SEO/` | Content, SEO, campaigns, schema, and analytics strategy |
| `11_TECHNICAL/` | Security, testing, deployment, and engineering operations |
| `12_DESIGN_SYSTEM/` | Reusable interface foundations and accessibility guidance |
| `98_LEGACY_ARCHIVE/` | Preserved superseded material; never an active authority |
| `99_STANDARDS/` | Project-wide documentation and quality standards |

## Authority Rules

1. Write each business fact once in its owning domain.
2. Reference canonical facts; do not copy them between website, marketing, CRM,
   or AI documents.
3. Never publish Draft, HOLD, Unverified, or Owner Input Required values.
4. Never invent prices, coverage, contact details, licenses, guarantees,
   certifications, regulatory compliance, or response-time commitments.
5. Preserve history through Git and the legacy archive; do not silently delete
   conflicting evidence.

## Start Here

1. Read `PROJECT_MANIFEST.md`.
2. Read `SYSTEM_ARCHITECTURE.md`.
3. Check `00_GOVERNANCE/CURRENT_PROJECT_STATUS.md`.
4. Review `00_GOVERNANCE/DECISION_LOG.md`.
5. Understand the operating model in `00_GOVERNANCE/AI_OPERATING_MODEL.md` and
   `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`.
6. Use `00_GOVERNANCE/AGENT_REGISTRY.md` and
   `08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_RUNBOOK.md` when delegating work.
7. Route models using `00_GOVERNANCE/MODEL_ROUTING_POLICY.md`.
8. Use `99_STANDARDS/QUALITY_CHECKLIST.md` before approving any release.

## Publication Gate

No content is ready for public use until its owner, status, sources, and review
date are recorded and the applicable quality checks pass.
