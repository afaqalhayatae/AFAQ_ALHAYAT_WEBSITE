# Integration Standard

## Document Control

- **Owner:** Business Owner
- **Status:** Approved Baseline
- **Version:** 1.0
- **Updated:** 2026-07-24

## Requirements

- Give every provider adapter a documented purpose, data boundary, owner,
  failure policy, retry policy, and disable path.
- Store credentials only in an approved secret system.
- Verify webhook origin, prevent replay, and process events idempotently.
- Queue recoverable work and quarantine repeated failures.
- Record consent before customer communications.
- Apply owner approval to external publishing, paid spend, production access,
  commercial promises, and irreversible actions.
- Provide a manual recovery path when an integration is unavailable.
