# Design Decisions Update

## Document Information

- **Owner:** Business Owner
- **Status:** Approved — decisions recorded here are effective immediately upon this document's creation
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Last Updated:** 2026-08-01
- **Package:** `00_GOVERNANCE/`
- **Resolves findings from:** `00_GOVERNANCE/DESIGN_SYSTEM_ASSET_ALIGNMENT_REPORT.md` §1–§4, and closes the AI-generated-media conflict left open by Decision 36 (`DECISION_LOG.md`, 2026-07-28).

## Purpose

Following the Owner's review of `DESIGN_SYSTEM_ASSET_ALIGNMENT_REPORT.md`, this document records four governance decisions that resolve the conflicts and open items identified in that review. These decisions are effective immediately. No code, asset, or filename was changed to produce this document — it is a decision record only. Any file changes required to fully implement these decisions (e.g. editing `02_BRAND/TYPOGRAPHY.md`, adding a new hero-image library) remain separate, not-yet-executed work.

---

## 1. AI-Generated Asset Policy

**Decision:** AI-generated visuals are approved for use in:
- Service cards
- Marketing visuals
- Brand visuals

**AI-generated visuals are NOT allowed for:**
- Real project evidence
- Completed work proof
- Real team documentation

**Resolves:** The conflict flagged in Decision 36 and confirmed with hard evidence in `DESIGN_SYSTEM_ASSET_ALIGNMENT_REPORT.md` §2.4/§3.3 — that all 172 `public/brand/icons/` files (Canva AI) and all 9 `public/brand/images/services/` files (gpt-image 2.0) are confirmed AI-generated, which sat in tension with `12_DESIGN_SYSTEM/LUXURY_DESIGN_DIRECTION.md` §10's blanket ban on "AI-generated media presented as real company evidence."

**Effect on existing assets:** The 172 brand icons and 9 approved service images — all used as service-card/marketing/brand visuals, none currently presented as project evidence, completed-work proof, or team documentation — are confirmed compliant with this policy under their current usage. `LUXURY_DESIGN_DIRECTION.md` §10's prohibition remains in force for the categories listed above as "not allowed"; this decision narrows what "presented as real company evidence" means in practice (it does not repeal §10, it defines its boundary).

**Not authorized by this decision:** using any AI-generated image as a substitute for a real testimonial, a real before/after result, a real safety-certification photo, or any other claim requiring documentary proof.

---

## 2. Typography Decision

**Final standard:**

| Language | Font |
|---|---|
| Arabic | **Cairo** |
| English | **Inter** |

**Resolves:** The conflict identified in `DESIGN_SYSTEM_ASSET_ALIGNMENT_REPORT.md` §3.2 — `02_BRAND/TYPOGRAPHY.md` named Cairo for Arabic; `12_DESIGN_SYSTEM/TYPOGRAPHY.md` v2.0 named Noto Kufi Arabic for Arabic. **`02_BRAND/TYPOGRAPHY.md`'s Arabic font (Cairo) is adopted as canonical**, superseding `12_DESIGN_SYSTEM/TYPOGRAPHY.md` v2.0's Noto Kufi Arabic on this point. English (Inter) was already consistent between both documents and is unchanged.

**Not yet done:** `12_DESIGN_SYSTEM/TYPOGRAPHY.md` still names Noto Kufi Arabic and its CSS fallback stack still reflects that choice — this document records the decision; it does not itself edit that file's font-family declarations, per this task's "do not modify assets/code" instruction. That edit is separate, not-yet-executed follow-up work.

---

## 3. Icon System Decision

**Two icon systems are approved, each for a distinct purpose:**

| System | Location | Purpose |
|---|---|---|
| Brand Icons | `public/brand/icons/` | Service and marketing illustrations |
| UI Icons | Lucide (code library) | Interface controls only |

