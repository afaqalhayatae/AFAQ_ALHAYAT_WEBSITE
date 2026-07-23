# Technical

## Purpose

Technical architecture, security, testing, deployment, and monitoring — per `SYSTEM_ARCHITECTURE.md` Sec. 5. This domain owns *how* systems are built; it must not own business policy.

The platform's technology stack is already decided and recorded at [`00_GOVERNANCE/TECH_STACK.md`](../00_GOVERNANCE/TECH_STACK.md): Next.js/TypeScript/React/Tailwind frontend, Next.js API Routes on Node.js, PostgreSQL via Prisma ORM, cloud hosting. This domain should build detailed architecture, security, testing, deployment, and monitoring documentation **on top of** that decided stack — not re-decide it.

---

# Planned structure

| Folder | Purpose | Status |
|---|---|---|
| `ARCHITECTURE/` | System architecture diagrams and decisions, building on `TECH_STACK.md`. | Not yet populated |
| `SECURITY/` | Detailed technical security implementation of `99_STANDARDS/SECURITY_STANDARD.md`. | Not yet populated |
| `TESTING/` | Test strategy and coverage approach. | Not yet populated |
| `DEPLOYMENT/` | CI/CD and release process (`TECH_STACK.md` notes GitHub Actions as planned). | Not yet populated |
| `MONITORING/` | Error logging and performance monitoring approach (`TECH_STACK.md` lists this as a stack requirement, not yet detailed). | Not yet populated |
| `DISASTER_RECOVERY/` | Backup and recovery procedures (`TECH_STACK.md` lists automated backups as a requirement, not yet detailed). | Not yet populated |

---

# Status

Structural placeholder; the one real technical decision that exists (`TECH_STACK.md`) is cross-referenced rather than duplicated. Detailed architecture/security/deployment documentation requires developer input to avoid inventing implementation details that may not match what's actually built.
