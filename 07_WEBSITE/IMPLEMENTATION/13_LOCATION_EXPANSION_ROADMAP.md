# Emirates/Location Expansion Roadmap

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — planning only. No page, content, or image is created by this document.
- **Version:** 1.0
- **Prepared:** 2026-07-28
- **Scope:** All seven UAE emirates, per the Approved Registry in `03_MARKET/SERVICE_AREAS.md`.
- **Depends on:** `03_MARKET/SERVICE_AREAS.md`, `02_BRAND/LOCAL_SEO_PROFILE.md`, `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`, `07_WEBSITE/IMPLEMENTATION/07_EXISTING_APP_INTEGRATION_AUDIT.md`.

## Note on scope

All seven emirates are already `Active` with "All catalog services" coverage in `SERVICE_AREAS.md`'s Approved Registry — this document does not seek new coverage approval, it plans how the six not-yet-built emirate pages catch up to Dubai, the only one currently live in the app (per the existing audit: `src/lib/catalog/locations.ts` contains only `LOC-AE-DU`).

---

## 0. Current App State (verified, not assumed)

- Dubai (`LOC-AE-DU`) is the only emirate with a generated location page today.
- Abu Dhabi, Sharjah, Ajman, Umm Al Quwain, Ras Al Khaimah, and Fujairah are approved in the registry but have no page yet — adding each is, per the app's own code comment, "a one-line addition, no route changes required" (the dynamic `[slug]` route already exists).
- Community-level (Tier 1) pages, e.g. Palm Jumeirah, are a separate, later tier requiring their own SEO/ops quality checklist per `SERVICE_AREAS.md` — out of scope for this emirate-level roadmap.

---

## 1. Per-Emirate Roadmap

| Emirate | Area ID | Service pages needed | Local SEO requirements | Image requirements |
|---|---|---|---|---|
| Dubai | `LOC-AE-DU` | Already live — this is the reference implementation for the other six | Already implemented: hreflang, canonical, sitemap inclusion | Currently illustration-only (no real photography yet, per `12_SERVICE_EXPANSION_ROADMAP.md`'s sequencing) |
| Abu Dhabi | `LOC-AE-AZ` | Add to `locations.ts`; page auto-generates per existing route | Unique, non-duplicated content per `LUXURY_DESIGN_DIRECTION.md` §6 ("must not be mass-produced copies with only the place name changed") — genuine local context required, not a Dubai copy with the name swapped | Generic, Abu-Dhabi-appropriate service-context imagery only; no branch/office implication (§8 of `11_VISUAL_ASSET_STRATEGY.md`) |
| Sharjah | `LOC-AE-SH` | Same as above | Same uniqueness requirement | Same constraint |
| Ajman | `LOC-AE-AJ` | Same as above | Same uniqueness requirement | Same constraint |
| Umm Al Quwain | `LOC-AE-UQ` | Same as above | Same uniqueness requirement | Same constraint |
| Ras Al Khaimah | `LOC-AE-RK` | Same as above | Same uniqueness requirement | Same constraint |
| Fujairah | `LOC-AE-FU` | Same as above | Same uniqueness requirement | Same constraint |

## 2. What "Genuine Local Context" Means Here (not invented per-emirate, sourced honestly)

Per `LUXURY_DESIGN_DIRECTION.md` §6's explicit ban on mass-produced location copies, each emirate page needs at least one of:

- Emirate-specific service relevance (e.g., coastal humidity affecting AC/pest patterns in Fujairah vs. a different consideration inland) — **only if this is an actual, verifiable operational fact**, never invented to sound locally specific.
- Locally relevant FAQ content (genuinely different questions a Sharjah customer might ask vs. an Abu Dhabi one), not a copy-pasted FAQ block with the emirate name swapped.
- Real internal links to that emirate's available services via `SERVICE_MATRIX.md` — generated from the matrix, not hand-authored per page, per `04_CONTENT_INTEGRATION_PLAN.md` §5's existing rule.

If no genuinely unique content exists for a given emirate beyond swapping the name, `LUXURY_DESIGN_DIRECTION.md` §6 says that page should **not** be published yet rather than shipped as a thin duplicate — a real content gate, not just a technical one.

## 3. Local SEO Requirements Common to All Six New Pages

- `hreflang`/canonical generation via the existing `buildAlternates` utility — no manual per-page markup.
- Coverage claims strictly at emirate level, per `SERVICE_AREAS.md`'s Publication Rules — no city/district/community claim bundled in until that area separately clears its own registry review.
- NAP consistency via the same `CONTACT_INFORMATION.md`-sourced adapter already used elsewhere — no per-emirate contact variation invented.
- Schema (`Service`/breadcrumb) generated from the same content adapter that renders the visible page, per the existing anti-drift rule in `05_SEO_IMPLEMENTATION_PLAN.md` §2.

## 4. Image Requirements Common to All Six New Pages

Per `11_VISUAL_ASSET_STRATEGY.md` §8: generic, emirate-appropriate service-context imagery, never implying a branch, office, or specific address. Until real photography exists for a given emirate, the existing illustration (`BrandPanel`) placeholder is the correct interim state — not a fabricated "local" stock photo standing in for one.

---

## 5. Sequencing Recommendation (not an authorization to proceed)

1. Add the six missing emirates to `locations.ts` as a technical/content task once each has at least the minimum genuine local content described in §2 — this can happen ahead of new imagery, since the current Dubai page also ships illustration-only today.
2. Prioritize emirates by whichever the Owner has actual operational insight to make genuinely locally relevant (§2), not by a fixed population/size ranking not verified here.
3. Layer in real photography per `11_VISUAL_ASSET_STRATEGY.md`/`12_SERVICE_EXPANSION_ROADMAP.md`'s sequencing once it exists — emirate pages and service pages share the same underlying image assets, they don't need a separate photography pass.

---

## What This Document Does Not Do

- Does not add any emirate to `locations.ts` or generate any page.
- Does not approve any specific local-content claim — §2's examples are illustrative of the *kind* of fact needed, not pre-approved content.
- Does not commission or approve any image.
- Does not open the Tier 1 community-page question — that remains its own, separately gated tier.

---

## Related Documents

- `03_MARKET/SERVICE_AREAS.md`
- `02_BRAND/LOCAL_SEO_PROFILE.md`
- `07_WEBSITE/IMPLEMENTATION/11_VISUAL_ASSET_STRATEGY.md`
- `07_WEBSITE/IMPLEMENTATION/12_SERVICE_EXPANSION_ROADMAP.md`