**Resolves:** The undocumented duality identified in `DESIGN_SYSTEM_ASSET_ALIGNMENT_REPORT.md` §1.1–§1.3 — `public/brand/icons/`'s detailed illustrated SVGs were never declared as an approved system anywhere, while `12_DESIGN_SYSTEM/ICONS.md` and `02_BRAND/ICONOGRAPHY.md` separately named Lucide as the icon library without acknowledging the brand icon set at all.

**Boundary established by this decision:** Brand Icons must not be used as interface controls (buttons, nav, form fields, action icons), and Lucide UI Icons must not be used as service/marketing illustrations. Each system's existing style rules remain as previously documented — Lucide stays line-icon/uniform-stroke per `12_DESIGN_SYSTEM/ICONS.md`; Brand Icons keep their existing illustrated style, not to be redrawn to match Lucide's spec.

**Not yet done:** Neither `12_DESIGN_SYSTEM/ICONS.md` nor `02_BRAND/ICONOGRAPHY.md` has been edited to reference `public/brand/icons/` as the approved Brand Icon source. That documentation update is separate, not-yet-executed follow-up work.

---

## 4. Image Usage Decision

**Decision:**
- The 9 current service images in `public/brand/images/services/` are **approved for service-card use**.
- They are **not approved for large hero sections** requiring higher resolution.
- **Future hero assets require a separate library** — not to be filled by upscaling, cropping, or repurposing the existing service-card images.

**Resolves:** `DESIGN_SYSTEM_ASSET_ALIGNMENT_REPORT.md` §2.2 — the 9 images (max 1536 px wide) fall short of `02_BRAND/BRAND_IMAGES.md`'s stated 1920×1080 minimum resolution, which more plausibly targets hero/full-bleed placements than card use. This decision resolves the ambiguity: card use is fine as-is; hero use is explicitly out of scope for these files.

**Not yet done:** No hero image library exists yet at `public/brand/images/hero/` (folder exists, empty, per `DESIGN_FREEZE_REPORT.md` §1.2). Producing that library is separate, not-yet-executed follow-up work, and remains subject to Decision 1 above (AI-generated visuals are allowed for marketing visuals, so a future AI-generated hero library is not excluded by that policy — only by this decision's resolution requirement).

---

## Summary of What Remains Open (Not Resolved by This Document)

1. `02_BRAND/BRAND_COLORS.md` vs `12_DESIGN_SYSTEM/COLORS.md` reconciliation — still open per Decision 35, unaffected by this document.
2. Editing `12_DESIGN_SYSTEM/TYPOGRAPHY.md` to replace Noto Kufi Arabic with Cairo, per Decision 2 above — not executed here.
3. Editing `12_DESIGN_SYSTEM/ICONS.md` / `02_BRAND/ICONOGRAPHY.md` to formally reference `public/brand/icons/`, per Decision 3 above — not executed here.
4. Producing the two missing pest-control service-card images (`service-pest-control.webp`, `service-cockroach-control.webp`) — still open, no image-generation tool available.
5. Producing a hero-image library, per Decision 4 above — not started.

---

## Related Documents

- `00_GOVERNANCE/DESIGN_SYSTEM_ASSET_ALIGNMENT_REPORT.md` — the review this document resolves.
- `00_GOVERNANCE/DESIGN_FREEZE_REPORT.md` — asset inventory baseline.
- `00_GOVERNANCE/DECISION_LOG.md` — Decision 35 (colors, still open), Decision 36 (photography direction; its AI-generated-media conflict is closed by §1 above).
- `00_GOVERNANCE/DESIGN_CHANGE_REQUEST.md` — required process for executing the "Not yet done" items listed above.

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-08-01 | Initial recording of four Owner decisions resolving `DESIGN_SYSTEM_ASSET_ALIGNMENT_REPORT.md`'s open items: AI-generated asset policy, Arabic typography (Cairo), two-system icon policy (Brand Icons vs Lucide UI Icons), and image usage scope (service cards only, hero deferred to a future library). No code, asset, or filename was changed. |
