# Deployment and Monitoring

## Document Control

- **Owner:** Business Owner
- **Status:** Draft — Hosting Verification Required
- **Version:** 0.1
- **Updated:** 2026-07-24

## Deployment Pipeline

1. Validate code, tests, security checks, and migration safety.
2. Build an immutable release artifact.
3. Deploy to a non-production environment.
4. Run smoke, accessibility, integration, and rollback checks.
5. Obtain the required approval.
6. Deploy production and verify health.
7. Record release evidence and monitor the change window.

## Monitoring Minimum

- availability and latency;
- application and integration errors;
- booking and enquiry completion;
- database health and migration status;
- failed jobs and approval queues;
- security and rate-limit events;
- backup completion and restore verification.

## Open Infrastructure Gate

The exact Hostinger plan and its runtime, database, SSH/CI, backup, region,
staging, logging, and scaling capabilities must be verified before this
document can become an approved deployment runbook.
