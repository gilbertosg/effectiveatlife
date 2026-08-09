# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

This is the static source for **effectiveatlife.com** — a public site that translates "Gil OS," a private personal-operating-system framework, into teaching content. There is no backend and no build step. Every page is a single, fully self-contained `.html` file (inline `<style>`, inline `<script>`, Tailwind loaded from the Play CDN) — this is a hard constraint from `assets/docs/Design-System-Guide.md`, not a stylistic default.

What's live today:
- `index.html` — the landing page.
- `blog/` — a hub plus one long-form article, with the pattern established for more.
- `ai-for-friends/` — a complete 4-module course (course hub → 4 module hubs → 21 lesson pages, 26 files total), built for HR / Legal / Marketing / Industrial Engineering / International Relations professionals.

The two documents that govern this project's content and visuals:
- `assets/docs/Effective-at-Life-Implementation-Guide-V1.md` — the original phased build plan (folder structure, what each page contains).
- `assets/docs/Design-System-Guide.md` — the enforced visual system (colors, type, layout, components, and an explicit "anti-slop" list). Follow it exactly; its rules override generic design instincts.

Two new reference docs exist specifically to speed up future content work — **read these before building a new article or lesson from scratch**:
- `assets/docs/Article-Template.md` — the full blog-article shell and typography pattern, annotated.
- `assets/docs/Lesson-Template.md` — the full course-lesson shell (chrome, callouts, progress pills, verification checklist), annotated.

## Architecture

**No build tooling.** No `package.json`, no bundler, no framework. Each `.html` file ships exactly as written to S3. There is nothing to `npm install`, build, lint, or test in the conventional sense.

**Shared shell, copy-paste not includes.** Because pages are single-file, the header/nav/footer, the Tailwind `tailwind.config` block (custom `os-*` and `accent-*` colors, `display`/`body`/`mono` font families), and the Google Fonts `<link>` tags are duplicated across every page in `index.html`, `blog/`, and all 26 files in `ai-for-friends/`. When adding a new page, copy the shell from the closest existing analog (a blog article for articles, a lesson page for lessons — see the two template docs above) rather than reinventing it. If the shell itself needs to change (a new nav item, a new brand color), there is no single source of truth to edit once — it has to be updated in every page that carries it. The course's shared CSS is the one deliberate exception — see `assets/css/custom.css` below.

**Directory layout:**
- `index.html` — landing page: hero, 7-pillar bento grid (`#pillars`), AI-as-foundation section (`#ai`), methodology/inspiration matrix (`#methodology`), operational loops (`#loops`).
- `blog/index.html` — blog hub (article grid with pillar pill-tags).
- `blog/*.html` — individual articles. See `assets/docs/Article-Template.md`.
- `ai-for-friends/index.html` — course hub (4 module cards).
- `ai-for-friends/module-{1,2,3,4}/index.html` — module hubs, each with a "Key Concepts" glossary (core table + `<details>` expandable full reference) and a "Support Resources" table.
- `ai-for-friends/module-{1,2,3,4}/lesson-{n}.html` — individual lessons. See `assets/docs/Lesson-Template.md`. Module 1 has 4 lessons, Module 2 has 3, Module 3 has 7, Module 4 has 7 (21 lessons total).
- `assets/docs/` — governing docs (Implementation Guide, Design System Guide) plus the two page templates and the raw markdown source content the course/blog were synthesized from (`assets/docs/ai-for-friends/`). `assets/docs/references/AI-for-Friends-Course-State-Report.md` is the living reference for the course's current structure, conversion pipeline, and styling conventions — read it before any course structural change.
- `assets/css/custom.css` — the one shared, non-inlined stylesheet, used only by the `ai-for-friends/` course pages (base resets, lesson typography, callout variants, course-menu dropdown). A deliberate, explicit exception to the single-file-delivery rule above — see the state report's CSS-extraction section for why. `assets/js` and `assets/images` exist but are currently empty.
- `error.html` — static 404/error page for S3 static hosting.

