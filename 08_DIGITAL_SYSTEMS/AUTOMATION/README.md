# Automation

## Purpose

Define controlled automation for knowledge, marketing, customer operations,
media production, publishing, notifications, and reporting.

## Safety Model

Automation is divided into risk classes:

| Class | Example | Approval |
|---|---|---|
| A — Read-only | Reporting, validation, draft suggestions | May run automatically |
| B — Internal reversible | Create draft, tag content, prepare schedule | Automated with audit trail |
| C — External reversible | Publish approved content, send non-sensitive notification | Explicit policy and approval |
| D — High impact | Pricing, payment, legal claim, customer commitment, deletion | Human approval every time |

## Architecture

Each workflow must define trigger, canonical inputs, validation, approval,
action, idempotency key, retry policy, audit record, alerting, owner, and
rollback.

## Required Controls

- Retrieve only approved canonical data.
- Block Draft, HOLD, Unverified, expired, or missing facts.
- Store secrets outside the repository.
- Use least-privilege accounts and environment separation.
- Prevent duplicate posting or messaging through idempotency.
- Log who approved what, when, and from which source version.
- Stop safely when dependencies or validation fail.
- Provide manual override and recovery procedures.

## Initial Automation Roadmap

1. Knowledge validation and broken-link reports
2. Draft content generation from approved service facts
3. Media brief and variant preparation
4. Approval queue
5. Scheduled publishing
6. Comment and lead triage
7. CRM handoff
8. Analytics and performance feedback

No live external action is authorized by this document alone.

