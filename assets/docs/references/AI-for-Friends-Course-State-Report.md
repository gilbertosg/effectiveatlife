# AI for Friends — Course Current-State Report

**Purpose of this document:** a single reference for the current state of the "AI for Friends" course — what content exists, how it's structured, how it gets converted from markdown source into the live HTML pages, and the styling conventions those pages use. Written to make ingesting the *next* lesson (writing a new `M-L_Title.md` and turning it into a new `module-N/lesson-N.html`) faster and more consistent than re-deriving all of this from scratch again.

This is a **snapshot** as of the time it was written. Treat it as a map, not a live source of truth — if a page or file referenced here has since changed, trust the current file over this document.

---

## 1. Overview

"AI for Friends" is a 4-module, 21-lesson crash course teaching non-technical professionals (HR, Legal, Marketing, Industrial Engineering, International Relations) to use Claude effectively — from foundational concepts through prompting technique, hands-on Claude Code file work and claude.ai Projects, to automating recurring multi-step workflows. It's part of effectiveatlife.com, built with the same no-build, single-self-contained-HTML-file-per-page approach as the rest of the site (see root `CLAUDE.md`).

**Current scope:** 26 HTML files total — 1 course index, 4 module hubs, 21 lesson pages. The course was originally 5 modules (Module 3 "Claude Code" had one lesson; Module 4 "Building Your AI Personal Assistant" covered claude.ai Projects in 6 lessons; Module 5 covered automation in 7 lessons). Module 4 was merged into Module 3 as lessons 3.2–3.7 (Module 3 is now 7 lessons total: 3.1 install + 3.2–3.7 Projects), and the old Module 5 was renumbered to the new Module 4 — see §12 for the full writeup of this change. There is no Module 5 anymore, and no Module 6 planned.

