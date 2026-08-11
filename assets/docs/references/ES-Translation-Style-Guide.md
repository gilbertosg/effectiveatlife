# ES Translation Style Guide — "AI for Friends" course

**Purpose:** the single reference for translating `ai-for-friends/**/*.html` into its `es/ai-for-friends/**/*.html` mirror. Read this in full before translating or editing any page in either direction. Written so the same voice, glossary, and path conventions apply whether a human or an agent does the next file.

This guide governs **only** the `ai-for-friends/` course, per the scope decision behind this pass. `index.html` and `blog/` are not translated yet and have no `es/` counterpart — course pages' "Pillars" and "Blog" nav links point at the English originals for now (not a bug; CLAUDE.md's documented gradual-rollout convention).

---

## 1. Voice

**Tú, not usted.** Direct, coaching, second-person-singular-informal — matches the English course's own "you" tone and is standard for modern Latin American tech/educational content. Conjugate accordingly throughout (imperatives, possessives, etc.) — e.g. "Abre Claude hoy y aplica..." not "Abra Claude hoy y aplique...".

Keep sentences short and concrete, mirroring the English original's style — this is not a place to add flourish the source doesn't have. Translate meaning and tone, not word-for-word; restructure a sentence if a literal translation would read awkwardly in Spanish.

---

## 2. Glossary

### 2a. Keep in English, unchanged

Product/brand names, model names, CLI-literal commands, keyboard shortcuts, file/menu paths, and acronyms a Mexican professional would still type or see on-screen exactly as written, regardless of OS/app language:

| Term | Notes |
|---|---|
| Claude, Claude Code, Claude Pro, claude.ai, Anthropic | Brand/product names |
| Sonnet, Haiku, Opus | Model names |
| Prompt | Per explicit user guidance — do not translate to "instrucción"/"aviso" |
| Token | Common as-is in Spanish AI writing; no clean one-word equivalent |
| Skill, Plugin | Claude Code's own feature names, shown in-product in English |
| VS Code, Git, PowerShell, Terminal.app, Xcode Command Line Tools | Software/tool names |
| cron, crontab, Task Scheduler, Full Disk Access | OS feature names — course screenshots/instructions are English-UI; may gloss the Spanish OS label in parentheses on first mention per lesson if it aids clarity (e.g. "Task Scheduler (Programador de tareas)"), but the English name stays primary |
| All literal commands, code, file paths, keyboard shortcuts | e.g. `curl -fsSL https://claude.ai/install.sh \| bash`, `Ctrl+Shift+X`, `pwd`/`ls`/`cd` |
| All URLs | `code.claude.com/docs`, `support.claude.com`, `claude.ai`, etc. — never translate or re-host |
| MCP (as an acronym) | Keep "MCP" untranslated inside translated phrases, e.g. "servidor MCP" |

### 2b. Translate normally

Ordinary vocabulary and course-specific labels — translate to natural Spanish, consistently across all 26 files:

| English | Spanish |
|---|---|
| Agent | Agente |
| Model | Modelo |
| Generative AI | IA generativa |
| Knowledge Base | Base de conocimiento |
| Context window | Ventana de contexto |
| MCP Server | Servidor MCP |
| LLM / Large Language Model | LLM / Modelo de lenguaje extenso (LLM) — keep acronym, translate the spelled-out form |
| RAG / Retrieval Augmented Generation | RAG / Generación aumentada por recuperación (RAG) |
| Project *(claude.ai feature)* | Proyecto |
| Pillars (nav) | Pilares |
| Blog (nav) | Blog *(unchanged — established loanword)* |
| Course (nav) | Curso |
| Menu (nav) | Menú |
| Course Home | Inicio del curso |
| Module N | Módulo N |
| Lesson N.N | Lección N.N |
| Start Course / Start Module | Comenzar el curso / Comenzar el módulo |
| Next: ... | Siguiente: ... |
| Verification | Verificación |
| Related Resources | Recursos relacionados |
| Support Resources | Recursos de soporte |
| Key Concepts | Conceptos clave |
| Lessons in This Module | Lecciones de este módulo |
| Overview | Resumen |
| Who This Module/Course Is For | Para quién es este módulo/curso |
| Why This Matters | Por qué es importante |
| Prerequisites | Requisitos previos |
| Time to Complete | Tiempo estimado |
| What's Next | Qué sigue |
| Optional | Opcional |
| Required | Obligatorio |
| STEP N OF N | PASO N DE N |
| N MIN | N MIN *(unchanged — universal abbreviation)* |
| Lesson complete / Module complete / Course complete | Lección completada / Módulo completado / Curso completado |
| Up next | A continuación |
| Troubleshooting | Solución de problemas |
| Windows, Mac | Unchanged — OS proper nouns |

When in doubt on a term not listed here: translate ordinary instructional prose; leave alone anything that is a literal product name, on-screen label, command, or URL.

---

## 3. Path-rewriting rules

