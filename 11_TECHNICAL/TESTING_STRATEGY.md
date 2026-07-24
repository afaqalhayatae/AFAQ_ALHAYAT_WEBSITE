# Testing Strategy

## Document Control

- **Owner:** Business Owner
- **Status:** Approved Baseline
- **Version:** 1.0
- **Updated:** 2026-07-24

## Required Test Layers

- Static checks: formatting, types, linting, dependency and secret scans.
- Unit tests: domain rules, validation, transformations, and permission logic.
- Integration tests: database, API, adapters, queues, and failure handling.
- Contract tests: request, response, error, event, and schema compatibility.
- End-to-end tests: bilingual discovery, enquiry, booking, consent, owner
  approval, and recovery journeys.
- Accessibility tests: keyboard, focus, semantics, contrast, and screen-reader
  behavior.
- Security tests: authentication, authorization, injection, rate limits, and
  sensitive-data exposure.
- Knowledge tests: canonical retrieval, pending-fact refusal, citation, and
  escalation.

## Release Rule

A release must have traceable acceptance criteria, passing automated checks,
reviewed exceptions, a rollback method, and owner approval for any A4 action.
