# Agent Runbook

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 1.0
- **Effective Date:** 2026-07-24

## Purpose

Provide the repeatable operating sequence for specialist agents working in this
repository.

## Standard Workflow

1. Read `CLAUDE.md` and the canonical governance documents.
2. Select the model route from
   `../../00_GOVERNANCE/MODEL_ROUTING_POLICY.md`.
3. Inspect Git branch, HEAD, and working-tree status.
4. Define a bounded job envelope.
5. Check path ownership and active-writer conflicts.
6. Establish or reference a recoverable checkpoint before writes.
7. Execute only within allowed paths and authority.
8. Run validation checks.
9. Send the result to Quality & Integration for independent review.
10. Request owner approval only when the approval workflow requires it.
11. Integrate, record evidence, and stop.

## Modes

### Audit

- Authority: `A0`
- Read-only.
- Output: findings, evidence, risks, recommendation.

### Draft

- Authority: `A1`
- May create or edit bounded internal drafts.
- Cannot approve, publish, or invent facts.

### Stabilize

- Authority: `A2` only when explicitly granted.
- Reversible internal corrections with Git recovery evidence.
- No deletion, irreversible migration, or canonical fact changes.

### Publish

- Authority: `A3` only under a certified policy.
- A new claim, channel, or risk condition returns the action to `A4`.

### Owner Gate

- Authority: `A4`.
- The agent prepares evidence and stops for the owner's explicit decision.

## Stop Conditions

Stop the current action when:

- Canonical sources conflict.
- Required evidence is missing.
- A requested path is owned by another active writer.
- The action becomes destructive or irreversible.
- A credential, payment, legal, licensing, regulatory, or safety boundary is
  reached.
- Validation fails.

## Completion Report

Every completed job reports:

- Job ID and agent role.
- Objective and authority.
- Sources used.
- Files read and changed.
- Checks performed and results.
- Open risks.
- Approval evidence, if any.
- Checkpoint and rollback reference.
- Recommended next action.

## Related Documents

- [`AGENT_ORCHESTRATION.md`](AGENT_ORCHESTRATION.md)
- [`../../00_GOVERNANCE/AGENT_REGISTRY.md`](../../00_GOVERNANCE/AGENT_REGISTRY.md)
- [`../../00_GOVERNANCE/AGENT_APPROVAL_WORKFLOW.md`](../../00_GOVERNANCE/AGENT_APPROVAL_WORKFLOW.md)
- [`../../00_GOVERNANCE/MODEL_ROUTING_POLICY.md`](../../00_GOVERNANCE/MODEL_ROUTING_POLICY.md)
