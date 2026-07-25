# Service DNA Draft — AC Maintenance

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — Expansion, Owner-Reviewed (Complete)
- **Version:** 0.4
- **Prepared:** 2026-07-24
- **Updated:** 2026-07-25 (Phase C.2 — Owner confirmed scope, promise, boundary vs. Electrical Maintenance, customer problems, Business Outcome, Brand Position, and Core Risks; all seven fields are now populated. WP2 B1: Customer Emotion interpretation confirmed as Owner judgment.)
- **Program:** `PROG-ESF-V1` (Program C — Enterprise Service Framework), Phase C.1.a / C.2
- **Service:** `SVC-AC-MAINTENANCE`

## What This Is

An ESMM Layer 2 (Service DNA) draft for AC Maintenance, prepared under
Phase C.1.a expansion authorization. Not `SERVICE_DNA_REGISTRY.md`; creates
no registry. `04_SERVICE_KNOWLEDGE/02_AC_MAINTENANCE/BUSINESS.md` and
`SAFETY.md` are deliberately fact-free governance scaffolds ("Owner Input
Register") stating that unknown facts "must not be inferred from a service
name, generic industry practice, or a source draft." This draft honors
that instruction: fields with no Owner decision behind them are marked
Pending Owner Input rather than filled from the service name or category.
This draft's structure was reviewed by `AGT-QA` (Pass, one defect
corrected) as part of the Phase C.1.a expansion batch. Following Phase
C.2 Owner Knowledge Capture, the Owner confirmed this service's scope,
promise, customer problems, boundary against Electrical Maintenance,
Business Outcome, Brand Position, and Core Risks (see Owner Review
Resolution below). All seven fields are now populated. Its content has
not been reviewed by `AGT-QA` since these updates and must not be cited
elsewhere or used to inform publishing, AI
answers, or customer-facing material.

---

## 1. Core Purpose

AC Maintenance is an approved service in AFAQ Alhayat's catalog
(`SVC-AC-MAINTENANCE`, category General Maintenance). **Owner-confirmed
2026-07-25:** covers inspection, routine maintenance, cleaning of relevant
components, addressing basic operating issues, and improving system
performance.

*Source: `SERVICE_CATALOG.md`; `BUSINESS.md` § Confirmed Identity; Owner
decision, 2026-07-25 (see Owner Review Resolution below).*

## 2. Core Promise

Improved cooling performance, equipment maintenance, reduced failures, and
improved comfort.

