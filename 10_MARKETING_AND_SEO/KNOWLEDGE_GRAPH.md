# Marketing Knowledge Graph

## Purpose

Define stable relationships that connect company, service, audience, location,
content, and channel knowledge without duplicating facts.

## Core Entities

- Organization
- Brand
- Service
- Service category
- Customer segment
- Location
- Content item
- Channel
- Campaign
- Conversion event

## Relationship Rules

- Organization `offers` Service only when the service is active in the catalog.
- Service `availableIn` Location only when approved in the service matrix.
- Content `about` Service through a stable service ID.
- Content `targets` Customer Segment as a planning relationship, not proof of
  service eligibility.
- Campaign `uses` Content and `promotes` approved Services.
- Conversion Event `attributedTo` a channel/campaign under documented consent
  and analytics rules.

## Identifier Policy

Never use display names as primary keys. IDs must be stable, language-neutral,
unique, and referenced by website, CRM, analytics, automation, and AI systems.

