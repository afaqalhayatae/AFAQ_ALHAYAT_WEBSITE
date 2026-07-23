# Service Matrix

## Purpose

Maps which services (from `SERVICE_CATALOG.md`) are available in which locations (from `03_MARKET/SERVICE_AREAS.md`), per `SYSTEM_ARCHITECTURE.md` Sec. 9.2. Website local-landing pages and booking availability must read from this matrix, not maintain their own coverage lists.

---

# Status

**Blocked — cannot be populated yet.** `03_MARKET/SERVICE_AREAS.md` is not yet finalized: three overlapping drafts remain on HOLD pending manual reconciliation (see `00_GOVERNANCE/MIGRATION/VALIDATION_REPORT.md` Sec. 3). Building this matrix before that reconciliation would risk encoding an unapproved or inconsistent area list as fact.

Once `SERVICE_AREAS.md` is finalized, this document should be populated as:

| Service ID | Location ID | Available |
|---|---|---|
| `SVC-PEST-CONTROL` | `LOC-AE-...` | Owner Input Required |

Naming for location IDs follows `99_STANDARDS/NAMING_CONVENTIONS.md`: `LOC-AE-<EMIRATE>-<AREA>`.
