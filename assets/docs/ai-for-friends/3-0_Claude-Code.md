<!-- HERO: Module 3: Claude Code — Terminal, Files, and Projects | Install Claude Code and point it at a folder of your real documents so it can draft, edit, and organize them for you. Then set up a Claude Project on the web so it remembers your standing instructions and reference material every time. No technical background required. -->

<!-- TOC: Overview#anchor-overview | Lessons in This Module#anchor-lessons | Key Concepts#anchor-concepts | What's Next#anchor-next -->

## Overview

Claude Code is an AI assistant that works directly on the files and folders on your computer. You ask in plain English; it reads, drafts, edits, and organizes real documents. It shows you every proposed change before saving anything, so nothing lands without your approval. Once that's working, this module goes further: a Claude Project on the web gives you the same standing instructions and reference material, so you stop re-explaining your role, your rules, and your reference documents in every new chat — two surfaces, one assistant, no copy-pasting your context back in either way.

### Who This Module Is For

This module targets professionals who work across many documents at once. No programming experience or terminal background is required.

**Target roles:**
- HR professionals
- Industrial engineering professionals
- International relations professionals
- Legal professionals
- Marketing professionals

### Why This Matters

The web version of Claude is a conversation *about* your documents. Claude Code works *on* them. Point it at a folder of many files and one instruction replaces dozens of individual uploads or copy-pastes. Output lands as real saved files, and every edit arrives as a before/after view you approve or reject. A Claude Project takes that same idea to the web: set it up once with your standing instructions and reference files, and every chat inside it gets to work immediately, with nothing re-pasted.

### What This Looks Like in Your Role

| Role | What Changes |
|---|---|
| **HR** | Screen 40 résumés against one job description in a single pass instead of uploading them one by one. A Recruiting Project then holds your rubric and tone permanently, so you stop re-explaining it in every chat. |
| **Industrial Engineering** | Compare cycle-time and downtime data across many shift reports in a single pass instead of exporting each one separately. Process terminology (takt time, changeover, OEE) lives permanently in CLAUDE.md or a Project's instructions instead of being re-explained each session. |
| **Legal** | Compare a clause such as indemnity language across many agreements in one pass with a single comparison table. Every edit arrives as a redline-style diff you approve or reject, and defined terms live permanently in a CLAUDE.md file, with a Contract Review Project handling quick web-chat questions the same way. |
| **Marketing** | Turn one piece of content into several channel variants as separate saved files from one instruction. Your brand voice and banned-words list live in CLAUDE.md for file work and in a Project's custom instructions for everyday chat. |
| **International Relations** | Check a ministry's agreements page and keep a running Word log automatically. A Diplomatic Affairs Project handles the same protocol and department-mapping rules for one-off web-chat questions. |

### By the End of This Module, You Will

- Know what Claude Code does that the web version can't, and when the web version is still better
- Have Claude Code installed and connected to your Claude Pro account
- Run a real task against a folder of your own documents and get a saved file back
- Know the safety habits that keep the tool scoped: Plan Mode, diff review, tight folder scoping
- Create a Claude Project with custom instructions written for your role, and know when to reach for it instead of Claude Code
- Upload reference documents a Project can draw on in every conversation, and keep its standing instructions current

### Prerequisites

- Claude Pro plan active (~$20/mo; the free tier does not include Claude Code)
- Windows 10 (build 1809+) or Windows 11, or macOS 12 or later, 4 GB+ RAM, and the ability to install software
- A folder of non-confidential practice documents

### Time to Complete

**100 to 110 minutes** across 7 lessons. Lesson 3.1 stands alone — do it first. Lessons 3.2 through 3.7 build on each other in order, since each one assumes the last one's setup exists already.

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-lessons -->

## Lessons in This Module

