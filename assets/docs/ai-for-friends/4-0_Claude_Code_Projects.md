<!-- HERO: Module 4: Building Your AI Personal Assistant | Build a Claude Project — a reusable workspace on claude.ai that knows your role, follows your standing instructions, and draws on your own reference documents. -->

<!-- TOC: Overview#anchor-overview | Lessons in This Module#anchor-lessons | Key Concepts#anchor-concepts | What's Next#anchor-next -->

## Overview

A Claude Project is a dedicated workspace on claude.ai built around one kind of recurring work. A plain chat starts from a blank slate every time. A Project does not. It holds your standing instructions and reference documents in one place, so every chat inside it gets to work immediately.

This module is a deliberate detour. Module 3 got you running Claude Code in a terminal; Module 5 takes Claude Code further into automation. In between, this module stays on the web, because a claude.ai Project solves a different, equally common problem: work you do in ordinary chat, on any device, that you're tired of re-explaining every time. Learn both — which one to reach for is mostly about whether you're working on files in a folder (Claude Code) or having a conversation (a Project).

### Who This Module Is For

This module targets professionals who already use Claude in a plain chat and want to stop re-explaining themselves on every conversation.

**Target roles:**
- Legal professionals
- Marketing professionals
- Industrial engineers
- International relations professionals
- HR professionals (recruiters)

### Why This Matters

A plain chat makes you re-explain your job, re-paste your templates, and re-state your rules every time. A Project holds all three permanently. You write your standing instructions once, upload your reference files once, and every future chat inside the Project inherits both.

### By the End of This Module, You Will

- Create a Claude Project with custom instructions written for your role
- Upload reference documents a Project can draw on in every conversation
- Keep a Project's standing instructions current as your work changes
- Use a working Project to design the next one

### Prerequisites

- A Claude account (claude.ai)
- Module 1 recommended, specifically [Lesson 1.1: How AI Models Work](1-1_How_AI_Models_Work.md)
- 10-15 minutes per lesson

### Time to Complete

**65 minutes** across 6 lessons.

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-lessons -->

## Lessons in This Module

| # | Lesson | Duration | What You Will Learn |
|---|--------|----------|---------------------|
| 4.1 | [What Is a Claude Project?](4-1_What_Is_A_Claude_Project.md) | 10 min | The three parts of a Project, why it beats a blank chat, and how to scope your first one. |
| 4.2 | [Creating Your First Project](4-2_Creating_Your_First_Project.md) | 15 min | The setup click path, the four sections of good custom instructions, and copy-ready templates for Legal, Marketing, Industrial Engineering, International Relations, and HR. |
| 4.3 | [Adding Project Knowledge](4-3_Adding_Project_Knowledge.md) | 10 min | How to upload reference files, which files to upload for your role, and exactly what a Project can and cannot reach. |
| 4.4 | [Keeping Your Standing Instructions Current](4-4_Keeping_Instructions_Current.md) | 10 min | Where a Project's memory actually lives and how to update it when a standing fact changes. |
| 4.5 | [Using Your Project to Design More Projects](4-5_Designing_More_Projects.md) | 10 min | A prompt that has Claude draft your next Project end to end, plus Projects worth building across all five roles. |
| 4.6 | [Worked Examples by Role](4-6_Worked_Examples_By_Role.md) | 10 min | One complete, end-to-end Project — name, instructions, files, and a sample chat — for Legal, Marketing, Industrial Engineering, International Relations, and HR. |

<!-- TIP: Complete Lessons in Order | Lessons 4.2 and 4.3 build directly on the Project you create in 4.1. Skipping ahead leaves you with nothing to practice on. -->

<!-- NOTE: Build a Real Project, Not a Practice One | Pick recurring work you actually do. A Project you use once a week teaches you more than five you set up and abandon. -->

<!-- INFO: Bookmark Lessons 4.2 and 4.3 | Lesson 4.2 holds the copy-ready instruction templates and Lesson 4.3 holds the upload guidance. You will return to both every time you build a new Project. -->

---

<!-- ANCHOR: anchor-concepts -->

## Key Concepts

Core terms introduced in this module. The lesson where each term is first defined is listed so you can return to the source explanation.

