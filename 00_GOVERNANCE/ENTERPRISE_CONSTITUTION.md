# Enterprise Constitution

## Document Information

- **Owner:** Business Owner
- **Status:** Approved
- **Version:** 1.0
- **Prepared:** 2026-07-24
- **Effective Date:** 2026-07-24 (ratified retroactively to this date)

---

## Preamble

This Constitution exists to state what must remain true about this enterprise
knowledge system regardless of which program, agent, technology, or business
decision comes next. Every other governing document in this repository is
scoped to a domain, a process, or a moment in time. This one is not. It holds
the small set of principles that every document, agent, and system operating
in this repository must satisfy.

This Constitution is a policy reference. It is not a power that stands above
the Business Owner.

---

## Authority and Owner Supremacy

The Business Owner is the sole human authority over AFAQ Alhayat's governed
knowledge system and retains ultimate authority at all times, without
exception.

This Constitution is the highest **policy reference** inside the repository —
the standard against which every other document, agent, workflow, and
automated system is measured. It does not outrank, bind, or limit the Owner.
The Owner may waive, override, or amend any part of it at any time. An Owner
decision takes effect immediately and does not require the amendment process
in this document to complete first; recording that decision for institutional
memory remains good practice under existing governance, not a precondition of
its validity.

Where any role, agent, automated system, or subordinate document claims final
authority over a matter, this Constitution and the Owner's authority prevail.

---

## Foundational Principles

1. **Knowledge Before Code** — Knowledge is created, checked, and approved
   before any system automates, publishes, or presents it. Systems consume
   knowledge; they do not originate it.

2. **Single Source of Truth** — Every fact exists once, owned by one place.
   Every other reference points to that source instead of restating it.

3. **Owner-Led, Agent-Operated** — The Owner leads and remains accountable.
   Agents and automated systems operate only within delegated, bounded
   authority; delegation of execution is never delegation of accountability.

4. **Truth Over Fabrication** — No agent or system may invent, assume, or
   infer a fact it cannot trace to an approved source. An unverifiable gap is
   reported, never filled.

5. **Traceability and Auditability** — Every consequential action must be
   traceable to its source, its actor, its authority, and its approval.
   Untraceable action is not trusted action.

6. **Reversibility and Safe Recovery** — Reversible action is preferred by
   default. Irreversible or destructive action requires the highest level of
   scrutiny and cannot proceed on inference alone.

7. **Proportional Autonomy** — The freedom granted to any agent or automated
   system must match the risk of the action it performs. Autonomy is earned by
   demonstrated safety, never assumed by default.

8. **Security and Privacy by Design** — Protection of credentials, personal
   data, and business-sensitive information is a baseline requirement of every
   design decision, not a control added afterward.

9. **Accessibility and Bilingual Equality** — Arabic and English are equal,
   first-class languages. Every system must remain usable and equivalent in
   meaning to the people it serves in either language.

10. **Scalability Without Unnecessary Complexity** — Growth is achieved by
    extending what already exists. Complexity is added only when the business
    need for it is real, not in anticipation of needs that do not yet exist.

11. **Preservation of Institutional History** — Knowledge, decisions, and
    superseded material are preserved, not deleted, so the organization never
    loses its own memory.

---

## Decision Hierarchy

```text
Business Owner
   (final human authority; not bound by the tiers below)
        │
        ▼
Enterprise Constitution
   (highest policy reference; binds all documents, agents, and systems)
        │
        ▼
Vision & Structure
   (PROJECT_MANIFEST.md, SYSTEM_ARCHITECTURE.md)
        │
        ▼
Operating Philosophy & Systems
   (AI_OPERATING_MODEL.md, and the Enterprise Agent Operating System
   when active)
        │
        ▼
Governance Execution
   (00_GOVERNANCE/* decisions, registries, and approval workflows)
        │
        ▼
Domain Knowledge
   (business, brand, market, service, operations, customer, marketing,
   technical, and design domains)
        │
        ▼
Implementation
   (software, published content, and automated execution)
```

A lower tier may add detail; it may never contradict a higher tier. The Owner
may act outside any tier at any time without first changing this Constitution.

---

## Delegation and Non-Overlap

This Constitution states principle only. It contains no business fact, no
agent identifier, no automation level, no implementation procedure, no folder
mechanic, and no technology choice. Those remain fully owned by the documents
already responsible for them: `SYSTEM_ARCHITECTURE.md` for structure and
naming, `AI_OPERATING_MODEL.md` and its related documents for roles and
automation levels, `PROJECT_MANIFEST.md` for vision and scope, and each
domain's own canonical sources for its facts.

`SYSTEM_ARCHITECTURE.md` remains, in its own words, the repository's
architectural constitution — the structural and technical constitution of how
the repository is built. This document is the philosophical constitution —
the standard the architectural constitution, and everything else, must
satisfy. Both descriptions are correct at their own tier; neither replaces the
other.

If a subordinate document is found to restate a principle from this
Constitution in its own words rather than referencing it, the restatement in
the subordinate document is the item to be corrected — not this Constitution.

---

## Interpretation and Conflict Escalation

No agent, automated system, or subordinate document may resolve a detected
conflict with this Constitution on its own authority.

The required flow is:

```text
Detect → Record evidence → Stop → Escalate to Owner
```

Any correction that follows is carried out through the repository's existing
authority, independent-review, and approval process — this Constitution
creates no separate correction mechanism of its own. Until the Owner decides,
the conflicting lower-tier content remains marked unresolved and must not be
treated as authoritative.

---

## Amendment and Ratification

This Constitution may be amended, waived, or ratified only by the Business
Owner. Agents may propose amendment language for review; they may never
merge, finalize, or self-ratify a change.

A change to a principle's substance is a major version. A clarification that
changes no principle is a minor version. Every version change is recorded in
the Ratification Record below; history is appended, never deleted or
overwritten.

---

## Ratification Record

| Version | Date | Status | Summary |
|---|---|---|---|
| 0.1 | 2026-07-24 | Draft | Initial draft prepared for independent non-overlap and consistency review. Not yet ratified. |
| 1.0 | 2026-07-24 | Approved | Ratified by the Business Owner, effective retroactively to 2026-07-24, per `DECISION_LOG.md` decision 32. EAOS v1 (decision 23) and ESMM/EPGM (decision 31) approvals, both dated 2026-07-24, remain valid under this Constitution and are not reopened. |
