# Booking Options — Pest Control

## Document Information

- **Service ID:** `SVC-PEST-CONTROL`
- **Status:** Draft preparation for future booking-system integration. Not connected to any live booking system. Per `SERVICE_MATRIX.md`'s consumer rules: booking systems must recheck current operational availability — nothing here should be read as a live, confirmed slot.
- **Prepared:** 2026-07-29

---

## Booking Service Name

- **English:** Pest Control
- **Arabic:** مكافحة الحشرات

## Booking Category

Cleaning & Pest Control (per `SERVICE_CATALOG.md`)

---

## Available Options

### Pest Type

Per `BUSINESS.md` "Customer Problems" and `CONTENT_EN.md`/`FAQ.md` "What pests do you treat?":

- Cockroach Control
- Ant Control
- Bed Bug Treatment
- Rodent Control
- Termite Control
- Mosquito Control
- Fly Control
- Other (free text — `FAQ.md` also lists fleas and "other common pests")

### Service Type (Property Category)

Per `BUSINESS.md` "Target Customers":

- Residential — Villa
- Residential — Apartment
- Residential — Building (shared/common areas)
- Commercial — Office
- Commercial — Restaurant / Café
- Commercial — Shop
- Commercial — Hotel
- Industrial — Factory
- Industrial — Warehouse
- Government — School / Hospital / Public Building

---

## Customer Selection Fields

- **Location** — dropdown of the 7 approved emirates (Abu Dhabi, Dubai, Sharjah, Ajman, Umm Al Quwain, Ras Al Khaimah, Fujairah) + free-text area, per `SERVICE_MATRIX.md`.
- **Property Type** — dropdown per "Service Type" above.
- **Pest Type** — dropdown per "Pest Type" above (multi-select, since more than one pest may be present).
- **Required Date** — date picker, no past dates.
- **Preferred Time** — dropdown: Morning / Afternoon / Evening.
- **Notes** — free text, optional. Suggested prompt drawn from `CUSTOMER_GUIDE.md`: "Please mention any children, pets, allergies, pregnancy, or other sensitive conditions in the treatment area" — this isn't optional context, `FAQ.md`/`FAQ_AR.md` require it to be disclosed before service for the safety assessment to be meaningful.
- **Phone Number** — required, UAE format validation.

---

## Suggested Booking Dropdown Options (consolidated)

```
Pest Type: [Cockroach | Ant | Bed Bug | Rodent | Termite | Mosquito | Fly | Other]
Property Type: [Villa | Apartment | Building | Office | Restaurant/Café | Shop | Hotel | Factory | Warehouse | School/Hospital/Public Building]
Emirate: [Abu Dhabi | Dubai | Sharjah | Ajman | Umm Al Quwain | Ras Al Khaimah | Fujairah]
Preferred Time: [Morning | Afternoon | Evening]
```

---

## What is explicitly NOT part of this booking form

Per this package's Evidence Gate (`README.md`, `BUSINESS.md`) and `SERVICE_MATRIX.md`'s consumer rules:

- **No price or quote field** — pricing is owned by `06_CUSTOMER_AND_SALES/*`, not yet established in this package, and always an owner-approval (`A4`) item.
- **No guaranteed time-slot or "confirmed within X hours" messaging** — coverage confirms the service is offered in the emirate, not a response-time commitment.
- **No warranty selection** — per `FAQ.md`/`FAQ_AR.md`, warranty details are confirmed in the written quotation/service order, not selectable at booking time.
- **No "child-safe" / "pet-safe" checkbox implying a blanket safety guarantee** — per `FAQ.md`, safety is case-specific and requires disclosure, not a pre-confirmed checkbox.

---

## Related Documents

- `01_PEST_CONTROL/BUSINESS.md`, `CUSTOMER_GUIDE.md`, `FAQ.md`, `FAQ_AR.md`
- `04_SERVICE_KNOWLEDGE/BOOKING_SERVICE_CATALOG.md`
- `04_SERVICE_KNOWLEDGE/SERVICE_MATRIX.md`
