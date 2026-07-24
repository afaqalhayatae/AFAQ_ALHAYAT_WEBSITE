# Canonical Data Model

## Document Control

- **Owner:** Business Owner
- **Status:** Draft — Contract Review Required
- **Version:** 0.1
- **Updated:** 2026-07-24

## Core Entities

- Service: references the canonical service ID and approved service knowledge.
- Service Area: references approved geographic coverage; it is not a branch.
- Customer and Contact Point: minimum data required for an approved purpose.
- Consent: channel, purpose, status, source, evidence, and timestamps.
- Enquiry: customer need, source, status, and safe free-text handling.
- Booking Request: requested service, location, schedule preference, and status.
- Quote Request: requirements and evidence; never an approved price by itself.
- Work Order: created only by an approved operational workflow.
- Approval: action, risk level, requester, decision, evidence, and expiry.
- Interaction: channel event linked to consent and retention rules.
- Audit Event: actor, action, target, outcome, timestamp, and correlation ID.

## Rules

- IDs are stable and never derived from mutable display names.
- Pending facts remain pending; applications must not convert them into truth.
- Personal data is minimized, access-controlled, retained by policy, and
  deletable through an approved process.
- Prices, warranties, credentials, and publication state require their
  designated owner gates.
