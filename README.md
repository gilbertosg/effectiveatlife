# Effective at Life

Source for **effectiveatlife.com** — a static site translating the "Gil OS" personal operating system (seven life pillars, AI as the system's foundation, weekly and daily review rituals) into public teaching content: a landing page, a blog, and an AI-literacy mini-course.

## Stack

Pure static HTML, CSS, and vanilla JavaScript. No backend, no build step, no package manager.

- **Tailwind CSS** via the Play CDN (`cdn.tailwindcss.com`), configured inline per page.
- **Fonts:** Space Grotesk (headings), Inter (body/long-form), JetBrains Mono (tags, metadata, technical labels) — via Google Fonts.
- Every page is a single self-contained `.html` file: markup, styles, and scripts all live in that one file. Nothing is bundled or compiled.

The visual system (colors, type, layout, component rules) is fully specified in [`assets/docs/Design-System-Guide.md`](assets/docs/Design-System-Guide.md). The build plan is in [`assets/docs/Effective-at-Life-Implementation-Guide-V1.md`](assets/docs/Effective-at-Life-Implementation-Guide-V1.md). Reusable page templates for new content live in [`assets/docs/Article-Template.md`](assets/docs/Article-Template.md) and [`assets/docs/Lesson-Template.md`](assets/docs/Lesson-Template.md).

## Structure

```
effectiveatlife/
├── index.html                  # Landing page
├── error.html                  # Static error page
├── blog/
│   ├── index.html              # Blog hub
│   └── weekly-review.html      # "The Friday Finish" article
├── ai-for-friends/              # AI-literacy mini-course (3 modules, built)
│   ├── index.html               # Course hub
│   ├── module-1/                # AI Foundations — hub + 4 lessons
│   ├── module-2/                # Setting Up Your Computer (optional) — hub + 3 lessons
│   └── module-3/                # Claude Code — hub + 1 lesson
├── assets/
│   ├── docs/                   # Design system, implementation guide, page templates
│   ├── css/ js/ images/        # Reserved for shared assets if ever needed
└── .github/workflows/main.yml  # Deploy workflow
```

## Local preview

There's no dev server or install step. Serve the directory with any static file server:

```bash
python3 -m http.server 8934
```

Then open `http://localhost:8934/index.html`. Opening files directly via `file://` isn't reliable for testing relative links or CDN behavior.

## Deployment

`.github/workflows/main.yml` deploys on every push, to any branch, via `aws s3 sync ./ s3://effectiveatlife-s3 --delete`. There's no staging environment — a push is a production deploy.

## Status

- ✅ Global design system + landing page
- ✅ Blog hub + first article ("The Friday Finish")
- ✅ AI for Friends mini-course (3 modules, 12 pages)
- ⏳ Remaining blog articles (efficiency vs. effectiveness, context engineering)
- ⏳ Spanish translation (`es/` mirror — see `CLAUDE.md` for the planned convention; language-pill UI already scaffolded)
