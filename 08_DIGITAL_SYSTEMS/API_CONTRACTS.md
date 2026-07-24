# API Contract Standard

## Document Control

- **Owner:** Business Owner
- **Status:** Approved Baseline
- **Version:** 1.0
- **Updated:** 2026-07-24

## Contract Rules

- Version public contracts and document compatibility.
- Validate request shape, size, type, locale, consent, and authorization.
- Return stable error codes, safe messages, correlation IDs, and retry hints.
- Make retried state-changing operations idempotent where practical.
- Use pagination and bounded filters for collections.
- Never expose secrets, internal prompts, stack traces, or unnecessary personal
  data.
- Record auditable events for approvals and high-impact changes.
- Treat integrations as adapters; provider-specific behavior must not leak into
  canonical domain rules.

## Approval Boundary

Documentation may define contracts. Production endpoints, credentials,
external writes, customer messaging, publishing, and destructive actions
remain subject to the autonomy and approval matrix.
