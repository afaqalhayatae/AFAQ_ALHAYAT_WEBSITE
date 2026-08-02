# AI Agent Future System

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — future foundation planning only. No agent defined here is built, deployed, or authorized to act.
- **Version:** 1.0
- **Prepared:** 2026-08-02
- **Depends on / relationship to existing documents:** `00_GOVERNANCE/AGENT_REGISTRY.md` and `AUTOMATION/AGENT_ORCHESTRATION.md` already define the **internal governance agent roster** (`AGT-ORCH`, `AGT-GOV`, `AGT-SVC`, `AGT-CX`, `AGT-WEB`, `AGT-MKT`, `AGT-AIX`, `AGT-DES`) — agents that read and write **this knowledge repository** under the one-owner operating model. This document is a **different, later layer**: future agents that would operate **against the live, deployed business** (website, CRM, social channels, ad accounts) once those systems exist. It does not replace, duplicate, or re-authorize the existing registry — every agent below is mapped to the existing `AGT-*` role that would supervise and approve its output before anything goes live.

---

## 1. Why This Is a Separate Layer

`AGENT_REGISTRY.md`'s roster governs *documentation and knowledge-base work* — bounded write scopes inside this repository, reviewed by `AGT-QA`. The six agents requested in this directive are *operational* — they would act on live systems that don't exist yet (no CRM, no live ad accounts, no deployed chatbot). Treating them as live-authorized today would violate `AGENT_REGISTRY.md`'s own rule that "agents may not... treat Draft, HOLD, or Unverified content as approved," since the systems they'd operate on are themselves not yet built (`PROJECT_EXECUTION_STATUS_REPORT.md` §3).

---

## 2. Future Agent Roster

| Future agent | Purpose | Primary inputs (already-canonical sources only) | Supervising existing role | Cannot do without Owner gate |
|---|---|---|---|---|
| **SEO Agent** | Monitor rankings, generate Service+City page candidates per `LOCAL_SEO_MASTER_PLAN.md`'s architecture, flag keyword drift against approved scope | `SERVICE_MASTER_MATRIX.md`, `SERVICE_AREAS.md`, `LOCAL_SEO_MASTER_PLAN.md` | `AGT-MKT` | Publish any page; claim keyword-volume/ranking data not actually measured |
| **Content Agent** | Draft service/location page content from approved `04_SERVICE_KNOWLEDGE/` facts only | Approved service packages, `SERVICE_CATALOG.md` | `AGT-SVC` / `AGT-MKT` | Invent scope, price, warranty, license, or response-time facts (same rule as this repository's own governing constraint) |
| **Design/Image Agent** | Manage image-asset pipeline, flag no-placeholder-rule violations (e.g., the Handyman/Waterproofing/CCTV gaps in `SERVICE_MASTER_MATRIX.md`) | `12_DESIGN_SYSTEM/`, `VISUAL_ASSET_MASTER_PLAN.md` | `AGT-DES` | Generate or approve a substitute/placeholder image — no-placeholder rule stays in force |
| **Customer Support Agent** | Live chatbot/email triage against `CONVERSATIONAL_ASSISTANT_STANDARD.md` and `ANSWER_POLICY.md` | `09_AI_KNOWLEDGE/`, approved service FAQs | `AGT-CX` / `AGT-AIX` | Make a commercial commitment (price, warranty, scheduling promise) beyond approved FAQ content; escalation to a human is mandatory for anything outside approved answers, per `ANSWER_POLICY.md` |
| **Analytics Agent** | Report on real measured traffic/conversion once analytics accounts are connected | Live analytics data only (none exists yet) | `AGT-WEB` | Report or extrapolate any figure before a real, connected data source exists — no simulated metrics |
| **Brand Agent** | Check outbound content (social, email, page copy) against `02_BRAND/` voice/identity/color rules before publish | `02_BRAND/` | `AGT-MKT` / `AGT-DES` | Approve its own output for publication — same "producing role cannot self-approve" rule already governing this repository's content pipeline |

---

## 3. Guardrails (inherited, not new)

Every future agent above inherits, unmodified, the constraints already governing this repository's agents:

- Never fabricate price, warranty, license, certification, response-time, or regulatory claims (`CLAUDE.md`, `AGENT_REGISTRY.md`).
- A producing agent may not approve its own work — an independent check (mapped in §2's "Supervising existing role" column) is required before anything reaches a live channel.
- `A4`-gated actions (money, credentials, DNS/hosting, contracts, external publishing) always require explicit, per-instance Owner approval — no future agent is granted standing authorization by this document.
- Every job follows the existing Required Job Envelope (`AGENT_ORCHESTRATION.md`) once implemented — `job_id`, `authority_level`, `allowed_write_paths`, `approval_required`, etc.

---

## 4. Build Sequence (recommended, not decided)

None of these six agents can meaningfully operate before their underlying live system exists:

1. SEO Agent and Content Agent are the most buildable first — they act on already-canonical repository content and don't require a live CRM.
2. Design/Image Agent depends on a selected image pipeline/tool (`PROJECT_EXECUTION_STATUS_REPORT.md` §4 risk — no such tool exists in this environment today).
3. Customer Support Agent depends on the chatbot infrastructure referenced in `07_WEBSITE`'s Phase 5 preparation (§5 below) — not yet built.
4. Analytics Agent depends on connected analytics accounts (`CURRENT_PROJECT_STATUS.md` "Work in Progress" — accounts not yet confirmed).
5. Brand Agent can review content produced by 1–2 as soon as they exist; it does not require a live system of its own.

---

## What This Document Does Not Do

- Does not build, deploy, or grant authorization to any agent listed above.
- Does not modify `AGENT_REGISTRY.md`, `AGENT_ORCHESTRATION.md`, or any other existing file.
- Does not connect to, or claim data from, any live analytics, CRM, or ad account.
- Does not stage, commit, or push anything.

---

## Related Documents

- `00_GOVERNANCE/AGENT_REGISTRY.md`, `00_GOVERNANCE/AI_OPERATING_MODEL.md`, `00_GOVERNANCE/AUTONOMY_AND_APPROVAL_MATRIX.md`
- `08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_ORCHESTRATION.md`, `AGENT_RUNBOOK.md`
- `09_AI_KNOWLEDGE/ANSWER_POLICY.md`, `CONVERSATIONAL_ASSISTANT_STANDARD.md`
- `10_MARKETING_AND_SEO/LOCAL_SEO_MASTER_PLAN.md` — SEO Agent's future scope
- `00_GOVERNANCE/PROJECT_EXECUTION_STATUS_REPORT.md` — current live-system readiness gaps referenced in §4
