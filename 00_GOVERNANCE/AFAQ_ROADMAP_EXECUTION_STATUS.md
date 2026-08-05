# AFAQ Alhayat Roadmap Execution Status

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — live execution log; updated as each phase progresses
- **Version:** 0.1
- **Prepared:** 2026-08-04

## Purpose

Tracks the 5-phase continuous-execution roadmap (Google Ecosystem → Search
Engine Ecosystem → SEO Production Audit → Google Business Profile Recovery
→ Production Readiness). Phase 1 (Google Ecosystem) is tracked in full
detail in `00_GOVERNANCE/GOOGLE_ECOSYSTEM_FINAL_STATUS.md` — this document
starts at Phase 2 and is the index for everything after it.

---

## Phase 1 — Google Ecosystem: CLOSED

See `GOOGLE_ECOSYSTEM_FINAL_STATUS.md` in full. Summary: Consent Mode v2
implemented and verified live; GTM/GA4 confirmed configured correctly in
production (indirect but solid evidence — see that document §6a);
sitemap/robots/canonical/hreflang all verified correct. Remaining:
`GOOGLE_SITE_VERIFICATION` (Owner), real browser Tag Assistant test after a
consent click (Owner or a future session with browser tooling).

---

## Phase 2 — Search Engine Ecosystem: DONE (code-complete)

**App commit `45a612d`.**

| Item | Status |
|---|---|
| Bing Webmaster Tools readiness | Code-ready — `BING_SITE_VERIFICATION` env var renders `msvalidate.01` meta tag once supplied, same pattern as Google. Unset today, nothing renders. |
| IndexNow readiness | **Complete, no Owner action needed.** A real, self-generated key is hosted at `public/{key}.txt` (`src/lib/seo/indexnow.ts` is the source of truth, tested against the actual file). Auto-submission on publish is a separate, later automation decision, not built. |
| Apple Safari compatibility | `viewport` export added with `themeColor: "#0f4c81"` (the existing approved brand navy, already used in `manifest.ts`) — verified rendering correctly in built HTML. `apple-icon.png`/manifest icons were already present. |
| Pinterest visibility | Domain verification code-ready (`PINTEREST_DOMAIN_VERIFICATION` → `p:domain_verify` meta), same pattern. Rich Pins need no extra code — they read the Open Graph tags already present. |
| Social sharing metadata / Open Graph | Already solid pre-existing implementation (real image, dimensions, alt text, sitewide fallback + per-page overrides) — audited, no gap found. |
| Twitter/X cards | Fixed a real gap found during verification: the homepage's own `generateMetadata` silently overrode the root layout's Twitter block, so the new `@afaqalhayat1` handle wasn't reaching it. Fixed in `page.tsx` too — verified both the homepage and a non-overriding page render it. |

**Owner action required:** obtain real verification codes from Bing Webmaster Tools and Pinterest Business (if domain verification there is wanted), set `BING_SITE_VERIFICATION` / `PINTEREST_DOMAIN_VERIFICATION` in production.

---

## Phase 3 — SEO Production Audit: IN PROGRESS

Most of this phase's scope was already covered by three documents produced
earlier this session — **not re-audited from scratch here, cross-referenced**:

| Item | Where it's covered |
|---|---|
| Technical SEO, sitemap, robots, canonical, hreflang | `10_MARKETING_AND_SEO/URL_AND_LINKING_AUDIT.md`, re-verified live in Phase 1/2 of this session |
| Metadata/titles/descriptions, FAQ coverage, CTA, image SEO | `10_MARKETING_AND_SEO/SEO_CONTENT_QUALITY_AUDIT.md` |
| Local SEO, service+location page structure | `10_MARKETING_AND_SEO/SEO_REALITY_MAP.md`, `LOCAL_SEO_MASTER_PLAN.md` |
| Schema markup | **New finding this session**: emirate hub pages (`locations/[slug]/page.tsx`) still emitted `LocalBusiness` schema — the same governance violation already fixed on the 57 service+city pages, just never checked here. **Fixed, tested, committed** (`c9b2ddf`) — removed outright rather than guessing at a replacement type. |
| Arabic/English SEO consistency | Verified structurally sound: every title/description/H1/meta-description/FAQ/city-content field in this codebase uses a paired `{ en, ar }` object — there is no code path that allows an English-only or Arabic-only value to ship for indexable content. Not a claim about translation *quality*, only that the bilingual-equality structure is enforced everywhere, consistently. |
| Service pages, location pages content depth | Already documented as an open item, not new: `SEO_CONTENT_QUALITY_AUDIT.md`'s FAQ/image gaps remain unaddressed (deliberately — real content, not a config fix). |

**Remaining for this phase**: writing real per-page FAQ content and adding
real per-service images (both explicitly deferred as content work, not
audit work, in the earlier report) is the actual remaining scope — not a
new audit, a content-production task.

---

## Phase 4 — Google Business Profile Recovery Preparation: PREPARED, OWNER ACTION REQUIRED

Full diagnosis already written: `GOOGLE_ECOSYSTEM_FINAL_STATUS.md` §5.
Summary — real risk factors identified from this project's own approved
data (not a guess at Google's actual stated reason, which requires Owner
access to see): UAE-wide service area claimed from a single Dubai address;
unconfirmed exact registered listing name; a shared business-center
address; unconfirmed branch/Place ID structure. Recovery checklist and
required-evidence list are both in that section. **No further preparation
is possible without the Owner reading Google's actual suspension notice.**

---

## Phase 5 — Production Readiness: IN PROGRESS