| Term | Defined In | Plain English Meaning |
|------|-----------|----------------------|
| **Claude Project** | Lesson 4.1 | A reusable workspace on claude.ai built around one kind of recurring work. |
| **Custom Instructions** | Lesson 4.1 | Plain-language standing rules that tell Claude who it is, how to behave, and how to format answers. |
| **Project Knowledge** | Lesson 4.1 | Reference files you upload once so Claude can draw on them in any chat inside the Project. |
| **Standing Instruction** | Lesson 4.4 | A fact that should always be true, written into the custom instructions so every chat uses it. |
| **My Context Block** | Lesson 4.2 | The section of your instructions holding the details about your role, systems, and preferences. |
| **Project Scope** | Lesson 4.1 | The single kind of recurring work a Project covers. One kind of work per Project. |
| **Meta Prompt** | Lesson 4.5 | A prompt that asks Claude to design a whole new Project for you, ready to paste in. |

<!-- EXPAND: Full Key Concepts Reference -->

| Term | Defined In | Plain English Meaning |
|------|-----------|----------------------|
| **Plain Chat** | Lesson 4.1 | A single conversation that forgets everything the moment it ends. |
| **Recruiting Assistant** | Lesson 4.1 | The example HR Project: candidate summaries, outreach messages, pipeline tracking. |
| **Contract Review** | Lesson 4.1 | The example Legal Project: clause review, risk flagging, tracking defined terms. |
| **Content Assistant** | Lesson 4.1 | The example Marketing Project: repurposing content, enforcing brand voice, campaign summaries. |
| **Process & Work-Order Assistant** | Lesson 4.1 | The example Industrial Engineering Project: nonconformance summaries, standard-work drafting, work-order status tracking. |
| **Diplomatic Affairs Assistant** | Lesson 4.1 | The example International Relations Project: briefing memos, protocol checks, agreement and cable tracking. |
| **Identity Line** | Lesson 4.2 | The "You are my ___ assistant" line that sets Claude's role for every chat in the Project. |
| **Responsibilities List** | Lesson 4.2 | The numbered list of standing jobs the Project handles. |
| **Output Format Rule** | Lesson 4.2 | Your default answer format (table, bullets) and any required fields. |
| **Required Fields** | Lesson 4.2 | The specific items Claude must extract or include in every answer. |
| **Reference Shelf** | Lesson 4.3 | The set of uploaded files a Project draws on, in place of you pasting them each time. |
| **Live System Access** | Lesson 4.3 | What a Project reaches by default: nothing beyond what you upload. Connectors (Module 5, Lesson 5.4) are the one way to deliberately extend that. |
| **Project Memory** | Lesson 4.4 | The custom instructions and uploaded files. There is no separate learned-preference feature. |
| **Repeat-Correction Rule** | Lesson 4.4 | If you correct Claude the same way in every chat, that correction belongs in the instructions. |
| **Project Template** | Lesson 4.5 | The four-part setup (name, description, instructions, file list) for a new Project. |

<!-- /EXPAND -->

<!-- INFO: Custom Instructions and CLAUDE.md Are the Same Idea, Two Surfaces | A Project's custom instructions (this module) and Claude Code's CLAUDE.md (Module 5) both do the same job: standing rules Claude reads automatically instead of you restating them every time. The difference is only which surface you're on. If you end up using both daily, that similarity is deliberate — the fix for "I keep repeating myself" is the same fix either way. -->

---

<!-- ANCHOR: anchor-next -->

## What's Next

**Next Module:** [Module 5: Automating Workflows with Claude Code](5-automating-workflows.md)

You know how AI models work and how to prompt them well (Module 1), how to set up your computer (Module 2), and how to run Claude Code on your own files (Module 3). Now you can build a Claude Project that knows your role, follows your standing instructions, and draws on your own reference documents.

Pick one recurring type of work and build a Project around it this week. That is what makes it stick. Module 5 goes one step further: teaching Claude Code to read and write native Word, PDF, and PowerPoint files, and chaining several steps into one repeatable, automated workflow.

**Support Resources:**

| Resource | Link | Purpose |
|----------|------|----------|
| Claude | claude.ai | Sign up and use Claude in your browser |
| Claude Docs | code.claude.com/docs | Official documentation |
| Claude Support | support.claude.com | Help center and account support |

<!-- CELEBRATION: Module 4 Complete! | You can now build a Claude Project that knows your role and remembers your standing instructions. -->

<!-- CHILDREN -->