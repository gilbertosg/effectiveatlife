# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

This is the static source for **effectiveatlife.com** — a public site that translates "Gil OS," a private personal-operating-system framework, into teaching content: a landing page, a blog, and a planned "AI for Friends" mini-course. There is no backend and no build step. Every page is a single, fully self-contained `.html` file (inline `<style>`, inline `<script>`, Tailwind loaded from the Play CDN) — this is a hard constraint from `assets/docs/Design-System-Guide.md`, not a stylistic default.

The two documents that govern this project are:
- `assets/docs/Effective-at-Life-Implementation-Guide-V1.md` — the phased build plan (folder structure, what each page contains).
- `assets/docs/Design-System-Guide.md` — the enforced visual system (colors, type, layout, components, and an explicit "anti-slop" list). Follow it exactly; its rules override generic design instincts.

## Architecture

**No build tooling.** No `package.json`, no bundler, no framework. Each `.html` file ships exactly as written to S3. There is nothing to `npm install`, build, lint, or test in the conventional sense.

**Shared shell, copy-paste not includes.** Because pages are single-file, the header/nav/footer, the Tailwind `tailwind.config` block (custom `os-*` and `accent-*` colors, `display`/`body`/`mono` font families), the Google Fonts `<link>` tags, and the base `<style>` block (scroll behavior, `.font-display`/`.font-mono` helpers, the `fade-up` keyframe animation, focus-visible outline, reduced-motion handling) are duplicated across `index.html`, `blog/index.html`, and `blog/weekly-review.html`. When adding a new page, copy this shell from an existing page rather than reinventing it, and if the shell itself needs to change, update it in every page — there is no single source of truth to edit once.

**Directory layout:**
- `index.html` — landing page (hero, 7-pillar bento grid, Driver/Passenger model, methodology matrix, operational loops).
- `blog/index.html` — blog hub (article grid with pillar pill-tags).
- `blog/*.html` — individual articles. Long-form pages add a `.prose-article` CSS block (in addition to the shared shell) for readable measure/line-height, and follow the Implementation Guide's rule of inserting a static email-capture block roughly halfway through the article body.
- `ai-for-friends/` — planned 3-module mini-course (Implementation Guide Phase 4); directory exists but is currently empty.
- `assets/docs/` — the two governing planning documents (see above). `assets/css`, `assets/js`, `assets/images` exist but are currently empty — per the Design Guide, pages are self-contained and don't rely on these, so only use them if a genuinely shared, non-inlineable asset (e.g. an image) is needed.
- `error.html` — static 404/error page for S3 static hosting.

**Known duplication bug to watch for:** the fade-in-on-scroll pattern uses a CSS `.fade-up` class (`opacity: 0` + a `fadeInUp` keyframe defined in each page's own `<style>` block) combined with an `IntersectionObserver` in a trailing `<script>` that adds `.fade-up` to grid items when they scroll into view. Do **not** put the static `fade-up` class on an element *and* also target it with the observer script — the observer sets `opacity: 0` via inline style on load, and re-adding a class the element already has does not restart a CSS animation, so the element stays permanently invisible. Hero-level content uses the static class only (animates once on load); scroll-triggered grids use the observer only.

## Content sourcing and privacy

Page copy is synthesized from a private "second-brain" knowledge vault (referenced in the Implementation Guide as `../[YOUR_SECOND_BRAIN_PATH]/`), not written from scratch. When pulling content from that vault for any public page:
- **Abstract identifying personal specifics** — partner/family names, employer name, exact financial or health numbers, home addresses/trip details — into illustrative framing (e.g. "a partner," "a target body-fat %," "a senior technical career track") rather than publishing them verbatim.
- **Never publish live private document links.** Vault source files may contain real Google Drive edit-links to personal spreadsheets/docs; these must be excluded entirely, not just paraphrased.
- Keep the actual system mechanics (pillar structure, Driver/Passenger rules, OKR methodology, ritual steps) real and specific — the abstraction applies to identifying personal data, not to the substance of the framework being taught.

## Deployment — read before running `git push`

`.github/workflows/main.yml` triggers `on: [push]` with **no branch filter**, and runs `aws s3 sync ./ s3://effectiveatlife-s3 --delete`. This means a push to **any** branch — not just `main` — syncs the entire working tree straight to the production S3 bucket and deletes anything in the bucket that isn't in the repo. There is no staging environment and no review gate. Treat every `git push` to this repo as a production deploy.

## Local preview

There's no dev server. Serve the directory with any static file server and open pages over `http://`, e.g.:
```
python3 -m http.server 8934
```
Opening `.html` files directly via `file://` is unreliable for verifying Tailwind CDN behavior and relative links (e.g. `blog/` ↔ root navigation) — use a local server instead.
