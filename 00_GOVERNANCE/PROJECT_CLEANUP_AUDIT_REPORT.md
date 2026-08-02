# Project Cleanup Audit Report

## Document Information

- **Owner:** Business Owner
- **Status:** Draft — audit only. **No file was deleted, moved, renamed, or modified by this report, and no commit was made in either repository.** This document itself is the only file written.
- **Version:** 1.0
- **Prepared:** 2026-08-01
- **Package:** `00_GOVERNANCE/`
- **Scope reviewed (read-only):**
  1. `/Users/ashrafeladrousi/Documents/AFAQ_ALHAYAT_ENTERPRISE_KNOWLEDGE` (this repo — governance/knowledge-base, git repo)
  2. `/Users/ashrafeladrousi/Documents/GitHub/afaqalhayatae-app` (the Next.js app repo, separate git repo)

## Method

`git status` was run in both repositories first. Both currently carry large uncommitted change sets — this is normal, active, ticket-based work-in-progress (WIP) as of 2026-08-01, **not** abandoned or unused content, and it is treated that way throughout this report. Duplicate detection used SHA-1 content hashing (`shasum`) file-by-file, not filename matching. Large-file and empty-folder detection used `find`. Code-reference checks used `grep` across `src/` for the app repo. Two known, intentional, temporary states were excluded from "unused/cruft" judgement per Owner instruction: `src/lib/catalog/blog.ts` and `src/lib/media/demo-visuals.ts` (both flagged `isDemo: true` / `SHOW_DEMO_VISUALS` — temporary demo/placeholder data pending real approved content).

---

## Executive Summary

- **No cross-repo duplicate assets** were found between the two repositories (hash comparison of every file under both `public/` trees returned zero matches).
- **The knowledge-base repo (`AFAQ_ALHAYAT_ENTERPRISE_KNOWLEDGE`) has no byte-identical duplicate files anywhere** (checked `public/`, all 12 `04_SERVICE_KNOWLEDGE/*/assets/` folders, and the whole repo tree) and no files over 5 MB.
- **The app repo has a confirmed, code-verified set of 45 byte-identical duplicate image pairs (~71 MB) inside `public/brand/images/`.** Every duplicate pair is a file that exists both at a flat/legacy path and at the nested `services/{category}/…` path that the current rendering code (`src/lib/catalog/service-content.ts`) actually reads. This is evidence of an in-progress asset-path restructuring, not random clutter — flagged for Owner review, not for blind deletion, since the untracked copies are current WIP.
- **`04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/` is mid-restructuring**: new numbered files (`01_SERVICE_PROFILE.md` … `06_PAGE_CONTENT.md`) explicitly state they are synthesized *from* the folder's existing legacy files (`CONTENT_EN.md`, `FAQ.md`, `SEO_AI.md`, etc.), which remain in place as their cited sources. Only 1 of 12 services has this new numbered set; the other 11 only gained `IMAGE_GENERATION_BRIEF.md` / `IMAGE_SEO_LIBRARY.md` so far.
- **The `00_START/` tree in the knowledge base is empty, legacy scaffolding, and is already documented** in `00_GOVERNANCE/MIGRATION/MIGRATION_PLAN.md` as "confirmed to hold no expected content; preserved in the migration record, nothing deleted." It must **not** be treated as new cruft — it is intentionally preserved migration history.
- **No genuinely orphaned test files** were confirmed in the app repo. Two files that looked orphaned by naming convention (`page-with-posts.test.tsx` in `blog/` and `blog/[slug]/`) both import and exercise the real `./page.tsx` — they are legitimately named scenario-suffixed test suites, not orphans.
- **node_modules (811 MB) and .next (397 MB)** account for almost all of the app repo's 1.4 GB footprint and are both correctly gitignored, regenerable build/dependency artifacts. Not a cleanup action.
- **Genuine, unambiguous cruft found:** 12 `.DS_Store` files (both repos combined), 1 `install-debug.log` (KB repo root, already gitignored), 1 empty non-legacy folder (`public/brand/images/brand/` in the app repo).

### Counts at a glance

| Category | KB repo | App repo |
|---|---|---|
| Byte-identical duplicate pairs | 0 | 45 (~71 MB) |
| Files > 5 MB | 0 | 18 (all in `node_modules`/`.next`) |
| Files > 10 MB | 0 | 11 (all in `node_modules`/`.next`) |
| Files > 50 MB | 0 | 3 (all in `node_modules`/`.next`) |
| Empty folders | 41 | 1 |
| `.DS_Store` / stray OS files | 8 | 4 |
| Confirmed orphaned code/test files | n/a | 0 |

---

## 1. Duplicate Files

### 1.1 App repo — confirmed byte-identical duplicates (HIGH factual confidence)