`es/` sits as a new top-level sibling of `ai-for-friends/`. A page at `es/ai-for-friends/module-1/lesson-1.html` is **one directory deeper** than its English counterpart at `ai-for-friends/module-1/lesson-1.html`, but the nesting *within* the course tree is identical.

**Rule of thumb:** any link that already climbs out of `ai-for-friends/` (root `index.html`, `blog/`, `assets/css/custom.css`) needs **one extra `../`**. Any link that stays inside the course tree (sibling lesson, own module hub, other module, course index) is copied **unchanged** — same relative string, same target filename, it just now resolves one level deeper along with the page itself.

| From (Spanish page) | Link target | English original's href | Spanish page's href |
|---|---|---|---|
| `es/ai-for-friends/index.html` | `assets/css/custom.css` | `../assets/css/custom.css` | `../../assets/css/custom.css` |
| `es/ai-for-friends/index.html` | root `index.html` | `../index.html` | `../../index.html` |
| `es/ai-for-friends/index.html` | `blog/index.html` | `../blog/index.html` | `../../blog/index.html` |
| `es/ai-for-friends/index.html` | own module hub | `module-1/index.html` | `module-1/index.html` *(unchanged)* |
| `es/ai-for-friends/module-1/index.html` or `lesson-N.html` | `assets/css/custom.css` | `../../assets/css/custom.css` | `../../../assets/css/custom.css` |
| `es/ai-for-friends/module-1/...` | root `index.html` | `../../index.html` | `../../../index.html` |
| `es/ai-for-friends/module-1/...` | `blog/index.html` | `../../blog/index.html` | `../../../blog/index.html` |
| `es/ai-for-friends/module-1/...` | course index | `../index.html` | `../index.html` *(unchanged)* |
| `es/ai-for-friends/module-1/...` | sibling lesson / own hub | `lesson-2.html` / `index.html` | *(unchanged)* |
| `es/ai-for-friends/module-1/...` | another module | `../module-2/index.html` | *(unchanged)* |

This means the **course-menu dropdown's internal links need zero rewriting** — only its visible label text gets translated. The only hrefs that change are the header logo, "Pillars", "Blog", and the `assets/css/custom.css` stylesheet link (one extra `../` each), plus the EN/ES pill (see §4).

---

## 4. Nav-wiring rules

### EN/ES pill

Original (inert) markup, present verbatim on all 26 English pages:
```html
<div class="flex items-center gap-1.5 text-[10px] text-os-tertiary normal-case">
  <span class="text-accent-cyan font-semibold">EN</span>
  <span class="text-white/20">/</span>
  <span class="cursor-default" title="Spanish version — coming soon">ES</span>
</div>
```

**On the English original**, once its Spanish counterpart exists, replace the `ES` span with a real link. The `../` count equals the file's own nesting depth (how many directories it sits under repo root), then `es/ai-for-friends/...`, same filename. For a module/lesson file (nested 2 deep — `ai-for-friends/module-N/`):
```html
<div class="flex items-center gap-1.5 text-[10px] text-os-tertiary normal-case">
  <span class="text-accent-cyan font-semibold">EN</span>
  <span class="text-white/20">/</span>
  <a href="../../es/ai-for-friends/module-1/lesson-1.html" class="hover:text-accent-cyan transition-colors">ES</a>
</div>
```
The course index (`ai-for-friends/index.html`, nested only 1 deep) uses one fewer `../`: `../es/ai-for-friends/index.html`.

**On the Spanish page**, mirror it — `EN` becomes the real link (back to the English original), `ES` becomes the static active label. The Spanish file sits **one directory deeper** than its English counterpart (the added `es/` ancestor), so its own nesting depth is one more: a Spanish module/lesson file is nested 3 deep, needing 3 `../` to reach root, then the plain `ai-for-friends/...` path (no `es/`):
```html
<div class="flex items-center gap-1.5 text-[10px] text-os-tertiary normal-case">
  <a href="../../../ai-for-friends/module-1/lesson-1.html" class="hover:text-accent-cyan transition-colors">EN</a>
  <span class="text-white/20">/</span>
  <span class="text-accent-cyan font-semibold">ES</span>
</div>
```
The Spanish course index (`es/ai-for-friends/index.html`, nested 2 deep) uses one fewer `../`: `../../ai-for-friends/index.html`.

**Rule of thumb, stated once to avoid the off-by-one this section previously had wrong:** count the slashes in the file's own path from repo root — that count is the number of `../` needed to reach root from that file, regardless of which locale it's in.

### hreflang

Once both locales exist for a page, add to **both** files' `<head>` (identical pair on each), using absolute URLs per SEO convention:
```html
<link rel="alternate" hreflang="en" href="https://effectiveatlife.com/ai-for-friends/module-1/lesson-1.html">
<link rel="alternate" hreflang="es" href="https://effectiveatlife.com/es/ai-for-friends/module-1/lesson-1.html">
<link rel="alternate" hreflang="x-default" href="https://effectiveatlife.com/ai-for-friends/module-1/lesson-1.html">
```
Place immediately after `<meta name="description">`. Do **not** add hreflang to `index.html` or `blog/` pages — they have no Spanish counterpart yet.

