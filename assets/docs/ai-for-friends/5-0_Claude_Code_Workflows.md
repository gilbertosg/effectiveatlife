<!-- HERO: Module 5: Automating Workflows with Claude Code | Teach Claude Code to read and write native Office files, connect to live systems, and chain several steps into one repeatable, automated workflow. -->

<!-- TOC: Overview#anchor-overview | Which Lesson Is For You#anchor-roles | Lessons in This Module#anchor-lessons | Key Concepts#anchor-concepts | What's Next#anchor-next -->

## Overview

Module 3 taught you Claude Code on your own files. Module 4 taught you claude.ai Projects for recurring web-chat work — a deliberate detour onto the web surface before this module returns to Claude Code and takes automation further. This module combines those ideas into something new: daily habits that make Claude Code sustainable, live connections to systems Claude Code can't reach on its own, and a packaged, reusable set of steps — a **plugin** — so one recurring, multi-part job runs the same way every time you invoke it, instead of you re-explaining it from scratch.

### Who This Module Is For

This module is for anyone who does the same multi-step job on a recurring basis and has completed Module 3. It assumes you have never automated anything with Claude Code before — the first lesson is daily habits, not a plugin.

**Target roles:**
- Legal professionals
- Marketing professionals
- Industrial engineers
- International relations professionals
- HR professionals (recruiters)

### Why This Matters

A claude.ai Project remembers your instructions and your files, but every step still happens inside one chat, by hand. Claude Code can go further: it can read a live webpage, connect to your real email and calendar, write a native Word document, and chain several steps together into one packaged workflow you trigger with a single command — and reuse every day, week, or month without rebuilding it.

### By the End of This Module, You Will

- Have the daily habits — session hygiene, fast diff review, usage awareness — that make Claude Code sustainable before you automate anything
- Add Anthropic's document skills so Claude Code can read and write real .docx, .pdf, and .pptx files — not just plain text
- Understand the difference between a skill (one capability) and a plugin (several capabilities packaged together)
- Understand what an MCP connection is and add one yourself, on claude.ai and in Claude Code
- Walk through one complete, real automation: checking a government webpage daily for new agreements, drafting follow-up emails, and building a running Word document — built entirely by dictating the requirements and letting Claude Code do the setup
- Connect Claude Code to your email and calendar and generate a daily briefing for the day ahead
- Monitor several websites or public feeds for new information and email yourself a digest that accounts for what you've already seen
- Turn a pile of articles and news into one compiled, on-brand piece of content — ready to publish
- Know how to turn off everything you build — a scheduled task, a plugin, an MCP connection — not just how to start it

### Prerequisites

- [Module 3: Claude Code — AI on Your Own Files](3-claude-code-setup.md), completed and installed
- [Module 4: Building Your AI Personal Assistant](4-claude-code.md) recommended, especially [Lesson 4.6](4-6_Worked_Examples_By_Role.md)

### Time to Complete

**3 to 3.5 hours** across 7 lessons. Each lesson after 5.4 stands on its own — do 5.1 through 5.4 in order the first time, since each later lesson assumes them, then return to whichever of 5.5–5.7 matches a task you actually repeat.

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-roles -->

## Which Lesson Is For You

Only Lessons 5.3, 5.5, and 5.6 are written around one specific role's example. Every role should still complete 5.1, 5.2, and 5.4 — they're the daily habits, the document skills, and the MCP concept every later lesson depends on, regardless of role.

| Role | Written For You | The Shape Still Fits You In |
|---|---|---|
| International Relations | 5.3 (webpage → follow-up → Word document) | — |
| Marketing | 5.6 (source monitoring → context-aware digest) | 5.3's shape (check → respond → assemble); 5.7's content pipeline was built with Marketing in mind too |
| Legal | — | 5.3's shape, swapping the webpage for a court docket or filing portal; 5.6's shape for tracking a regulator's announcements |
| Industrial Engineering | — | 5.3's shape, swapping the webpage for a supplier compliance portal; 5.6's shape for a recurring nonconformance sweep |
| HR (Recruiting) | — | 5.5's single-skill shape, swapping calendar/email for an applicant-tracking system once an MCP connection exists for it |