All 45 pairs below were confirmed identical via SHA-1. Each pair is one file that lives at a **flat/legacy path** and one that lives at the **nested `services/{category}/` path**. `grep` of `src/` confirms only the nested path is built by the image-resolution code:

```
src/lib/catalog/service-content.ts:116:  src: `/brand/images/services/pest-control/${hero.fileName}`
src/lib/catalog/service-content.ts:182:  src: `/brand/images/services/${card.folder}/${card.fileName}`
```

`card.folder` is populated from `src/data/SERVICE_DATABASE.json` as `"maintenance"`, `"cleaning"`, or `"pest-control"` — i.e. the code only ever resolves to `services/maintenance/…`, `services/cleaning/…`, `services/pest-control/…`. No string in `src/` builds a path to the flat `services/*.webp` files or to the top-level `public/brand/images/pest-control/` folder.

| Duplicate group | Files | Reason flagged | Size | Risk |
|---|---|---|---|---|
| Pest-control top-level vs. nested | `public/brand/images/pest-control/*.webp` (12 files: `001…010`-prefixed cards, `HERO_PEST_CONTROL_21x9.webp`, `pest-control-hero-banner-afaq-branded-21x9-v2.webp`) **↔** the same 12 filenames under `public/brand/images/services/pest-control/` | Byte-identical (SHA-1 match); only the nested path is referenced in code | ~25 MB (top-level copy) | MEDIUM |
| Maintenance flat vs. nested | 33 files such as `services/ac-maintenance-service-card-afaq-v1.webp`, `services/plumbing-repair-service-card-afaq-v1.webp`, `services/landscape-garden-design-maintenance-service-card-afaq-v2.webp`, etc. **↔** the same 33 filenames under `services/maintenance/` | Byte-identical (SHA-1 match); only the nested `services/maintenance/` path is referenced in code | ~46 MB (flat copy) | MEDIUM |

Full duplicate-pair list (hash, both paths) was generated during this audit and is available on request; it is omitted here for length but every filename is one of the 45 pairs described above (10 numbered pest-control cards + hero + hero-banner-v2, plus the 33 maintenance service-card files listed in the app repo's own `public/brand/images/services/` and `services/maintenance/` folders).

**Why MEDIUM, not LOW/safe-to-delete:** these flat-path files are currently **untracked (new) in `git status`**, i.e. active WIP per the Owner's own instructions — they may be the deliberate "old" side of an in-progress folder migration the Owner hasn't finished or approved yet. Do not delete without Owner confirmation that the nested `services/{category}/` path is the final, sole convention going forward.

### 1.2 Knowledge-base repo — no byte-identical duplicates

- `public/brand/icons/` (172 SVGs) and `public/brand/images/` (11 files): zero duplicate hashes.
- All 12 `04_SERVICE_KNOWLEDGE/*/assets/` folders: zero duplicate hashes. Only `01_PEST_CONTROL/assets/` currently has real files (2 in `hero/`, 2 in `service-cards/`); every other service's `assets/` subfolder tree is empty (confirmed independently by this audit and by the KB's own `SERVICE_MASTER_DATABASE.md`, which states the same finding).
- `cockroach-control-service-card-v1.webp` vs. `-v2.webp` and `pest-control-hero-v1.png` vs. `pest-control-homepage-hero-v1.webp` are **not duplicates** — different hashes, genuinely different images. `CHANGELOG.md` (entries 1.11/1.12) documents that v1 was flagged for unapproved content claims ("CERTIFIED SOLUTIONS", mismatched support-hours badges) and v2 is the Owner-supplied "approved revision" with an assigned Asset ID (`PC-SVC-COCKROACH-01`) — but v2 itself still has open QA flags per that changelog entry. Both files are part of the documented evidence trail; neither should be deleted without an explicit Owner/CHANGELOG decision.

| File | Reason flagged | Size | Risk |
|---|---|---|---|
| `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/assets/service-cards/cockroach-control-service-card-v1.webp` | Superseded-looking name, but content differs from v2 and is cited in CHANGELOG as evidence of a rejected claim set — not a safe delete | 1.9 MB | MEDIUM |
| `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/assets/service-cards/cockroach-control-service-card-v2.webp` | "Approved revision" per CHANGELOG 1.12, but still has open QA flags (family-safety claim, "eco-friendly" claim, possible warranty-language wording) — not fully cleared | 1.2 MB | MEDIUM |
| `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/assets/hero/pest-control-hero-v1.png` | Different image purpose/format than the webp hero (has embedded Arabic text, badges, phone number baked in per CHANGELOG 1.9) — not a duplicate of the webp hero, but overlapping purpose | 2.1 MB | MEDIUM |
| `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/assets/hero/pest-control-homepage-hero-v1.webp` | Matches `PC-HERO-01` spec per CHANGELOG 1.10 but flagged with an AI text-fidelity artifact ("CLEANLIIESS") needing QA before approval | 1.5 MB | MEDIUM |

