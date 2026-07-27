# Business Facts Verification

## Document Information

- **Owner:** Business Owner
- **Status:** Resolved — all 6 rows decided 2026-07-27
- **Version:** 1.1
- **Prepared:** 2026-07-27
- **Source finding:** `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md` §11
- **Escalation format:** `AUTONOMY_AND_APPROVAL_MATRIX.md` — Escalation Payload

## Purpose

`~/Documents/GitHub/afaqalhayatae-app` currently renders six categories of contact/local-SEO facts on every public page (header and footer) that this repository's own canonical sources — `02_BRAND/CONTACT_INFORMATION.md` and `02_BRAND/LOCAL_SEO_PROFILE.md` — mark `Pending` / `Owner Input Required`. This is a live conflict with the first Hard Publication Block in `CURRENT_PROJECT_STATUS.md` ("Unverified contact or account details").

This document does not assume either direction. Each fact below needs an explicit Owner decision: **Confirm** (the value in the app is correct — the canonical document is updated to `Approved`), **Correct** (the value is wrong — supply the right one), or **Reject** (no such fact exists yet — it must be removed/blocked from the app). No fact here is treated as true until marked Confirmed or Corrected below; no agent may fill in a blank on the Owner's behalf.

**Per `AUTONOMY_AND_APPROVAL_MATRIX.md`: silence is not approval.** Until each row below is explicitly decided, its value remains blocked for any public deployment, and the application must not be launched publicly with these facts live.

---

## 1. WhatsApp Number

- **Value currently in app:** Same as the approved phone number, `+971 58 543 1766` (`src/lib/brand/links.ts` → `WHATSAPP_URL`; `contact.info.whatsapp` in i18n messages).
- **Canonical status:** `CONTACT_INFORMATION.md` — *"Owner Confirmation Required. Do not assume that the approved phone number is also the official WhatsApp number."*
- **Risk if wrong:** Customers message a number that isn't monitored as WhatsApp, or a wrong number entirely.
- **Owner decision:** ☒ **CONFIRM — phone = WhatsApp, +971 58 543 1766.** Applied 2026-07-27: `CONTACT_INFORMATION.md` updated to Approved. No app change needed — the value already matched.

## 2. Email Address

- **Value currently in app:** `Info@afaqalhayatae.com` (`contact.info.email`, rendered as a live `mailto:` link).
- **Canonical status:** `CONTACT_INFORMATION.md` — *"No official email address has been confirmed. Do not derive an email address from the approved domain."* The value present is exactly an `info@`-style address derived from the approved domain — the pattern this document explicitly prohibits.
- **Risk if wrong:** Customer inquiries sent to an inbox that doesn't exist or isn't monitored.
- **Owner decision:** ☒ **CONFIRM — `Info@afaqalhayatae.com` is real and monitored.** Applied 2026-07-27: `CONTACT_INFORMATION.md` updated to Approved. No app change needed — the value already matched.

## 3. Physical Address / Branch

- **Value currently in app:** "Dubai - Oud Metha, Um Hurair Street - Al Makhawi Center" (ar/en), plus a Google Maps link (`GOOGLE_MAPS_URL`).
- **Canonical status:** `LOCAL_SEO_PROFILE.md` — *"Address: Owner Input Required. No verified street address exists... Branch IDs: Owner Input Required. No branch structure has been defined yet."*
- **Risk if wrong:** Publishing a fake or outdated branch location is a Hard Publication Block in its own right ("Fake branches, virtual offices... identities") independent of this verification.
- **Owner decision:** ☒ **CONFIRM — real, current business address as shown.** Applied 2026-07-27: `LOCAL_SEO_PROFILE.md` updated to Approved. No app change needed — the value already matched. Branch count/structure was not addressed by this decision and remains a separate open item in `LOCAL_SEO_PROFILE.md`.

## 4. Working Hours

- **Value currently in app:** "Saturday–Thursday, 9:00–19:00" (`contact.info.hours`).
- **Canonical status:** `CONTACT_INFORMATION.md` — *"Owner Input Required. Hours have not been verified."*
- **Risk if wrong:** Customers attempt contact outside actual operating hours.
- **Owner decision:** ☒ **CORRECT — real hours: 24/7.** Applied 2026-07-27: `CONTACT_INFORMATION.md` updated to Approved; `afaqalhayatae-app` i18n messages (`contact.info.hours`, en/ar) updated to "24/7."

## 5. Social Media Profile Links

- **Value currently in app:** 8 links rendered in the footer — Facebook, Instagram, TikTok, LinkedIn, X, Pinterest, Threads, YouTube (`SOCIAL_LINKS` in `src/lib/brand/links.ts`).
- **Canonical status:** `CONTACT_INFORMATION.md` — *"Owner Input Required. Add only verified profile URLs. Platform names alone must not be treated as proof that an official company account exists."*
- **Risk if wrong:** Linking to an account that isn't the business's, or that doesn't exist/is inactive, damages trust and local-SEO signal consistency.
- **Owner decision:** ☒ **CONFIRM all 8 — all existing official links.** Applied 2026-07-27: `CONTACT_INFORMATION.md` updated to Approved with all 8 URLs. No app change needed — the values already matched.
  - ☒ Facebook confirmed real
  - ☒ Instagram confirmed real
  - ☒ TikTok confirmed real
  - ☒ LinkedIn confirmed real
  - ☒ X confirmed real
  - ☒ Pinterest confirmed real
  - ☒ Threads confirmed real
  - ☒ YouTube confirmed real

## 6. Google Business Profile / Map Coordinates

- **Value currently in app:** A Google Maps short link tied to the address in item 3.
- **Canonical status:** `LOCAL_SEO_PROFILE.md` — *"Map Coordinates: Owner Input Required."*
- **Owner decision:** ☒ **CONFIRM — existing map link is correct and owner-managed.** Applied 2026-07-27: `LOCAL_SEO_PROFILE.md` updated to Approved for the Maps/GBP link. No app change needed — the value already matched. Precise numeric lat/long coordinates were not separately supplied and remain a distinct open item.

---

## What Happens Next, Per Row

- **Confirm or Correct →** the corresponding field in `CONTACT_INFORMATION.md` and/or `LOCAL_SEO_PROFILE.md` is updated to `Approved` with the exact value the Owner gave here, as its own dated edit — not silently folded into this document.
- **Reject →** the corresponding hardcoded value in `afaqalhayatae-app` (`src/lib/brand/links.ts` and/or the i18n messages) is removed or replaced with a blocked/absent UI state, per the blocked-field pattern already established in `04_CONTENT_INTEGRATION_PLAN.md` §3.
- **No answer →** the fact stays `Pending`, stays blocked, and the application must not be publicly deployed while any row here remains undecided — consistent with `CURRENT_PROJECT_STATUS.md`'s Hard Publication Blocks and `AUTONOMY_AND_APPROVAL_MATRIX.md`'s "silence is not approval."

---

## Related Documents

- `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md`
- `00_GOVERNANCE/IMPLEMENTATION_STATUS_CORRECTION.md`
- `02_BRAND/CONTACT_INFORMATION.md`
- `02_BRAND/LOCAL_SEO_PROFILE.md`
- `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`
