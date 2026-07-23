# Customer and Sales

## Purpose

Booking, customer journeys, sales, customer support, pricing, warranty, and commercial policies — per `SYSTEM_ARCHITECTURE.md` Sec. 5. This domain owns commercial facts (prices, packages, warranty terms); it must not redefine service technical facts owned by `04_SERVICE_KNOWLEDGE/`.

---

# Planned structure

| Folder | Purpose | Status |
|---|---|---|
| `BOOKING/` | Booking process and rules. | Not yet populated |
| `CUSTOMER_JOURNEYS/` | Mapped customer journeys per service/channel. | Not yet populated |
| `SALES/` | Sales process, lead handling, upsell/cross-sell. | Not yet populated |
| `CUSTOMER_SUPPORT/` | Support process and escalation. | Not yet populated |
| `PRICING/` | Pricing model, packages. | Not yet populated |
| `WARRANTY/` | Warranty terms. | Not yet populated |
| `POLICIES/` | Cancellation, refund, and service policies. | Not yet populated |

---

# Related draft source material (unapproved, held)

Several relevant drafts exist but are not yet approved or migrated — see `00_GOVERNANCE/MIGRATION/VALIDATION_REPORT.md` Sec. 3 (Service Packages, Annual Maintenance Contracts, Emergency Services, Pricing Strategy, Customer Support, Booking Process, Service Policies, Warranty Policy, After-Service Process, Upsell/Cross-sell). They remain at their original migration-discovery paths, unmoved, pending a placement decision for each.

---

# Why this domain is not yet populated

Prices, warranty terms, and commercial policies are exactly the kind of fact this project's rules prohibit inventing (`CLAUDE_MIGRATION_PROMPT.md`: "Do not replace placeholder contact facts with guesses... prices, warranty... require authoritative user confirmation"). This domain requires business-owner-approved commercial terms before it can be populated with real content rather than structural placeholders.

---

# Status

Structural placeholder only. Populate once commercial terms are confirmed by ownership and the held draft material is reviewed.
