# Digital Systems

## Document Control

- **Owner:** Business Owner
- **Status:** Foundation Complete — Implementation Review Required
- **Version:** 1.0
- **Updated:** 2026-07-24

## Index

- [Canonical Data Model](DATA_MODEL.md)
- [API Contract Standard](API_CONTRACTS.md)
- [CRM, Customer Portal, and Owner Dashboard](CRM_AND_PORTALS.md)
- [Integration Standard](INTEGRATION_STANDARD.md)
- [Agent Orchestration](AUTOMATION/AGENT_ORCHESTRATION.md)
- [Agent Runbook](AUTOMATION/AGENT_RUNBOOK.md)

`DATABASE/WORDPRESS_DATABASE_ARCHITECTURE.md` is retained as non-canonical
research. The canonical implementation direction is owned by
[`TECH_STACK.md`](../00_GOVERNANCE/TECH_STACK.md).

## Purpose

CRM, customer portal, admin dashboard, API, database, integrations, and automation specifications — per `SYSTEM_ARCHITECTURE.md` Sec. 5. This domain owns data models and system behavior; it must not own human-facing master content (that belongs to the domain the data represents).

---

# Current contents

| Folder | Contents |
|---|---|
| `DATABASE/` | `WORDPRESS_DATABASE_ARCHITECTURE.md` — hybrid WordPress + operational database architecture, migrated from the WordPress research track (see `00_GOVERNANCE/DECISION_LOG.md` decision 13). |
| `AUTOMATION/` | `AGENT_ORCHESTRATION.md` and `AGENT_RUNBOOK.md` — control-plane architecture and repeatable operating workflow; see `00_GOVERNANCE/AI_OPERATING_MODEL.md`. |

# Planned structure (not yet populated)

| Folder | Purpose |
|---|---|
| `CRM/` | Customer relationship management data model and rules. |
| `CUSTOMER_PORTAL/` | Customer-facing account/portal specification. |
| `ADMIN/` | Internal admin dashboard specification. |
| `API/` | API resource design (`/api/v1/...` per `NAMING_CONVENTIONS.md`). |
| `INTEGRATIONS/` | Third-party integrations (WhatsApp, payment, maps, etc.). |
| `AUTOMATION/` | Workflow automation specifications. |

---

# Why most of this domain is not yet populated

System design (CRM fields, API contracts, integrations) depends on technology decisions not yet made or recorded anywhere in the migrated source material — see `00_GOVERNANCE/TECH_STACK.md`. Authoring detailed specifications without a confirmed stack would mean inventing a system that may not match what's actually built.

---

# Status

Mostly structural placeholder; `DATABASE/` has real migrated content.