### 1.3 Knowledge-base repo — documentation restructuring in `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/`

Only `01_PEST_CONTROL/` (of the 12 service folders) currently has **both** an older flat document set and a newer numbered document set covering overlapping topics. Content was read and compared directly:

| Old file (existing, git-tracked, currently modified) | New file (untracked) | Overlap found |
|---|---|---|
| `CONTENT_EN.md`, `CONTENT_AR.md` | `01_SERVICE_PROFILE.md` | `01_SERVICE_PROFILE.md`'s own header states it is "sourced entirely from … `BUSINESS.md`, `CONTENT_EN.md`, `CONTENT_AR.md`, `SEO_AI.md`, `SERVICE_CATALOG.md`" — confirmed by reading both: title, description, and service list in `01_SERVICE_PROFILE.md` are the same facts as `CONTENT_EN.md`/`CONTENT_AR.md`, reformatted with per-fact source citations. |
| `SEO_AI.md` | `02_SEO_DATA.md` | Same SEO-facts domain; not diffed line-by-line but both exist and cover SEO metadata for the same service. |
| — | `03_BOOKING_OPTIONS.md` | New content, no legacy equivalent found. |
| `FAQ.md`, `FAQ_AR.md` | `04_FAQ.md` | `04_FAQ.md`'s header states questions 1–8 are "carried forward unchanged from" `FAQ.md`/`FAQ_AR.md`, reformatted for snippet-friendliness; questions 9–10 are new. Read comparison of Q1–Q3 in both files confirms same facts, same safety caveats, same wording pattern. |
| — | `05_IMAGE_METADATA.md` | New content, indexes the real asset files in `assets/`. |
| — (no single prior page-content file) | `06_PAGE_CONTENT.md` | New consolidated content, drawing on the above. |

