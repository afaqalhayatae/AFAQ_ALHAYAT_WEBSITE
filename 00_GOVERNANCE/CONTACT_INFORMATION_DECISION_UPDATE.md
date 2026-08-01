# Contact Information Decision Update

## Document Information

- **Owner:** Business Owner
- **Status:** Approved — decision recorded here is effective immediately upon this document's creation.
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Last Updated:** 2026-08-01
- **Package:** `00_GOVERNANCE/`
- **Resolves:** The currency gap flagged in `07_WEBSITE/NAVIGATION_ARCHITECTURE.md` §6, between `00_GOVERNANCE/WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` §7 and the current state of `02_BRAND/CONTACT_INFORMATION.md`.

## Purpose

This document resolves the conflict between an earlier governance position on contact-information approval status and the current canonical source. No canonical document was edited to produce this resolution — `02_BRAND/CONTACT_INFORMATION.md` is unchanged, no website file was touched, and no application code was touched. This is a documentation-only reconciliation of which record governs.

---

## 1. Previous Governance Position

`00_GOVERNANCE/WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` §7 (2026-08-01) recorded that "all public contact values (WhatsApp number/link, email, physical address, working hours, and all eight social profile links) remain Pending until Owner verification," restating a finding originally from `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md` §11 — an earlier audit that found these values hardcoded in the live application while the canonical brand documents marked them `Pending`/`Owner Input Required`. `WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §7 carried the same position forward as an open decision point.

This position was accurate to the state of `02_BRAND/CONTACT_INFORMATION.md` **at the time that earlier audit was written**, but had not been re-checked against the canonical document's current content when the two 2026-08-01 governance documents restated it.

---

## 2. Current Source Status

`02_BRAND/CONTACT_INFORMATION.md`'s own "Status" section currently marks the following `Approved`, each with a stated verification date:

| Field | Status | Verified |
|---|---|---|
| Phone | Approved | 2026-07-23 (business owner, direct confirmation) |
| Website domain | Approved | 2026-07-23 |
| Hosting provider | Approved | 2026-07-23 |
| WhatsApp | Approved | 2026-07-27 (`BUSINESS_FACTS_VERIFICATION.md` row 1) |
| Email | Approved | 2026-07-27 (`BUSINESS_FACTS_VERIFICATION.md` row 2) |
| Working hours (24/7) | Approved | 2026-07-27 (`BUSINESS_FACTS_VERIFICATION.md` row 4) |
| Social profile URLs | Approved | 2026-07-27 (`BUSINESS_FACTS_VERIFICATION.md` row 5) |
| Emergency-service availability | **Pending** | Not verified |

This `Approved` status was committed to the repository (commit `4651d8f`, "Approve business facts and sync verification records") **before** the current session began — it is not a new change, only a fact this task re-confirmed by reading the document directly rather than relying on the earlier audit's restated claim.

**Not covered here:** the physical address is owned by `02_BRAND/LOCAL_SEO_PROFILE.md`, not `CONTACT_INFORMATION.md`, and was not re-checked by this document — its approval status is unaffected by this decision.

---

## 3. Decision

**The canonical source for contact information status is `02_BRAND/CONTACT_INFORMATION.md`.**

Its "Status" section (§2 above) governs which fields may be treated as approved. No other document — including the two 2026-08-01 governance documents that restated an outdated position — overrides it.

---

## 4. Website Usage Rule

- Fields marked `Approved` in `CONTACT_INFORMATION.md` (currently: Phone, Website domain, Hosting provider, WhatsApp, Email, Working hours, Social profile URLs) **may be used in navigation and website CTAs.**
- Fields marked `Pending` (currently: Emergency-service availability) **must not** be used or implied anywhere on the website until `CONTACT_INFORMATION.md` marks them `Approved`.
- **Any future change to a contact value must update `CONTACT_INFORMATION.md` first** — the canonical document is never updated to match what the website already renders; the website is updated to match what the canonical document already approves. This preserves the existing "knowledge is the source of truth; the application is a consumer" principle (`07_WEBSITE/IMPLEMENTATION/01_APPLICATION_ARCHITECTURE.md` §1).

---

## 5. Reconciliation Note

`WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §7 and `WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` §7 reflect a previous state of `CONTACT_INFORMATION.md` and are now superseded by this document on the specific question of contact-value approval status. Both documents remain historically accurate records of what was believed true on 2026-08-01 at the time they were written — **this document does not retroactively edit either of them.** If the Owner wants those two documents' text updated to avoid future confusion, that is separate, not-yet-executed follow-up work, not performed here.

`07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md` §11 — the original source of the "hardcoded, unverified" finding — is also not edited by this document. Its finding about the live application's behavior (hardcoding these values into `Header`/`Footer`) is a separate question from the canonical documents' approval status: the values the app currently hardcodes should now be checked against `CONTACT_INFORMATION.md`'s current `Approved` list to see whether they actually match the approved values, which this document does not do — that verification is separate, not-yet-executed follow-up work.

---

## What This Document Does Not Do

- Does not modify `02_BRAND/CONTACT_INFORMATION.md`.
- Does not modify any website file (`07_WEBSITE/*`) or the `WEBSITE_ARCHITECTURE_DECISION_REPORT.md`/`_UPDATE.md` documents it reconciles against.
- Does not modify any application code.
- Does not verify whether the live application's currently-hardcoded values actually match `CONTACT_INFORMATION.md`'s approved values — only that the canonical document's status itself is `Approved` for the fields listed in §2.
- Does not change the Emergency-service or physical-address approval status — both remain exactly as recorded in their respective canonical sources.

---

## Related Documents

- `02_BRAND/CONTACT_INFORMATION.md` — canonical source this decision defers to.
- `02_BRAND/LOCAL_SEO_PROFILE.md` — owns physical address, not covered here.
- `00_GOVERNANCE/BUSINESS_FACTS_VERIFICATION.md` — verification record referenced in §2.
- `07_WEBSITE/NAVIGATION_ARCHITECTURE.md` §6 — where this conflict was first flagged.
- `00_GOVERNANCE/WEBSITE_ARCHITECTURE_DECISION_REPORT.md` §7, `WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` §7 — superseded on this specific point, per §5 above.
- `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md` §11 — original hardcoded-values finding, whose live-app-vs-canonical match is still unverified.

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-08-01 | Resolved the currency conflict between `WEBSITE_ARCHITECTURE_DECISION_UPDATE.md` §7 and `CONTACT_INFORMATION.md`'s current Approved status. Established `CONTACT_INFORMATION.md` as the canonical source of record and set the website usage rule for approved vs. pending fields. No canonical document, website file, or application code modified. |