<!-- NOTE: One Detailed Example, Several Reusable Shapes | Lesson 5.3 is written for International Relations, but the shape — check something new, draft a response, assemble output — repeats through 5.5, 5.6, and 5.7 with a different data source each time. Read the lesson written for your role closely, then skim at least one other — the pattern is what transfers, not the specific example. -->

---

<!-- ANCHOR: anchor-lessons -->

## Lessons in This Module

| # | Lesson | Duration | What You Will Learn |
|---|--------|----------|---------------------|
| 5.1 | [Your Claude Code Daily Habits](5-1_Your_Claude_Code_Daily_Habits.md) | 15-20 min | Session hygiene (`/clear`, `/resume`, `/compact`), a fast diff-review habit, usage awareness, and the four rules for anything that will run unattended. |
| 5.2 | [Installing Anthropic Skills](5-2_Installing_Anthropic_Skills.md) | 15 min | How to add Anthropic's document-processing skills so Claude Code can read and write real Word, PDF, and PowerPoint files. |
| 5.3 | [International Relations: Automating the Agreements Workflow](5-3_International_Relations_Agreements_Workflow.md) | 40-55 min | What a skill and a plugin actually are, then a full worked example: build a Claude Code project by dictating the requirements, package a three-step plugin that checks a webpage, drafts a follow-up email, and builds a running Word document — and how to turn it off. |
| 5.4 | [What Is an MCP Server?](5-4_What_Is_An_MCP_Server.md) | 20 min | What an MCP connection is, how to add one as a Connector on claude.ai, how to add one in Claude Code with `claude mcp add`, and the honest limits of what's available today. |
| 5.5 | [Daily Briefing from Email and Calendar](5-5_Daily_Briefing_Email_And_Calendar.md) | 20-25 min | Connect Claude Code to your email and calendar through an MCP connection, then build one skill that reads today's meetings and recent email into a single morning briefing. |
| 5.6 | [Staying Informed: A Market-Awareness Digest](5-6_Staying_Informed_Market_Awareness_Digest.md) | 25-30 min | Monitor several websites or public feeds, summarize only what's genuinely new against what you've already seen, and email yourself a digest — built for Marketing but useful for any role that needs to stay current. |
| 5.7 | [From Sources to Story: A Content-Generation Pipeline](5-7_From_Sources_To_Story_Content_Generation.md) | 30-35 min | Gather articles and news, compile them into one organized digest, and draft a finished, on-brand piece of content from it — the closing lesson of this course. |

<!-- TIP: Do 5.1 and 5.4 Before Any Automation Lesson | 5.1's four rules for anything unattended and 5.4's MCP mechanics are referenced, not re-explained, in every lesson from 5.3 onward. -->

<!-- NOTE: Do 5.2 Before 5.3, 5.6, or 5.7 | Any lesson that writes a Word document needs the document skills from 5.2 installed first. -->

---

<!-- ANCHOR: anchor-concepts -->

## Key Concepts

Core terms introduced in this module. The lesson where each term is first defined is listed so you can return to the source explanation.

| Term | Defined In | Plain English Meaning |
|------|-----------|----------------------|
| **Skill** | Lesson 5.2 | A packaged capability Claude Code can use, such as reading or writing a specific file type, or performing one well-defined task. |
| **Plugin** | Lesson 5.3 | Several related skills and commands packaged together as one reusable, distributable unit. |
| **Marketplace** | Lesson 5.2 | A catalog of installable plugins. Anthropic runs a public one; you can also point Claude Code at your own project folder as a private one. |
| **SKILL.md** | Lesson 5.3 | The one required file inside every skill folder — its instructions, written for Claude, not for a human reader. |
| **plugin.json** | Lesson 5.3 | The manifest file that names a plugin and lists its version, so Claude Code recognizes it as one unit. |
| **WebFetch** | Lesson 5.3 | Claude Code's built-in ability to open and read a live webpage — no extra setup required. |
| **MCP Server / Connector** | Lesson 5.4 | A live connection between Claude and a real system — your email or calendar provider, for example — added via claude.ai's Connectors or Claude Code's `claude mcp add`, so Claude can read and act on real data there. |
| **Knowledge Log** | Lesson 5.3 | A running file a skill checks against before reporting anything, so a second run reports only what's genuinely new — the same file behind "account for what I already know" in 5.3, 5.6, and 5.7. |
| **Content Digest** | Lesson 5.7 | A compiled, deduplicated summary pulled from several sources, organized by theme and ready to turn into one finished piece of content. |