**Source of truth split:**
- Raw content lives as markdown in `assets/docs/ai-for-friends/*.md` (25 files — synthesized from an external private "second-brain" vault, per root CLAUDE.md's content-sourcing rules).
- Governing visual/structural rules live in `assets/docs/references/Design-System-Guide.md`, `Lesson-Template.md`, `Article-Template.md`, and the original `Effective-at-Life-Implementation-Guide-V1.md`.
- The actual shipped pages live in `ai-for-friends/**/*.html`.

These three layers have diverged somewhat over time (see §7) — this report reconciles them.

**Module 4/5 source quality note:** unlike Modules 1–3's markdown (which had a mix of stray `[cite: N]` artifacts, one empty lesson file, and one file with duplicated tail content — see §3), the Module 4 and 5 source files arrived clean: no citation artifacts, no empty files, no truncation issues. The only recurring issue that repeats from the earlier modules is the filename-mismatch pattern described in §2.

---

## 2. Course Map

| Module | Lesson | Markdown source (`assets/docs/ai-for-friends/`) | HTML output (`ai-for-friends/`) | Topic |
|---|---|---|---|---|
| 1 — AI Foundations | hub | `1-0_AI_Foundations_module.md` | `module-1/index.html` | Module overview, glossary, support resources |
| 1 | 1.1 | `1-1_How_AI_Models_Work.md` | `module-1/lesson-1.html` | How LLMs work (pattern prediction, not thinking); terminology; Assistant/Agent/Agentic System; the 7-step agentic loop |
| 1 | 1.2 | `1-2_Prompt_Engineering_vs_Context_Engineering.md` | `module-1/lesson-2.html` | Prompt vs. context engineering; 5 prompting patterns; the CONTEXT/ROLE/TASK/FORMAT/CONSTRAINTS formula |
| 1 | 1.3 | `1-3_Practical_Prompting_Techniques.md` | `module-1/lesson-3.html` | Few-shot, role, chain-of-thought, meta prompting; COSTARS framework; interview-style prompting; validation habits |
| 1 | 1.4 | `1-4_Chossing_AI_Model.md` *(sic, source filename typo)* | `module-1/lesson-4.html` | Choosing between Haiku/Sonnet/Opus; cost/speed tradeoffs |
| 2 — Setting Up Your Computer *(optional)* | hub | `2-0_Setting_Up_Computer.md` | `module-2/index.html` | Module overview — explicitly optional warm-up, not a Module 3 prerequisite |
| 2 | 2.1 | `2-1_Installing_Windows_terminal.md` | `module-2/lesson-1.html` | Installing a standalone Windows terminal, setting PowerShell as default (Windows-only lesson — Mac readers are directed to skip to 2.2) |
| 2 | 2.2 | `2-2_Intalling_VS_Code.md` *(sic, source filename typo)* | `module-2/lesson-2.html` | Installing VS Code, finding the Extensions panel |
| 2 | 2.3 | `2-3_Navigating_Terminal.md` **(has duplicated tail content — see §3)** | `module-2/lesson-3.html` | Four basic terminal commands (`pwd`, `ls`, `cd`, `cd ..`) via a practice exercise |
| 3 — Claude Code | hub | `3-0_Claude-Code.md` | `module-3/index.html` | Module overview; web Claude vs. Claude Code; role-specific value table; merged Key Concepts glossary covering both the CLI and Projects |
| 3 | 3.1 | `3-1_Claude_Code_Installation.md` **(structural outlier — see §3)** | `module-3/lesson-1.html` | Full install (Claude Pro, VS Code, Git, Claude Code CLI); extensions; graduated hands-on tutorial |
| 3 | 3.2 | `3-2_Claude_Code_Project_Basics.md` *(was `4-1`, see §12)* | `module-3/lesson-2.html` | The three parts of a Project (name, custom instructions, Project knowledge); why a Project beats a blank chat |
| 3 | 3.3 | `3-3_First_Project.md` *(was `4-2`)* | `module-3/lesson-3.html` | Creating a Project; the four sections of good custom instructions; copy-ready templates for all five roles |
| 3 | 3.4 | `3-4_Project_Material.md` *(was `4-3`)* | `module-3/lesson-4.html` | Uploading Project knowledge; what a Project can and cannot reach by default |
| 3 | 3.5 | `3-5_Project_Instructions.md` *(was `4-4`)* | `module-3/lesson-5.html` | Where a Project's "memory" lives; keeping standing instructions current |
| 3 | 3.6 | `3-6_Using_Projects_to_Design_More.md` *(was `4-5`)* | `module-3/lesson-6.html` | Using a working Project to design the next one via a meta-prompt |
| 3 | 3.7 | `3-7_Examples_by_Role.md` *(was `4-6`)* | `module-3/lesson-7.html` | Five complete, finished Projects (Legal, Marketing, Industrial Engineering, International Relations, HR) |
| 4 — Automating Workflows with Claude Code | hub | `4-0_Claude_Code_Workflows.md` *(was `5-0`)* | `module-4/index.html` | Module overview; skill vs. plugin concept; "Which Lesson Is For You" role-relevance table |
| 4 | 4.1 | `4-1_Claude_Code_Daily_Habits.md` *(was `5-1`)* | `module-4/lesson-1.html` | Session hygiene, fast diff review, usage awareness, the four rules for anything unattended |
| 4 | 4.2 | `4-2_Installing_Antrhopic_Skills.md` *(was `5-2`, sic, source filename typo)* | `module-4/lesson-2.html` | Installing Anthropic's `document-skills` plugin (docx/pdf/pptx/xlsx) |
| 4 | 4.3 | `4-3_Automating_Agreements_RI_Example.md` *(was `5-3`)* **(0-indexed Step 0–6, see §3)** | `module-4/lesson-3.html` | Full worked example: dictate-to-setup a 3-skill plugin (check webpage → draft follow-up → build Word doc) |
| 4 | 4.4 | `4-4_What_is_an_MCP_Server.md` *(was `5-4`)* | `module-4/lesson-4.html` | What an MCP connection is; adding one via claude.ai Connectors and `claude mcp add` |
| 4 | 4.5 | `4-5_Daily_Email_Briefing.md` *(was `5-5`)* | `module-4/lesson-5.html` | Connecting email/calendar via MCP; one single-skill daily briefing |
| 4 | 4.6 | `4-6_Market_Awareness.md` *(was `5-6`)* | `module-4/lesson-6.html` | Two-skill plugin: monitor sources, report only what's new, email a digest |
| 4 | 4.7 | `4-7_Content-Generation.md` *(was `5-7`)* | `module-4/lesson-7.html` | Three-skill plugin: gather articles → compile digest → draft on-brand content (course's final lesson) |
| — | — | *(no single 1:1 source)* | `ai-for-friends/index.html` | Course hub — syllabus overview, links to all 4 module hubs |

The HTML filenames use `lesson-N.html` numbered **within each module** (not global), matching the markdown's `M-L` convention exactly except the HTML drops the module digit from the filename (module is the directory instead).

**Filename-mismatch note (repeats the `1-4_Chossing`/`2-2_Intalling` pattern from Modules 1–2, and turns out to be far more widespread than first flagged):** a full cross-link audit during the Module 3/4 merge (§12) found that **every single cross-link in the Module 2–5-era markdown sources cited a filename that doesn't exist on disk** — either a typo variant or a completely different idealized name (e.g. the old `4-0` cited `4-1_What_Is_A_Claude_Project.md` and `4-2_Creating_Your_First_Project.md`, but the real files were `4-1_Claude_Code_Project_Basics.md` and `4-2_First_Project.md`; the old `5-0` cited `5-1_Your_Claude_Code_Daily_Habits.md` vs. the real `5-1_Claude_Code_Daily_Habits.md`). This doesn't affect the HTML output (converted by hand against the actual files, not by following the markdown's internal links), but it's a trap for anyone scripting a conversion pipeline off these cross-references — **always resolve lesson number → actual filename from the directory listing** (`ls assets/docs/ai-for-friends/`), never from another file's citation of it.

---

## 3. Markdown Source Content Structure

### Naming convention

`<module>-<lesson>_<Title_Case_With_Underscores>.md`. First digit = module number. Second digit = lesson number, where **`0` is reserved for the module overview/hub file**.

### Recurring skeleton — module hub files (`X-0`)

1. `<!-- HERO: Title | Subtitle -->`
2. `<!-- TOC: ... -->`
3. `## Overview`
4. `### Who This Module Is For` + target roles
5. `### Why This Matters`
6. *(Module 3 only)* `### What This Looks Like in Your Role` — role-by-role value table
7. `### By the End of This Module, You Will`
8. `### Prerequisites`
9. `### Time to Complete`
10. `## Lessons in This Module` — table (lesson #, title/link, duration, summary) + callouts
11. `## Key Concepts` — core-terms table (5–7 rows) + `<!-- EXPAND -->...<!-- /EXPAND -->` extended glossary
12. `## What's Next` — next module link + **Support Resources table** (Claude / Claude Docs / Claude Support — same 3 rows in every hub)
13. `<!-- CHILDREN -->`

### Recurring skeleton — individual lesson files (Module 1 & 2 style)

1. `<!-- HERO/MENU: ... -->`
2. `<!-- TOC: ... -->`
3. `## Overview` → `### Why This Matters` → `### Prerequisites` → `### Time to Complete`
4. `<!-- PROGRESS: Step list -->`
5. Numbered `## Step N: <Title>` sections, each with `### What You'll Do`, `### Instructions`, optional `### Key Concepts` table/examples, callouts, occasional `EXPAND` or `COLUMNS` blocks
6. `## Verification` — `- [ ]` checklist + a troubleshooting `NOTE`
7. `<!-- CELEBRATION: Lesson Complete! | ... -->`
8. `### What's Next` — next lesson link + Related Resources (same 3 links repeated, though URL formatting varies — see §7)
9. `<!-- CHILDREN -->`

**`3-1_Claude_Code_Installation.md` breaks this pattern entirely** — it's a plain numbered-section guide (`Section 0`–`Section 5`, subsections like `2.1`) using blockquote callouts (`> 🔒`, `> 💬 In Plain English:`, `> ✅ Checkpoint:`) instead of the `TIP/NOTE/INFO/WARNING` directive system, with no `HERO`/`TOC`/`PROGRESS`/`Verification`/`CELEBRATION` scaffolding. Don't use it as a template for a new lesson's markdown structure — use `1-1` through `1-4` or `2-2`/`2-3` instead.

**Modules 4 and 5 follow the standard directive skeleton exactly** — no structural outlier repeats `3-1`'s pattern. `5-3_Automating_Agreements_RI_Example.md` is 0-indexed (`## Step 0` through `## Step 6`, matching `3-1`'s 0-indexed shape) since its content mirrors a "Step 0: mechanic/concept, then Steps 1+: applied" structure — but see §5 for why this did **not** carry over `3-1`'s oversized/purple step-num CSS treatment; that turned out to be specific to `3-1`'s single-giant-lesson framing, not a "0-indexed lessons get the big treatment" rule.

**Module 4's hub (`4-0`) has one section not present in any other hub**: "Which Lesson Is For You" — a table mapping each of the five target roles to which lesson was written specifically for them (4.3, 4.5, or 4.6) versus which lessons' *shape* still transfers even without a role-specific worked example. This exists because Module 4, unlike Modules 1–3, has several lessons built around one specific role's scenario (International Relations for 4.3, Marketing for 4.6) rather than covering all roles evenly in every lesson — the table exists to point non-IR/non-Marketing readers at the right lesson to read closely versus skim.

### Directive vocabulary (all HTML comments in the raw markdown)

`HERO`, `MENU` (1-4 only), `TOC`, `ANCHOR`, `PROGRESS`, `TIP`, `NOTE`, `INFO`, `WARNING`, `EXPAND`/`/EXPAND`, `COLUMNS: N/N`/`COLSEP`/`/COLUMNS`, `CELEBRATION`, `CHILDREN`. See §4 for what each becomes in HTML.

### Known content issues to resolve before/while ingesting

- ~~**`2-1_Installing_Windows_terminal.md` is completely empty (0 bytes).**~~ **RESOLVED** (see §11) — content was written from scratch to match the existing `module-2/lesson-1.html`, plus a Mac-skip callout, during the Windows/Mac parity pass.
- **`2-3_Navigating_Terminal.md` has Module 3's entire hub content duplicated at its tail** (after the legitimate lesson content's closing `<!-- CHILDREN -->` around line 161, a second full copy of `3-0_Claude-Code.md`'s content runs through line 281, carrying `[cite: 3]`/`[cite: 4]` markers). Truncate at the genuine `<!-- CHILDREN -->` if re-deriving this file.
- **Stray `[cite: N]` reference markers** litter nearly every line of `1-1`, `1-2`, `1-3`, `1-4`, and the first ~161 lines of `2-3` — leftover artifacts from whatever tool generated/exported the markdown. Strip these before converting to HTML.
- **Filename typos**: `1-4_Chossing_AI_Model.md` ("Chossing"), `2-2_Intalling_VS_Code.md` ("Intalling"). Internal cross-links inside other files sometimes reference the *correctly spelled* filename (e.g. a link to `1-4_Choosing_AI_Model.md`), which won't resolve against the actual typo'd filename — a broken-link risk if anyone follows those markdown links programmatically. The HTML output itself spells both correctly, so this is a source-file-only issue.
- **Support/docs URL inconsistency in the source markdown itself**: `code.claude.com/docs` vs `docs.claude.com/docs` vs `docs.anthropic.com/claude/docs`; `support.claude.com` vs `support.anthropic.com` — inconsistent across files, and this inconsistency carried through into the HTML (see §7).

---

## 4. Markdown → HTML Conversion Method

| Markdown directive / pattern | Becomes in HTML |
|---|---|
| `<!-- HERO: Title \| Subtitle -->` | The lesson/hub header `<h1>` + dek `<p>` inside the `bg-grid` hero `<header>` |
| `<!-- TOC: ... -->` | Progress-pill row (lessons) or Lessons-in-this-module table (hubs) |
| `<!-- PROGRESS: Step list -->` | The anchor-link progress pills: `<a href="#step-N">` matched to each `<h2 id="step-N">` |
| `## Step N: Title` | `<h2 id="step-N"><span class="step-num">N</span>Title</h2>` |
| `TIP` callout | `<div class="callout callout-tip"><span class="callout-label">…</span><p>…</p></div>` (cyan) |
| `NOTE` callout | `.callout-note` (teal) |
| `INFO` callout | `.callout-info` (purple) |
| `WARNING` callout | `.callout-warning` (amber) |
| `<!-- EXPAND -->...<!-- /EXPAND -->` | `<details><summary>…</summary><div>…</div></details>` |
| `<!-- COLUMNS: 50/50 -->...COLSEP...<!-- /COLUMNS -->` | A two-column grid (`.col-2` where defined, or inline grid utilities) |
| `- [ ]` Verification checklist items | `<div class="checklist-item"><span class="checklist-box"></span><span class="text-sm text-os-secondary">…</span></div>` rows inside a `bg-white/5 border border-white/10` card |
| `<!-- CELEBRATION: ... -->` | The closing gradient "Lesson complete" card: `<div class="mt-10 rounded-2xl bg-gradient-to-br from-accent-cyan/10 to-transparent border border-accent-cyan/20 p-6">` |
| Role-tailored examples (HR/Legal/Marketing/Industrial Engineering) | Either a comparison table with one row/column per role, or nested inside an `EXPAND` block for the less-common roles |
| `### Key Concepts` table (hub files) | The `.glossary` table + `<details>` "Full Key Concepts reference" expansion |
| Support Resources table | The identical 3-row `.glossary`-styled table on hubs (Claude / Claude Docs / Claude Support) |
| `<!-- CHILDREN -->` | End of convertible content — nothing after this marker should be converted (relevant for `2-3`'s duplicated tail, see §3) |

This mapping is not automated — there is no build tooling or script; conversion is done by hand (or by an LLM) reading the markdown and producing the HTML directly, following the shell patterns in §5.

---

## 5. HTML Page Structure Reference

All 27 pages are single self-contained files — Tailwind via Play CDN, inline `<style>`, inline `<script>`, no build step, matching the site-wide constraint in root `CLAUDE.md`.

### Shared shell (present, near-byte-identical, on all 27 pages)

**`<head>`:**
```html
<script src="https://cdn.tailwindcss.com"></script>
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          'os-deep': '#0A0F1C', 'os-surface': '#111827', 'os-surface-light': '#1F2937',
          'os-primary': '#FFFFFF', 'os-secondary': '#9CA3AF', 'os-tertiary': '#6B7280',
          'accent-cyan': '#00F0FF', 'accent-teal': '#00C2D1', 'accent-purple': '#7B2CBF', 'accent-amber': '#FBBF24',
        },
        fontFamily: {
          display: ['"Space Grotesk"', 'sans-serif'], body: ['Inter', 'sans-serif'], mono: ['"JetBrains Mono"', 'monospace'],
        },
      },
    },
  };
</script>
```
Plus Google Fonts preconnect + stylesheet (`Space+Grotesk:wght@500;600;700`, `Inter:wght@400;500;600`, `JetBrains+Mono:wght@400;500`). Title pattern: `Lesson X.Y: <Title> — AI for Friends` / `Module N: <Title> — AI for Friends`.

**No inline `<style>` block anymore — CSS lives in `assets/css/custom.css`.** As of the CSS extraction pass (see §10), every page's `<head>` ends with a single stylesheet link instead of a bespoke `<style>` block:
```html
<link rel="stylesheet" href="../assets/css/custom.css">   <!-- course index: one level up -->
<link rel="stylesheet" href="../../assets/css/custom.css"> <!-- every module hub/lesson: two levels up -->
```
placed immediately after the Google Fonts `<link>`, right before `</head>`. The Tailwind CDN `<script>` + inline `tailwind.config` block stays inline per-page exactly as before — only the raw CSS was extracted, not the Tailwind config or the trailing menu-toggle `<script>`. See §10 for the full contents and rationale.

**Fixed header/nav** (identical structure everywhere):
```html
<header class="fixed top-0 inset-x-0 z-50 border-b border-white/[0.08] bg-os-deep/80 backdrop-blur-md">
  <div class="max-w-7xl mx-auto px-6 h-16 flex items-center justify-between">
    <a href="<root-relative>index.html" class="flex items-center gap-2.5 group">
      <span class="w-2 h-2 rounded-full bg-accent-cyan shadow-[0_0_8px_rgba(0,240,255,0.8)]"></span>
      <span class="font-display font-semibold tracking-tight text-[15px]">EFFECTIVE<span class="text-accent-cyan">/</span>AT LIFE</span>
    </a>
    <nav class="hidden md:flex items-center gap-6 font-mono text-xs text-os-secondary uppercase tracking-wide">
      <!-- Pillars / Blog / Course links, course-menu dropdown, EN/ES pill -->
    </nav>
    <a href="..." class="...">  <!-- right-side CTA, varies by page role --> </a>
  </div>
</header>
```

**Course-menu dropdown** (button + panel + JS, copy verbatim — only the active-row highlight changes per lesson):
```html
<button type="button" id="course-menu-btn" class="flex items-center gap-1.5 hover:text-accent-cyan transition-colors" aria-expanded="false" aria-haspopup="true" aria-controls="course-menu-panel">
  Menu
  <svg width="10" height="10" viewBox="0 0 10 10" fill="none" class="mt-px"><path d="M1 3L5 7L9 3" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
</button>
<div id="course-menu-panel" class="hidden absolute right-0 top-full mt-4 w-[19rem] rounded-2xl bg-os-surface border border-white/10 shadow-2xl shadow-black/40 p-3 normal-case">
  <!-- one block per module: module row + nested lesson links, separated by <div class="border-t border-white/10 my-1"></div> -->
  <a href="..." class="flex items-center justify-center gap-1.5 px-2 py-2 rounded-lg text-xs font-mono text-accent-cyan hover:bg-white/5 transition-colors">Course Home</a>
</div>
```
On lesson pages, the current lesson's own link inside this panel gets `class="block px-2 py-1 rounded text-xs text-accent-cyan bg-white/5"` instead of the default `class="block px-2 py-1 rounded text-xs text-os-secondary hover:text-accent-cyan hover:bg-white/5 transition-colors"`. Module hubs do **not** self-highlight their own module row (only the top-level "Course" nav link goes cyan).

**EN/ES language pill** (ES intentionally disabled, per the i18n scaffolding in root CLAUDE.md):
```html
<div class="flex items-center gap-1.5 text-[10px] text-os-tertiary normal-case">
  <span class="text-accent-cyan font-semibold">EN</span>
  <span class="text-white/20">/</span>
  <span class="cursor-default" title="Spanish version — coming soon">ES</span>
</div>
```

**Right-side header CTA** (the one deliberately-varying shell element): filled cyan `Start Course`/`Start Module`/`Module N` button on Module 1, 3, and 4 pages (i.e. every required module); **outline/ghost style** (`border border-white/20 text-os-secondary hover:border-accent-cyan/50 hover:text-accent-cyan`) on all Module 2 pages, signaling "optional." Note this filled-cyan CTA is the one shell element that stays cyan regardless of the page's own module-identity color (e.g. Module 4's CTA button is filled cyan even though its numeral/badge is white) — only the numeral/badge/dropdown color varies per module, never this button.

**Footer** (byte-identical on all 27 files):
```html
<footer class="px-6 py-16 border-t border-white/[0.08]">
  <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-start md:items-center justify-between gap-8">
    <div>
      <div class="flex items-center gap-2.5 mb-3">
        <span class="w-2 h-2 rounded-full bg-accent-cyan shadow-[0_0_8px_rgba(0,240,255,0.8)]"></span>
        <span class="font-display font-semibold tracking-tight text-sm">EFFECTIVE<span class="text-accent-cyan">/</span>AT LIFE</span>
      </div>
      <p class="font-mono text-xs text-os-tertiary max-w-sm">You do not rise to the level of your goals. You fall to the level of your systems.</p>
    </div>
    <p class="font-mono text-xs text-os-tertiary">© 2026 Effective at Life. Built as a system, not a slogan.</p>
  </div>
</footer>
```

**Trailing `<script>`** — every page has exactly 3 `<script>` tags: the Tailwind CDN include, the inline config, and this menu-toggle script (byte-identical everywhere; **there is no IntersectionObserver anywhere in this course** — see §7):
```html
<script>
  (function () {
    const btn = document.getElementById('course-menu-btn');
    const panel = document.getElementById('course-menu-panel');
    if (!btn || !panel) return;
    function closeMenu() { panel.classList.add('hidden'); btn.setAttribute('aria-expanded', 'false'); }
    function openMenu() { panel.classList.remove('hidden'); btn.setAttribute('aria-expanded', 'true'); }
    btn.addEventListener('click', (e) => {
      e.stopPropagation();
      panel.classList.contains('hidden') ? openMenu() : closeMenu();
    });
    document.addEventListener('click', (e) => {
      if (!panel.contains(e.target) && e.target !== btn) closeMenu();
    });
    document.addEventListener('keydown', (e) => { if (e.key === 'Escape') closeMenu(); });
  })();
</script>
```

### Lesson-page-specific structure

**Hero header** — breadcrumb, `<h1 class="font-display font-bold tracking-tight text-3xl sm:text-4xl leading-[1.15] mb-4">`, dek `<p class="text-os-secondary text-lg leading-relaxed mb-6">`, meta badges (`{N} MIN`, `STEP {N} OF {TOTAL}` — see §7 for this badge's inconsistencies), all wrapped in `class="... fade-up"` (static, load-once animation).

**Progress pills:**
```html
<div class="flex flex-wrap gap-2 font-mono text-[10px]">
  <a href="#step-1" class="px-2.5 py-1 rounded-full bg-accent-cyan/15 border border-accent-cyan/40 text-accent-cyan hover:bg-accent-cyan/25 transition-colors">1. Short label</a>
  <a href="#step-2" class="px-2.5 py-1 rounded-full border border-white/10 text-os-tertiary hover:text-accent-cyan hover:border-accent-cyan/40 transition-colors">2. Short label</a>
</div>
```
First pill filled/active, rest outlined — this is **static**, not scroll-spy driven.

**Step headings:**
```html
<h2 id="step-1"><span class="step-num">1</span>Step Title</h2>
```
```css
.lesson-body h2 { font-family: 'Space Grotesk', sans-serif; font-weight: 600; letter-spacing: -0.01em; font-size: 1.5rem; margin-top: 3rem; margin-bottom: 0.75rem; scroll-margin-top: 6rem; }
.lesson-body h2 .step-num { display: inline-flex; align-items: center; justify-content: center; width: 2rem; height: 2rem; border-radius: 9999px; margin-right: 0.75rem; background: rgba(0,240,255,0.1); border: 1px solid rgba(0,240,255,0.4); color: #00F0FF; font-family: 'JetBrains Mono', monospace; font-size: 0.8rem; font-weight: 500; vertical-align: middle; }
```
`scroll-margin-top: 6rem` on the `h2` is what keeps `#step-N` anchor jumps from hiding under the fixed header. Sequential integers starting at 1, except `module-3/lesson-1.html` which is 0-indexed (`step-0`–`step-5`, mirroring its 6-section source) and uses a larger, purple-tinted variant of this CSS (`font-size: 1.7rem`, `background: rgba(123,44,191,0.12)`, `color: #B18CE0`) to match its "big lesson" theme. **`module-4/lesson-3.html` (originally `module-5/lesson-3.html`, renumbered — see §12) is also 0-indexed (`step-0`–`step-6`) but deliberately keeps the standard cyan step-num CSS** — confirming the oversized/purple treatment is specific to `3-1`'s single-giant-lesson framing, not a rule that "0-indexed lessons get bigger step-nums."

**Callout boxes — all 4 variants:**
```css
.callout { border-radius: 0.75rem; padding: 1.1rem 1.25rem; margin: 1.5rem 0; border: 1px solid; font-size: 0.9rem; line-height: 1.65; }
.callout-label { font-family: 'JetBrains Mono', monospace; font-size: 0.7rem; text-transform: uppercase; letter-spacing: 0.08em; display: block; margin-bottom: 0.4rem; }
.callout-tip { background: rgba(0,240,255,0.06); border-color: rgba(0,240,255,0.25); } .callout-tip .callout-label { color: #00F0FF; }
.callout-note { background: rgba(0,194,209,0.06); border-color: rgba(0,194,209,0.25); } .callout-note .callout-label { color: #00C2D1; }
.callout-info { background: rgba(123,44,191,0.08); border-color: rgba(123,44,191,0.3); } .callout-info .callout-label { color: #B18CE0; }
.callout-warning { background: rgba(251,191,36,0.07); border-color: rgba(251,191,36,0.3); } .callout-warning .callout-label { color: #FBBF24; }
.callout p { color: #D1D5DB; margin-bottom: 0; }
```
```html
<div class="callout callout-info">
  <span class="callout-label">The Core Insight</span>
  <p>AI does not think. It predicts what text should come next based on patterns.</p>
</div>
```
Pick a variant deliberately (tip = actionable suggestion, note = clarifying aside, info = core concept, warning = real risk) — don't default to `callout-info` for everything.

**`<details>`/`<summary>` expand blocks:**
```css
.lesson-body details { border-radius: 0.75rem; border: 1px solid rgba(255,255,255,0.1); background: rgba(255,255,255,0.03); margin: 1.5rem 0; overflow: hidden; }
.lesson-body summary { cursor: pointer; padding: 1rem 1.25rem; font-family: 'Space Grotesk', sans-serif; font-weight: 600; font-size: 0.9rem; list-style: none; display: flex; align-items: center; justify-content: space-between; }
.lesson-body summary::-webkit-details-marker { display: none; }
.lesson-body summary::after { content: '+'; font-family: 'JetBrains Mono', monospace; color: #00F0FF; font-size: 1.1rem; }
.lesson-body details[open] summary::after { content: '\2212'; }
.lesson-body details > div { padding: 0 1.25rem 1.25rem; }
```
Reserved for genuinely optional depth (troubleshooting, full reference tables, extra role-specific examples) — not a substitute for organizing core content into steps.

**Verification checklist:**
```html
<h2 class="!mt-16">Verification</h2>
<div class="rounded-2xl bg-white/5 border border-white/10 p-6">
  <div class="checklist-item"><span class="checklist-box"></span><span class="text-sm text-os-secondary">Concrete, checkable outcome</span></div>
</div>
```
```css
.checklist-item { display: flex; align-items: flex-start; gap: 0.75rem; padding: 0.6rem 0; }
.checklist-box { width: 1.1rem; height: 1.1rem; border-radius: 0.3rem; border: 1.5px solid rgba(0,240,255,0.5); flex-shrink: 0; margin-top: 0.15rem; }
```
Static — empty `<span>`, not a real `<input type="checkbox">`. 2–4 concrete, lesson-specific items; no generic filler.

**Closing "lesson complete" card:**
```html
<div class="mt-10 rounded-2xl bg-gradient-to-br from-accent-cyan/10 to-transparent border border-accent-cyan/20 p-6">
  <p class="font-mono text-[11px] uppercase tracking-widest text-accent-cyan mb-2">Lesson complete</p>
  <p class="text-sm text-os-secondary">Summary sentence.</p>
</div>
```
(`module-3/lesson-1.html` uses the purple variant: `from-accent-purple/15 ... border-accent-purple/20`, label `text-accent-purple`.)

**Prev/next nav:**
```html
<nav class="px-6 pb-24">
  <div class="max-w-2xl mx-auto flex items-center justify-between gap-4 pt-8 border-t border-white/[0.08]">
    <a href="index.html" class="font-mono text-xs text-os-tertiary hover:text-accent-cyan transition-colors">&larr; Module 1</a>
    <a href="lesson-2.html" class="flex items-center gap-2 px-5 py-3 rounded-lg bg-[#00F0FF] text-black font-display font-bold text-sm hover:shadow-[0_0_20px_rgba(0,240,255,0.4)] transition-shadow">Next: Lesson Title &rarr;</a>
  </div>
</nav>
```
Must be manually updated on both the new page and its neighbors when a lesson is inserted — no single source of truth.

### Module-hub-specific structure

**Key Concepts glossary:**
```html
<div class="rounded-2xl border border-white/10 overflow-hidden fade-up">
  <table>
    <thead><tr><th>Term</th><th>Defined In</th><th>Plain English Meaning</th></tr></thead>
    <tbody><tr><td><strong>Prompt</strong></td><td>Lesson 1.1</td><td>The instruction or question you type to the AI.</td></tr></tbody>
  </table>
  <details>
    <summary>Full Key Concepts reference</summary>
    <div><table><tbody><!-- extended term list, no <thead> --></tbody></table></div>
  </details>
</div>
```
```css
.glossary table { width: 100%; border-collapse: collapse; font-size: 0.88rem; }
.glossary th { text-align: left; font-family: 'JetBrains Mono', monospace; font-size: 0.68rem; text-transform: uppercase; letter-spacing: 0.05em; color: #6B7280; padding: 0.7rem 0.9rem; border-bottom: 1px solid rgba(255,255,255,0.1); }
.glossary td { padding: 0.8rem 0.9rem; border-bottom: 1px solid rgba(255,255,255,0.06); color: #9CA3AF; vertical-align: top; }
.glossary tr:last-child td { border-bottom: none; }
```
(`.glossary details`/`summary` reuses the identical +/− pattern as the lesson `<details>` CSS above.)

**Support Resources table** — identical structure in all five hubs (Claude / Claude Docs / Claude Support, 3 rows), same `.glossary` styling.

Module hubs also carry a "Lessons in this module" card list before the glossary, and an "Up next" gradient card after Support Resources pointing at the next module — absent only on the *current* last module's hub (Module 4's, as of this writing).

**Module identity colors, updated for all 4 modules:** `01` AI Foundations = `accent-cyan`; `02` Setting Up Your Computer = `os-tertiary` (muted, signals optional); `03` Claude Code = `accent-purple`; `04` Automating Workflows with Claude Code = `os-primary`/white. The white identity color and `04` numeral both carried over unchanged from the pre-merge Module 5 (see §12) — only the module's position/number changed, not its color, to minimize churn. `accent-teal`, previously Module 4's identity color before the merge, is no longer used as a module numeral color at all (it remains in the Tailwind config and is still used elsewhere as a general secondary-highlight accent per the Design System Guide, just not tied to a module identity anymore). Module colors deliberately don't use `accent-amber` — the Design System Guide reserves amber for `callout-warning` only. These colors apply only to the module numeral/badge (in the course-menu dropdown, course-index cards, and each module's own hero numeral) — lesson step-num badges stay the standard cyan variant regardless of module, except `module-3/lesson-1.html`'s purple/oversized exception noted above.

**The "terminal module" markers migrate forward each time a module is appended (or renumbered)** — this is now an established, expected part of the ingestion process, not a one-off fix: when Module 3 was the last module, its hub had no "Up next" card and its one lesson's closing card read "Course complete" with a "Back to Course Home" nav button. When Module 4 was added, Module 3's hub gained an "Up next" card pointing at Module 4, and its lesson's closing card/nav changed to "Module 3 complete" / "Next: Module 4". After the Module 3/4 merge and Module 5→4 renumber (§12), the terminal module is the new Module 4 (still "Course complete", no forward pointer — same content as old Module 5's, just renumbered) — the same migration will need to happen to it whenever a new module is eventually added after it.

### Relative link/path conventions

Strictly depth-based (`../` count = directory levels to the target):
- **Course index** → root: `../index.html`, `../blog/index.html`. → module hubs: `module-N/index.html` (bare, same level).
- **Module hubs** → root: `../../index.html`. → course index: `../index.html`. → own lessons: `lesson-N.html` (bare). → other modules: `../module-M/...`.
- **Lessons** → root: `../../index.html`. → own module hub: `index.html` (bare). → sibling lessons: `lesson-N.html` (bare). → other modules: `../module-M/...`.

File-to-file links within the same directory are always bare filenames, never `./`-prefixed. Applied with no exceptions across all 27 files. Once the planned `es/` locale mirror exists, these hardcoded relative paths (especially inside the course-menu dropdown) will need to become locale-aware — see root `CLAUDE.md`'s i18n section.

---

## 6. Styling Quick-Reference

**Palette:**

| Token | Hex | Usage |
|---|---|---|
| `os-deep` | `#0A0F1C` | Page background |
| `os-surface` | `#111827` | Card/section backgrounds, dropdown panel bg |
| `os-surface-light` | `#1F2937` | Defined, but **unused** in this course (see §7) |
| `os-primary` | `#FFFFFF` | Primary text/headings |
| `os-secondary` | `#9CA3AF` | Body text |
| `os-tertiary` | `#6B7280` | Meta text, tags |
| `accent-cyan` | `#00F0FF` | Primary actions, active states, `callout-tip` |
| `accent-teal` | `#00C2D1` | Secondary highlights, `callout-note` |
| `accent-purple` | `#7B2CBF` | Data accents, `callout-info` border (label text uses lighter `#B18CE0`), Module 3's step-num theme and module-numeral color |
| `accent-amber` | `#FBBF24` | `callout-warning` only — deliberately never repurposed as a module-identity color |

**Module identity colors** (numeral/badge only, not step-nums): `01`=`accent-cyan`, `02`=`os-tertiary`, `03`=`accent-purple`, `04`=`os-primary`/white.

**Fonts:** Space Grotesk (`font-display`, headings/step-nums), Inter (`font-body`, body text — default), JetBrains Mono (`font-mono`, tags/metadata/labels/code). All via Google Fonts `<link>`, weights `500;600;700` / `400;500;600` / `400;500` respectively.

**Cards:** `rounded-2xl`, `bg-white/5 backdrop-blur-md border border-white/10`, hover `hover:-translate-y-1 hover:shadow-[0_8px_30px_rgba(0,240,255,0.1)]`.

**Key component classes** (as of §10's CSS extraction, defined once in `assets/css/custom.css` and shared by every page — no longer per-page inline): `.step-num` (+ `.lesson-body--lg` modifier, used only on `module-3/lesson-1.html`), `.callout`/`.callout-{tip,note,info,warning}` (all four always available now), `.checklist-item`/`.checklist-box`, `.glossary` (table/details), `.toc-pill` (markup usage still only in `module-3/lesson-1.html`, but the rule itself is now defined globally), `.col-2`, `.fade-up`/`@keyframes fadeInUp`, `.bg-grid`.

For the complete, authoritative visual system (anti-slop rules, motion rules, full component vocabulary beyond the course), see `Design-System-Guide.md` in this same folder — this section is a condensed cheat sheet, not a replacement.

---

## 7. Known Inconsistencies to Watch For

These don't currently break anything, but copying from the "wrong" example page will propagate them. Worth normalizing on a future cleanup pass.

- **`os-surface-light` (`#1F2937`) is defined in every page's Tailwind config but never actually used as a class anywhere in the 27 files.** Dead config value, carried by copy-paste.
- **Docs/support link domain drift** — three variants for the same two links across pages:
  - `code.claude.com/docs` + `support.claude.com` — most pages (Module 1 hub/lessons 1–3, `module-2/lesson-3.html`, Module 3 hub/lesson, and **all of Module 3's lessons 3.2–3.7 (originally Module 4) and the new Module 4 (originally Module 5)**)
  - `docs.claude.com/docs` + `support.claude.com` — `module-1/lesson-4.html`, `module-2/index.html`, `module-2/lesson-1.html`
  - `docs.anthropic.com/claude/docs` + `support.anthropic.com` — **only** `module-2/lesson-2.html`, the sole page still on the legacy `anthropic.com` domain. This one is stale relative to the rest of the site and should be updated to match the others on next touch.
- ~~**`module-1/lesson-1.html`'s meta badge reads "STEP 1 OF 5"**~~ **RESOLVED** (see §10) — fixed to "STEP 1 OF 4" during the CSS extraction pass.
- **The "STEP N OF N" badge only exists in Module 1's four lessons.** Module 2 and 3 lessons use a time + status-tag pattern instead (e.g. `5 MIN` / `OPTIONAL`, `75–90 MIN` / `REQUIRED`), and Modules 4/5 also use the time+status pattern (see the entry below this one). This looks like an intentional-but-undocumented divergence between module "sub-templates" — treat it as a per-module decision, not a bug to unify, unless the user says otherwise.
- **Progress-pill markup style diverges once:** every lesson inlines the full Tailwind utility string on each `<a href="#step-N">` pill except `module-3/lesson-1.html`, which factors it into a dedicated `.toc-pill` class. Functionally identical, and now that `.toc-pill`'s rule lives in the shared `assets/css/custom.css` (§10) it's trivially available to any future page — but the *markup pattern itself* (inline utilities vs. the `.toc-pill` class) still isn't unified, so still check which convention the page you're copying from uses.
- ~~**`<ol>` styling done two different ways**~~ **RESOLVED** (see §10) — standardized on the dedicated `.lesson-body ol`/`li::marker` CSS rule (now in `assets/css/custom.css`); `module-1/lesson-1.html`'s inline-utility-class `<ol>` was converted to a bare `<ol>` to match.
- ~~**Callout CSS block isn't uniformly "define all 4 variants always"**~~ **RESOLVED** (see §10) — moot now that all four variants are defined once in the shared `assets/css/custom.css` and available on every page regardless of which variants that page's body actually uses.
- **The Module 1 "STEP N OF N" badge bug was not propagated forward.** When Modules 4 and 5 were built, the badge convention was deliberately standardized on Module 3's time+status pattern (`{N} MIN` / `REQUIRED`) rather than Module 1's `STEP N OF N` pattern (which §7's earlier entry flags as buggy — `module-1/lesson-1.html` still incorrectly reads "STEP 1 OF 5"). Modules 2, 3, 4, and 5 all use the time+status pattern; only Module 1 uses the step-count pattern. If normalizing this later, treat Module 1 as the outlier to fix, not the other four.
- **The `.fade-up` + IntersectionObserver duplication bug documented in root `CLAUDE.md` cannot currently occur anywhere in this course** — there is no `IntersectionObserver` in any of the 27 files (confirmed still true after Modules 4/5, which copied the identical menu-toggle-only trailing `<script>` verbatim). Every `.fade-up` use is the static, load-once variant, including on hub-page card grids (which use staggered inline `style="animation-delay: 0.05s"` etc. instead of scroll-triggering). This is worth knowing explicitly: don't go looking for that bug here, but if a future page adds a scroll-triggered observer to a shell that still carries static `.fade-up` classes on grid items, that's exactly when the described failure mode would first appear.

---

## 8. Future Lesson-Ingestion Checklist

Starting point: a new `M-L_Title.md` file has been (or needs to be) written in `assets/docs/ai-for-friends/`.

1. **Clean the source markdown.** Strip any stray `[cite: N]` artifacts (see §3). Verify internal cross-links point at the actual filenames on disk, not idealized/typo-corrected ones.
2. **Map directives to HTML** using the lookup table in §4 as you go, rather than improvising new markup patterns.
3. **Copy the page shell verbatim** from the nearest existing same-type page — another lesson for a lesson, another module hub for a hub (§5). Don't reinvent the `<head>`, base `<style>`, header/nav, footer, or menu-toggle script.
4. **Update page-specific content:** `<title>`/meta description, breadcrumb, `<h1>`/dek, meta badges, progress pills (one `<a href="#step-N">` per `<h2 id="step-N">`), sequential `step-num` values, callout variants chosen deliberately (not defaulting to `callout-info`), verification checklist items that are concrete and lesson-specific (2–4 items).
5. **Wire navigation:** set the course-menu dropdown's active-row highlight on the new page; add/update the prev/next nav bar on the new page *and* on its immediate neighbors (this has no single source of truth — three files need touching for one new lesson mid-sequence).
6. **Update the module hub:** add the new lesson to its "Lessons in this module" table, and to the Key Concepts glossary if it introduces new core terms.
7. **Make a conscious choice on the two divergent conventions** flagged in §7 (full vs. trimmed callout CSS block; inline-utility vs. `.toc-pill`-class progress pills; `<ol>` styling method) rather than silently propagating whichever one happened to be in the page you copied from.
8. **Preview locally before pushing** — `python3 -m http.server 8934` from the repo root, then check the new page and its immediate neighbors (progress pills scroll correctly under the fixed header, callouts render, dropdown highlights the right lesson). Root `CLAUDE.md` notes that `git push` to **any** branch deploys straight to production S3 with `--delete` — there's no staging environment, so this local check is the only gate before go-live.

    **If a Spanish `es/` mirror exists (see §13) when you add a new lesson**, budget for a second translation pass — the new English lesson has no Spanish counterpart yet, and the new lesson also needs to be added to the course-menu dropdown of all 26+26 = 52 files (English and Spanish), not just the English 26.
9. **A new module means editing every existing HTML file, not just the new module's own pages.** Adding Module 4/5 required updating the course-menu dropdown in all 12 pre-existing files (every Module 1–3 hub and lesson, plus the course index) to list the new module and its lessons — the dropdown is copy-paste-identical shell content, so it drifts out of sync with reality the moment a module is added unless every file is touched. Budget for this — it's the single largest share of the update work, larger than building the new module's own pages.
10. **The previously-last module needs "un-terminaling."** Before this batch, Module 3 was the last module: its hub had no "Up next" card, and its lesson's closing card read "Course complete" with nav pointing at "Back to Course Home." Adding Module 4 required going back and adding an "Up next" card to Module 3's hub, and changing its lesson's closing card to "Module 3 complete" with nav pointing at "Next: Module 4." The same edit will be needed on Module 5 whenever a Module 6 is added — check the current last module's hub and final lesson specifically, don't assume only new files need touching.
11. **Recompute the course index's totals by hand.** `ai-for-friends/index.html`'s hero badges (module count, lesson count, total hours) and its "How to Use This Course" tip grid don't update automatically — sum each module's stated lesson count and duration range from its hub page, and add a tip to the grid if the new module needs one (e.g. Modules 4/5 got a combined 4th tip; the grid's column count was changed from 3 to 2 to fit it cleanly as a 2×2 layout).

---

## 9. Page Cleanup Tips

The suggestions below were originally framed as things to *decide on*. The CSS-extraction idea (first bullet) has since been decided and **executed** — see §10 for the full writeup of what actually changed. The remaining bullets are still open decisions, not changes already made.

**The central tension** that motivated writing this section in the first place: the Design System Guide's anti-slop rule #6 states single-file delivery is a hard constraint — "all HTML, CSS, and JS delivered in a single `.html` file per page." The CSS extraction below is a deliberate, explicit exception to that rule, made by the user with the tradeoff visible beforehand — not a quiet architecture change. The still-open ideas below carry the same tension and shouldn't be adopted without an equally explicit decision.

- ~~**Extract the repeated inline `<style>` block into a shared `assets/css/course.css`.**~~ **DONE** — see §10. (Landed at `assets/css/custom.css`, not `course.css` — naming picked by the user.) The original reasoning still holds as the record of *why*: the base styles and shared component CSS were near-identical across all 27 files with only small deliberate variations (Module 2's trimmed callout-variant sets, Module 3's oversized step-num, `module-3/lesson-1.html`'s `.toc-pill`/`.col-2`/`ol` rules), so a single shared file turns a 27-file propagation into a one-file edit.
- **Extract the course-menu dropdown's toggle `<script>` into `assets/js/course-menu.js`.** This script is byte-identical in every one of the 27 files (open/close/escape/click-outside logic for the `#course-menu-btn`/`#course-menu-panel` pair) — zero per-page variation, making it the safest candidate for extraction if any JS is extracted at all. Same single-file-delivery tradeoff as the CSS extraction above.
- **A middle path that respects single-file delivery: a local, unshipped generator script.** Rather than serving shared CSS/JS at runtime, a script (Node or Python, run manually before a deploy — not part of the GitHub Actions workflow) could assemble each page from a shared shell template plus a small per-page content file, then write out the final flat, fully self-contained HTML files exactly as they exist today. Authoring stays DRY (one shell to edit); what ships to S3 is still single-file per page, so the anti-slop rule holds. This is the most build-tooling-heavy option and would be a real scope decision, not a quick win.
- **A lint/consistency-check script**, independent of whether any extraction happens: a grep-based script that checks every `*.html` file's course-menu dropdown lists the current full set of modules/lessons (comparing against a small manifest, or just against one known-good file), and flags any file that's drifted. This batch's dropdown updates were done via 12 manual find-and-replace edits, checked by hand — a script would catch the next module addition's drift automatically instead of relying on careful review.
- **Normalize the two small inconsistencies already flagged in §7**, since they're low-risk, low-effort cleanups independent of any larger extraction decision: update `module-2/lesson-2.html`'s stale `docs.anthropic.com`/`support.anthropic.com` links to match the `code.claude.com`/`support.claude.com` domain used everywhere else, and either start using `os-surface-light` (`#1F2937`) somewhere deliberate or remove it from the Tailwind config across all 27 files to stop carrying dead config.
- **Pick one *markup* convention for progress pills** (inline Tailwind utilities vs. the `.toc-pill` class) and apply it as the default for all future pages. The `<ol>` half of this bullet is now resolved (§10 standardized on the `.lesson-body ol` CSS rule everywhere) — this bullet now only covers the still-open progress-pill markup fork, so the shell doesn't keep quietly forking into more variants as the course grows.

---

## 10. CSS Extraction & Consolidation (Completed)

This section documents a change actually made to the codebase — unlike §9, which is a list of options still awaiting a decision. The user decided to extract the course's shared CSS out of each page's inline `<style>` block and into one file, and asked for two already-documented bugs to be fixed in the same pass.

### What changed

**New file: `assets/css/custom.css`.** Contains every shared CSS rule the 27 course pages use: base resets (`html`/`body`, `.font-display`/`.font-mono`, `.bg-grid`, `@keyframes fadeInUp`/`.fade-up`, `::selection`, focus-visible, reduced-motion), `.lesson-body` typography (`h2`/`.step-num`, `h3`, `p`, `table`/`th`/`td`, `strong`, `ol`, `ul.plain`), all four `.callout-{tip,note,info,warning}` variants (always defined now, unconditionally), `.lesson-body details`/`summary`, `.lesson-body pre`, `.checklist-item`/`.checklist-box`, `.col-2`, `.toc-pill`, and `.glossary` (table/details, used on hub pages). Organized top-to-bottom in that order with section-comment dividers.

**Every one of the 27 pages** (course index, 5 module hubs, 21 lessons) had its inline `<style>...</style>` block removed and replaced with a single stylesheet link in the same position (right after the Google Fonts `<link>`, before `</head>`):
```html
<link rel="stylesheet" href="../assets/css/custom.css">    <!-- ai-for-friends/index.html -->
<link rel="stylesheet" href="../../assets/css/custom.css"> <!-- everything under module-N/ -->
```
**Explicitly out of scope for this extraction**: the Tailwind CDN `<script>` + inline `tailwind.config` block, and the trailing course-menu-toggle `<script>`. Both remain inline, byte-identical, on every page — only the raw CSS was moved. This was a deliberate scope decision (the ask was specifically about not wanting to see a `<style>` block at the top of each file), not an oversight; extracting the JS/Tailwind-config too is still an open option, tracked in §9's second bullet.

**Design-note on the anti-slop "single-file delivery" rule:** this extraction is a knowing, explicit exception to that rule, made by the user with the tradeoff already visible from §9's writeup — not a silent architecture drift. Future pages added to this course should link `assets/css/custom.css` the same way rather than reverting to inline `<style>` blocks, unless the user decides otherwise.

### Resolving page-specific CSS variance

Before extraction, a few pages had CSS that genuinely differed from the norm — these needed a real decision, not just a copy-paste into one file:

- **`module-3/lesson-1.html`'s oversized, purple-tinted step headings** (`.lesson-body h2` at `1.7rem` with a `2.1rem` purple step-num badge, vs. the standard `1.5rem`/`2rem` cyan) were the one piece of page-specific visual identity that couldn't just be merged into a single shared rule without either erasing that page's distinct look or making every page's headings bigger. Resolved by adding a **new modifier class, `.lesson-body--lg`**, to `custom.css` (scoped as `.lesson-body.lesson-body--lg h2` / `.lesson-body.lesson-body--lg h2 .step-num`) and adding that class to `module-3/lesson-1.html`'s single `<div class="lesson-body ...">` wrapper. One-line markup change, page keeps its original look, no inline override needed.
- **Table sizing had two near-identical "flavors"** — `.lesson-body table`/`th`/`td` at `0.9rem`/`0.7rem` font-size (majority, 18 files, module-1's original convention) vs. `0.88rem`/`0.68rem` (3 files: `module-3/lesson-1.html`, `module-4/lesson-6.html`, `module-5/lesson-3.html`). Standardized on the majority (`0.9rem`/`0.7rem`) as the one rule in `custom.css` — a negligible size difference on the 3 minority files, well within "unify for consistency."
- **Module 2's "only define the callout variants actually used" convention** and **Module 1/3's "define all four always" convention** are both moot now — `custom.css` defines all four unconditionally, so every page gets full callout support regardless of which variants its own body happens to use.
- **`.col-2` and `.toc-pill`**, previously scoped CSS living only in the files that used them (`module-3/lesson-1.html` for both; `.col-2` also in `module-1/lesson-2.html`, `-3.html`, `-4.html`, and `module-4/lesson-1.html`, `-4.html`), are now defined once, globally — inert on pages that don't reference the class in their markup.

### The two bug fixes made in the same pass

- **`module-1/lesson-1.html`'s "STEP 1 OF 5" → "STEP 1 OF 4".** Confirmed via grep that no other file has the same "OF 5" typo, and that siblings `lesson-2.html`/`-3.html`/`-4.html` already correctly read "OF 4".
- **`<ol>` styling fork resolved.** `custom.css` carries the single `.lesson-body ol`/`li::marker` rule (the convention already used by 20 of the 21 lesson files). `module-1/lesson-1.html` — the one file that instead inlined `class="space-y-2 pl-5 list-decimal text-os-secondary marker:text-accent-cyan marker:font-mono"` directly on its `<ol>` tags — had that class attribute removed, so it now renders via the shared rule like every other lesson.

### Verification performed

- `grep -rl '<style>' ai-for-friends/` returns no files.
- Every file under `ai-for-friends/` (course index, hubs, lessons) links `assets/css/custom.css` at the correct relative depth for its location.
- `grep -rn 'OF 5' ai-for-friends/` and `grep -rn 'list-decimal' ai-for-friends/` both return nothing.
- `.lesson-body--lg` appears in exactly one file, `module-3/lesson-1.html`.
- Visual spot-check in a browser (course index, each module hub, `module-1/lesson-1.html`, `module-3/lesson-1.html`, one Module 4 and one Module 5 lesson) confirmed no unstyled-flash or broken layout, all four callout variants render correctly, and the course-menu dropdown still opens/closes/highlights correctly post-extraction.

---

## 11. Windows/Mac Parity (Completed)

The course's setup/install content was originally authored Windows-only. A full-course survey confirmed the scope was Module 2 (entirely Windows-scoped), Module 3 Lesson 1 (dense PowerShell-only install content), and Module 5's four "run it automatically" scheduling steps (Lessons 5.3, 5.5, 5.6, 5.7). Modules 1 and 4 have no OS-specific content and were untouched. This section documents the convention adopted so future lessons stay consistent.

### The convention: labeled subsections, no new UI

Per an explicit user decision, Windows/Mac distinctions use **plain bold-label subsections** — a `<p class="!mb-2 text-os-primary font-semibold text-sm">Windows</p>` / `...Mac</p>` pair, each followed by its own `<ol>`/`<pre>` — rather than a tabs or toggle widget. No new CSS or JS was added; this reuses the existing `.col-2` "Always/Never" label styling already in `custom.css`. In markdown sources, the equivalent is a bold `**Windows**` / `**Mac**` line, or a `### Instructions — Windows` / `### Instructions — Mac` heading split when the step already used a heading.

**When to split vs. inline:** full Windows/Mac subsections are reserved for genuinely multi-step sequences that diverge (installers, the install script, cron vs. Task Scheduler). A single differing keyboard shortcut or path gets an inline parenthetical instead, e.g. `Ctrl+Shift+X (Windows) / Cmd+Shift+X (Mac)`, or `(same on Windows and Mac)` when nothing actually differs — never fabricate a difference where none exists (confirmed identical: `Ctrl+C`, `Shift+Tab`, `Ctrl + `` `` for the integrated terminal, `pwd`/`cd`/`cd ..`).

### What changed, by module

- **Module 2 — "Setting Up Your Computer"**: reframed from Windows-only to Windows-and-Mac. Lesson 2.1 ("Installing Windows Terminal") is the one lesson that stays genuinely Windows-only — Mac ships with Terminal.app pre-installed, so there's nothing to install — and now opens with a callout directing Mac readers straight to Lesson 2.2. Its previously **empty** markdown source (`2-1_Installing_Windows_terminal.md`, flagged in §2/§3 as a known gap) was written from scratch in the same pass, since the lesson had to be touched anyway. Lessons 2.2 (VS Code install) and 2.3 (terminal navigation) got full Windows/Mac subsections and parenthetical path/shortcut equivalents. The hub's Key Concepts glossary was updated to note Windows-vs-Mac distinctions inline rather than deleting the Windows-specific terms.
- **Module 3, Lesson 3.1** (the required Claude Code onboarding guide): the largest single change. VS Code install, Claude Code install (`irm ... | iex` on Windows vs. `curl -fsSL https://claude.ai/install.sh | bash` on Mac), the Git prerequisite (Git for Windows vs. macOS's Xcode Command Line Tools, triggered by running `git --version`), the troubleshooting table, the "other terminals" table, and the six-commands table all got Mac rows/subsections. The module hub's glossary (PowerShell, PATH, Git for Windows, Integrated Terminal entries) was updated to note the Mac equivalent instead of reading as Windows-only.
- **Module 5, Lessons 5.3/5.5/5.6/5.7**: each lesson's "Optional — Run It Automatically" step got a parallel **Mac** path using `cron` (`crontab -e`, standard cron syntax, saved via the default `nano` editor) alongside the existing Windows Task Scheduler path, plus a callout about macOS's Privacy & Security → Full Disk Access requirement — cron jobs silently no-op without it, the most common real-world gotcha, called out with the same platform-friction honesty the Windows steps already used for Defender/SmartScreen. Each lesson's "Turning It Off" step got a matching Mac line (delete/comment the crontab entry). Lesson 5.3 additionally got a Mac equivalent for its Windows-dictation mention (`Win+H` → macOS System Settings → Keyboard → Dictation, default trigger is pressing Fn twice).
- **Site-wide badges**: the course index (`ai-for-friends/index.html`) and Module 3's hub badge pill changed from "Windows" to "Windows & Mac". Module 2's badge and prerequisites were updated the same way as part of its own pass.

### Verification performed

- `grep -rn "Windows only|WINDOWS ONLY|Windows-only" ai-for-friends/ assets/docs/ai-for-friends/` returns only the intentionally-scoped hits: Module 2 Lesson 2.1 (genuinely Windows-only — no Mac install step exists) and the Module 3 troubleshooting table's Defender/SmartScreen row (genuinely Windows-only warning).
- Every "Optional — Run It Automatically" step in Module 5 (5.3, 5.5, 5.6, 5.7) has both a Windows and a Mac path, each with its own scheduled-command block and a Full Disk Access callout on the Mac side.
- Every markdown source edited in this pass has its HTML counterpart mirrored 1:1, keeping the manual conversion pipeline (§4) in sync — no source drifted ahead of or behind its rendered page.

---

## 12. Module 3/4 Merge and Module 5 → 4 Renumber (Completed)

The course originally had two adjacent modules that read as an awkward split from a learner's seat: Module 3 ("Claude Code") had exactly one lesson (the CLI install/onboarding guide), then the course jumped into Module 4 ("Building Your AI Personal Assistant"), six lessons entirely about a different product surface — claude.ai's web "Projects" feature — whose own copy explicitly called itself *"a deliberate detour"* from Claude Code. The user asked for these to be collapsed into one continuous "Claude Code" module: install it, then keep going into Projects. Module 5 ("Automating Workflows with Claude Code") then simply became the new Module 4.

### What changed

- **Module 3 is now 7 lessons** (3.1–3.7): 3.1 is unchanged (the install guide). 3.2–3.7 are the six former Module 4 lessons, absorbed with renumbered metadata, breadcrumbs, prev/next nav, in-body cross-references, and course-menu dropdown entries. The old Module 4 hub (`module-4/index.html` / `4-0_Claude_Code_Projects.md`) was deleted — its content (lessons table, Key Concepts glossary, badges) was merged directly into `module-3/index.html` / `3-0_Claude-Code.md`. The merged hub's target-roles badge now includes International Relations (previously missing from Module 3's own badge despite 3.1's meta description already listing it — a small pre-existing inconsistency fixed in the same pass).
- **The old Module 5 became the new Module 4**, a straight renumber (5.1–5.7 → 4.1–4.7) with no content changes beyond the numbering itself and its cross-references — including fixing its own cross-references to the old Projects module, which now correctly point at Module 3 (e.g. "Lesson 5.4" citing the old Module 4's reference-material lesson now reads "Lesson 3.4").
- **Two-directional renumbering was the main risk** throughout this pass: files becoming the new Module 3 lessons had to convert self-references (old "Module 4" → "Module 3") while also correctly handling references to the automation module (old "Module 5" → new "Module 4"); files becoming the new Module 4 lessons had the mirror problem (self-references "Module 5" → "Module 4", while references to the old Projects module "Module 4" → new "Module 3"). Getting these two directions crossed was the single biggest correctness risk in the whole pass and was checked explicitly in every file's verification grep.
- **Editorial framing fix**: `module-3/lesson-1.html`'s closing card previously read "Module 3 complete" and treated finishing the install guide as the end of the module, handing off to "Module 4" as a separate thing. Since installing Claude Code is now just the first of seven lessons in the same module, this was rewritten to "Installation Done" with a lighter transition into 3.2, and its "Next" nav now points at `lesson-2.html` instead of the old module boundary.
- **File moves** used `git mv` throughout to preserve history. HTML: `module-4/lesson-1.html`–`lesson-6.html` → `module-3/lesson-2.html`–`lesson-7.html`; `module-4/index.html` deleted; `module-5/index.html` and `lesson-1.html`–`lesson-7.html` → `module-4/index.html` and `lesson-1.html`–`lesson-7.html`. Markdown: `4-1_Claude_Code_Project_Basics.md`–`4-6_Examples_by_Role.md` → `3-2_Claude_Code_Project_Basics.md`–`3-7_Examples_by_Role.md`; `4-0_Claude_Code_Projects.md` deleted; `5-0_Claude_Code_Workflows.md`–`5-7_Content-Generation.md` → `4-0_Claude_Code_Workflows.md`–`4-7_Content-Generation.md`.
- **Course-menu dropdown scrollability**: separately from the merge, the dropdown panel (`#course-menu-panel`, duplicated verbatim across all 26 files) had no `max-height`/`overflow` constraint at all — at 4–5 modules and 21 lessons it could already run off the bottom of a shorter viewport with no way to reach the last module's lessons. Fixed by adding `max-h-[calc(100vh-6rem)] overflow-y-auto` to the panel's class list, applied everywhere the dropdown itself was already being touched for the renumber (all 26 files).
- **A pre-existing bug caught during the merge**: `git mv` renames a file but does not touch its content, so the absorbed lessons' internal prev/next hrefs (which pointed at sibling files by their *old* filenames, e.g. `module-4/lesson-1.html`'s "Next" pointing at `lesson-2.html`) silently broke the moment the files landed at their new `module-3/lesson-N.html` paths with shifted numbering. This was caught and fixed during verification, not assumed correct from the file move alone — worth remembering for any future lesson renumber or reorder: **a file move never fixes the content inside the file**, hrefs and lesson-number text both need independent verification after any `git mv`.
- **Module identity color**: the new Module 4 kept its original white/`os-primary` identity color (inherited unchanged from the old Module 5) rather than being reassigned — minimizes churn since that color is already baked into every one of its files' numeral/badge classes. `accent-teal`, the old Module 4's color, is now unused as a module identity but remains available as the Design System Guide's general secondary-highlight accent.
- **Course index and docs**: `ai-for-friends/index.html`'s hero stats (modules 5→4, lesson count unchanged at 21, total hours unchanged at ~6.5 since the math redistributes rather than removes content), module card grid (merged 03+04 card, renumbered 05→04), and "How to Use This Course" tip copy were all updated. Root `CLAUDE.md`'s course description — already stale before this change (still described the pre-Module-4/5 3-module course) — was corrected to the current 4-module, 26-file state in the same pass (see its own diff for detail; not duplicated here).

### Verification performed

- `grep -rn "module-5\|Module 5"` across `ai-for-friends/` and `assets/docs/ai-for-friends/` returns nothing — the old Module 5 identity is fully gone, only the new Module 4 (same content) remains.
- `grep -rn "Lesson 4\.[1-6]\b"` (old meaning, Projects lessons) and `grep -rn "Lesson 5\.[1-7]\b"` (old meaning, automation lessons) both return nothing — every hit was either correctly renumbered or, where "Lesson 4.X"/"Module 4" legitimately now refers to the *new* Module 4 (automation), manually confirmed correct for its new meaning rather than assumed.
- File counts: 26 total HTML files under `ai-for-friends/` (was 27); `module-3/` has 8 files (index + 7 lessons), `module-4/` has 8 files (index + 7 lessons); `module-5/` no longer exists on disk.
- Full prev/next navigation chain manually verified end to end: 3.1 → 3.2 → 3.3 → 3.4 → 3.5 → 3.6 → 3.7 → Module 4 hub, with no broken or self-referencing links.
- Browser check (local `python3 -m http.server`, Claude in Chrome) confirmed: the course-menu dropdown's Mac-skip callout, Module 3's merged 7-lesson table, and Module 4's renumbered scheduling step all render correctly with no layout issues, and the dropdown scrolls correctly at a constrained viewport height.

---

## 13. Spanish (`es/`) Mirror (Completed)

The course's i18n scaffolding (the disabled "EN · ES" pill, documented in root `CLAUDE.md`) was activated: all 26 English pages now have a real, complete Spanish translation at `es/ai-for-friends/**` (52 HTML files total on disk for this course). Scope was the course only — `index.html` and `blog/` remain English-only; their nav links from Spanish course pages point at the English originals (no dead links, matches the documented gradual-rollout convention).

**Governing reference**: `assets/docs/references/ES-Translation-Style-Guide.md` — voice (tú), the full EN/ES glossary (what stays in English — Claude Code, Prompt, model names, CLI commands, product/OS UI names — vs. what translates normally — Agent→Agente, Context window→Ventana de contexto, MCP Server→Servidor MCP), the path-rewriting rules per page depth, and the EN/ES pill + hreflang wiring pattern. Read this before touching any `es/` file or adding a new English lesson that needs a Spanish counterpart.

### What changed

- **New tree**: `es/ai-for-friends/index.html` + `module-{1,2,3,4}/index.html` + `module-{1,2,3,4}/lesson-*.html` — 26 new files, same filenames and nesting as the English tree, one `es/` ancestor deeper. HTML structure (classes, ids, Tailwind config, the course-menu-toggle script, all SVGs) copied byte-for-byte from each English source; only text nodes, `<title>`, and meta description/title were translated.
- **All 26 English files** got two small additions — the previously-inert `ES` pill span became a real link to its Spanish counterpart, and an `<link rel="alternate" hreflang="...">` triple (en/es/x-default, absolute URLs) was added to `<head>`. Nothing else in the English files changed — verified via `git diff --stat` showing an identical `5 ++++-` diff on every one of the 26 files.
- **Every one of the 52 files'** course-menu dropdown lists all 4 modules/21 lessons in the page's own locale, with correct active-row highlighting per page. Internal course links (sibling lessons, own module hub, other modules) needed **no path change** between locales — only links escaping `ai-for-friends/` (root `index.html`, `blog/`, `assets/css/custom.css`) needed one extra `../` for the added `es/` ancestor.
- **Structural outliers translated as-is, not normalized**: `module-3/lesson-1.html`'s 0-indexed/purple `.lesson-body--lg` styling and `module-4/lesson-3.html`'s 0-indexed-but-standard-styling were both preserved exactly in their Spanish counterparts. Windows/Mac split content (Module 2's setup lessons, `module-3/lesson-1.html`, `module-4/lesson-3.html`/`-5.html`/`-6.html`/`-7.html`) has both OS paths translated in full on the Spanish side too.

### Execution method (for repeating this on a future new lesson)

One lesson (`module-1/lesson-1.html`) was translated and browser-verified by hand first, as the concrete tone/pattern reference. The remaining 25 files were split by module across 4 parallel agents, each given the style guide, the verified sample, and an explicit file list. **Important operational lesson**: background agents launched with `isolation: "worktree"` get a git worktree checked out from the last *commit* — they cannot see new, still-uncommitted files (the style guide and sample were both uncommitted at launch time). The first attempt at this had to be aborted and relaunched without worktree isolation for exactly this reason. If delegating a similar bulk-translation pass again, either commit the reference files first, or don't use worktree isolation for agents that need to read sibling uncommitted work.

### Verification performed

- File count: `find es/ai-for-friends -name "*.html" | wc -l` → 26.
- `grep -L '<html lang="es">'` across all 26 Spanish files → empty (all correct).
- Every Spanish file has exactly 3 `hreflang` occurrences (en/es/x-default).
- `assets/css/custom.css` link depth verified correct at both nesting levels (`../../` for the Spanish course index, `../../../` for Spanish module/lesson files).
- `git diff --stat -- ai-for-friends/` shows all 26 English files changed by the identical `5 ++++-` — confirms no unintended content drift.
- No leftover untranslated nav shell strings (checked for literal "Pillars"/"Course"/"Menu"/"Module N"/"Course Home" — none found; "Blog" is intentionally unchanged, an established Spanish loanword per the style guide).
- Browser check (local `python3 -m http.server`, Claude in Chrome): Spanish course index, the purple 0-indexed outlier (`module-3/lesson-1.html`), a Windows/Mac split lesson (`module-2/lesson-2.html`), and the terminal module's closing lesson (`module-4/lesson-7.html`, confirming "Curso completado" / "Volver al Inicio del Curso" framing with no fabricated next-module link) — all rendered correctly, EN/ES pill round-trip confirmed working in both directions, course-menu dropdown opens/closes/highlights correctly, no console errors.

### Open items flagged by the translating agents, not yet resolved

- **HR abbreviation**: "RR. HH." was used consistently across all 4 agents/modules (a good sign of convergence), but this wasn't a pre-set glossary entry — worth confirming this is the preferred convention before any further content is added.
- **Coined terms not in the original glossary**, used consistently within Module 3 but worth reviewing: Diff→"Diff" (kept), Plan Mode→"Modo Plan", Slash Command→"Comando Slash", Project Folder→"Carpeta del Proyecto", Plain Chat→"Chat Simple".
- **Code-block (`<pre>`) translation boundary**: natural-language content inside `<pre>` blocks (dictation scripts, sample digest output) was translated; literal artifacts (SKILL.md frontmatter, CLI confirmation strings, file paths) were left in English. This wasn't explicit in the style guide before this pass — now worth codifying there if it's the desired convention going forward.
