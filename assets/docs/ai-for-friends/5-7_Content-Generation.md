<!-- HERO: Lesson 5.7: From Sources to Story — A Content-Generation Pipeline | Gather articles, compile them into one digest, and draft a finished, on-brand piece of content from it. -->

<!-- TOC: Overview#anchor-overview | Step 1: Dictate the Workflow#anchor-step-1 | Step 2: Build the Three-Skill Plugin#anchor-step-2 | Step 3: Install and Run It#anchor-step-3 | Step 4: Optional — Run It on a Schedule#anchor-step-4 | Verification#anchor-verification -->

## Overview

This closing lesson adds one more stage to the pattern from Lessons 5.3 and 5.6: gather, compile, and now **produce** — turning a pile of articles and news into one finished, on-brand piece of content, ready to publish. It is the same shape you've now built three times, extended one step further.

### Why This Matters

Content generation usually starts with research: reading a dozen articles to find the two or three worth writing about. Automating that research step — and handing the writer a compiled, organized digest instead of a dozen open tabs — is where this workflow earns its time back.

### Prerequisites

- [Lesson 5.2: Installing Anthropic Skills](5-2_Installing_Anthropic_Skills.md), completed — this lesson's final skill can write a Word draft
- [Lesson 5.3](5-3_International_Relations_Agreements_Workflow.md) and [Lesson 5.6](5-6_Staying_Informed_Market_Awareness_Digest.md) recommended — this lesson reuses their plugin structure and knowledge-log pattern without re-explaining them
- A brand-voice CLAUDE.md, if you already built one in [Lesson 4.6](4-6_Worked_Examples_By_Role.md) for Marketing — reuse it here

### Time to Complete

**30 to 35 minutes**

<!-- PROGRESS: Step 1: Dictate the Workflow | Step 2: Build the Plugin | Step 3: Install and Run | Step 4: Optional Scheduling | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-1 -->

## Step 1: Dictate the Workflow

Describe the whole pipeline in one message — sources, target content, and tone — the same dictate-to-setup pattern used throughout this module.

### What You'll Do

You will describe your sources and the content you want produced, and review what Claude Code proposes.

### Instructions

1. Create a new folder, for example `content-pipeline`, and open it in Claude Code.
2. Adapt and send the example dictation below.
3. Answer any clarifying questions.
4. Review the proposed `CLAUDE.md` before approving.

### Example Dictation

```text
I want a workflow that turns news articles into one piece of content
I can publish. Here are my sources: [list your 3-6 news sites, blogs,
or feeds]. I care about articles touching these themes: [list your
themes, e.g., industry trends, regulatory changes, competitor moves].
Once new articles come in, I want them grouped into one organized
digest by theme, not just a flat list. Then I want a draft piece of
content built from that digest — specifically a [blog post / LinkedIn
post / newsletter section], around [word count], in our brand voice:
[describe your tone, e.g., confident, plain-spoken, no hype]. Set this
up as a project with a README and a CLAUDE.md capturing my sources,
themes, content format, and tone, and ask me anything you need first.
```

### What Claude Code Should Produce

```text
content-pipeline/
├── README.md Explains the pipeline
├── CLAUDE.md Standing rules: sources, themes,
│ content format, brand voice
├── data/
│ └── seen-articles-log.md Every article already gathered
├── digests/
│ └── theme-digests/ Compiled, theme-grouped digests
└── output/
└── drafts/ Finished content drafts land here
```

<!-- NOTE: Reuse a Brand-Voice CLAUDE.md If You Have One | If you already built a Marketing Project in Lesson 4.6, its custom instructions — brand voice, banned words, tone — describe almost exactly what this CLAUDE.md needs. Copy from it instead of starting blank. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Build the Three-Skill Plugin

Three skills, the same shape as Lesson 5.3's gather-respond-assemble pattern: `gather-articles`, `compile-digest`, `draft-content`. This reuses the plugin file structure from Lesson 5.3 — `.claude-plugin/marketplace.json`, `plugins/<name>/.claude-plugin/plugin.json`, `skills/<name>/SKILL.md` — so this step focuses on the three skills themselves.

### What You'll Do

You will have Claude Code build all three skills, one at a time, and run the full pipeline.

### Instructions

1. Ask Claude Code to build `gather-articles`, review it.
2. Ask for `compile-digest`, review it.
3. Ask for `draft-content`, review it.
4. Run all three commands in order against real sources.

### Skill 1 — `/gather-articles`

**What to tell Claude Code to build:**