**Known duplication bug to watch for:** the fade-in-on-scroll pattern uses a CSS `.fade-up` class (`opacity: 0` + a `fadeInUp` keyframe defined in each page's own `<style>` block) combined with an `IntersectionObserver` in a trailing `<script>` that adds `.fade-up` to grid items when they scroll into view. Do **not** put the static `fade-up` class on an element *and* also target it with the observer script — the observer sets `opacity: 0` via inline style on load, and re-adding a class the element already has does not restart a CSS animation, so the element stays permanently invisible. Hero-level content uses the static class only (animates once on load); scroll-triggered grids use the observer only. This bug has bitten this project twice already (once on `blog/index.html`, once conceptually in the original `index.html` hero) — check for it explicitly any time a page's content isn't fading in.

## Design system & visual identity

`Design-System-Guide.md` is the source of truth — read it in full before making visual decisions. Quick reference for what's already locked in:

**Palette:** `os-deep #0A0F1C` (page background), `os-surface #111827` / `os-surface-light #1F2937` (card/section backgrounds), `os-primary #FFFFFF` / `os-secondary #9CA3AF` / `os-tertiary #6B7280` (text hierarchy), `accent-cyan #00F0FF` (primary actions, active states), `accent-teal #00C2D1` (secondary highlights), `accent-purple #7B2CBF` (tertiary/data accents), `accent-amber #FBBF24` (warning callouts only — added in the course, not in the original guide).

**Type:** Space Grotesk (`font-display`) for headings and major numbers; Inter (`font-body`) for body text; JetBrains Mono (`font-mono`) for tags, metadata, labels, and technical data. All loaded via Google Fonts `<link>`, never self-hosted.

**Layout:** CSS Grid Bento Box (`grid-cols-1 md:grid-cols-3 lg:grid-cols-4`, `gap-4`/`gap-6`), glassmorphic cards (`bg-white/5 backdrop-blur-md border border-white/10 rounded-2xl`), hover elevate + glow (`hover:-translate-y-1 hover:shadow-[0_8px_30px_rgba(0,240,255,0.1)]`).

**Component vocabulary that emerged building the course** (not in the original Design Guide, but now the established pattern — reuse these, don't reinvent):
- **Callout boxes**, four variants by border/label color: `callout-tip` (cyan), `callout-note` (teal), `callout-info` (purple), `callout-warning` (amber). Structure: `<div class="callout callout-{variant}"><span class="callout-label">LABEL</span><p>...</p></div>`.
- **`<details>`/`<summary>` expand blocks** for optional-depth content (troubleshooting, "full reference" tables, "more examples"), styled to match the card system with a `+`/`−` indicator that flips on `[open]`.
- **Numbered `step-num` headings** (`<h2 id="step-N"><span class="step-num">N</span>Heading</h2>`) with `scroll-margin-top: 6rem` so they land correctly below the fixed header when jumped to.
- **Progress pills** at the top of long-form pages — anchor links (`<a href="#step-N">`) to each step, not decorative spans.
- **Course-menu dropdown** — a `Menu` button in the nav (all `ai-for-friends/**` pages) that reveals every module and lesson nested, so any course page is one click from any other. Toggled by a small vanilla-JS snippet duplicated at the bottom of each page (same duplication-not-includes tradeoff as the rest of the shell).
- **Verification checklists** — static, non-interactive checkbox rows (`.checklist-item` + `.checklist-box`) at the end of each lesson, not real form inputs.

**Anti-slop constraints (from the Design Guide, still enforced):** no text drop-shadows, no pure black backgrounds, no generic Bootstrap-blue buttons, no dense unbroken text blocks, every visual element must be informational, not decorative.

## Frontend design skill

Every layout, palette, and signature-element decision on this site — the landing page bento grid, the hero's "system status readout" signature card, the course's callout/glossary/progress-pill system — was made by invoking the **`frontend-design`** skill, not by default template instincts. When building new sections or pages:
- Invoke the skill for anything genuinely new (a new page type, a new section pattern).
- For content that fits an existing pattern (another blog article, another course lesson), the skill's job is now **consistency enforcement**, not fresh brainstorming — the palette, type system, and component vocabulary above already answer most of the brief. Follow the closest existing template rather than re-deriving a new visual language.
- The skill's own guidance still applies where it's genuinely open: copy quality, the specific "signature element" for a brand-new section, and catching anything that reads as a generic AI-generated default.

## Internationalization (Spanish) — not built yet, but scaffolded

A Spanish translation is the next planned initiative. Groundwork already exists in all 26 `ai-for-friends/**` pages: a small **EN · ES** language pill in the course nav, with ES currently rendered disabled (`title="Spanish version — coming soon"`, no `href`) so it's visible without being a dead link.

**The convention when this gets built:**
- **English stays at its current, unprefixed paths** (`ai-for-friends/...`, `blog/...`, `index.html`) as the default locale. Existing links and any external references keep working.
- **Spanish mirrors the identical directory structure under `es/`** — e.g. `es/ai-for-friends/module-1/lesson-1.html`, `es/blog/weekly-review.html`, `es/index.html`. Same filenames, same nesting, just translated content.
- **Only content changes.** CSS, layout, component structure, and JS stay identical between locales — translating a page means duplicating its HTML file into the `es/` mirror and translating the text nodes, not redesigning it.
- **Update `<html lang="en">` → `<html lang="es">`** on every translated page.
- **Wire the language pill.** Each English page's disabled `ES` span becomes a real link to its `es/` counterpart; each Spanish page's `EN` becomes a real link back. Until every page has a translated counterpart, keep the pill disabled on pages that don't yet have one — don't link to a 404.
- **Add `hreflang` alternate `<link>` tags at that point, not before.** Adding them now would point search engines at Spanish pages that don't exist yet.
- The course-menu dropdown's hrefs will need a locale-aware base path once `es/` exists (currently hardcoded relative paths like `../module-2/index.html`).

## Content sourcing and privacy

Page copy is synthesized from a private "second-brain" knowledge vault (referenced in the Implementation Guide as `../[YOUR_SECOND_BRAIN_PATH]/`), not written from scratch. When pulling content from that vault for any public page:
- **Abstract identifying personal specifics** — partner/family names, employer name, exact financial or health numbers, home addresses/trip details — into illustrative framing (e.g. "a partner," "a target body-fat %," "a senior technical career track") rather than publishing them verbatim.
- **Never publish live private document links.** Vault source files may contain real Google Drive edit-links to personal spreadsheets/docs; these must be excluded entirely, not just paraphrased.
- Keep the actual system mechanics (pillar structure, OKR methodology, ritual steps) real and specific — the abstraction applies to identifying personal data, not to the substance of the framework being taught.
- Be equally careful with any book/framework attribution added to the page (e.g. the Methodology table) — verify claims before publishing them as fact, and avoid linking out to guessed URLs (a wrong or dead link on a public credibility-driven page is a real trust cost). Prefer no link over a fabricated one.

## Deployment — read before running `git push`

`.github/workflows/main.yml` triggers `on: [push]` with **no branch filter**, and runs `aws s3 sync ./ s3://effectiveatlife-s3 --delete`. This means a push to **any** branch — not just `main` — syncs the entire working tree straight to the production S3 bucket and deletes anything in the bucket that isn't in the repo. There is no staging environment and no review gate. Treat every `git push` to this repo as a production deploy.

## Local preview

There's no dev server. Serve the directory with any static file server and open pages over `http://`, e.g.:
```
python3 -m http.server 8934
```
Opening `.html` files directly via `file://` is unreliable for verifying Tailwind CDN behavior and relative links (e.g. `blog/` ↔ root, or `ai-for-friends/module-2/` ↔ `module-1/` navigation) — use a local server instead.
