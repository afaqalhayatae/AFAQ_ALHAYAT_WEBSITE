# Solution Architecture

## Document Control

- **Owner:** Business Owner
- **Status:** Approved Direction — Implementation Verification Required
- **Version:** 1.0
- **Updated:** 2026-07-24

## Purpose

Define the implementation boundary for the AFAQ Alhayat digital platform
without introducing source code, credentials, or unverified infrastructure
facts.

## Canonical Architecture

- Next.js and React deliver the bilingual customer and owner interfaces.
- TypeScript is the application language.
- Next.js server capabilities provide the initial API boundary.
- MySQL owns transactional platform data.
- Prisma owns the application data-access schema and migrations.
- External services connect only through documented adapters.
- The enterprise knowledge repository remains the source of approved business
  facts; application databases must not silently become a competing authority.

## Logical Layers

1. Presentation: public website, booking, customer portal, owner dashboard.
2. Application: service, booking, enquiry, consent, content, and approval flows.
3. Domain: governed business rules and references to canonical knowledge.
4. Data: MySQL through Prisma with auditable migrations.
5. Integration: analytics, messaging, email, maps, storage, and future CRM.
6. Operations: deployment, monitoring, backups, incident response, and recovery.

## Implementation Gates

- Hostinger plan verified: Next.js, Node.js, and MySQL confirmed supported
  (`DECISION_LOG.md` decision 34). Deployment method, secrets, backups, and
  observability remain to be confirmed.
- Confirm pending contact, consent, pricing, warranty, and service facts.
- Approve the data model and API contracts before coding dependent features.
- No production credential or secret may be stored in this repository.

## Canonical References

- Technology direction: [`TECH_STACK.md`](../00_GOVERNANCE/TECH_STACK.md)
- Security: [`SECURITY_IMPLEMENTATION_STANDARD.md`](SECURITY_IMPLEMENTATION_STANDARD.md)
- Data model: [`DATA_MODEL.md`](../08_DIGITAL_SYSTEMS/DATA_MODEL.md)
- API contracts: [`API_CONTRACTS.md`](../08_DIGITAL_SYSTEMS/API_CONTRACTS.md)