**This is a documented, explicit, in-progress consolidation** — the new files cite the old files as their sources rather than duplicating facts independently, and neither the CHANGELOG nor README currently states the old files are deprecated or safe to remove. **Flagged for Owner review**: once the numbered set is reviewed/approved, the Owner may want to formally deprecate/archive the old flat files (`CONTENT_EN.md`, `CONTENT_AR.md`, `FAQ.md`, `FAQ_AR.md`, `SEO_AI.md`, `README.md`, `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `TRAINING.md`, `CUSTOMER_GUIDE.md`, `MEDIA.md`) into `98_LEGACY_ARCHIVE/`, per this repo's own non-duplication rule (`SYSTEM_ARCHITECTURE.md` §7). No such decision is recorded yet, so this report does **not** recommend deletion or archival — only flags it for the Owner's call. Risk: **MEDIUM** (both sides are currently referenced/active; nothing here is orphaned, but the eventual overlap needs a resolution decision).

Other 11 service folders (`02_AC_MAINTENANCE` … `12_WATER_LEAK_DETECTION`) only gained `IMAGE_GENERATION_BRIEF.md` and `IMAGE_SEO_LIBRARY.md` (untracked) — they have **not** started the same numbered-file restructuring yet, so no equivalent overlap exists there today. Noted for awareness only.

### 1.4 Knowledge-base repo — `CONTENT_EN.html` (untracked, new)

`04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/CONTENT_EN.html` (5.3 KB) is a VS Code Markdown-preview HTML export of `CONTENT_EN.md` (confirmed by its embedded `<!-- From extension vscode.github -->` CSS and `.vscode-dark`/`.vscode-light` classes at the top of the file — a tool-generated artifact, not hand-authored content). However, `CHANGELOG.md` entry 1.11 references it as an active source ("`CONTENT_EN.html`'s own draft still lists competency evidence … as unconfirmed"), so it is currently being treated as live reference material, not disposable.

| File | Reason flagged | Size | Risk |
|---|---|---|---|
| `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/CONTENT_EN.html` | Tool-generated (VS Code export) near-duplicate of `CONTENT_EN.md` in a different format; but actively cited in CHANGELOG.md as reference content | 5.3 KB | MEDIUM |

---

## 2. Unused Files

### 2.1 App repo — no confirmed orphaned code or test files

- Searched for `.test.ts(x)` files with no matching source file. Two candidates surfaced by naming convention alone: `src/app/[locale]/blog/page-with-posts.test.tsx` and `src/app/[locale]/blog/[slug]/page-with-posts.test.tsx`. Both were opened and both **do** import and exercise the real, current page component (`import BlogPage from "./page"` / `import BlogArticlePage from "./page"`). They are legitimately named scenario-suffixed test suites (testing the "with posts" rendering path), not orphans. No further orphaned test files were found.
- The 45 duplicate image files from §1.1 are the only "possibly unused" files confirmed by code-reference grep — see §1.1 for detail and risk rationale. They are not listed again here to avoid double-counting.

### 2.2 Knowledge-base repo — empty asset-placeholder folders (confirmed intentional)

`04_SERVICE_KNOWLEDGE/{02_AC_MAINTENANCE … 12_WATER_LEAK_DETECTION}/assets/{hero,blog,trust,process,service-cards}/` (50 empty folders total across 10 services — `03_GENERAL_CLEANING`, `05_WATER_TANK_CLEANING`, `06_PLUMBING`, `07_ELECTRICAL_MAINTENANCE`, `09_HANDYMAN`, `02_AC_MAINTENANCE`, `04_DEEP_CLEANING`, `08_PAINTING`, `10_DRAIN_UNBLOCKING`, `11_WATERPROOFING`, `12_WATER_LEAK_DETECTION`) are empty by design — `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md` itself states: "A scan of every `assets/` subfolder … found real image files in exactly one place … Every other service's `assets/` subfolder structure exists but is empty." **Not cruft — confirmed intentional scaffolding, awaiting future asset delivery.** Risk: **LOW**, and the recommendation is to keep, not delete (listed in §5 and in Must-Keep list C, not Safe-to-delete list A).

### 2.3 Knowledge-base repo — `00_START/` legacy migration residue (confirmed documented, not new cruft)

The entire `00_START/` tree (see full list in §5) contains no files except stray `.DS_Store`s. This is **not** new/unnoticed cruft: `00_GOVERNANCE/MIGRATION/MIGRATION_PLAN.md` line 23 states "Empty directories `00_START/01_BRAND` and `00_START/02_MARKET` confirmed to hold no expected content; preserved in the migration record, nothing deleted." The deeper empty paths (`00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES`, `.../05_WORDPRESS`, `.../06_DESIGN_SYSTEM/07_WEBSITE`, `00_START/TEMP/01_BRAND/02_MARKET`) correspond one-for-one to source paths catalogued in `00_GOVERNANCE/MIGRATION/CURRENT_STATE_INVENTORY.md` and resolved in `00_GOVERNANCE/MIGRATION/DUPLICATE_AND_CONFLICT_REPORT.md` (decisions CNF-01 through CNF-08) — every real file that used to live in this tree was migrated to its current canonical top-level location or to `98_LEGACY_ARCHIVE/`, leaving these empty shells behind as an intentional audit trail. **Recommendation: keep, do not delete** — this is documented project history, not unused clutter. See §5 and list C.

### 2.4 No abandoned drafts found with independent evidence

No file was found that is referenced nowhere, clearly superseded by name, and outside current git-status WIP, beyond the items already discussed in §1 and §2.2–2.3 (all of which have their own specific evidence and caveats above). Per the audit brief, nothing else is asserted as "abandoned" without such evidence.

---

## 3. Large Files

All large files found are inside gitignored build/dependency folders (`node_modules/`, `.next/`) in the app repo. **Zero files over 5 MB exist anywhere in the knowledge-base repo.**

### 3.1 Files > 5 MB (app repo only)

| File | Size | Context | Risk |
|---|---|---|---|
| `node_modules/lightningcss-darwin-arm64/lightningcss.darwin-arm64.node` | 8.1 MB | npm dependency binary | LOW |
| `node_modules/@rolldown/binding-darwin-arm64/rolldown-binding.darwin-arm64.node` | 16 MB | npm dependency binary | LOW |
| `node_modules/typescript/lib/_tsc.js` | 5.9 MB | npm dependency | LOW |
| `node_modules/typescript/lib/typescript.js` | 8.7 MB | npm dependency | LOW |
| `node_modules/@prisma/engines/schema-engine-darwin-arm64` | 23 MB | Prisma engine binary | LOW |
| `node_modules/prisma/build/schema_engine_bg.wasm` | 5.4 MB | Prisma engine wasm | LOW |
| `node_modules/@next/swc-darwin-arm64/next-swc.darwin-arm64.node` | 116 MB | Next.js compiler binary | LOW |
| `node_modules/@img/sharp-libvips-darwin-arm64/lib/libvips-cpp.8.17.3.dylib` | 15 MB | image-processing dependency binary | LOW |
| `node_modules/@electric-sql/pglite/dist/pglite.data` | 5.0 MB | Postgres-in-WASM dev dependency data | LOW |
| `node_modules/@electric-sql/pglite/dist/pglite.wasm` | 8.3 MB | Postgres-in-WASM dev dependency | LOW |
| `node_modules/@prisma/dev/dist/runtime-assets/pglite.data` | 5.0 MB | Prisma dev-runtime data | LOW |
| `node_modules/@prisma/dev/dist/runtime-assets/pglite.wasm` | 8.3 MB | Prisma dev-runtime | LOW |
| `node_modules/@prisma/studio-core/dist/ui/index.js` | 14 MB | Prisma Studio UI bundle | LOW |
| `node_modules/@prisma/studio-core/dist/ui/index.cjs` | 14 MB | Prisma Studio UI bundle | LOW |
| `.next/dev/cache/turbopack/v16.2.12/00000123.sst` | 7.9 MB | Turbopack dev cache | LOW |
| `.next/dev/cache/turbopack/v16.2.12/00000013.sst` | 5.0 MB | Turbopack dev cache | LOW |
| `.next/dev/cache/turbopack/v16.2.12/00000122.sst` | 10 MB | Turbopack dev cache | LOW |
| `.next/dev/cache/turbopack/v16.2.12/00000126.sst` | 13 MB | Turbopack dev cache | LOW |

### 3.2 Files > 10 MB (subset of above)

`@rolldown/binding-darwin-arm64` (16 MB), `@prisma/engines/schema-engine-darwin-arm64` (23 MB), `@img/sharp-libvips-darwin-arm64` (15 MB), `@prisma/studio-core/dist/ui/index.js` (14 MB), `@prisma/studio-core/dist/ui/index.cjs` (14 MB), `.next/dev/cache/turbopack/.../00000124.sst` (13 MB), `.next/dev/cache/turbopack/.../00000122.sst` (10 MB), `.next/dev/cache/turbopack/.../00000126.sst` (13 MB), `.next/dev/cache/turbopack/.../00000119.sst` (58 MB), `.next/dev/cache/turbopack/.../00000118.sst` (133 MB), `@next/swc-darwin-arm64/next-swc.darwin-arm64.node` (116 MB). All LOW risk — regenerable dependency/cache artifacts.

### 3.3 Files > 50 MB

| File | Size | Context | Risk |
|---|---|---|---|
| `node_modules/@next/swc-darwin-arm64/next-swc.darwin-arm64.node` | 116 MB | Next.js/SWC compiler native binary — reinstalled by `npm install` | LOW |
| `.next/dev/cache/turbopack/v16.2.12/00000119.sst` | 58 MB | Turbopack dev build cache | LOW |
| `.next/dev/cache/turbopack/v16.2.12/00000118.sst` | 133 MB | Turbopack dev build cache | LOW |

None of these should be deleted as a "fix" — they regenerate automatically (`npm install`, `next dev`/`next build`). If local disk space is a concern, `.next/` can be cleared safely since it's a build cache (Owner can run the project's normal clean command), but this is a housekeeping convenience, not a repository cleanliness issue.

---

## 4. Build/Cache/Generated Files

| Item | Location | Size | Gitignored? | Note | Risk |
|---|---|---|---|---|---|
| `node_modules/` | app repo root | 811 MB | Yes (`/node_modules` in `.gitignore`) | Regenerable dependency tree. Do not delete as a "cleanup" action — normal, expected, required to run the app. | LOW |
| `.next/` | app repo root | 397 MB | Yes (`/.next/` in `.gitignore`) | Regenerable Next.js build/dev cache, including the large Turbopack `.sst` cache files in §3. | LOW |
| `tsconfig.tsbuildinfo` | app repo root | 174 KB | Yes (`*.tsbuildinfo` in `.gitignore`) | TypeScript incremental-build cache. Regenerable. | LOW |
| `.next/build` | inside `.next/` | n/a | Yes (parent is ignored) | Internal Next.js build subfolder, not a separate top-level cache folder. | LOW |

No `.turbo/`, `dist/`, `build/`, `coverage/`, or `.vercel/` top-level folders were found in either repo. The knowledge-base repo has no `package.json`/build tooling at all (by design — it is a pure Markdown knowledge base per its own `CLAUDE.md`), so it has zero build/cache artifacts.

Both `.gitignore` files were read directly and confirmed to cover the items above (app repo's `.gitignore` lists `/node_modules`, `/.next/`, `*.tsbuildinfo`, `.DS_Store`, `.vercel`, `/out/`, `/build`, `/coverage`, `/src/generated/prisma`; KB repo's `.gitignore` is a conservative OS/editor-only baseline covering `.DS_Store`, `*.swp`/`*.swo`, `install-debug.log`, `.vscode/`, `.idea/`).

---

## 5. Empty Folders

### 5.1 App repo (1 found)

| Folder | Reason flagged | Git-tracked? | Risk |
|---|---|---|---|
| `public/brand/images/brand/` | Empty, no files, not referenced by any exact matching path found in `src/` (a test fixture in `brand-panel.test.tsx` references the differently-shaped string `/images/brand/services/...`, which is an arbitrary prop value in a test, not a real asset path — noted in §6.3, not treated as a reference to this folder) | No (empty dirs aren't tracked by git) | LOW |

### 5.2 Knowledge-base repo (41 found)

**Group A — intentional per-service asset placeholders (confirmed by `SERVICE_MASTER_DATABASE.md`, 50-ish subfolders across 10 services, not cruft — see §2.2):**
`04_SERVICE_KNOWLEDGE/{02_AC_MAINTENANCE,03_GENERAL_CLEANING,04_DEEP_CLEANING,05_WATER_TANK_CLEANING,06_PLUMBING,07_ELECTRICAL_MAINTENANCE,08_PAINTING,09_HANDYMAN,10_DRAIN_UNBLOCKING,11_WATERPROOFING,12_WATER_LEAK_DETECTION}/assets/{hero,blog,trust,process,service-cards}/` (each service is missing 4–5 of these subfolders, all empty) — Risk **LOW**, recommendation: **keep**.

**Group B — documented legacy migration residue (confirmed by `00_GOVERNANCE/MIGRATION/*` — see §2.3, not cruft):**
`00_START/01_BRAND/`, `00_START/02_MARKET/`, `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/04_SERVICES/`, `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/05_WORDPRESS/`, `00_START/01_BUSINESS/02_BRAND/06_DESIGN_SYSTEM/07_WEBSITE/`, `00_START/TEMP/01_BRAND/02_MARKET/` — Risk **LOW**, recommendation: **keep as historical record**, per explicit migration-plan text quoted in §2.3.

**Group C — unexplained empty folders, no documentation found referencing them as intentional (flagged for Owner review):**

| Folder | Reason flagged | Risk |
|---|---|---|
| `07_WEBSITE/01_HOMEPAGE/99_STANDARDS/` | Empty; sits alongside 5 real numbered homepage docs (`00_HOMEPAGE_ARCHITECTURE.md` … `04_HOMEPAGE_COMPONENTS.md`); no doc explains its intended future content | MEDIUM |
| `07_WEBSITE/03_SERVICES/03_SERVICE_KNOWLEDGE/01_PEST_CONTROL/` | Empty; the `03_SERVICE_KNOWLEDGE` name duplicates the top-level `04_SERVICE_KNOWLEDGE/` folder's purpose/name; this exact nested path is referenced in `SYSTEM_ARCHITECTURE.md`, `99_STANDARDS/NAMING_CONVENTIONS.md`, and the same `00_GOVERNANCE/MIGRATION/` inventory/conflict reports discussed in §2.3 — likely the same migration-era residue, but not explicitly named as "preserved, do not delete" the way `00_START` is | MEDIUM |
| `10_MARKETING_AND_SEO/CAMPAIGNS/` | Empty; sits alongside real content files/folders in `10_MARKETING_AND_SEO/` (e.g. `SOCIAL_MEDIA/` has 12 real files) — plausibly an intentional placeholder for future campaign docs, but nothing states that | LOW |
| `public/brand/images/{master-library,projects,about,team,locations,hero,equipment}/` (7 folders) | Empty subfolders under the KB's own `public/brand/images/` — the icons tree has a populated `master-library/` (137 files) but the images tree's `master-library/` and the other 6 named folders are empty | LOW |
| `public/brand/icons/{features,locations,header,services}/` (4 folders) | Empty subfolders under `public/brand/icons/`, alongside populated `cleaning/`, `maintenance/`, `pest-control/`, `master-library/` folders | LOW |

None of Group C is recommended for deletion in this report — they read as plausible placeholders for a still-growing asset library, consistent with the pattern already confirmed intentional in Group A, but no document explicitly says so for these specific folders the way `SERVICE_MASTER_DATABASE.md` does for Group A. **Flagged for Owner confirmation only.**

---

## 6. Organization Issues

### 6.1 App repo — dual image-path convention (see §1.1 for full detail)

`public/brand/images/` currently has two parallel conventions for the same service-card and pest-control images: a flat/top-level path and a nested `services/{category}/` path. Only the nested path is read by the current rendering code. This is the same finding as §1.1, restated here as an organization issue rather than a duplicate-file issue: whichever convention is not chosen as final should eventually be removed, but that is an Owner decision, not something this audit resolves.

### 6.2 Knowledge-base repo — inconsistent restructuring progress across services (see §1.3)

Only `01_PEST_CONTROL/` has the new 6-file numbered restructuring; the other 11 services only received 2 new files each (`IMAGE_GENERATION_BRIEF.md`, `IMAGE_SEO_LIBRARY.md`). This is not wrong, just uneven — worth Owner visibility so the eventual rollout plan for the other 11 services is deliberate rather than accidental drift.

### 6.3 App repo — minor path-string inconsistency in a test fixture (LOW significance)

`src/components/brand-panel.test.tsx` passes `src="/images/brand/services/pest-control-afaq-alhayat-dubai.jpg"` as an arbitrary prop value to a rendered component. This string does not match the app's real asset path convention (`/brand/images/...`, not `/images/brand/...`) and does not correspond to any real file on disk. Because it is a test-fixture value rather than an assertion against a real file, this is a minor internal-consistency note, not a broken reference — flagged only in case it was meant to mirror a real path and drifted. Risk: **LOW**.

### 6.4 Knowledge-base repo — possible topic overlap between `07_WEBSITE/IMPLEMENTATION/06_DEPLOYMENT_PLAN.md` (new, untracked) and `11_TECHNICAL/DEPLOYMENT_AND_MONITORING.md` (existing)

Both titles suggest deployment-process content. This audit did not do a full line-by-line comparison of the two (out of scope for the time available), but the naming overlap and the fact that `07_WEBSITE/IMPLEMENTATION/` is a brand-new untracked folder of 12 files sitting in the *website content* domain while `11_TECHNICAL/` is the repo's existing *technical/infra* domain is worth an Owner glance to confirm there's no unintended fact duplication, per this repo's own non-duplication rule. Risk: **MEDIUM** (unverified, flagged for review only).

### 6.5 Naming-convention note

No case-sensitivity or naming-convention violations were found in top-level folder names in either repo (KB repo's `UPPER_SNAKE_CASE` convention is followed consistently at the top level; the app repo's `kebab-case` file/asset convention is followed consistently in `public/brand/images/`).

---

## A) Safe to Delete (LOW risk, unambiguous cruft, not part of current git-status WIP)

| File | Repo | Size | Reason |
|---|---|---|---|
| `.DS_Store` (repo root) | KB | 8.0 KB | macOS Finder metadata, gitignored |
| `00_START/.DS_Store` | KB | 8.0 KB | macOS Finder metadata, gitignored |
| `00_START/01_BUSINESS/.DS_Store` | KB | 8.0 KB | macOS Finder metadata, gitignored |
| `00_START/01_BUSINESS/02_BRAND/.DS_Store` | KB | 8.0 KB | macOS Finder metadata, gitignored |
| `00_START/01_BUSINESS/02_BRAND/06_DESIGN_SYSTEM/.DS_Store` | KB | 6.0 KB | macOS Finder metadata, gitignored |
| `00_START/01_BUSINESS/02_BRAND/03_MARKET_RESEARCH/.DS_Store` | KB | 8.0 KB | macOS Finder metadata, gitignored |
| `07_WEBSITE/.DS_Store` | KB | 6.0 KB | macOS Finder metadata, gitignored |
| `install-debug.log` (repo root) | KB | 7.3 KB | Stray installer debug log, already gitignored by filename | 
| `.DS_Store` (repo root) | App | 8.0 KB | macOS Finder metadata, gitignored |
| `public/.DS_Store` | App | 8.0 KB | macOS Finder metadata, gitignored |
| `public/brand/.DS_Store` | App | 6.0 KB | macOS Finder metadata, gitignored |
| `public/brand/images/.DS_Store` | App | 6.0 KB | macOS Finder metadata, gitignored |
| `public/brand/images/brand/` (empty folder) | App | — | Empty, not git-tracked, no code reference found |

**Note:** deleting the `.DS_Store`/log files is low-stakes housekeeping the Owner can do at any time (they regenerate and are already gitignored); this report does not perform the deletion itself per the audit-only instruction.

## B) Needs Owner Approval (MEDIUM/HIGH risk, ambiguous, possible in-progress restructuring, or large/footprint items worth awareness)

| Item | Repo | Why it needs a decision |
|---|---|---|
| 45 duplicate image pairs, flat vs. nested `services/{category}/` paths (~71 MB orphaned-copy side) | App | Byte-identical, only nested path is code-referenced, but flat side is current untracked WIP — needs Owner confirmation on final path convention before removal |
| `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/` old-style docs (`CONTENT_EN.md`, `CONTENT_AR.md`, `FAQ.md`, `FAQ_AR.md`, `SEO_AI.md`, `README.md`, `BUSINESS.md`, `OPERATIONS.md`, `SAFETY.md`, `TRAINING.md`, `CUSTOMER_GUIDE.md`, `MEDIA.md`) vs. new numbered set (`01_SERVICE_PROFILE.md`…`06_PAGE_CONTENT.md`) | KB | New files cite old files as sources; no deprecation decision recorded yet — Owner call on whether/when to archive the old set |
| `cockroach-control-service-card-v1.webp` / `v2.webp`, `pest-control-hero-v1.png`, `pest-control-homepage-hero-v1.webp` | KB | Not duplicates; each carries open QA flags per CHANGELOG — Owner decision needed on final approval/replacement, not a cleanup matter |
| `CONTENT_EN.html` | KB | Tool-generated export, actively cited in CHANGELOG as reference — Owner call on whether to keep as a working artifact or regenerate/remove once `CONTENT_EN.md` is finalized |
| `07_WEBSITE/01_HOMEPAGE/99_STANDARDS/` (empty) | KB | No documentation found explaining intended future content |
| `07_WEBSITE/03_SERVICES/03_SERVICE_KNOWLEDGE/01_PEST_CONTROL/` (empty) | KB | Likely migration residue (same era as `00_START/`) but not explicitly documented as "preserved" the way `00_START` is |
| `10_MARKETING_AND_SEO/CAMPAIGNS/` (empty) | KB | No documentation confirming intent |
| `public/brand/images/{master-library,projects,about,team,locations,hero,equipment}/` (empty) | KB | No documentation confirming intent |
| `public/brand/icons/{features,locations,header,services}/` (empty) | KB | No documentation confirming intent |
| `07_WEBSITE/IMPLEMENTATION/06_DEPLOYMENT_PLAN.md` vs. `11_TECHNICAL/DEPLOYMENT_AND_MONITORING.md` | KB | Possible topic overlap, not verified line-by-line in this audit |
| `.next/` Turbopack cache files > 50 MB, `@next/swc-darwin-arm64` binary | App | Large footprint, but normal/regenerable — awareness only, no action needed unless disk space is a concern |

## C) Must Keep

- `node_modules/` and `.next/` (both repos' build/dependency artifacts where applicable) — regenerable, gitignored, required to run/build the app.
- `tsconfig.tsbuildinfo` — gitignored TypeScript build cache.
- All files listed in the `git status` output of both repos as modified (`M`) or untracked (`??`) at the time of this audit (2026-08-01) — active WIP per Owner's ticket workflow, not abandoned.
- `src/lib/catalog/blog.ts` and `src/lib/media/demo-visuals.ts` — known, intentional, temporary demo/placeholder data (`isDemo: true` / `SHOW_DEMO_VISUALS`) pending real approved content; not cruft.
- `00_START/` entire tree (all empty subfolders) — documented, preserved migration history per `00_GOVERNANCE/MIGRATION/MIGRATION_PLAN.md`; do not delete.
- `04_SERVICE_KNOWLEDGE/*/assets/{hero,blog,trust,process,service-cards}/` empty placeholder folders for the 11 services without delivered assets yet — confirmed intentional scaffolding per `SERVICE_MASTER_DATABASE.md`.
- `services/pest-control/`, `services/maintenance/`, `services/cleaning/` nested image folders in the app repo — the actively code-referenced side of the §1.1/§6.1 duplicate pairs.
- The nested `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/assets/` real image files (all 4) and both cockroach-service-card versions — active evidence trail per CHANGELOG, pending Owner decision (also listed in B for the decision itself, but the files must not be deleted absent that decision).
- All other repository content not specifically flagged above (all service-knowledge folders, all governance/brand/market/operations/customer/AI/marketing/technical/design-system/legacy-archive/standards documents, all `src/` application code, all `public/brand/icons/` populated folders).

---

## Related Documents

- `00_GOVERNANCE/COLOR_SYSTEM_AUDIT_REPORT.md` — prior audit, same house style, unrelated scope (brand/design-system color tokens).
- `00_GOVERNANCE/DESIGN_SYSTEM_ASSET_ALIGNMENT_REPORT.md` — prior audit of `public/brand/icons/` and `public/brand/images/` in this repo only; this report extends duplicate/size/organization checking to the full KB repo plus the separate app repo.
- `00_GOVERNANCE/MIGRATION/MIGRATION_PLAN.md`, `CURRENT_STATE_INVENTORY.md`, `DUPLICATE_AND_CONFLICT_REPORT.md`, `VALIDATION_REPORT.md` — source evidence for the `00_START/` legacy-residue finding in §2.3 and §5.2 Group B.
- `04_SERVICE_KNOWLEDGE/SERVICE_MASTER_DATABASE.md` — source evidence for the empty per-service asset-folder finding in §2.2 and §5.2 Group A.
- `04_SERVICE_KNOWLEDGE/01_PEST_CONTROL/CHANGELOG.md` — source evidence for the image-asset findings in §1.2 and §1.4.

---

## Change Log

| Version | Date | Description |
|---|---|---|
| 1.0 | 2026-08-01 | Initial audit-only cleanup review of both the knowledge-base repo and the app repo, per Owner instruction. No file deleted, moved, renamed, or modified; no commit made. |
