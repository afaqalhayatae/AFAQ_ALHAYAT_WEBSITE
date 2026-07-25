# Decision Flow

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.1
- **Prepared:** 2026-07-24
- **Program:** `PROG-EAOS-V1`

## Purpose

Chains `AUTONOMY_AND_APPROVAL_MATRIX.md`, the job envelope, `AGENT_RUNBOOK.md`
stop conditions, QA, and `AGENT_APPROVAL_WORKFLOW.md` phase gates into one
traceable path. Introduces no new decision rule — every step below already
exists in one of those documents; this file only states the order.

## Unified Flow

```text
Trigger
  -> Classify activity against AUTONOMY_AND_APPROVAL_MATRIX.md -> authority level
  -> AGT-ORCH creates JOB_ASSIGNMENT (job envelope, per COMMUNICATION_PROTOCOL.md)
  -> Specialist executes within allowed_write_paths / forbidden_actions
  -> Continuous stop-condition check (AGENT_RUNBOOK.md "Stop Conditions")
       -> triggered -> ESCALATION -> see "Incident and Stop-Condition
          Escalation" below
  -> QA_REQUEST -> AGT-QA validates against QUALITY_CHECKLIST.md and
     QUALITY_GATES.md
       -> fail -> back to Specialist (bounded retry) or ESCALATION
  -> Phase Gate check (AGENT_APPROVAL_WORKFLOW.md: Start / Edit / Integrate /
     Publish / Delete)
       -> A4 or canonical conflict -> APPROVAL_REQUEST (owner format, unchanged)
       -> Owner APPROVAL_RESPONSE
  -> Integrate / Publish / Reject
  -> INTEGRATION_RECORD -> Job Ledger, and DECISION_LOG.md if an approved
     fact changed
```

## Incident and Stop-Condition Escalation

A concise extension of `AGENT_RUNBOOK.md`'s existing Stop Conditions — not a
separate incident-response document.

**Severity tiers:**

- **Minor** — a single job's stop condition triggers (missing evidence,
  path conflict); handled by `AGT-ORCH` reassigning or pausing the job.
- **Major** — a stop condition affects more than one job, or a canonical
  source conflict is found; escalated to the Owner as an `ESCALATION`
  message.
- **Critical** — a safety, credential, legal, or destructive-action boundary
  is reached; escalated to the Owner immediately, work halts until resolved.

**Escalation path:** any role detecting a stop condition sends `ESCALATION`
to `AGT-ORCH`, which classifies severity and, for Major/Critical, forwards an
`APPROVAL_REQUEST`-style report to the Owner using the same format already
required by `AGENT_APPROVAL_WORKFLOW.md`.

**Tagging:** an escalation that is recorded (Major or Critical) is tagged
with an `INC-####` identifier from `REGISTRIES.md` §4, for traceability in
the Job Ledger. Minor stop conditions do not require an incident tag unless
they recur.

**No separate resolution mechanism.** Correction after an incident follows
the exact same authority, QA, and approval process already defined — this
section creates no new correction path.

## Validation

- No agent may resolve a Major or Critical escalation on its own authority.
- Every Phase Gate decision follows `AGENT_APPROVAL_WORKFLOW.md`'s Approval
  Semantics unchanged (silence is not approval; scope is exact; a new
  high-risk fact resets to `A4`).

## Related Documents

`AUTONOMY_AND_APPROVAL_MATRIX.md`, `AGENT_RUNBOOK.md`,
`AGENT_APPROVAL_WORKFLOW.md`, `COMMUNICATION_PROTOCOL.md`, `REGISTRIES.md`,
`QUALITY_GATES.md`.
