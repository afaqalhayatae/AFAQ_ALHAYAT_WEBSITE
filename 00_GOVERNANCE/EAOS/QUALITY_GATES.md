# Quality Gates

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24
- **Program:** `PROG-EAOS-V1`

## Purpose

Maps six gates onto the job lifecycle, wrapping — not replacing —
`99_STANDARDS/QUALITY_CHECKLIST.md`, which remains itself Draft and is not
promoted to Approved by this document.

## The Six Gates

1. **Intake Gate** — the job envelope is complete (all fields in
   `COMMUNICATION_PROTOCOL.md` present).
2. **Content Gate** — `QUALITY_CHECKLIST.md`'s Documentation Checklist
   (single source of truth, naming, no placeholders presented as fact,
   bilingual parity where applicable).
3. **Independent QA Gate** — `AGT-QA` verdict; the producing role cannot
   clear its own work.
4. **Canonical Conflict Gate** — cross-checked against
   `SYSTEM_ARCHITECTURE.md` §6/§7; any conflict stops here and routes to
   `DECISION_FLOW.md`'s escalation path.
5. **Owner Gate** — fires only when `AUTONOMY_AND_APPROVAL_MATRIX.md` marks
   the activity `A4`, or Gate 4 found a conflict.
6. **Integration/Recovery Gate** — a Git checkpoint exists and a rollback
   reference is recorded before the Job Ledger entry is written.

## Validation

- A job cannot skip a gate; a failed gate returns the job to the producing
  role, not forward to the next gate.
- Gate 3 and Gate 5 can never be satisfied by the same role that produced
  the work under review.

## Known Pre-Existing Gap

`99_STANDARDS/QUALITY_CHECKLIST.md` is itself `Status: Draft`. This document
does not resolve that; Gate 2 is only as strong as that checklist until the
Owner separately approves it.

## Related Documents

`99_STANDARDS/QUALITY_CHECKLIST.md`, `SYSTEM_ARCHITECTURE.md`,
`AUTONOMY_AND_APPROVAL_MATRIX.md`, `DECISION_FLOW.md`,
`COMMUNICATION_PROTOCOL.md`.
