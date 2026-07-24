# Security Implementation Standard

## Document Control

- **Owner:** Business Owner
- **Status:** Approved Baseline
- **Version:** 1.0
- **Updated:** 2026-07-24

## Mandatory Controls

- Validate and normalize all untrusted input.
- Authorize every protected action on the server.
- Apply least privilege to owner, agent, integration, and service identities.
- Keep secrets outside Git and outside documentation.
- Encrypt transport with HTTPS and use secure session settings.
- Protect state-changing requests from CSRF and abusive automation.
- Rate-limit public forms, authentication, and sensitive APIs.
- Record security-relevant events without logging sensitive content.
- Minimize personal data and define retention before collection.
- Require explicit owner approval for production credentials, DNS, payments,
  publishing, destructive data actions, and access-policy changes.

## Release Gate

No feature handling identity, customer data, messaging, payments, or publishing
may ship until its threat review, access rules, validation, audit events,
failure behavior, and recovery path are tested.
