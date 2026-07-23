# Retrieval Policy

## Purpose

Defines which document an AI system must retrieve from for a given type of question, using the source-of-truth registry already established in `SYSTEM_ARCHITECTURE.md` Sec. 6.

---

# Retrieval Map

| Question type | Retrieve from |
|---|---|
| Company identity, history, mission, vision | `01_BUSINESS/COMPANY_PROFILE.md`, `01_BUSINESS/VISION.md`, `01_BUSINESS/MISSION.md` |
| Phone, WhatsApp, email, domain, address, hours | `02_BRAND/CONTACT_INFORMATION.md` — answer only fields individually marked Approved |
| Coverage area / "do you serve X city" | `03_MARKET/SERVICE_AREAS.md` — emirates are approved; lower-level locations require an explicit registry row |
| What a service includes, its process, safety | `04_SERVICE_KNOWLEDGE/<SERVICE>/*` |
| Service list / "what services do you offer" | `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` |
| Pricing, packages, warranty | `06_CUSTOMER_AND_SALES/PRICING/`, `06_CUSTOMER_AND_SALES/WARRANTY/` (not yet authored) |
| Brand voice, visual identity | `02_BRAND/BRAND_VOICE.md`, `02_BRAND/BRAND_GUIDELINES.md` |
| Booking process | `06_CUSTOMER_AND_SALES/BOOKING/` (not yet authored) |

---

# Rule

If the retrieval target does not exist yet, or exists only as a draft/HOLD item, the AI system must say so rather than substitute a plausible-sounding answer. See `ANSWER_POLICY.md`.
