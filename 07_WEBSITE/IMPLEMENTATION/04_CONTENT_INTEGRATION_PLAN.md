# Content Integration Plan

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only, no content adapter built by this document
- **Version:** 1.0
- **Prepared:** 2026-07-27
- **Depends on:** `00_GOVERNANCE/03_CONTENT_TO_WEBSITE_MAPPING.md`, `04_SERVICE_KNOWLEDGE/*`, `03_MARKET/SERVICE_AREAS.md`, `02_BRAND/CONTACT_INFORMATION.md`

## Note on scope

This document describes how governed knowledge becomes rendered website content without ever being copied or forked. It does not build the adapter, does not generate any page, and does not publish any fact.

---

## 1. Principle

Per `SYSTEM_ARCHITECTURE.md` §7, the application must **reference**, never duplicate, business facts. Concretely, this means: no service description, price, coverage claim, or contact detail is ever retyped directly into a `.tsx` file. Every such value flows through a content adapter that reads this knowledge repository (or a build-time snapshot of it) as its only source.

---

## 2. Content Adapter Responsibilities

| Adapter module (see `02_FOLDER_STRUCTURE.md`) | Reads from | Produces |
|---|---|---|
| `services.ts` | `04_SERVICE_KNOWLEDGE/SERVICE_CATALOG.md`, `<NN_SERVICE>/BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `CUSTOMER_GUIDE.md`, `FAQ.md`, `SEO_AI.md`, `CONTENT_AR.md`/`CONTENT_EN.md`, `MEDIA.md` | Typed `Service` content objects, one per `SVC-<NAME>`, including a `publishable: boolean` derived from package maturity status |
| `locations.ts` | `03_MARKET/SERVICE_AREAS.md`, `04_SERVICE_KNOWLEDGE/SERVICE_MATRIX.md` | Typed `Area` content objects, restricted strictly to registry rows; service availability per area computed from the matrix, never assumed |
| `brand.ts` | `02_BRAND/CONTACT_INFORMATION.md`, `LOCAL_SEO_PROFILE.md` | Typed `ContactPoint` values, each with a `status: "approved" | "pending"` flag driving the blocked-field UI pattern |
| `seo.ts` | `<NN_SERVICE>/SEO_AI.md`, `07_WEBSITE/01_HOMEPAGE/03_HOMEPAGE_SEO_AI.md`, `10_MARKETING_AND_SEO/SCHEMA_STRATEGY.md` | Typed metadata + schema.org objects per page |

The adapter is a **read path only** — it never writes back to the knowledge repository, and knowledge-repository edits remain a governed, human/agent-reviewed process independent of the application's deploy cycle.

---

## 3. Publishability Gating (the core safety mechanism)

Every content type carries an explicit maturity/status field already present in its governing document, and the adapter must surface it rather than assume completeness from a folder's mere existence:

- **Services:** `SERVICE_CATALOG.md`'s "Knowledge package status" column (`Complete` / `Review-ready` / `Structurally complete draft` / `Blocked`) maps to a `publishable` flag. Only `Complete` and owner-confirmed `Review-ready` packages render full public claims (methods, scope detail); draft/blocked packages render, at most, a name and a "details coming soon" state — never fabricated detail to fill the gap.
- **Locations:** Only rows present in `03_MARKET/SERVICE_AREAS.md`'s Approved Registry generate pages. Emirate rows are page-ready now; Tier 1–3 community rows additionally require the SEO/ops quality checklist in that same document before a dedicated page is generated — the adapter should distinguish "in registry" from "quality-gate cleared."
- **Contact facts:** Only fields marked `Approved` in `CONTACT_INFORMATION.md`'s status table render; `Pending` fields render as absent, never as an empty string or guessed value.
- **Commercial facts (pricing, warranty, booking):** Not modeled as content at all in Phase 1/2 — these remain hard-blocked at the adapter level until their owning `06_CUSTOMER_AND_SALES/*` document exits Draft status, consistent with the `A4` gate on commercial claims.

---

## 4. Bilingual Content Parity

- Each service's `CONTENT_AR.md` and `CONTENT_EN.md` are paired inputs; the adapter treats a service as bilingual-ready only when both exist and both have passed the parity check already required by `PROJECT_MANIFEST.md` ("Arabic and English are equal first-class languages... facts cannot diverge").
- Parity is a **content-review responsibility**, not an automatic diff — phrasing legitimately differs by language, but the underlying facts (scope, process, safety notes, FAQ answers) must match. This plan recommends a manual bilingual-parity checklist item per service page before publish, not an automated translation-equivalence tool (which the repository's standards do not currently define).

---

## 5. Location Content Integration Detail

- Location pages consume `SERVICE_AREAS.md` directly for name (EN/AR), type, parent emirate, and effective date, and `SERVICE_MATRIX.md` for which services are active in that area.
- The adapter must reject generating a page for any `area_id` not present in the registry — this is the mechanism that prevents the "coverage overstatement" risk already flagged in `00_GOVERNANCE/01_PROJECT_AUDIT_REPORT.md`.
- Priority-community pages (Tier 1–3) additionally carry the registry's own caveat that they are marketing priorities, not branch addresses — the adapter/page template must not imply a physical branch.

---

## 6. AI / Entity Content Integration

- `09_AI_KNOWLEDGE/ENTITY_REGISTRY.md` and `ENTITY_RELATIONSHIPS.md` define the canonical entity model already used for AI answers; the same entity identifiers should back the on-page schema.org markup (see `05_SEO_IMPLEMENTATION_PLAN.md`) so AI-answer content and visible page content never diverge from each other.
- Any future on-site AI assistant consumes the same content adapter and is bound by `09_AI_KNOWLEDGE/ANSWER_POLICY.md` — it does not get a separate, looser content path.

---

## 7. Content Update Workflow (proposed, not yet implemented)

1. A knowledge-repository change (new/updated service fact, new approved area, corrected contact field) is committed and reviewed under this repository's existing governance.
2. On the application's next build (or a scheduled/triggered re-sync for ISR pages), the content adapter re-reads the updated source and regenerates only the affected pages.
3. No manual re-typing of facts into the application ever occurs — if a developer or agent finds themselves typing a business fact directly into a component, that is treated as a process failure, not a shortcut.

The exact sync mechanism (git submodule, scheduled fetch, CI step copying a content snapshot into the build) is an implementation-time engineering decision for Phase 1 scaffolding, not decided by this document.

---

## What This Document Does Not Do

- It does not build the adapter or write any parsing/sync code.
- It does not generate a single page or piece of schema markup.
- It does not decide the exact technical sync mechanism between the two repositories.

---

## Related Documents

- `00_GOVERNANCE/03_CONTENT_TO_WEBSITE_MAPPING.md`
- `01_APPLICATION_ARCHITECTURE.md`
- `05_SEO_IMPLEMENTATION_PLAN.md`