```text
Build a skill called gather-articles. Its job: fetch each source
listed in CLAUDE.md, extract every article's title, date, and a short
summary, and compare against data/seen-articles-log.md. Keep only
articles not already logged and matching one of our themes in
CLAUDE.md. Append each new, on-theme article to the log with its
title, date, theme, source link, and summary.
```

**What this produces (`skills/gather-articles/SKILL.md`, abbreviated):**

```markdown
---
name: gather-articles
description: Fetch each source, extract new on-theme articles, and log
them. Use when the user says "gather articles" or "/gather-articles."
---

# gather-articles

1. Read the source list and theme list from CLAUDE.md.
2. Fetch each source with WebFetch and extract each article's title,
date, and a short summary.
3. Read data/seen-articles-log.md — everything logged so far.
4. Keep only articles not already logged and matching a theme.
5. Append each one to the log with title, date, theme, source link,
and summary.
6. Report how many new, on-theme articles were found.
```

### Skill 2 — `/compile-digest`

**What to tell Claude Code to build:**

```text
Build a skill called compile-digest. Its job: read every article in
data/seen-articles-log.md not yet compiled, group them by theme, and
write one organized digest file to digests/theme-digests/ with a
section per theme, each article listed with its summary and source
link. Mark each included article "compiled" in the log.
```

**What this produces (`skills/compile-digest/SKILL.md`, abbreviated):**

```markdown
---
name: compile-digest
description: Group uncompiled logged articles by theme into one
organized digest file. Use when the user says "compile the digest"
or "/compile-digest."
---

# compile-digest

1. Read data/seen-articles-log.md. Find every article marked
"gathered" but not yet "compiled."
2. Group them by theme.
3. Write digests/theme-digests/<date>-digest.md: one section per
theme, each article's title, summary, and source link.
4. Mark each included article "compiled" in the log.
5. Report the digest's file path and how many themes it covers.
```

### Skill 3 — `/draft-content`

**What to tell Claude Code to build:**

```text
Build a skill called draft-content. Its job: read the latest digest
in digests/theme-digests/, and draft one piece of content in the
format and tone described in CLAUDE.md — a blog post, LinkedIn post,
or newsletter section, at the target length also in CLAUDE.md.
Reference specific points from the digest rather than writing
generically. If the target format is a Word document, use the docx
skill to save it to output/drafts/; otherwise save it as Markdown.
```

**What this produces (`skills/draft-content/SKILL.md`, abbreviated):**

```markdown
---
name: draft-content
description: Draft one piece of content from the latest theme digest,
in the format and voice set in CLAUDE.md. Use when the user says
"draft the content" or "/draft-content."
---

# draft-content

1. Read the most recent file in digests/theme-digests/.
2. Read the target format, length, and brand voice from CLAUDE.md.
3. Draft the content, referencing specific articles and themes from
the digest rather than generic statements.
4. If the target format is a Word document, use the docx skill to
save output/drafts/<date>-draft.docx. Otherwise save
output/drafts/<date>-draft.md.
5. Show the draft and note which digest it was built from.
```

### Sample Output

```text
/gather-articles → "4 new on-theme articles logged across 2 themes."
/compile-digest → "Compiled digests/theme-digests/tuesday-digest.md
— 2 themes: Industry Trends (3 articles),
Regulatory Changes (1 article)."
/draft-content → "Drafted output/drafts/tuesday-draft.md — a
420-word blog post referencing all 3 Industry
Trends articles and the regulatory update.
Saved in brand voice per CLAUDE.md."
```

<!-- INFO: What Made This Fast | The draft didn't start from a blank page — it started from an already-organized, already-themed digest. That's the entire value of splitting gather, compile, and draft into three separate skills instead of one. -->

---

<!-- ANCHOR: anchor-step-3 -->

## Step 3: Install and Run It

Same install pattern as every plugin in this module.

### What You'll Do

You will register the project as a local marketplace, install the plugin, and confirm all three commands run in sequence.

### Instructions

1. Register the local marketplace and install the plugin.
2. Restart Claude Code.
3. Run the three commands in order.

### The Commands

```text
/plugin marketplace add /path/to/content-pipeline
/plugin install content-pipeline@content-pipeline
```

Then, after restarting Claude Code inside the project folder:

```text
/gather-articles
/compile-digest
/draft-content
```

<!-- TIP: Review the Draft Before Publishing | draft-content produces a first draft, not a finished piece. Read it against the source articles, fact-check anything specific, and edit the tone before it goes anywhere public — the same validation habit from Lesson 1.3 applies here. -->

---

<!-- ANCHOR: anchor-step-4 -->

## Step 4: Optional — Run It on a Schedule

