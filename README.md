# Effective at Life

Source for **effectiveatlife.com** — a static site translating the "Gil OS" personal operating system (seven life pillars, AI as the system's foundation, weekly and daily review rituals) into public teaching content: a landing page, a blog, and an AI-literacy mini-course.

## Stack

Pure static HTML, CSS, and vanilla JavaScript. No backend, no build step, no package manager.

- **Tailwind CSS** via the Play CDN (`cdn.tailwindcss.com`), configured inline per page.
- **Fonts:** Space Grotesk (headings), Inter (body/long-form), JetBrains Mono (tags, metadata, technical labels) — via Google Fonts.
- Every page is a single self-contained `.html` file: markup, styles, and scripts all live in that one file. Nothing is bundled or compiled.

The visual system (colors, type, layout, component rules) is fully specified in [`assets/docs/Design-System-Guide.md`](assets/docs/Design-System-Guide.md). The build plan is in [`assets/docs/Effective-at-Life-Implementation-Guide-V1.md`](assets/docs/Effective-at-Life-Implementation-Guide-V1.md).

## Structure

```
effectiveatlife/
├── index.html                  # Landing page
├── error.html                  # Static error page
├── blog/
│   ├── index.html              # Blog hub
│   └── weekly-review.html      # "The Friday Finish" article
├── ai-for-friends/             # AI-literacy mini-course (planned, not yet built)
├── assets/
│   ├── docs/                   # Design system + implementation guide
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
- ⏳ Remaining blog articles (efficiency vs. effectiveness, context engineering)
- ⏳ AI for Friends mini-course (3 modules)
