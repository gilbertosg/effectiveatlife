# Article Template

Reference pattern for new `blog/*.html` articles, extracted from the live `blog/weekly-review.html`. Copy the skeleton below, then follow the customization checklist. See `CLAUDE.md` → "Design system & visual identity" for the token/component vocabulary this pattern draws on, and `Design-System-Guide.md` for the full visual spec.

## When to use this

Any new long-form article added to `blog/`. Not for the blog hub itself (`blog/index.html` follows a card-grid pattern, not this prose pattern) and not for course lessons (see `Lesson-Template.md` — lessons use numbered steps and callouts; articles are straight long-form prose with one embedded CTA).

## Full skeleton

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>{ARTICLE TITLE} — Effective at Life</title>
<meta name="title" content="{ARTICLE TITLE}">
<meta name="description" content="{ONE-SENTENCE HOOK, ~150-200 CHARS — this is what shows in the blog hub card and search results}">

<script src="https://cdn.tailwindcss.com"></script>
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          'os-deep': '#0A0F1C',
          'os-surface': '#111827',
          'os-surface-light': '#1F2937',
          'os-primary': '#FFFFFF',
          'os-secondary': '#9CA3AF',
          'os-tertiary': '#6B7280',
          'accent-cyan': '#00F0FF',
          'accent-teal': '#00C2D1',
          'accent-purple': '#7B2CBF',
        },
        fontFamily: {
          display: ['"Space Grotesk"', 'sans-serif'],
          body: ['Inter', 'sans-serif'],
          mono: ['"JetBrains Mono"', 'monospace'],
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
  body {
    background-color: #0A0F1C;
    color: #FFFFFF;
    font-family: 'Inter', sans-serif;
    -webkit-font-smoothing: antialiased;
  }
  .font-display { font-family: 'Space Grotesk', sans-serif; }
  .font-mono { font-family: 'JetBrains Mono', monospace; }

  .bg-grid {
    background-image:
      linear-gradient(rgba(255,255,255,0.035) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.035) 1px, transparent 1px);
    background-size: 44px 44px;
  }

  @keyframes fadeInUp {
    0% { opacity: 0; transform: translateY(18px); }
    100% { opacity: 1; transform: translateY(0); }
  }
  .fade-up {
    opacity: 0;
    animation: fadeInUp 0.7s ease-out forwards;
  }

  ::selection { background: rgba(0,240,255,0.25); color: #FFFFFF; }

  a:focus-visible, button:focus-visible, input:focus-visible {
    outline: 2px solid #00F0FF;
    outline-offset: 3px;
    border-radius: 4px;
  }

  /* Long-form article measure and rhythm */
  .prose-article p { margin-bottom: 1.5em; line-height: 1.8; }
  .prose-article h2 {
    font-family: 'Space Grotesk', sans-serif;
    font-weight: 600;
    letter-spacing: -0.01em;
    font-size: 1.6rem;
    margin-top: 3rem;
    margin-bottom: 1.25rem;
  }
  .prose-article ul { margin-bottom: 1.5em; }
  .prose-article li { line-height: 1.75; margin-bottom: 0.6em; }
  .prose-article strong { color: #FFFFFF; font-weight: 600; }

  @media (prefers-reduced-motion: reduce) {
    html { scroll-behavior: auto; }
    .fade-up { animation: none !important; opacity: 1 !important; }
  }
</style>
</head>
<body class="bg-os-deep text-os-primary font-body antialiased">

<!-- ============ NAV ============ -->
<header class="fixed top-0 inset-x-0 z-50 border-b border-white/[0.08] bg-os-deep/80 backdrop-blur-md">
  <div class="max-w-7xl mx-auto px-6 h-16 flex items-center justify-between">
    <a href="../index.html" class="flex items-center gap-2.5 group">
      <span class="w-2 h-2 rounded-full bg-accent-cyan shadow-[0_0_8px_rgba(0,240,255,0.8)]"></span>
      <span class="font-display font-semibold tracking-tight text-[15px]">EFFECTIVE<span class="text-accent-cyan">/</span>AT LIFE</span>
    </a>
    <nav class="hidden md:flex items-center gap-8 font-mono text-xs text-os-secondary uppercase tracking-wide">
      <a href="../index.html#pillars" class="hover:text-accent-cyan transition-colors">Pillars</a>
      <a href="../index.html#ai" class="hover:text-accent-cyan transition-colors">AI</a>
      <a href="../index.html#methodology" class="hover:text-accent-cyan transition-colors">Inspiration</a>
      <a href="index.html" class="text-accent-cyan">Blog</a>
      <a href="../ai-for-friends/index.html" class="hover:text-accent-cyan transition-colors">Course</a>
    </nav>
    <a href="../index.html#pillars" class="font-mono text-xs uppercase tracking-wide px-4 py-2 rounded-lg bg-[#00F0FF] text-black font-bold hover:shadow-[0_0_15px_rgba(0,240,255,0.4)] transition-shadow">
      View System
    </a>
  </div>
</header>

<!-- ============ ARTICLE HEADER ============ -->
<header class="relative pt-40 pb-16 px-6 overflow-hidden bg-grid">
  <div class="absolute inset-0 bg-gradient-to-b from-os-deep via-os-deep/95 to-os-deep pointer-events-none"></div>
  <div class="relative max-w-2xl mx-auto fade-up">
    <a href="index.html" class="font-mono text-xs text-os-tertiary hover:text-accent-cyan transition-colors">&larr; Blog</a>
    <div class="flex items-center gap-2 mt-6 mb-6">
      <span class="font-mono text-[10px] px-2.5 py-1 rounded-full border border-accent-cyan/40 text-accent-cyan">{PILLAR e.g. L3 · CAREER}</span>
      <span class="font-mono text-[10px] px-2.5 py-1 rounded-full border border-white/20 text-os-secondary">{SECOND PILLAR, optional}</span>
    </div>
    <h1 class="font-display font-bold tracking-tight text-4xl sm:text-5xl leading-[1.1] mb-6">
      {ARTICLE TITLE}
    </h1>
    <p class="text-os-secondary text-lg leading-relaxed mb-6">
      {ONE-TO-TWO SENTENCE DEK — the article's thesis, stated plainly}
    </p>
    <div class="flex items-center gap-4 font-mono text-[11px] text-os-tertiary pt-6 border-t border-white/[0.08]">
      <span>{YYYY-MM-DD}</span>
      <span>&middot;</span>
      <span>{N} min read</span>
    </div>
  </div>
</header>

<!-- ============ ARTICLE BODY ============ -->
<article class="px-6 pb-24">
  <div class="prose-article max-w-2xl mx-auto text-os-secondary text-[17px]">

    <p>{Opening hook paragraph — name the problem the reader recognizes.}</p>

    <p>{Second paragraph — introduce the system/answer.}</p>

    <h2>{First subhead}</h2>
    <p>{Body copy.}</p>
    <ul class="space-y-2 pl-5 list-disc marker:text-accent-cyan">
      <li><strong>{Bold lead-in}</strong> — {supporting detail}.</li>
    </ul>

    <!-- Repeat <h2>/<p>/<ul> blocks for as many sections as the article needs. -->
    <!-- Internal links to landing-page sections use the same accent-cyan underline treatment: -->
    <!-- <a href="../index.html#pillars" class="text-accent-cyan hover:underline">seven pillars</a> -->

    <!-- ============ EMAIL CAPTURE (static placeholder — no backend wired) ============ -->
    <!-- Place roughly halfway through the article body, per the Implementation Guide. -->
    <div class="not-prose my-12 rounded-2xl bg-gradient-to-br from-white/[0.06] to-transparent backdrop-blur-md border border-white/10 p-8">
      <p class="font-mono text-[11px] uppercase tracking-widest text-accent-cyan mb-3">Get the next dispatch</p>
      <h3 class="font-display font-semibold text-xl mb-2">One system note a month. No noise.</h3>
      <p class="text-os-secondary text-sm leading-relaxed mb-6">
        New pillar breakdowns and rituals, synthesized from the vault, straight to your inbox.
      </p>
      <form class="flex flex-col sm:flex-row gap-3" onsubmit="return false">
        <label for="email-capture" class="sr-only">Email address</label>
        <input
          id="email-capture"
          type="email"
          required
          placeholder="you@domain.com"
          class="flex-1 rounded-lg bg-white/5 border border-white/15 px-4 py-3 text-sm text-os-primary placeholder:text-os-tertiary focus:outline-none focus:border-accent-cyan/60"
        >
        <button type="submit" class="px-5 py-3 rounded-lg bg-[#00F0FF] text-black font-display font-bold text-sm hover:shadow-[0_0_20px_rgba(0,240,255,0.4)] transition-shadow whitespace-nowrap">
          Subscribe
        </button>
      </form>
    </div>

    <!-- Remaining sections continue here -->

    <h2>Quick answers</h2>
    <p><strong>{FAQ question}?</strong> {Answer.}</p>

    <p class="pt-4 font-display text-xl text-os-primary">{One-line closing statement — matches the site's declarative voice.}</p>

  </div>
</article>

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

</body>
</html>
```

## Customization checklist for a new article

1. `<title>`, `<meta name="title">`, `<meta name="description">` — unique per article, description is what renders on the blog hub card.
2. Article header: back-link stays `href="index.html"` (relative to `blog/`), pillar pill-tags (1–2, matching the `L{n} · PILLAR` pattern used elsewhere), H1, dek, date, read time.
3. Body: plain `<h2>`/`<p>`/`<ul>` sections — no callouts, no numbered steps, no `<details>`. Articles are prose; that component vocabulary belongs to lessons (see `Lesson-Template.md`). Internal links to the landing page use `text-accent-cyan hover:underline`.
4. Email capture block: keep it roughly at the article's midpoint by word count. It is **static and non-functional** (`onsubmit="return false"`) — there is no email backend wired up. Don't imply otherwise in surrounding copy, and don't wire a real endpoint without checking with the user first (a live form on a public S3 site needs a real service — Mailchimp, ConvertKit, etc. — decided deliberately, not defaulted into).
5. Add the new article as a card to `blog/index.html`'s grid, matching the existing card markup (pillar pill-tags, title, one-line dek, date/read-time footer row).
6. Prev/next: articles don't currently link to each other (only one exists); add that nav pattern once there are two or more, mirroring the lesson prev/next bar in `Lesson-Template.md`.

## Known gap

This skeleton's nav includes `AI` and `Inspiration` links that the original `blog/weekly-review.html` predates and does not yet have — that file's live nav is missing both. Include them in any new article, and backfill `blog/weekly-review.html` and `blog/index.html` the next time either is touched, so the whole site's nav stays in sync.