The gather-and-compile steps can run unattended; drafting is worth doing with a person still reviewing the result.

### What You'll Do

You will schedule `/gather-articles` and `/compile-digest` to run automatically, leaving `/draft-content` as a manual step you run when you're ready to write.

### Instructions — Windows

1. Before proceeding, revisit [Lesson 5.1, Step 4](5-1_Your_Claude_Code_Daily_Habits.md#anchor-step-4) — confirm you trust both scheduled skills' output from manual runs first.
2. Open **Windows Task Scheduler**.
3. Schedule the two gathering commands to run daily or weekly.
4. Leave `/draft-content` for you to run by hand, once you've reviewed the digest.

### The Scheduled Commands — Windows

```text
claude -p "/gather-articles" --cwd "C:\path\to\content-pipeline"
claude -p "/compile-digest" --cwd "C:\path\to\content-pipeline"
```

### Instructions — Mac

1. Before proceeding, revisit [Lesson 5.1, Step 4](5-1_Your_Claude_Code_Daily_Habits.md#anchor-step-4) — confirm you trust both scheduled skills' output from manual runs first.
2. Open **Terminal** and run `crontab -e` (opens in the `nano` editor by default).
3. Add both lines below on a daily or weekly cadence, then save (`Ctrl+O`, Enter, `Ctrl+X` in nano). Leave `/draft-content` for you to run by hand, once you've reviewed the digest.

### The Scheduled Commands — Mac

```text
0 8 * * * claude -p "/gather-articles" --cwd "$HOME/content-pipeline"
5 8 * * * claude -p "/compile-digest" --cwd "$HOME/content-pipeline"
```

<!-- WARNING: Mac — Grant Full Disk Access | cron jobs on macOS often fail silently unless the terminal app running them has Full Disk Access. Go to System Settings → Privacy & Security → Full Disk Access and enable it for Terminal (or your terminal app). -->

<!-- WARNING: This Step Is Optional | Running all three commands yourself already works. Automating only the first two, and keeping the draft step manual, is a deliberate choice — not a requirement. -->

<!-- NOTE: Why Leave Drafting Manual | Automating research is low-risk — worst case, an irrelevant article gets logged. Automating what gets published carries more risk, so this lesson keeps a person deciding when to draft and reviewing before anything goes out. -->

<!-- NOTE: Turning It Off | On Windows: disable or delete the two scheduled tasks in Windows Task Scheduler. On Mac: run crontab -e and delete or comment out both lines. Either way, also disable the plugin the same way shown in Lesson 5.3, Step 6, if you want to stop entirely. Your logged articles and past digests stay exactly as they are either way. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed all three required steps (Step 4 is optional). Confirm your setup by checking each item below:

- [ ] `data/seen-articles-log.md` grows with each `/gather-articles` run without duplicating articles
- [ ] `/compile-digest` produces a digest grouped by theme, not a flat list
- [ ] `/draft-content` produces a draft that references specific articles from the digest, in your brand voice
- [ ] You reviewed the draft against the source articles before considering it finished

<!-- NOTE: Not Working? | If the draft reads generically instead of referencing real articles, confirm draft-content is actually reading the digest file, not writing from general knowledge. -->

---

<!-- CELEBRATION: Curriculum Complete! | You have built four real automations across four different data sources — a webpage, email and calendar, public feeds, and news articles — all using the same gather-respond-assemble shape. -->

### What's Next

You have finished this course. You know how AI models work and how to prompt them well (Module 1), how to set up your computer (Module 2), how to run Claude Code on your own files (Module 3), how to build a claude.ai Project (Module 4), and how to package a repeatable, multi-step workflow as a Claude Code plugin — with daily habits, MCP connections, and teardown steps built in along the way (Module 5).

Pick one recurring task from your own role that this course hasn't covered yet, and build a plugin around it using the same shape: check or gather something, compile or respond to it, produce a finished output. Start small — one skill, like Lesson 5.5, is sometimes the whole answer. And whatever you build, make sure you know how to turn it off — Lesson 5.1 and every automation lesson since has said why that matters.

**Related Resources:**
- [claude.ai](https://claude.ai) — The Claude AI platform
- [code.claude.com/docs](https://code.claude.com/docs) — Official documentation
- [support.claude.com](https://support.claude.com) — Help center and account support

<!-- TIP: The Pattern Is the Takeaway | Gather, compile, produce. Check, draft, assemble. Scan, log, digest. Four lessons, one repeating shape — that shape is what to carry into your own next workflow, more than any single command. -->

<!-- CHILDREN -->