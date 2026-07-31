# Design Change Request

## Document Information

- **Owner:** Business Owner
- **Status:** Approved — process document, effective immediately upon Design Freeze
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Last Updated:** 2026-08-01
- **Package:** `00_GOVERNANCE/`
- **Depends on:** `00_GOVERNANCE/DESIGN_FREEZE_REPORT.md`, `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`, `00_GOVERNANCE/DECISION_LOG.md`

## Purpose

Following the Design Freeze (`DESIGN_FREEZE_REPORT.md`, 2026-08-01), no change to a frozen visual-identity element — colors, icons, image style, layout/component design, or any asset inside `public/brand/icons/`, `public/brand/images/`, `12_DESIGN_SYSTEM/`, or `02_BRAND/` — may be made without first recording a Design Change Request here and receiving explicit Owner approval. This document defines the required record format and holds the running log of all such requests.

This process does not itself approve anything. An unapproved request stays unapproved indefinitely; no agent may treat "logged" as equivalent to "approved."

---

## 1. Required Fields for Every Request

Every future design change — regardless of size — must be logged below with all five fields completed before any work begins:

1. **Reason for the change** (سبب التعديل) — why the change is being requested; what problem, gap, or Owner instruction motivates it.
2. **Affected element** (العنصر المتأثر) — the exact file, folder, or asset being changed (e.g. `12_DESIGN_SYSTEM/COLORS.md`, `public/brand/icons/pest-control/icon-pest-cockroach.svg`, "primary color token").
3. **Expected impact** (التأثير المتوقع) — what else could be affected downstream (other pages, other services, brand consistency, SEO, existing approved assets).
4. **Owner approval** (موافقة المالك) — status: `Requested`, `Approved`, or `Rejected`, with the date and, where given in writing, a reference/quote of the Owner's approval.
5. **Status** — `Open`, `Approved — Not Yet Executed`, `Executed`, or `Rejected`.

A request missing any of the five fields is incomplete and must not be executed.

---

## 2. Process

1. Whoever identifies a needed design change adds a new row to the log in §3 using the template in §1 — reason, affected element, expected impact — with Owner approval marked `Requested`.
2. The request is presented to the Business Owner for a decision. No agent may pre-approve a design change on the Owner's behalf.
3. Only after the Owner marks the request `Approved` (with date) may the change be executed.
4. Once executed, the request's Status is updated to `Executed`, and — if the change affects an existing Decision Log entry (e.g. Decision 35 or 36) — a new dated entry is added to `00_GOVERNANCE/DECISION_LOG.md` referencing this request.
5. If the Owner declines, Status is set to `Rejected` and the request remains in the log as a permanent record — it is not deleted.

---

## 3. Change Request Log

*No design change has been requested or approved since the Design Freeze (2026-08-01). This table is initialized empty and will be appended to as requests occur.*

| # | Date | Reason | Affected Element | Expected Impact | Owner Approval | Status |
|---|---|---|---|---|---|---|
| — | — | — | — | — | — | — |

---

## Related Documents

- `00_GOVERNANCE/DESIGN_FREEZE_REPORT.md` — the frozen baseline this process protects.
- `00_GOVERNANCE/DECISION_LOG.md` — permanent record of Owner decisions, updated once a request is executed.
- `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md` — general automation-level gating this process sits alongside.

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-08-01 | Initial creation of the Design Change Request process, per Owner instruction accompanying the Design Freeze. Log table initialized empty. |
