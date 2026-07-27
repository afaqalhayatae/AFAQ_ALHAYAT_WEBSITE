# Phase 1 Implementation — Owner Approval

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 1.0
- **Effective Date:** 2026-07-27
- **Scope:** Authorizes Phase 1 (non-production scaffolding) of the separate website application, per `01_APPLICATION_ARCHITECTURE.md`–`06_DEPLOYMENT_PLAN.md` in this folder and `00_GOVERNANCE/IMPLEMENTATION_READINESS_REPORT.md`.
- **Rollback point:** Knowledge-repository commit `7eb1f06031884b55cbaca1dcc6aea92afff0590a` (2026-07-27) — see §4.

## Note on scope

This document records the Business Owner's approval of five implementation-preparation decisions and defines Phase 1's boundaries, review checkpoints, and rollback point. **It does not authorize writing application code.** Coding may begin only after this file exists and the readiness review referenced in §5 has been completed, and remains bounded by §2 and by `IMPLEMENTATION_READINESS_REPORT.md`'s "Prohibited Until Gate Approval" list.

---

## 1. Approved Decisions

| # | Decision | Effect on existing governance |
|---|---|---|
| 1 | `12_DESIGN_SYSTEM/COLORS.md` is the single implementation color source. All Tailwind color tokens are generated from it, and only it. | Resolves the color-token conflict flagged in `01_APPLICATION_ARCHITECTURE.md` §6 between `12_DESIGN_SYSTEM/COLORS.md` and `02_BRAND/BRAND_COLORS.md`, in the direction that document's §6 already recommended (`LUXURY_DESIGN_DIRECTION.md`'s "the approved tokens in `COLORS.md` remain the source of truth"). This is now an Owner decision, not an inferred reading. |
| 2 | `02_BRAND/BRAND_COLORS.md` is retained as brand/print reference only (e.g., the Gold `#D4AF37` accent, marketing collateral) and does not drive any UI implementation token, until a future reconciliation of the two documents. | No file is merged, deleted, or edited by this decision. The conflict is not silently erased — both documents remain as-is; this decision only settles which one implementation code reads from. |
| 3 | The website application is created as a separate repository/project, proposed name `afaqalhayatae-web` (Owner's final naming choice), not yet created. | Confirms the two-repository model already described in `02_FOLDER_STRUCTURE.md` §1 as an Owner decision rather than a proposal. |
| 4 | No application code, package manifest, or dependency is added inside `AFAQ_ALHAYAT_ENTERPRISE_KNOWLEDGE`. | Reaffirms `PROJECT_MANIFEST.md`'s "Out of Scope: Source code implementation" boundary and `CLAUDE.md`'s "Not yet built" section for this repository. |
| 5 | The canonical stack remains Next.js, TypeScript, React, Tailwind CSS, Node.js, MySQL, Prisma. | Confirms `DECISION_LOG.md` decision 34 (MySQL supersedes the PostgreSQL reference in decision 22 and the prior `TECH_STACK.md` text); no other stack component changes. |

None of these decisions authorizes production deployment, credentials, DNS/hosting changes, paid spend, or any commercial/legal/safety claim — those remain `A4` under `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md` and are unaffected by this approval.

---

## 2. Scope of Phase 1

Phase 1 is limited to the "Authorized First Implementation Scope" already defined in `00_GOVERNANCE/IMPLEMENTATION_READINESS_REPORT.md`, applied through the five companion plans in this folder:

- Create the `afaqalhayatae-web` repository and its Git protections (branch rules, required checks) — no other repository is affected.
- Scaffold the approved stack (Next.js App Router, TypeScript, Tailwind, Prisma) per `01_APPLICATION_ARCHITECTURE.md` and `02_FOLDER_STRUCTURE.md`.
- Implement design tokens from `12_DESIGN_SYSTEM/{COLORS,TYPOGRAPHY,SPACING,GRID}.md` (colors per decision 1 above), layout primitives, bilingual (`ar`/`en`) routing, and accessibility scaffolding — no page content yet beyond empty-state/placeholder contracts.
- Implement the read-only content adapter pattern described in `04_CONTENT_INTEGRATION_PLAN.md`, without wiring commercial content (pricing, warranty, booking) per that document's §3.
- Implement `prisma/schema.prisma` mirroring `08_DIGITAL_SYSTEMS/DATA_MODEL.md` v0.2 exactly, against local/CI MySQL only — no staging or production database.
- Implement CI (lint, typecheck, test) per `06_DEPLOYMENT_PLAN.md` §3, local/CI environments only.
- Preserve every pending fact (contact details, prices, warranty, licenses, response-time commitments) as a blocked/absent UI state — never a placeholder or invented value.

Explicitly out of scope for Phase 1: staging deployment, production deployment, any credential or secret beyond local/CI test values, live third-party integrations (analytics, CRM, chatbot, payment, email/SMS/WhatsApp), and any customer-facing publication.

---

## 3. Review Checkpoints

Checkpoints mirror the environment pipeline already defined in `06_DEPLOYMENT_PLAN.md` §3 and are restated here as Phase 1's specific gates:

1. **Local build checkpoint** — scaffolding builds, lints, and type-checks locally before any commit is pushed.
2. **CI checkpoint** — GitHub Actions (lint, typecheck, test) must pass green on every change; no merge without it.
3. **Design Acceptance Gate** — per `LUXURY_DESIGN_DIRECTION.md` §11: every component reviewed independently in Arabic and English, token usage traced only to `12_DESIGN_SYSTEM/*` (colors per decision 1), no ad hoc values.
4. **Content/SEO pre-publish gate** — per `05_SEO_IMPLEMENTATION_PLAN.md` §8: applies once any page renders governed content, even in a non-production environment, to catch drift before it becomes a habit.
5. **Owner checkpoint** — the Business Owner reviews progress before Phase 1 is declared complete and before any request to advance to staging (`06_DEPLOYMENT_PLAN.md` §9's Phase 2). This is a distinct, later approval — not implied by this document.

No checkpoint in this list authorizes moving past Phase 1 into staging or production; that remains a separate future Owner approval per `06_DEPLOYMENT_PLAN.md`.

---

## 4. Rollback Point

- **Knowledge repository:** commit `7eb1f06031884b55cbaca1dcc6aea92afff0590a` (2026-07-27, branch `main`) is the reference state as of this approval. Phase 1 application work makes no change to this repository beyond the documents already in `07_WEBSITE/IMPLEMENTATION/`; if any future implementation step is found to require a knowledge-repository change, that change is proposed and reviewed on its own, separate from application code.
- **Application repository:** once `afaqalhayatae-web` is created, its own first scaffolding commit becomes its rollback point. Per `06_DEPLOYMENT_PLAN.md` §6, rollback is always by redeploying/reverting to a prior known-good commit — never `git push --force` or `reset --hard` — consistent with this repository's non-destructive posture (`SYSTEM_ARCHITECTURE.md` §14).
- If Phase 1 is halted or reversed, no database migration beyond local/CI ever ran against real data, and no credential beyond local/CI test values was ever issued — so rollback carries no data-loss or credential-revocation risk at this stage.

---

## 5. Next Step

A project readiness review follows this approval before any coding begins, covering: whether all five companion planning documents (`01`–`06`) are internally consistent with these decisions, whether any open gate in `IMPLEMENTATION_READINESS_REPORT.md` blocks even Phase 1 scope, and whether `DECISION_LOG.md` needs a corresponding entry.

---

## Related Documents

- `01_APPLICATION_ARCHITECTURE.md`
- `02_FOLDER_STRUCTURE.md`
- `03_COMPONENT_STRATEGY.md`
- `04_CONTENT_INTEGRATION_PLAN.md`
- `05_SEO_IMPLEMENTATION_PLAN.md`
- `06_DEPLOYMENT_PLAN.md`
- `00_GOVERNANCE/IMPLEMENTATION_READINESS_REPORT.md`
- `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`
- `00_GOVERNANCE/DECISION_LOG.md`
