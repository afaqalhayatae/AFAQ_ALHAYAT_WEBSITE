# Autonomy and Approval Matrix

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 1.0
- **Effective Date:** 2026-07-23

## Decision Matrix

| Activity | Default level | Agent may prepare | Agent may execute | Owner gate |
|---|---:|---:|---:|---|
| Read and audit repository | A0 | Yes | Yes | No |
| Draft or improve internal documentation | A1 | Yes | Yes, on isolated branch | Before canonical approval |
| Correct links, metadata, and formatting | A2 | Yes | Yes, with checks and rollback | Only if meaning changes |
| Add an owner-confirmed service to registries | A2 | Yes | Yes, with recorded decision | Owner confirmation is the source |
| Draft website or landing-page content | A1 | Yes | No public publishing | Before publishing |
| Publish pre-approved evergreen content | A3 | Yes | Yes, after workflow certification | Policy approval, then exceptions only |
| Answer routine customer questions | A3 | Yes | Yes from approved knowledge | Escalate missing/conflicting facts |
| Confirm booking availability | A3 | Yes | Only against live capacity rules | Exceptions and overrides |
| Quote a price or warranty | A4 | Yes, from approved commercial rules | No | Every untemplated commitment |
| Create or change paid-media spend | A4 | Yes | No | Every budget or threshold change |
| Send bulk email/SMS/WhatsApp | A4 initially | Yes | After consent and workflow approval | Initial launch and policy changes |
| Change credentials, DNS, hosting, or security | A4 | Yes | No | Every action |
| Delete, overwrite, or irreversibly migrate data | A4 | Yes | No | Every action plus backup evidence |
| Legal, licensing, regulatory, or safety claim | A4 | Yes, with evidence | No | Verified evidence and owner approval |

## Escalation Payload

An agent requesting owner approval must provide:

1. The exact decision required.
2. Recommended option.
3. Evidence and canonical sources.
4. Customer, legal, cost, security, and reputation impact.
5. Reversible checkpoint and rollback.
6. What continues safely if the owner does not answer.

## Approval Interpretation

- Silence is not approval.
- Approval applies only to the exact described scope.
- Recurring approval requires an explicit policy and limits.
- A higher-risk new fact resets approval to `A4`.
- Agents cannot approve their own high-risk work; Quality & Integration must
  review it before it reaches the owner.
