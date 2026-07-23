# Service Knowledge

## Purpose

This domain holds the authoritative, website-independent definition of every service AFAQ Alhayat offers: what it is, who it serves, how it is delivered, and the approved bilingual content that describes it. Per `SYSTEM_ARCHITECTURE.md` Sec. 5, this domain owns service technical facts; it must not own website layout or global contact facts (owned by `07_WEBSITE/` and `02_BRAND/` respectively).

---

# Structure

- `SERVICE_CATALOG.md` — the official list of services, stable IDs, and category.
- `SERVICE_MATRIX.md` — service-to-location availability (depends on `03_MARKET/SERVICE_AREAS.md`, not yet finalized).
- `SERVICE_WORKFLOW.md` — the shared service-delivery workflow shape, where one exists.
- `SERVICE_KPIS.md` — cross-service quality/performance indicators.
- `SERVICE_GLOSSARY.md` — shared terminology.
- `<NN>_<SERVICE_NAME>/` — one folder per service, following the structure in `99_STANDARDS/SERVICE_TEMPLATE.md`.

---

# Current status

| Service package | Status |
|---|---|
| `01_PEST_CONTROL/` | Complete — 11-document package migrated and canonical (see `00_GOVERNANCE/DECISION_LOG.md` decision 6). |
| All other services in `SERVICE_CATALOG.md` | Not yet built. Draft source material exists but is held (not approved) pending a folder-numbering decision — see `00_GOVERNANCE/MIGRATION/VALIDATION_REPORT.md` Sec. 3. |

---

# Related sources

- Service list origin: [`01_BUSINESS/COMPANY_PROFILE.md`](../01_BUSINESS/COMPANY_PROFILE.md) — "Core Services."
- Geographic coverage: `03_MARKET/SERVICE_AREAS.md` — not yet created; pending manual reconciliation of 3 held drafts (see `00_GOVERNANCE/MIGRATION/VALIDATION_REPORT.md` Sec. 3).
- Documentation shape: [`99_STANDARDS/SERVICE_TEMPLATE.md`](../99_STANDARDS/SERVICE_TEMPLATE.md).
