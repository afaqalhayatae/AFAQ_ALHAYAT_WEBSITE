# Multi-Platform Automation Architecture

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — extends Approved architecture; authorizes no live posting, tool purchase, or account connection
- **Version:** 0.1
- **Prepared:** 2026-08-04
- **Updated:** 2026-08-07 — the "Idea" and "Copywriting/Captions/Hashtag
  research" sub-stages now have a real, machine-readable source:
  `GET /api/social-content/facts` in `afaqalhayatae-app` (API-key gated,
  read-only), built for the Owner-requested n8n drafting workflow. It
  returns exactly the same `APPROVED_SERVICE_CONTENT_SLUGS`-gated facts
  the public service/landing pages already render — no new fact, no
  write access, no publishing capability. This still does not authorize
  any live posting, tool purchase, or account connection — those remain
  as this document already states them.

## Purpose

Deliverable 3 of 5. `AUTOMATION_AND_PUBLISHING.md` is already an **Approved
Architecture** with its own macro pipeline, Fast-Track Classes A–D,
Platform Connection Policy, Publishing Controls, failure-handling rules,
and a 10-step Initial Implementation Sequence. `AGENT_ORCHESTRATION.md`
defines the general control plane and Job Envelope schema every agent job
in this repository already uses. **This document does not re-derive
either** — it fills the one genuinely missing piece: the concrete
AI-content-workflow sub-stages (idea → copy → captions → hashtags → image
prompts → video scripts → schedule) that decompose stages 3–4 of
`CONTENT_PRODUCTION_WORKFLOW.md`'s existing 10-stage workflow, plus how a
social-publishing agent job would use `AGENT_ORCHESTRATION.md`'s existing
Job Envelope schema.

## 1. Where this sits in the existing pipeline

`AUTOMATION_AND_PUBLISHING.md`'s macro pipeline (unchanged):
`Approved strategy → canonical facts → content brief → script/copy draft →
media production → bilingual/platform review → approval → scheduling →
publishing → monitoring → analytics → learning`

`CONTENT_PRODUCTION_WORKFLOW.md`'s 10 stages (unchanged):
1. Select an approved objective and audience need
2. Create a brief with canonical service and brand references
3. Draft Arabic and English copy
4. Produce channel-specific visual and video variants
5. Verify facts, claims, language, safety, rights, accessibility
6. Obtain the required approval class
7. Schedule with an idempotency key
8. Confirm publication and store platform identifiers
9. Monitor responses and performance
10. Record learnings without rewriting canonical business facts

**This document's sub-stages sit entirely inside stages 3–4**, producing
the actual drafts that stage 5 then verifies:

| Sub-stage | Output | Feeds |
|---|---|---|
| Idea | One approved objective + real canonical fact reference (service ID / FAQ ID / location ID) | Stage 1–2 output, unchanged |
| Copywriting | Arabic-primary draft copy, one per format from `CONTENT_CALENDAR_STRUCTURE.md`'s platform-format table | Stage 3 |
| Captions | Platform-length-appropriate caption variants (Instagram/Facebook/LinkedIn/X each have different real length norms) | Stage 3 |
| Hashtag research | Drawn from real, already-used service/location terms — never fabricated trending tags, never a community name blocked by `LOCAL_SEO_CONFLICT_RESOLUTION_PLAN.md` | Stage 3 |
| Image prompts | Only for **disclosed** generated/illustrative assets, per `MEDIA_STANDARDS.md`'s generation-method/disclosure requirement — never for content presented as real customer work | Stage 4 |
| Video scripts | Hook/shot-list/narration/captions/CTA per `MEDIA_STANDARDS.md`'s pre-production checklist | Stage 4 |
| Scheduling | Idempotency key assignment, per `AUTOMATION_AND_PUBLISHING.md`'s Publishing Controls | Stage 7, unchanged |

## 2. AI Use boundaries (restated, not new)

`CONTENT_PRODUCTION_WORKFLOW.md`'s AI Use clause already governs every
sub-stage above: AI may research approved sources, draft, translate for
review, brief, and generate *disclosed* creative assets. AI may **not**
invent company facts, impersonate customers, approve its own high-impact
claims, or publish without the configured gate. No sub-stage above changes
this.

## 3. Job Envelope usage (reusing `AGENT_ORCHESTRATION.md`'s schema, not a new one)

Any future automated job for a social content sub-stage uses the existing
required fields — `job_id, agent_role, objective, authority_level,
allowed_sources, allowed_tools, allowed_write_paths, forbidden_actions,
budget_limit, validation_checks, approval_required, rollback_reference,
deadline` — with `agent_role` set to the supervising role from
`AI_AGENT_FUTURE_SYSTEM.md` (§ below), and `allowed_write_paths` scoped to
the specific `CONTENT_CALENDAR.md` entry being drafted, never a live
platform account directly (publishing itself remains human-gated per
Fast-Track Class).

## 4. Fast-Track Class mapping for each sub-stage

Reusing `AUTOMATION_AND_PUBLISHING.md`'s existing A–D classes, not a new
scheme:

| Sub-stage | Fast-Track Class | Why |
|---|---|---|
| Idea, hashtag research | A (Auto-Draft) | No claim risk, easily reversible |
| Copywriting, captions | A or B depending on pillar | Evergreen education = A; anything nearing a claim = B (Approval Queue) |
| Image prompts, video scripts | B | Needs human review before any asset is produced against it |
| Scheduling of an *already-approved* item | B | Mechanical once approval exists |
| Anything touching price/offer/guarantee/license/safety/legal | D (Manual Only) | Unchanged — matches `PUBLISHING_APPROVAL_POLICY.md`'s High tier |

## 5. What this document explicitly does not do

- Does not authorize any live posting, tool connection, or spend — same
  standing line as `AUTOMATION_AND_PUBLISHING.md`: "No live posting is
  authorized by this document alone."
- Does not invent a new pipeline, job schema, or approval scheme — every
  mechanism used here already exists elsewhere in this repository.
- Does not touch Pinterest's or TikTok/Snapchat's own already-specified
  automation flows — those remain their own platform-specific
  instantiations of the same macro pipeline.

## Related Documents

- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/AUTOMATION_AND_PUBLISHING.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/CONTENT_PRODUCTION_WORKFLOW.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/CONTENT_CALENDAR_STRUCTURE.md`
- `10_MARKETING_AND_SEO/SOCIAL_MEDIA/MEDIA_STANDARDS.md`
- `08_DIGITAL_SYSTEMS/AUTOMATION/AGENT_ORCHESTRATION.md`
- `08_DIGITAL_SYSTEMS/AUTOMATION/AI_AGENT_FUTURE_SYSTEM.md`
