# Customer and Sales

## Purpose

Booking, customer journeys, sales, customer support, pricing, warranty, and commercial policies — per `SYSTEM_ARCHITECTURE.md` Sec. 5. This domain owns commercial facts (prices, packages, warranty terms); it must not redefine service technical facts owned by `04_SERVICE_KNOWLEDGE/`.

---

# Planned structure

| Folder | Purpose | Status |
|---|---|---|
| `BOOKING/` | Booking process and rules. | Draft source material present |
| `CUSTOMER_JOURNEYS/` | Mapped customer journeys per service/channel. | Governed draft foundation |
| `SALES/` | Sales process, lead handling, upsell/cross-sell. | Draft source material present |
| `CUSTOMER_SUPPORT/` | Support process and escalation. | Draft source material present |
| `PRICING/` | Pricing model, packages. | Draft source material present; owner-gated |
| `WARRANTY/` | Canonical warranty governance and approved terms. | Governed draft foundation |
| `POLICIES/` | Cancellation, refund, and service policies. | Draft source material present; owner/legal-gated |

---

# Related draft source material (unapproved, held)

Several relevant drafts exist but are not yet approved — see
`00_GOVERNANCE/MIGRATION/VALIDATION_REPORT.md` Sec. 3. They remain preserved
as source material pending owner review. The legacy
`POLICIES/WARRANTY_POLICY_DRAFT.md` is not canonical; warranty ownership and
its disposition are tracked under `WARRANTY/`.

---

# Why this domain is not yet populated

Prices, warranty terms, and commercial policies are exactly the kind of fact this project's rules prohibit inventing (`CLAUDE_MIGRATION_PROMPT.md`: "Do not replace placeholder contact facts with guesses... prices, warranty... require authoritative user confirmation"). This domain requires business-owner-approved commercial terms before it can be populated with real content rather than structural placeholders.

---

# Status

Draft foundation only. No commercial term is publishable until confirmed by
the owner with an effective date and any required legal review.
