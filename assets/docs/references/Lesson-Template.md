# Lesson Template

Reference pattern for new `ai-for-friends/module-{n}/lesson-{n}.html` pages, extracted from the live `ai-for-friends/module-1/lesson-1.html`. Copy the skeleton below, then follow the customization checklist. See `CLAUDE.md` → "Design system & visual identity" for the token/component vocabulary this pattern draws on, and `Design-System-Guide.md` for the full visual spec.

## When to use this

Any new lesson page inside a course module. Not for module hub pages (`module-{n}/index.html` — those follow a different pattern: lesson-list cards, a "Key Concepts" glossary table + `<details>` full reference, a "Support Resources" table; read an existing hub file directly if building a new one) and not for blog articles (see `Article-Template.md` — articles are plain prose, lessons are numbered steps with callouts).

## Full skeleton

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lesson {N.N}: {LESSON TITLE} — AI for Friends</title>
<meta name="title" content="Lesson {N.N}: {LESSON TITLE}">
<meta name="description" content="{ONE-SENTENCE SUMMARY of what the lesson teaches}">

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

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">

<style>
  html { scroll-behavior: smooth; }
  body { background-color: #0A0F1C; color: #FFFFFF; font-family: 'Inter', sans-serif; -webkit-font-smoothing: antialiased; }
  .font-display { font-family: 'Space Grotesk', sans-serif; }
  .font-mono { font-family: 'JetBrains Mono', monospace; }
  .bg-grid {
    background-image: linear-gradient(rgba(255,255,255,0.035) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.035) 1px, transparent 1px);
    background-size: 44px 44px;
  }
  @keyframes fadeInUp { 0% { opacity: 0; transform: translateY(18px); } 100% { opacity: 1; transform: translateY(0); } }
  .fade-up { opacity: 0; animation: fadeInUp 0.7s ease-out forwards; }
  ::selection { background: rgba(0,240,255,0.25); color: #FFFFFF; }
  a:focus-visible, button:focus-visible, summary:focus-visible { outline: 2px solid #00F0FF; outline-offset: 3px; border-radius: 4px; }
  @media (prefers-reduced-motion: reduce) { html { scroll-behavior: auto; } .fade-up { animation: none !important; opacity: 1 !important; } }

  /* Lesson body typography */
  .lesson-body h2 {
    font-family: 'Space Grotesk', sans-serif; font-weight: 600; letter-spacing: -0.01em;
    font-size: 1.5rem; margin-top: 3rem; margin-bottom: 0.75rem; scroll-margin-top: 6rem;
  }
  .lesson-body h2 .step-num {
    display: inline-flex; align-items: center; justify-content: center;
    width: 2rem; height: 2rem; border-radius: 9999px; margin-right: 0.75rem;
    background: rgba(0,240,255,0.1); border: 1px solid rgba(0,240,255,0.4);
    color: #00F0FF; font-family: 'JetBrains Mono', monospace; font-size: 0.8rem; font-weight: 500;
    vertical-align: middle;
  }
  .lesson-body p { line-height: 1.75; margin-bottom: 1.25em; color: #9CA3AF; }
  .lesson-body table { width: 100%; border-collapse: collapse; margin: 1.5rem 0; font-size: 0.9rem; }
  .lesson-body th { text-align: left; font-family: 'JetBrains Mono', monospace; font-size: 0.7rem; text-transform: uppercase; letter-spacing: 0.05em; color: #6B7280; padding: 0.75rem 1rem; border-bottom: 1px solid rgba(255,255,255,0.1); }
  .lesson-body td { padding: 0.85rem 1rem; border-bottom: 1px solid rgba(255,255,255,0.06); color: #9CA3AF; vertical-align: top; }
  .lesson-body tr:last-child td { border-bottom: none; }
  .lesson-body strong { color: #FFFFFF; font-weight: 600; }

  /* Callouts — four variants, pick by intent (see checklist below) */
  .callout { border-radius: 0.75rem; padding: 1.1rem 1.25rem; margin: 1.5rem 0; border: 1px solid; font-size: 0.9rem; line-height: 1.65; }
  .callout-label { font-family: 'JetBrains Mono', monospace; font-size: 0.7rem; text-transform: uppercase; letter-spacing: 0.08em; display: block; margin-bottom: 0.4rem; }
  .callout-tip { background: rgba(0,240,255,0.06); border-color: rgba(0,240,255,0.25); }
  .callout-tip .callout-label { color: #00F0FF; }
  .callout-note { background: rgba(0,194,209,0.06); border-color: rgba(0,194,209,0.25); }
  .callout-note .callout-label { color: #00C2D1; }
  .callout-info { background: rgba(123,44,191,0.08); border-color: rgba(123,44,191,0.3); }
  .callout-info .callout-label { color: #B18CE0; }
  .callout-warning { background: rgba(251,191,36,0.07); border-color: rgba(251,191,36,0.3); }
  .callout-warning .callout-label { color: #FBBF24; }
  .callout p { color: #D1D5DB; margin-bottom: 0; }

  /* Expand / details — for optional-depth content */
  .lesson-body details { border-radius: 0.75rem; border: 1px solid rgba(255,255,255,0.1); background: rgba(255,255,255,0.03); margin: 1.5rem 0; overflow: hidden; }
  .lesson-body summary { cursor: pointer; padding: 1rem 1.25rem; font-family: 'Space Grotesk', sans-serif; font-weight: 600; font-size: 0.9rem; list-style: none; display: flex; align-items: center; justify-content: space-between; }
  .lesson-body summary::-webkit-details-marker { display: none; }
  .lesson-body summary::after { content: '+'; font-family: 'JetBrains Mono', monospace; color: #00F0FF; font-size: 1.1rem; }
  .lesson-body details[open] summary::after { content: '\2212'; }
  .lesson-body details > div { padding: 0 1.25rem 1.25rem; }

  /* Code / prompt blocks */
  .lesson-body pre { background: #111827; border: 1px solid rgba(255,255,255,0.08); border-radius: 0.6rem; padding: 1rem 1.15rem; overflow-x: auto; margin: 1rem 0; font-family: 'JetBrains Mono', monospace; font-size: 0.8rem; line-height: 1.6; color: #D1D5DB; white-space: pre-wrap; }

  /* Verification checklist — static, not real form inputs */
  .checklist-item { display: flex; align-items: flex-start; gap: 0.75rem; padding: 0.6rem 0; }
  .checklist-box { width: 1.1rem; height: 1.1rem; border-radius: 0.3rem; border: 1.5px solid rgba(0,240,255,0.5); flex-shrink: 0; margin-top: 0.15rem; }
</style>
</head>
<body class="bg-os-deep text-os-primary font-body antialiased">

<!-- ============ NAV ============ -->
<!-- The course-menu dropdown below is IDENTICAL across all 12 ai-for-friends pages except for href depth
     (module hubs and lessons are both 2 levels deep, so paths match) and which link is highlighted active.
     Copy it verbatim from the closest existing lesson and just update the active-state class on the
     current lesson's own link (text-accent-cyan bg-white/5 instead of the default hover classes). -->
<header class="fixed top-0 inset-x-0 z-50 border-b border-white/[0.08] bg-os-deep/80 backdrop-blur-md">
  <div class="max-w-7xl mx-auto px-6 h-16 flex items-center justify-between">
    <a href="../../index.html" class="flex items-center gap-2.5 group">
      <span class="w-2 h-2 rounded-full bg-accent-cyan shadow-[0_0_8px_rgba(0,240,255,0.8)]"></span>
      <span class="font-display font-semibold tracking-tight text-[15px]">EFFECTIVE<span class="text-accent-cyan">/</span>AT LIFE</span>
    </a>
    <nav class="hidden md:flex items-center gap-6 font-mono text-xs text-os-secondary uppercase tracking-wide">
      <a href="../../index.html#pillars" class="hover:text-accent-cyan transition-colors">Pillars</a>
      <a href="../../blog/index.html" class="hover:text-accent-cyan transition-colors">Blog</a>
      <a href="../index.html" class="text-accent-cyan">Course</a>

      <div class="relative">
        <button type="button" id="course-menu-btn" class="flex items-center gap-1.5 hover:text-accent-cyan transition-colors" aria-expanded="false" aria-haspopup="true" aria-controls="course-menu-panel">
          Menu
          <svg width="10" height="10" viewBox="0 0 10 10" fill="none" class="mt-px"><path d="M1 3L5 7L9 3" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
        </button>
        <div id="course-menu-panel" class="hidden absolute right-0 top-full mt-4 w-[19rem] rounded-2xl bg-os-surface border border-white/10 shadow-2xl shadow-black/40 p-3 normal-case">
          <div class="mb-1">
            <a href="{path-to-module-1}/index.html" class="flex items-center gap-2 px-2 py-2 rounded-lg hover:bg-white/5 transition-colors">
              <span class="font-mono text-xs text-accent-cyan">01</span>
              <span class="font-display font-semibold text-sm text-os-primary">AI Foundations</span>
            </a>
            <div class="ml-8 space-y-0.5 pb-2">
              <a href="{...}/lesson-1.html" class="block px-2 py-1 rounded text-xs text-os-secondary hover:text-accent-cyan hover:bg-white/5 transition-colors">1.1 How AI Models Work</a>
              <!-- ...one link per lesson in module 1... -->
            </div>
          </div>
          <div class="border-t border-white/10 my-1"></div>
          <div class="mb-1">
            <a href="{path-to-module-2}/index.html" class="flex items-center gap-2 px-2 py-2 rounded-lg hover:bg-white/5 transition-colors">
              <span class="font-mono text-xs text-os-tertiary">02</span>
              <span class="font-display font-semibold text-sm text-os-primary">Setting Up Your Computer</span>
              <span class="font-mono text-[9px] text-os-tertiary ml-auto">OPTIONAL</span>
            </a>
            <div class="ml-8 space-y-0.5 pb-2"><!-- ...module 2 lessons... --></div>
          </div>
          <div class="border-t border-white/10 my-1"></div>
          <div>
            <a href="{path-to-module-3}/index.html" class="flex items-center gap-2 px-2 py-2 rounded-lg hover:bg-white/5 transition-colors">
              <span class="font-mono text-xs text-accent-purple">03</span>
              <span class="font-display font-semibold text-sm text-os-primary">Claude Code</span>
            </a>
            <div class="ml-8 space-y-0.5 pb-2"><!-- ...module 3 lessons... --></div>
          </div>
          <div class="border-t border-white/10 my-2"></div>
          <a href="../index.html" class="flex items-center justify-center gap-1.5 px-2 py-2 rounded-lg text-xs font-mono text-accent-cyan hover:bg-white/5 transition-colors">Course Home</a>
        </div>
      </div>

      <!-- Language pill — ES is intentionally disabled (no href) until Spanish pages exist. See CLAUDE.md → Internationalization. -->
      <div class="flex items-center gap-1.5 text-[10px] text-os-tertiary normal-case">
        <span class="text-accent-cyan font-semibold">EN</span>
        <span class="text-white/20">/</span>
        <span class="cursor-default" title="Spanish version — coming soon">ES</span>
      </div>
    </nav>
    <a href="index.html" class="font-mono text-xs uppercase tracking-wide px-4 py-2 rounded-lg bg-[#00F0FF] text-black font-bold hover:shadow-[0_0_15px_rgba(0,240,255,0.4)] transition-shadow">
      Module {N}
    </a>
  </div>
</header>

<!-- ============ LESSON HEADER ============ -->
<header class="relative pt-40 pb-14 px-6 overflow-hidden bg-grid">
  <div class="absolute inset-0 bg-gradient-to-b from-os-deep via-os-deep/95 to-os-deep pointer-events-none"></div>
  <div class="relative max-w-2xl mx-auto fade-up">
    <div class="font-mono text-xs text-os-tertiary mb-6">
      <a href="../index.html" class="hover:text-accent-cyan transition-colors">AI for Friends</a>
      <span class="mx-1.5">/</span>
      <a href="index.html" class="hover:text-accent-cyan transition-colors">Module {N}</a>
      <span class="mx-1.5">/</span>
      <span class="text-os-secondary">Lesson {N.N}</span>
    </div>
    <h1 class="font-display font-bold tracking-tight text-3xl sm:text-4xl leading-[1.15] mb-4">{LESSON TITLE}</h1>
    <p class="text-os-secondary text-lg leading-relaxed mb-6">
      {One-sentence framing of what this lesson teaches and why it matters.}
    </p>
    <div class="flex flex-wrap items-center gap-2 mb-8">
      <span class="font-mono text-[10px] px-2.5 py-1 rounded-full border border-white/15 text-os-tertiary">{N} MIN</span>
      <span class="font-mono text-[10px] px-2.5 py-1 rounded-full border border-white/15 text-os-tertiary">STEP {N} OF {TOTAL LESSONS IN MODULE}</span>
    </div>
    <!-- Progress pills — real anchor links, not decorative. One per <h2 id="step-N"> below. -->
    <div class="flex flex-wrap gap-2 font-mono text-[10px]">
      <a href="#step-1" class="px-2.5 py-1 rounded-full bg-accent-cyan/15 border border-accent-cyan/40 text-accent-cyan hover:bg-accent-cyan/25 transition-colors">1. {Short label}</a>
      <a href="#step-2" class="px-2.5 py-1 rounded-full border border-white/10 text-os-tertiary hover:text-accent-cyan hover:border-accent-cyan/40 transition-colors">2. {Short label}</a>
      <!-- ...one pill per step... -->
    </div>
  </div>
</header>

<!-- ============ LESSON BODY ============ -->
<article class="px-6 pb-24">
  <div class="lesson-body max-w-2xl mx-auto text-[16px]">

    <h2 id="step-1"><span class="step-num">1</span>{Step Title}</h2>
    <p>{Explanation.}</p>

    <table>
      <thead><tr><th>{Col}</th><th>{Col}</th><th>{Col}</th></tr></thead>
      <tbody>
        <tr><td><strong>{Term}</strong></td><td>{Meaning}</td><td>{Why it matters}</td></tr>
      </tbody>
    </table>

    <!-- Callouts — pick the variant by intent, don't mix them up:
         callout-tip     (cyan)   = an actionable suggestion
         callout-note    (teal)   = a clarifying aside, "don't worry about X"
         callout-info    (purple) = a core concept/principle worth flagging
         callout-warning (amber)  = a real risk (confidentiality, cost, data loss) -->
    <div class="callout callout-info">
      <span class="callout-label">{The Core Insight}</span>
      <p>{One or two sentences.}</p>
    </div>

    <!-- <details> for optional-depth content: troubleshooting, "full reference" tables, extra examples -->
    <details>
      <summary>{Expand label}</summary>
      <div>
        <p>{Extra content only shown when opened.}</p>
      </div>
    </details>

    <!-- Repeat <h2 id="step-N">...</h2> blocks for every step -->

    <h2 class="!mt-16">Verification</h2>
    <div class="rounded-2xl bg-white/5 border border-white/10 p-6">
      <div class="checklist-item"><span class="checklist-box"></span><span class="text-sm text-os-secondary">{Concrete, checkable outcome}</span></div>
    </div>

    <h2 class="!mt-10 !text-base">Related Resources</h2>
    <ul class="list-none pl-0 text-sm text-os-secondary space-y-1.5">
      <li><a href="https://claude.ai" class="text-accent-cyan hover:underline">claude.ai</a> — The Claude AI platform</li>
      <li><a href="https://code.claude.com/docs" class="text-accent-cyan hover:underline">Claude documentation</a> — Official documentation</li>
      <li><a href="https://support.claude.com" class="text-accent-cyan hover:underline">Claude support</a> — Help center and troubleshooting</li>
    </ul>

    <div class="mt-10 rounded-2xl bg-gradient-to-br from-accent-cyan/10 to-transparent border border-accent-cyan/20 p-6">
      <p class="font-mono text-[11px] uppercase tracking-widest text-accent-cyan mb-2">Lesson complete</p>
      <p class="text-sm text-os-secondary">{One or two sentences summarizing what the learner now knows.}</p>
    </div>

  </div>
</article>

<!-- ============ PREV/NEXT ============ -->
<nav class="px-6 pb-24">
  <div class="max-w-2xl mx-auto flex items-center justify-between gap-4 pt-8 border-t border-white/[0.08]">
    <a href="{prev-lesson-or-index}.html" class="font-mono text-xs text-os-tertiary hover:text-accent-cyan transition-colors">&larr; {Prev label}</a>
    <a href="{next-lesson-or-module}.html" class="flex items-center gap-2 px-5 py-3 rounded-lg bg-[#00F0FF] text-black font-display font-bold text-sm hover:shadow-[0_0_20px_rgba(0,240,255,0.4)] transition-shadow">
      Next: {Next label} &rarr;
    </a>
  </div>
</nav>

<!-- ============ FOOTER ============ -->
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

<!-- Course-menu dropdown toggle — required any time the dropdown markup above is present -->
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

</body>
</html>
```

## Customization checklist for a new lesson

1. `<title>`, `<meta name="title">`, `<meta name="description">`, breadcrumb, H1, dek, time/step badges.
2. **Course-menu dropdown**: copy verbatim from an existing lesson in the target module (path depth is identical for every `module-{n}/lesson-{n}.html` and `module-{n}/index.html` file — always `../` to reach `ai-for-friends/`, no path prefix needed for links within the same module). Only the active-state highlight (which lesson link gets `text-accent-cyan bg-white/5` instead of the hover classes) changes.
3. **Progress pills**: one `<a href="#step-N">` per step, and a matching `<h2 id="step-N">` in the body. `scroll-margin-top: 6rem` on `.lesson-body h2` is what keeps the jump target from hiding under the fixed header — don't remove it.
4. **`step-num` badges**: sequential integers starting at 1 (module 3's single long lesson uses 0-indexed section numbers instead — `step-0` through `step-5` — because it mirrors a 6-section source doc; that's the one exception, not the pattern to copy by default).
5. **Callouts**: pick the variant deliberately (see the four-variant note inline in the skeleton) — don't default to `callout-info` for everything.
6. **`<details>`**: only for genuinely optional depth (troubleshooting, "full reference," extra role-specific examples) — not a substitute for organizing the core content into steps.
7. **Verification checklist**: 2–4 concrete, checkable outcomes tied to what the lesson actually taught — not generic "you understand X" filler.
8. **Related Resources**: keep to real, stable links (claude.ai, official docs, official support) — see `CLAUDE.md` → "Content sourcing and privacy" on not fabricating URLs.
9. **Prev/next nav** and the **module hub's lesson list** both need updating when a lesson is added or reordered — there's no single source of truth, per the "shared shell, copy-paste not includes" note in `CLAUDE.md`.
10. If the new lesson is the first in a new module, also build a module hub (`module-{n}/index.html`) — read an existing hub (e.g. `ai-for-friends/module-1/index.html`) directly for that pattern; it's not covered by this template.
