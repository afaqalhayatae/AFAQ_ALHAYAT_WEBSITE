# Canonical Data Model

## Document Control

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 0.2
- **Updated:** 2026-07-26

## Core Entities

- Service: references the canonical service ID and approved service knowledge.
- Service Area: references approved geographic coverage; it is not a branch.
- Customer: id and a list of Contact Points; minimum data required for an
  approved purpose.
- Contact Point: id, customer reference, channel, and value.
- Consent: id, channel, purpose, status, source, evidence, and timestamps.
- Enquiry: customer need, source, status, and safe free-text handling.
- Booking Request: requested service, location, schedule preference, and status.
- Quote Request: requirements and evidence; never an approved price by itself.
- Work Order: created only by an approved operational workflow; it must
  reference the Approval that authorized its creation.
- Approval: id, action, target type, target ID, risk level, requester,
  decision, evidence, and expiry.
- Interaction: channel event linked to consent and retention rules.
- Audit Event: actor, action, target, outcome, timestamp, and correlation ID.

## Rules

- IDs are stable and never derived from mutable display names.
- Pending facts remain pending; applications must not convert them into truth.
- Personal data is minimized, access-controlled, retained by policy, and
  deletable through an approved process. Per-record deletion capability is a
  required pre-production implementation gate and does not block this
  document's approval.
- Prices, warranties, credentials, and publication state require their
  designated owner gates.
- An Approval must match the exact action instance — target type and target
  ID — that it authorizes; a generically approved record does not satisfy an
  entity's approval-gated creation rule.
- Service and Service Area synchronization with the canonical catalog and
  coverage documents (`04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`,
  `03_MARKET/SERVICE_AREAS.md`) is a future implementation step and does not
  block this document's approval.