<!-- EXPAND: Full Key Concepts Reference -->

| Term | Defined In | Plain English Meaning |
|------|-----------|----------------------|
| **Document Skills** | Lesson 5.2 | Anthropic's bundle of four skills — docx, pdf, pptx, xlsx — for reading and writing native Office files. |
| **`/plugin marketplace add`** | Lesson 5.2 | The command that tells Claude Code about a new catalog of installable plugins. |
| **`/plugin install`** | Lesson 5.2 | The command that adds one specific plugin from an already-known marketplace. |
| **Local Marketplace** | Lesson 5.3 | A marketplace whose catalog is just a folder on your own computer — no GitHub account or team required. |
| **Dictation-to-Setup** | Lesson 5.3 | Describing a whole workflow out loud (or by typing it as one long message) and letting Claude Code build the folder structure, README, and CLAUDE.md from that description. |
| **Chained Skills** | Lesson 5.3 | Multiple skills inside one plugin, each handling one stage of a multi-step workflow. |
| **`${CLAUDE_PLUGIN_ROOT}`** | Lesson 5.3 | A portable path variable a plugin's files use to reference its own scripts and templates, regardless of where it is installed. |
| **`claude mcp add`** | Lesson 5.4 | The Claude Code command that adds an MCP connection, with a transport type, a name, and an address or command. |
| **`--scope user`** | Lesson 5.4 | The flag that makes an MCP connection available in every Claude Code project on your computer, not just the one you added it from. |
| **`/mcp`** | Lesson 5.4 | The command that lists every MCP connection currently active in a session and the tools each one provides. |
| **The Four Rules for Anything Unattended** | Lesson 5.1 | Plan Mode's diff review doesn't apply once nothing's at the keyboard; a silent failure looks like nothing happened; scheduled runs still cost usage; know how to turn it off before you turn it on. |

<!-- /EXPAND -->

---

<!-- ANCHOR: anchor-next -->

## What's Next

You have reached the end of this curriculum. You know how AI models work and how to prompt them well (Module 1), how to set up your computer (Module 2), how to run Claude Code on your own files (Module 3), how to build a claude.ai Project (Module 4), and now how to build daily Claude Code habits, connect to live systems, and package a repeatable, multi-step workflow as a plugin (Module 5).

Pick one recurring, multi-step job you do today and build a small plugin around it. Start with one or two skills, not five — Lesson 5.5's single-skill briefing and Lesson 5.3's three-skill plugin are both real, complete examples of the right size for a first attempt.

<!-- INFO: Custom Instructions and CLAUDE.md Are the Same Idea, Two Surfaces | Module 4's custom instructions (claude.ai Projects) and this module's CLAUDE.md (Claude Code) both do the same job — standing rules Claude reads automatically instead of you restating them — for two different products. If you use both daily, that similarity is deliberate, not a coincidence: whichever surface you're on, the fix for "I keep repeating myself" is the same one. -->

**Support Resources:**

| Resource | Link | Purpose |
|----------|------|----------|
| Claude | claude.ai | Sign up and use Claude in your browser |
| Claude Docs | code.claude.com/docs | Official documentation |
| Claude Support | support.claude.com | Help center and account support |

<!-- CELEBRATION: Curriculum Complete! | You can now use Claude on the web, set up your computer, run Claude Code on your own files, build a Claude Project, connect Claude Code to live systems, and package a repeatable multi-step workflow as a plugin — and turn any of it off when you're done with it. -->

<!-- CHILDREN -->