### `<html lang>`

English files keep `lang="en"`. Every Spanish file uses `lang="es"`.

---

## 5. File manifest (26 pairs)

| English source | Spanish target |
|---|---|
| `ai-for-friends/index.html` | `es/ai-for-friends/index.html` |
| `ai-for-friends/module-1/index.html` | `es/ai-for-friends/module-1/index.html` |
| `ai-for-friends/module-1/lesson-1.html` … `lesson-4.html` | `es/ai-for-friends/module-1/lesson-1.html` … `lesson-4.html` |
| `ai-for-friends/module-2/index.html` | `es/ai-for-friends/module-2/index.html` |
| `ai-for-friends/module-2/lesson-1.html` … `lesson-3.html` | `es/ai-for-friends/module-2/lesson-1.html` … `lesson-3.html` |
| `ai-for-friends/module-3/index.html` | `es/ai-for-friends/module-3/index.html` |
| `ai-for-friends/module-3/lesson-1.html` … `lesson-7.html` | `es/ai-for-friends/module-3/lesson-1.html` … `lesson-7.html` |
| `ai-for-friends/module-4/index.html` | `es/ai-for-friends/module-4/index.html` |
| `ai-for-friends/module-4/lesson-1.html` … `lesson-7.html` | `es/ai-for-friends/module-4/lesson-1.html` … `lesson-7.html` |

Same filenames, same nesting — only the `es/` ancestor is new.

**Two structural outliers to translate carefully, not skip or simplify:**
- `module-3/lesson-1.html` — 0-indexed steps (`step-0`–`step-5`), oversized purple `.lesson-body--lg` step-num styling, plain numbered-section structure (no `HERO`/`PROGRESS`/`CELEBRATION` scaffolding the other lessons have). Translate content only — do not "fix" it to match the standard lesson shape.
- Windows/Mac split lessons (`module-2/lesson-1.html`–`lesson-3.html`, `module-3/lesson-1.html`, `module-4/lesson-3.html`/`-5.html`/`-6.html`/`-7.html`) — translate both the Windows and Mac subsections; do not drop either.

---

## 6. What never changes

Copy byte-for-byte, no translation, no restructuring: every class, `id`, `data-*` attribute, the Tailwind config `<script>`, the trailing course-menu-toggle `<script>`, the `assets/css/custom.css` link tag itself (only its `href` depth changes per §3), all SVG markup, and the footer's structure (only its Spanish text changes — see below).

Footer tagline translates like any other body text: "You do not rise to the level of your goals. You fall to the level of your systems." → "No te elevas al nivel de tus metas. Caes al nivel de tus sistemas." Copyright line: "© 2026 Effective at Life. Built as a system, not a slogan." → "© 2026 Effective at Life. Construido como un sistema, no como un eslogan."

---

## 7. Additional terms established during the first full pass

These weren't decided before the course's 26 files were translated; they emerged consistently across independent translators and should be treated as settled for future lessons:

| English | Spanish | Notes |
|---|---|---|
| HR (role name) | RR. HH. (compact/label use) / Recursos Humanos (prose) | Converged independently across all 4 translators |
| Industrial Engineering | Ingeniería Industrial | |
| International Relations | Relaciones Internacionales | |
| Legal, Marketing | Legal, Marketing | Unchanged |
| Diff | Diff | Kept — common loanword in Spanish dev usage |
| Plan Mode | Modo Plan | |
| Slash Command | Comando Slash | |
| Project Folder | Carpeta del Proyecto | |
| Plain Chat | Chat Simple | |
| Pipeline | Flujo | e.g. "Content-Generation Pipeline" → "Flujo de Generación de Contenido" |

**Code block (`<pre>`) translation boundary**: translate natural-language content inside `<pre>` blocks (dictation scripts, sample tool output, prose the user would read) into Spanish; leave literal artifacts unchanged (SKILL.md frontmatter/body, CLI confirmation strings, file paths, variable names).

**User-authored example names** (e.g. illustrative Project names like "Recruiting Assistant") translate normally, since they're example labels, not fixed product names — e.g. "Recruiting Assistant" → "Asistente de Reclutamiento".

---

## 8. QA checklist per file

- [ ] `<html lang="es">`
- [ ] `<title>` and `<meta name="description">` translated
- [ ] hreflang pair added to both EN and ES files (§4)
- [ ] Every internal course link unchanged per §3; every link escaping `ai-for-friends/` has exactly one extra `../`
- [ ] EN/ES pill wired both directions (§4)
- [ ] Course-menu dropdown lists all 4 modules/21 lessons in Spanish labels, correct active-row highlight for the current page
- [ ] No English prose leaked outside the §2a keep-list
- [ ] No Spanish leaked into a §2a keep-list term
- [ ] Renders with no console errors; callouts, tables, checklist, progress pills all present