| # | Lesson | Duration | What You Will Learn |
|---|--------|----------|---------------------|
| 3.1 | [Claude Code Onboarding Guide](3-1_Claude_Code_Installation.md) | 35-45 min | When to use the web version versus Claude Code, full install and login, recommended VS Code extensions, terminal basics, a hands-on tutorial ending in a real saved file, CLAUDE.md, and reusable slash commands. |
| 3.2 | [What Is a Claude Project?](3-2_Claude_Code_Project_Basics.md) | 10 min | The three parts of a Project, why it beats a blank chat, and how to scope your first one. |
| 3.3 | [Creating Your First Project](3-3_First_Project.md) | 15 min | The setup click path, the four sections of good custom instructions, and copy-ready templates for all five roles. |
| 3.4 | [Giving Your Project Reference Material](3-4_Project_Material.md) | 10 min | How to upload reference files, which files to upload for your role, and exactly what a Project can and cannot reach. |
| 3.5 | [Keeping Your Standing Instructions Current](3-5_Project_Instructions.md) | 10 min | Where a Project's memory actually lives and how to update it when a standing fact changes. |
| 3.6 | [Using Your Project to Design More Projects](3-6_Using_Projects_to_Design_More.md) | 10 min | A prompt that has Claude draft your next Project end to end, plus Projects worth building across all five roles. |
| 3.7 | [Worked Examples by Role](3-7_Examples_by_Role.md) | 10 min | One complete, end-to-end Project — name, instructions, files, and a sample chat — for all five roles. |

<!-- WARNING: Confidentiality — Read This Before You Start | Claude Pro is a personal subscription with no corporate data agreement, admin oversight, audit logs, or retention controls. Practice on non-sensitive material. Before running real client files, employee records, or privileged material through it, check with your employer's IT or Legal team. -->

<!-- NOTE: You Cannot Break Your Computer | Claude asks permission before it changes anything and shows you exactly what it plans to change. Plan Mode restricts it to reading and thinking until you approve a written plan. -->

<!-- INFO: When the Web Version Is Still Better | Use the web version for quick one-off questions with no files, working from your phone, brainstorming out loud, or image and screenshot analysis. Most people use both. -->

---

<!-- ANCHOR: anchor-concepts -->

## Key Concepts

Core terms introduced in this module. The lesson where each term is first defined is listed so you can return to the source explanation.

| Term | Defined In | Plain English Meaning |
|------|-----------|----------------------|
| **Claude Code** | Lesson 3.1 | An AI assistant that reads, drafts, and edits the real files in a folder you open on your computer. |
| **VS Code** | Lesson 3.1 | The free Microsoft program Claude Code runs inside. Like Word, but built to open a whole folder of files at once. |
| **Project Folder** | Lesson 3.1 | The one folder you open. Claude can only see and touch files inside it, and nothing else. |
| **Terminal** | Lesson 3.1 | A text box where you type instructions instead of clicking. You need about six commands total. |
| **Diff** | Lesson 3.1 | A side-by-side before/after view of a change Claude proposes, which you approve or reject. |
| **CLAUDE.md** | Lesson 3.1 | A plain-text file of standing instructions Claude reads automatically at the start of every session in that folder. |
| **Slash Command** | Lesson 3.1 | A saved, reusable prompt you trigger with a short `/name` instead of retyping a long instruction. |
| **Claude Project** | Lesson 3.2 | A reusable workspace on claude.ai built around one kind of recurring work — the web-side counterpart to a Claude Code project folder. |
| **Custom Instructions** | Lesson 3.2 | Plain-language standing rules that tell Claude who it is, how to behave, and how to format answers — a Project's version of CLAUDE.md. |
| **Project Knowledge** | Lesson 3.2 | Reference files you upload once so Claude can draw on them in any chat inside the Project. |

<!-- EXPAND: Full Key Concepts Reference -->

