# Email System Foundation

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — future foundation planning only. No mailbox, DNS record, or sending infrastructure is created by this document.
- **Version:** 1.0
- **Prepared:** 2026-08-02
- **Depends on / relationship to existing documents:** `10_MARKETING_AND_SEO/EMAIL_MARKETING.md` is the already-approved **marketing policy** (consent, audience rules, campaign governance, and — importantly — already lists SPF/DKIM/DMARC as required Technical Readiness items). This document does **not** duplicate that policy. It is the **mailbox/systems-integration foundation** this repository's planned structure calls for (`08_DIGITAL_SYSTEMS/README.md`'s `INTEGRATIONS/` folder): which addresses exist, what each routes to, and how they connect into CRM/booking/agent workflows once built.
- **Approved domain:** `afaqalhayatae.com` (per `CURRENT_PROJECT_STATUS.md`'s Approved Owner Facts). No other domain is used anywhere in this plan.
- **Automation gate:** Per `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`, DNS records (SPF/DKIM/DMARC), hosting configuration, and mailbox provisioning are `A4` — owner approval required every time. This document plans the target state; it does not create or request creation of any DNS record or mailbox.

---

## 1. Mailbox Foundation

| Address | Purpose | Primary consumer (future) |
|---|---|---|
| `info@afaqalhayatae.com` | General public inquiries — the default published contact address for non-transactional questions | Front-desk/owner inbox, later a shared CRM inbox |
| `sales@afaqalhayatae.com` | Inbound quote requests, new-customer sales inquiries, booking-adjacent questions before a booking exists | Sales workflow (`06_CUSTOMER_AND_SALES/SALES/`) |
| `support@afaqalhayatae.com` | Post-booking support, service issues, complaints, warranty/follow-up questions | Customer Support workflow (`06_CUSTOMER_AND_SALES/CUSTOMER_SUPPORT/`) |
| `marketing@afaqalhayatae.com` | Outbound campaign sending, unsubscribe/reply handling for marketing messages, review-request follow-up | Marketing automation (§2), governed by `EMAIL_MARKETING.md`'s consent rules |

**Note (not yet resolved):** `02_BRAND/CONTACT_INFORMATION.md` records email as still Pending/Unverified — these four addresses are a **target mailbox plan**, not a confirmation that any of them currently exists or is published. Publishing any address as a live contact point remains gated by that file's own approval status.

---

## 2. Email Campaign & Automation Plan (foundation only)

All items below are governed by `EMAIL_MARKETING.md`'s existing Audience Rules (consent-only, no purchased lists, suppression handling, unsubscribe compliance) — not restated here, only mapped to mailbox and trigger:

| Campaign type | Sends from | Trigger | Governing rule |
|---|---|---|---|
| Booking confirmation / reminder | `support@` (transactional) | Booking created/updated in CRM (not yet built) | Transactional, not a marketing send — `EMAIL_MARKETING.md`'s distinction between transactional and promotional flows |
| Customer follow-up (post-service) | `support@` | Service marked complete | Transactional; may include a soft marketing element only with recorded consent |
| Review request | `marketing@` or `support@` (TBD — Owner to decide tone/ownership) | N days after service completion | Requires consent; must comply with review-platform policy — no fabricated or incentivized reviews per `CURRENT_PROJECT_STATUS.md`'s hard publication blocks |
| Seasonal campaigns (e.g., AC maintenance pre-summer, pest-control seasonal) | `marketing@` | Calendar-driven, content sourced from already-approved service content only | Consent-gated marketing list only; content must trace to an approved `04_SERVICE_KNOWLEDGE/` package, no invented seasonal claim |
| Sales inquiry auto-acknowledgment | `sales@` | Inbound form/email received | Transactional |

No campaign in this table is scheduled, built, or sent by this document — this is a routing and governance map for when the sending infrastructure exists.

---

## 3. Deliverability Foundation (SPF / DKIM / DMARC)

`EMAIL_MARKETING.md` already requires SPF, DKIM, DMARC, and TLS before the first campaign. This section adds the **multi-mailbox specificity** that policy document doesn't cover:

- All four addresses (`info@`, `sales@`, `support@`, `marketing@`) must resolve under the **same verified sending domain** (`afaqalhayatae.com`) so a single SPF record and DKIM key set covers all of them — no per-mailbox subdomain fragmentation unless a future high-volume marketing sender (e.g., a dedicated ESP) requires SPF/DKIM alignment via a marketing subdomain, which is a later, separate decision.
- DMARC policy should start at `p=none` (monitoring only) across all four senders before any enforcement (`p=quarantine`/`p=reject`), consistent with standard deliverability practice — not yet configured, no policy record exists today.
- Bounce, complaint, and suppression handling (already required by `EMAIL_MARKETING.md`) must span all four mailboxes' outbound traffic, not just `marketing@`, since `support@`/`sales@` transactional sends also affect domain reputation.
- **Nothing in this section is implemented.** SPF/DKIM/DMARC record creation is an `A4` DNS action requiring explicit Owner authorization at the hosting/DNS provider (Hostinger, per `CURRENT_PROJECT_STATUS.md`).

---

## 4. Remaining Gates

- Mailbox creation and DNS record changes — `A4`, Owner approval required, not performed here.
- Publishing any of these addresses as a live contact point — gated by `CONTACT_INFORMATION.md`'s own Pending/Unverified status for email.
- CRM/booking-system integration referenced in §1–2 — depends on the CRM itself being built (`08_DIGITAL_SYSTEMS/README.md` lists `CRM/` as planned, not yet populated).
- ESP (email service provider) selection is not made by this document — no specific vendor is named or implied.

---

## What This Document Does Not Do

- Does not create, request, or configure any mailbox, DNS record, or ESP account.
- Does not modify `EMAIL_MARKETING.md`, `CONTACT_INFORMATION.md`, or any other existing file.
- Does not send, schedule, or draft any actual email.
- Does not stage, commit, or push anything.

---

## Related Documents

- `10_MARKETING_AND_SEO/EMAIL_MARKETING.md` — governing marketing/consent policy
- `02_BRAND/CONTACT_INFORMATION.md` — canonical contact-fact status (email still Pending)
- `06_CUSTOMER_AND_SALES/SALES/`, `CUSTOMER_SUPPORT/` — future consumers of `sales@`/`support@`
- `08_DIGITAL_SYSTEMS/README.md` — planned `INTEGRATIONS/` folder this document populates
- `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md` — `A4` gate for DNS/hosting actions
