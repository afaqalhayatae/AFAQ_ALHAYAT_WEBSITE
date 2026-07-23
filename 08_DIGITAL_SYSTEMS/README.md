# Digital Systems

## Purpose

CRM, customer portal, admin dashboard, API, database, integrations, and automation specifications — per `SYSTEM_ARCHITECTURE.md` Sec. 5. This domain owns data models and system behavior; it must not own human-facing master content (that belongs to the domain the data represents).

---

# Current contents

| Folder | Contents |
|---|---|
| `DATABASE/` | `WORDPRESS_DATABASE_ARCHITECTURE.md` — hybrid WordPress + operational database architecture, migrated from the WordPress research track (see `00_GOVERNANCE/DECISION_LOG.md` decision 13). |

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