| Term | Defined In | Plain English Meaning |
|------|-----------|----------------------|
| **Claude Cowork** | Lesson 3.1 | The option built for editing or creating a single Word, Excel, or PowerPoint file, with no terminal needed. |
| **Plan Mode** | Lesson 3.1 | A setting that limits Claude to reading and thinking until you approve a written plan. Your best guardrail. |
| **Permission Prompt** | Lesson 3.1 | The ask that appears before Claude writes or edits. Options are allow-once, allow-always, or deny. |
| **Integrated Terminal** | Lesson 3.1 | The terminal panel built into VS Code, opened with Ctrl and the backtick key (same shortcut on Mac). The only terminal you need. |
| **PowerShell** | Lesson 3.1 | A built-in Windows program for typing instructions. Used once, just for the install. (Mac uses Terminal with a one-line curl install instead.) |
| **PATH** | Lesson 3.1 | The list of places your computer looks for programs. A command must be on it to run from any folder — on Windows this lives in environment variables, on Mac in `~/.zshrc`. |
| **Extension** | Lesson 3.1 | A small add-on for VS Code, like an app for your phone, that adds features such as PDF viewing or spell check. |
| **Markdown (.md)** | Lesson 3.1 | A simple plain-text formatting style. The recommended format to work in, exporting to Word or PDF at the end. |
| **Model** | Lesson 3.1 | The specific AI doing the work, such as Sonnet or Opus, shown in the prompt's model indicator. |
| **Token** | Lesson 3.1 | A unit of text usage that counts against your plan limit. |
| **Usage Limits** | Lesson 3.1 | Claude Pro's rolling roughly 5-hour session caps plus weekly caps. Web chat and Claude Code share one pool. |
| **Git for Windows** | Lesson 3.1 | A recommended free install that adds Git Bash, an alternative terminal, to your machine. (On Mac, Git ships via Xcode Command Line Tools — no separate download needed.) |
| **Standing Instruction** | Lesson 3.5 | A fact that should always be true, written into the custom instructions so every chat uses it. |
| **My Context Block** | Lesson 3.3 | The section of your instructions holding the details about your role, systems, and preferences. |
| **Project Scope** | Lesson 3.2 | The single kind of recurring work a Project covers. One kind of work per Project. |
| **Meta Prompt** | Lesson 3.6 | A prompt that asks Claude to design a whole new Project for you, ready to paste in. |
| **Plain Chat** | Lesson 3.2 | A single conversation that forgets everything the moment it ends. |
| **Recruiting Assistant** | Lesson 3.2 | The example HR Project: candidate summaries, outreach messages, pipeline tracking. |
| **Contract Review** | Lesson 3.2 | The example Legal Project: clause review, risk flagging, tracking defined terms. |
| **Content Assistant** | Lesson 3.2 | The example Marketing Project: repurposing content, enforcing brand voice, campaign summaries. |
| **Process & Work-Order Assistant** | Lesson 3.2 | The example Industrial Engineering Project: nonconformance summaries, standard-work drafting, work-order status tracking. |
| **Diplomatic Affairs Assistant** | Lesson 3.2 | The example International Relations Project: briefing memos, protocol checks, agreement and cable tracking. |
| **Identity Line** | Lesson 3.3 | The "You are my ___ assistant" line that sets Claude's role for every chat in the Project. |
| **Responsibilities List** | Lesson 3.3 | The numbered list of standing jobs the Project handles. |
| **Output Format Rule** | Lesson 3.3 | Your default answer format (table, bullets) and any required fields. |
| **Required Fields** | Lesson 3.3 | The specific items Claude must extract or include in every answer. |
| **Reference Shelf** | Lesson 3.4 | The set of uploaded files a Project draws on, in place of you pasting them each time. |
| **Live System Access** | Lesson 3.4 | What a Project reaches by default: nothing beyond what you upload. Connectors (Module 4, Lesson 4.4) are the one way to deliberately extend that. |
| **Project Memory** | Lesson 3.5 | The custom instructions and uploaded files. There is no separate learned-preference feature. |
| **Repeat-Correction Rule** | Lesson 3.5 | If you correct Claude the same way in every chat, that correction belongs in the instructions. |
| **Project Template** | Lesson 3.6 | The four-part setup (name, description, instructions, file list) for a new Project. |

<!-- /EXPAND -->

<!-- INFO: Custom Instructions and CLAUDE.md Are the Same Idea, Two Surfaces | A Project's custom instructions (3.2–3.7) and Claude Code's CLAUDE.md (3.1) both do the same job: standing rules Claude reads automatically instead of you restating them every time. The difference is only which surface you're on — the terminal or the web. If you end up using both daily, that similarity is deliberate — the fix for "I keep repeating myself" is the same fix either way. -->

---

<!-- ANCHOR: anchor-next -->

## What's Next

**Next Module:** [Module 4: Automating Workflows with Claude Code](4-0_Claude_Code_Workflows.md)

Module 4 teaches Claude Code daily habits, live connections to real systems through MCP, and how to package a repeatable, multi-step workflow as a plugin — building on both the file-based Claude Code skills from Lesson 3.1 and the Project skills from Lessons 3.2 through 3.7.

**Support Resources:**

| Resource | Link | Purpose |
|----------|------|----------|
| Claude | claude.ai | Sign up and use Claude in your browser |
| Claude Docs | code.claude.com/docs | Official documentation |
| Claude Support | support.claude.com | Help center and account support |

<!-- CHILDREN -->
