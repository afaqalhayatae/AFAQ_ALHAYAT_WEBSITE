# Website

## Purpose

Channel architecture, page composition, and UI content mapping for the AFAQ Alhayat website. Per `SYSTEM_ARCHITECTURE.md` Sec. 5, this domain owns presentation and page structure — it must **not** own master service, contact, or market facts. Every page pulls those from their canonical domain (`02_BRAND/`, `03_MARKET/`, `04_SERVICE_KNOWLEDGE/`, `06_CUSTOMER_AND_SALES/`).

---

# Structure

| Folder | Status |
|---|---|
| `01_HOMEPAGE/` | In Review — documents exist; public claims must pass canonical-fact gates. |
| `02_ABOUT/` | Not yet built. Should reference `01_BUSINESS/COMPANY_PROFILE.md` and `01_BUSINESS/VISION.md`/`MISSION.md`, not restate them. |
| `03_SERVICE_PAGES/` | Not yet built. Should map one page per entry in `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`. |
| `04_LOCATIONS/` | Not yet built. Emirates and the initial premium-priority communities are approved in the registry; pages still require unique content, operations review, and SEO quality approval. |
| `05_BOOKING/` | Not yet built. Depends on `06_CUSTOMER_AND_SALES/BOOKING/`, not yet authored. |
| `06_BLOG/` | Not yet built. |
| `07_CONTACT/` | Not yet built. Phone and domain are approved; WhatsApp, email, address, and hours remain pending and must not be inferred. |
| `08_LEGAL_PAGES/` | Not yet built. Requires legal/owner-approved terms, privacy policy, etc. — do not draft legal text without review. |
| `09_ERROR_PAGES/` | Not yet built. |
| `WORDPRESS/` | Legacy implementation research; non-canonical for the approved build. The canonical direction is in `00_GOVERNANCE/TECH_STACK.md`. |
| `GOOGLE_LIVE_ECOSYSTEM.md` | Approved live Google Maps, Places, reviews, Search Console, analytics, consent, and security architecture. |

---

# Rule

If a fact could be true regardless of which channel displays it (a phone number, a service description, a coverage area), it does not belong in this domain — it belongs in the domain that owns it, referenced from here.

The implementation stack is owned by `00_GOVERNANCE/TECH_STACK.md`. Website
documents define presentation and channel behavior, not an alternative stack.
