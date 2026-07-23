# Quality Checklist

## Document Information

- Project: AFAQ Alhayat Enterprise Knowledge
- Standard: Quality Gate
- Version: 1.0
- Status: Draft
- Applies To: All Documentation and Published Content

---

# Purpose

A pre-publish / pre-release checklist so that no document or page goes live without meeting the project's baseline standards. Consolidates checks already implied across `DOCUMENTATION_STANDARD.md`, `NAMING_CONVENTIONS.md`, and `SYSTEM_ARCHITECTURE.md` into one gate.

---

# Documentation Checklist

- [ ] Title, purpose, and status are present (per `DOCUMENTATION_STANDARD.md`).
- [ ] File and folder names follow `NAMING_CONVENTIONS.md`.
- [ ] No fact is duplicated from another domain — it is linked instead (Single Source of Truth, `SYSTEM_ARCHITECTURE.md` Sec. 7).
- [ ] No placeholder value (phone, price, address, license, etc.) is presented as approved fact.
- [ ] Bilingual content (where required) expresses equivalent facts in Arabic and English.
- [ ] Related documents are linked.

---

# Publishing Checklist (website, schema, AI, campaigns)

- [ ] Contact data pulled from `02_BRAND/CONTACT_INFORMATION.md`, not hard-coded, and confirmed **not** Draft/Unverified.
- [ ] Service claims match `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md` and the relevant service package.
- [ ] Coverage claims match the finalized `03_MARKET/SERVICE_AREAS.md` (not any of the held draft area documents).
- [ ] No invented license, certification, guarantee, or regulatory claim.
- [ ] Accessibility basics checked once `ACCESSIBILITY_STANDARD.md` is populated.

---

# Service Package Checklist

- [ ] Follows `SERVICE_TEMPLATE.md` structure.
- [ ] Has a stable `SVC-<NAME>` ID registered in `SERVICE_CATALOG.md`.
- [ ] Safety and compliance sections do not assert unverified regulatory facts.

---

# Status

Draft — checklist compiled from existing standards; should be reviewed and formally approved by an accountable owner before being treated as a hard release gate.
