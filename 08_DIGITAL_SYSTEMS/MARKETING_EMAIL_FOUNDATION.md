# Marketing Email Foundation

## Document Information

- **Status:** Draft — future foundation planning only, not itself an authorization to provision any mailbox or DNS record
- **Prepared:** 2026-08-02
- **Relationship to existing documents:** `08_DIGITAL_SYSTEMS/INTEGRATIONS/EMAIL_SYSTEM_FOUNDATION.md` (this session, prior turn) already covers mailbox identities, campaign routing, and SPF/DKIM/DMARC in full detail. **This document does not restate that content.** It adds the two campaign types this directive names that the prior document didn't cover (Welcome emails, Promotions) and serves as the requested root-level file at this specific path.

---

## 1. Email Identities (full detail in `EMAIL_SYSTEM_FOUNDATION.md` §1 — summarized here)

`marketing@afaqalhayatae.com` · `sales@afaqalhayatae.com` · `info@afaqalhayatae.com` · `support@afaqalhayatae.com` — all under the approved domain `afaqalhayatae.com`. None is provisioned yet; `CONTACT_INFORMATION.md` currently records `Info@afaqalhayatae.com` as the one Approved, live email address.

## 2. Campaign Plans

| Campaign | Sends from | Trigger | Status |
|---|---|---|---|
| Welcome email | `marketing@` or `info@` (TBD) | New contact captured with consent (e.g., booking form, newsletter signup) | **New in this document** — introduces the contact to AFAQ AL HAYAT's service range; no discount or promise, per Evidence Gate |
| Booking confirmation | `support@` | Booking created (per `EMAIL_SYSTEM_FOUNDATION.md` §2) | Already defined |
| Customer follow-up | `support@` | Service marked complete | Already defined |
| Review request | `marketing@`/`support@` | N days post-service | Already defined |
| Promotions | `marketing@` | Calendar-driven or campaign-specific | **New in this document** — any promotional content must trace to an approved price/offer in `06_CUSTOMER_AND_SALES/PRICING/`, which is currently gated; no promotional email may state a discount or price until that gate clears |
| Seasonal campaigns | `marketing@` | Calendar-driven (e.g., pre-summer AC maintenance) | Already defined |

All campaigns remain governed by `10_MARKETING_AND_SEO/EMAIL_MARKETING.md`'s existing consent/audience rules — not re-derived here.

## 3. Technical Preparation (full detail in `EMAIL_SYSTEM_FOUNDATION.md` §3 — summarized here)

SPF, DKIM, and DMARC (starting at `p=none`) across all four mailboxes under the single verified `afaqalhayatae.com` sending domain. **Not implemented** — DNS record creation is `A4` (Owner approval required every time), per `AUTONOMY_AND_APPROVAL_MATRIX.md`.

---

## What This Document Does Not Do

- Does not create, request, or configure any mailbox, DNS record, or ESP account.
- Does not modify `EMAIL_SYSTEM_FOUNDATION.md`, `EMAIL_MARKETING.md`, or `CONTACT_INFORMATION.md`.
- Does not send, schedule, or draft any actual email, including any Welcome or Promotions email content.

## Related Documents

- `08_DIGITAL_SYSTEMS/INTEGRATIONS/EMAIL_SYSTEM_FOUNDATION.md` — full mailbox/deliverability foundation (this document extends it)
- `10_MARKETING_AND_SEO/EMAIL_MARKETING.md` — governing consent/audience policy
- `06_CUSTOMER_AND_SALES/PRICING/` — gate for any future Promotions content