*Source: Owner decision, 2026-07-25 ("Customers choose AC Maintenance to
improve cooling, maintain the equipment, reduce failures, and improve
comfort"). No specific method, timeframe, price, or warranty is stated or
implied.*

## 3. Core Risks

Risks may relate to handling AC components and related electrical parts.
Work may involve access to elevated locations or AC units requiring
attention. Some faults may require technical assessment before action.

*Source: Owner decision, 2026-07-25. These are stated as risk categories
only, not safety procedures or operational instructions — no control
measure, PPE, or method is specified. `SAFETY.md` still contains no
formal hazard assessment for this service; a competent safety review
remains a separate, open item beyond this Core Risks entry.*

## 4. Core Constraints

- **Boundary vs. Electrical Maintenance** (Owner-confirmed 2026-07-25): AC
  system operation and AC-related issues belong to AC Maintenance; general
  electrical faults or power supply issues outside the AC system route to
  Electrical Maintenance.
- General electrical work outside the AC system is excluded, including
  general electrical supply/installation work.
- Work outside AC specialization must not be performed as AC Maintenance.
- Cannot claim technician qualifications, diagnostic process, safety
  controls, or escalation rules beyond what is stated above.
- Cannot state service deliverables, parts policy, warranty terms, or
  emergency availability.
- Cannot make geographic, response-time, or marketing claims without
  substantiation.

*Source: `BUSINESS.md` § Evidence Gate; `README.md` § Required Before
Approval; Owner decision, 2026-07-25.*

## 5. Customer Emotion

Concern about cooling performance or equipment reliability, and the need
for a well-maintained, comfortable environment.

*Source: interpreted from the Owner's 2026-07-25 statement of customer
problems ("cooling performance issues, reduced performance, unusual
sounds, water leakage from the unit, and periodic maintenance needs").
Interpretive, not a direct restatement — this names the given problem,
not a stated emotion.*

**Owner-confirmed 2026-07-25 (Round 4):** the interpreted entry above is
accepted as Owner judgment. No replacement content was supplied — this
remains labeled as interpretation, not sourced fact, and is not elevated
to a directly-sourced claim by this confirmation.

## 6. Business Outcome

Help maintain AC performance and reduce operational issues.

*Source: Owner decision, 2026-07-25. No number, price, or metric is
stated or implied.*

## 7. Brand Position

A reliable AC maintenance service supporting indoor comfort.

*Source: Owner decision, 2026-07-25. No claim of being the best or
largest is stated or implied.*

---

## Owner Review Resolution (2026-07-25)

1. **Customer problems:** cooling performance issues, reduced performance,
   unusual sounds, water leakage from the unit, and periodic maintenance
   needs.
2. **Scope:** inspection, routine maintenance, cleaning of relevant
   components, addressing basic operating issues, and improving system
   performance.
3. **Exclusions:** general electrical work outside the AC system,
   including general electrical supply/installation work, and any
   unrelated work.
4. **Boundary vs. Electrical Maintenance:** AC system operation and
   AC-related issues belong to AC Maintenance; general electrical faults
   or power supply issues outside the AC system route to Electrical
   Maintenance.
5. **Customer reason:** improved cooling, equipment maintenance, reduced
   failures, and improved comfort — recorded as Core Promise.
6. **Safety:** a general principle ("AC and electrical-related work must
   follow appropriate safety practices") was given, not a specific
   hazard — recorded in Core Risks with that distinction made explicit;
   the related statement that work outside AC specialization must not be
   performed as AC Maintenance is recorded in Core Constraints. Specific
   hazards remain Pending Owner Input.
7. Recorded into Core Purpose, Core Promise, Core Risks (partially), Core
   Constraints, and Customer Emotion (interpreted, flagged for
   confirmation). No task, equipment, price, or warranty was added beyond
   what is stated above.
8. **Remaining undefined, kept Pending Owner Input:** specific Core Risks
   content.

## Owner Review Resolution — Round 2 (2026-07-25, Business Outcome & Brand Position)

1. **Business Outcome:** "Help maintain AC performance and reduce
   operational issues."
2. **Brand Position:** "A reliable AC maintenance service supporting
   indoor comfort."
3. No claim of being the best, largest, or otherwise unsupported market
   position was added.

This resolution also explains, but does not modify, the confirmed
Cross-sell relationship already recorded in `SERVICE_RELATIONSHIPS_DRAFT.md`
(`SVC-AC-MAINTENANCE` → `SVC-ELECTRICAL-MAINTENANCE`) — that file is
unchanged, per instruction. This resolution creates no new business fact
beyond what is stated above, does not create `SERVICE_DNA_REGISTRY.md`,
and does not touch ESMM or EPGM.

## Owner Review Resolution — Round 3 (2026-07-25, Core Risks)

1. **Core Risks:** may relate to handling AC components and related
   electrical parts; work may involve access to elevated locations or AC
   units requiring attention; some faults may require technical
   assessment before action. Recorded as risk categories only — not
   converted into safety procedures or operational instructions. No
   hazard beyond these three points is claimed. This closes the last
   remaining field for this service; all seven fields are now populated.

## Owner Review Resolution — Round 4 (2026-07-25, Customer Emotion — Phase C.2 WP2 B1)

1. **Customer Emotion:** the drafted interpretation is confirmed as Owner
   judgment. No replacement content was supplied. Remains labeled as
   interpretation, not sourced fact.
2. This closes the last open item for this service identified by the
   AGT-QA consolidated review (Phase C.2 Work Package 2).

## Validation Performed

- Every field traces to `BUSINESS.md`, `SAFETY.md`, `README.md`,
  `SERVICE_CATALOG.md`, or the 2026-07-25 Owner decision for
  `SVC-AC-MAINTENANCE` only.
- No claim was inferred from the service name or expanded beyond the
  points the Owner confirmed.
- Customer Emotion is explicitly marked interpretive, not a direct
  restatement; Owner-confirmed (Round 4) as accepted judgment, not
  elevated to sourced fact.
- Core Risks is explicitly distinguished as a general principle, not a
  specific hazard list — not silently treated as resolved.
- All seven fields are populated from Owner-confirmed facts; none remain
  Pending Owner Input.
- No number, guarantee, price, or warranty claim appears in any field.
- `SERVICE_RELATIONSHIPS_DRAFT.md` was not modified.
- This file does not modify `ENTERPRISE_SERVICE_META_MODEL.md`,
  `ENTERPRISE_PUBLICATION_GATE_MODEL.md`, or any file under
  `04_SERVICE_KNOWLEDGE/`.
- No `SERVICE_DNA_REGISTRY.md` was created.

## Status

Draft — Expansion, Owner-Reviewed (Complete). All seven fields are now
populated from Owner-confirmed facts (2026-07-25); the Customer Emotion
interpretive-confirmation flag closed the same day (Phase C.2 WP2 B1).
Not approved, not canonical.
