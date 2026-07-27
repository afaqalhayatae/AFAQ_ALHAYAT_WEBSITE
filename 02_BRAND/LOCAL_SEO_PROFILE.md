# Local SEO Profile

## Purpose

This document is the authoritative source for NAP (Name, Address, Phone) consistency, branch identifiers, map coordinates, and business-profile URLs used across local SEO, schema markup, location pages, and AI answers, per `SYSTEM_ARCHITECTURE.md` Sec. 6.

It does not duplicate contact facts already owned by `CONTACT_INFORMATION.md`; it references them.

---

# Business Name (as registered for local listings)

Owner Input Required — must match the legal/trade name exactly as it should appear on Google Business Profile and other directories.

---

# Address

Dubai - Oud Metha, Um Hurair Street - Al Makhawi Center (EN); دبي - عود ميثاء، شارع أم هرير - مركز المخاوي (AR).

**Verification:** Confirmed directly by the business owner on 2026-07-27, via
`00_GOVERNANCE/BUSINESS_FACTS_VERIFICATION.md` row 3.

---

# Phone / WhatsApp

See [`CONTACT_INFORMATION.md`](CONTACT_INFORMATION.md) — canonical source. Do
not duplicate the number here. Phone and WhatsApp are both owner-approved
(same number).

---

# Map Coordinates

Google Maps profile link confirmed and approved: https://maps.app.goo.gl/jeLNXvJB9fV8JxPG7
(`00_GOVERNANCE/BUSINESS_FACTS_VERIFICATION.md` row 6, 2026-07-27).

Precise numeric latitude/longitude (for structured-data `geo` properties) has
not been separately supplied and remains Owner Input Required — the approved
map link does not by itself substitute for coordinates if a future schema
implementation needs them.

---

# Branch IDs

Owner Input Required. No branch structure has been defined yet. If AFAQ Alhayat operates from a single location, state that explicitly here once confirmed; do not assume.

---

# Business Profile URLs

- Google Business Profile / Maps: Approved — https://maps.app.goo.gl/jeLNXvJB9fV8JxPG7
  (`00_GOVERNANCE/BUSINESS_FACTS_VERIFICATION.md` row 6, 2026-07-27).
- Other directory listings (if any): Owner Input Required.

---

# Service Area Reference

Geographic coverage is owned by `03_MARKET/SERVICE_AREAS.md`. All seven UAE
emirates are owner-approved at emirate level. City, district, community,
branch, and address claims remain unapproved until added to that registry.

---

# Status

Partially Verified — the phone, WhatsApp, email, working hours, domain,
hosting provider, address, Google Maps/Business Profile link, social profile
URLs, and emirate-level coverage all have owner approval (see
`CONTACT_INFORMATION.md` and `00_GOVERNANCE/BUSINESS_FACTS_VERIFICATION.md`).
The registered listing name (as it should appear on Google Business Profile),
branch structure/count, precise numeric map coordinates, Place ID, and other
directory listings remain pending. LocalBusiness schema or public listings
must not be generated until these remaining fields are verified — approval of
the fields above authorizes their own display, not a complete schema entity.