| Area | Status | Commit |
|---|---|---|
| Security | Baseline headers added (X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy); valibot advisory resolved via non-force `npm audit fix`. CSP deliberately deferred — needs a nonce-based design given how many inline scripts (schema JSON-LD, GTM, Consent Mode) already exist; a rushed CSP risks breaking them. | `7b4da1f` |
| Accessibility | Skip-to-content link added (WCAG 2.4.1), verified in both locales. | `5a969c4` |
| Error handling | Branded bilingual 404 pages for both real 404 scenarios (locale-resolved `notFound()` calls, and fully-unmatched paths) — previously fell through to Next's generic default. | `8cff848` |
| Performance | **Partial.** Bundle size checked (lean: 1.3MB static JS, largest chunk 224KB — no action needed). Fixed a real over-fetch bug: `next/image` `sizes` mismatched the actual 3-column grid on services/maintenance/cleaning listings and blog cards, causing oversized image downloads on every listing page (`6e30de1`). Fonts/scripts already optimal (self-hosted next/font, GTM deferred `afterInteractive`). Not done: Core Web Vitals need a real Lighthouse/PSI run against the live production URL (not available this session, no browser tooling connected) — flagged, not blocking. |
| Mobile experience | **Done.** Static audit against real device breakpoints/RTL/touch-target rules (no live browser tooling available this session, so screenshot-based visual QA is still outstanding — see below). Fixed 3 confirmed bugs: Footer's copyright/legal row had no bottom clearance from the fixed `MobileCtaBar` and was covered on scroll-to-bottom; the header's mobile hamburger button and the EN/AR language-switcher links had no explicit touch-target sizing (bare icon / bare text, inconsistent with the 40-48px controls used everywhere else); mobile nav-menu links lacked tap-area padding. Everything else audited (hero art direction, sidebar desktop-only gating, RTL logical properties, form control sizing, icon sizing) was already correct — no changes needed. Typecheck/lint/tests(component)/build all pass. `7d74bac`. |
| Logging | **Done.** `src/lib/logging/logger.ts` (structured JSON to console) wired into all 10 API routes' catch-all fallback — previously leaked raw internal error messages to the client with zero server-side trace; now logs server-side and returns a generic 500. `7417336`. |
| Monitoring | Not yet reviewed — no error-tracking/APM service configured (would be a new external service, likely Owner-gated). |

**Remaining gap**: mobile experience was audited statically, not against live iPhone Safari / Android Chrome screenshots (no browser tooling connected this session) — worth a real device/emulator pass when available.

**Next**: Performance is the highest-value remaining pure-code item — needs a real audit (bundle size, image loading, Core Web Vitals proxy checks) before any fix. Monitoring is likely Owner-gated (new external service).

---

---

## Production Completion Pass (2026-08-05)

Owner moved execution from audit mode to production-completion mode.
Scope: location pages, service pages, navigation, homepage sidebar.

| Item | Status |
|---|---|
| Emirate location pages (7) | **Done.** Added FAQ section (real, already-approved Q&A — emirate-specific where one exists, else 4 universal coverage FAQs), real per-emirate SEO title + meta description (was bare city name / on-page intro), brought Dubai's intro to the same named-community standard the other 6 already had. Verified in actual build output, not just a successful build. `bbe4ae8`. |
| Service pages (16 Owner-approved services) | **13/16 already had real photos + FAQs — no gap.** Found and closed 1 real gap: Handyman had approved content/SEO but no card image (silently excluded from the maintenance grid, illustration-only detail page) — a real, correctly-branded candidate photo existed unwired in the asset library; visually reviewed for the same defect class that correctly rejected Waterproofing's candidate (typo baked into the image), found clean, wired it in. `6443390`. Waterproofing's rejection stands untouched — real defect, not re-attempted. 11 newer services (CCTV, smart home, swimming pool, kitchen, interior decoration, interlock, lighting, wood-alternative, wallpaper, thermal insulation, rooftop) are explicitly Draft / not Owner-approved / not wired into SERVICE_DATABASE.json per their own foundation docs — correctly left untouched, not a code gap. |
| Navigation | Structural review only — no browser tooling connected this session, so this is not a real visual QA pass. 7 top-level items (Home/Services/Locations/About/Contact/Blog/FAQ), consistent responsive desktop/mobile split, active-state handling all present and unchanged since the Mobile UX pass fixed its touch-target issues. No structural problem found worth changing blind. |
| Homepage sidebar (`home-sidebar.tsx`) | **Recommend: keep, not confirmed to need redesign or removal.** Well-engineered (desktop-only, no mobile conflict, defensive `max-h`/`overflow-y-auto` sizing, real approved content only) — confirmed during the Mobile UX pass. One real design observation: the header is `sticky top-0`, so its own phone/WhatsApp/Request-Service CTAs are already persistently visible while scrolling — the sidebar's CTA block is therefore somewhat redundant with an already-persistent surface, not filling a gap the header leaves open. No conversion data available this session (no analytics access) to say whether it helps or hurts — Owner requested it explicitly one day before this pass (`136be77`, 2026-08-04). Not removed or redesigned without evidence; flagging for a data-driven call once real analytics on it exist, per the decision boundary this repo already draws around unverified claims. |

## Related Documents

- `00_GOVERNANCE/GOOGLE_ECOSYSTEM_FINAL_STATUS.md`
- `10_MARKETING_AND_SEO/URL_AND_LINKING_AUDIT.md`
- `10_MARKETING_AND_SEO/SEO_CONTENT_QUALITY_AUDIT.md`
- `10_MARKETING_AND_SEO/SEO_REALITY_MAP.md`
- `10_MARKETING_AND_SEO/LOCAL_SEO_MASTER_PLAN.md`
