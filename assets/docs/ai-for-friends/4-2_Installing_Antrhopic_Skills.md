<!-- HERO: Lesson 4.2: Installing Anthropic Skills | Add four skills in one install and Claude Code stops treating Word, PDF, and PowerPoint files as plain text. -->

<!-- TOC: Overview#anchor-overview | Step 1: What a Skill Adds That Plain Claude Code Doesn't Have#anchor-step-1 | Step 2: Add Anthropic's Skill Marketplace#anchor-step-2 | Step 3: Install the Document Skills#anchor-step-3 | Step 4: Verify It Worked#anchor-step-4 | Verification#anchor-verification -->

## Overview

By the end of this lesson, you will have installed Anthropic's document-processing skills and confirmed Claude Code can build a real, openable .docx file. Out of the box, Claude Code can read a Word file as compressed text and struggles to write a properly formatted one. These skills fix both.

### Why This Matters

Lesson 4.3 ends with Claude Code assembling a running Word document — an agreement summary, a follow-up email, a response, and your notes, added to the same file every day without breaking its formatting. That only works if Claude Code has the right skill installed first. This lesson is that one-time setup step.

### Prerequisites

- [Module 3: Claude Code — Terminal, Files, and Projects](3-0_Claude-Code.md), completed and installed
- [Lesson 4.1: Your Claude Code Daily Habits](4-1_Claude_Code_Daily_Habits.md) recommended
- Claude Code running in a terminal (VS Code's integrated terminal is fine)

### Time to Complete

**15 minutes**

<!-- PROGRESS: Step 1: What a Skill Adds | Step 2: Add the Marketplace | Step 3: Install the Skills | Step 4: Verify | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-1 -->

## Step 1: What a Skill Adds That Plain Claude Code Doesn't Have

A `.docx`, `.pptx`, or `.xlsx` file is not plain text — it is a small archive of formatting instructions. Without a skill telling it how, Claude Code can still open one, but it reads it as compressed, hard-to-follow content, and writing a new one from scratch produces a file that often will not open correctly in Word or PowerPoint.

### What You'll Do

You will understand what a skill is and why "document skills" specifically are worth installing before Lesson 4.3.

### Instructions

1. Read the before/after comparison below.
2. Note that this is a one-time install — once added, every Claude Code project on your computer can use it.
3. Keep this in mind heading into Step 2: you are installing one plugin that bundles four skills at once.

### Before and After

| Without the Skill | With the Skill Installed |
|---|---|
| Claude Code reads a `.docx` as raw, hard-to-parse content | Claude Code reads the actual formatted text, tables, and headings |
| A new Word file Claude Code writes often has broken formatting or won't open cleanly | A new Word file opens correctly, with real headings, tables, and page setup |
| PDFs are readable but nothing can be extracted cleanly | Text and simple tables extract cleanly from a PDF |
| PowerPoint decks are barely usable as input or output | Claude Code can read slide content and build a properly formatted deck |

<!-- INFO: One Plugin, Four Skills | Anthropic packages docx, pdf, pptx, and xlsx together as a single plugin called `document-skills`. You install it once and get all four. -->

<!-- TIP: This Is Optional Until You Need It | If you never ask Claude Code to touch a Word, PDF, or PowerPoint file, you don't need this. Lesson 4.3 needs it for its Word-document step, so install it now if you plan to do that lesson. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Add Anthropic's Skill Marketplace

Claude Code does not ship with every possible skill pre-installed. Skills come from a **marketplace** — a catalog of installable plugins — and you point Claude Code at one before you can install anything from it.

### What You'll Do

You will register Anthropic's official skill marketplace with Claude Code.

### Instructions

1. Open Claude Code in a terminal (any project folder is fine for this step).
2. Type the command below and press Enter.
3. Wait for Claude Code to confirm the marketplace was added.

### The Command

```text
/plugin marketplace add anthropics/skills
```

### What You Should See

```text
Marketplace "anthropic-agent-skills" added.
Run /plugin install <name>@anthropic-agent-skills to install a plugin from it.
```

<!-- NOTE: One-Time Step | You only need to add a given marketplace once per computer. Every future Claude Code session already knows about it. -->

<!-- WARNING: Only Add Marketplaces You Trust | A marketplace is a catalog of instructions Claude Code will follow. `anthropics/skills` is Anthropic's own official repository. Do not add a marketplace from an unfamiliar source without checking with your IT or security team first. -->

---

<!-- ANCHOR: anchor-step-3 -->

## Step 3: Install the Document Skills

With the marketplace added, installing the actual skills is one more command.

### What You'll Do

You will install the `document-skills` plugin, which bundles the docx, pdf, pptx, and xlsx skills together.

### Instructions

1. In the same Claude Code session, type the install command below.
2. Press Enter and wait for confirmation.
3. Restart Claude Code (close and reopen your terminal, or start a new session) so the new skills load.

### The Command

```text
/plugin install document-skills@anthropic-agent-skills
```

### What You Should See

```text
Installed "document-skills" (docx, pdf, pptx, xlsx).
Restart Claude Code for the new skills to take effect.
```

<!-- TIP: Check What's Installed | Type /plugin at any time to see a list of every marketplace and plugin currently installed on your computer. -->

---

<!-- ANCHOR: anchor-step-4 -->

## Step 4: Verify It Worked

The fastest proof a skill is active is asking Claude Code to use it.

### What You'll Do

You will ask Claude Code to build a one-page Word document and confirm it opens correctly.

### Instructions

1. Open a project folder in Claude Code (any folder — this is just a test).
2. Type the prompt below.
3. Open the resulting file in Word (or a viewer that supports .docx) and confirm it looks like a real document, not broken formatting.

### The Test Prompt

```text
Create a one-page Word document called skill-test.docx with a title,
"Skill Test," and three bullet points describing what you can now do
with Word files that you couldn't do before this skill was installed.
```

### What You Should See

A real `skill-test.docx` file appears in your project folder's Explorer sidebar. Opening it shows a formatted title and three bullet points — not a wall of XML or broken text.

<!-- INFO: If It Didn't Work | Confirm you restarted Claude Code after Step 3. Skills load at session start, not mid-session. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed all four steps. Confirm your setup by checking each item below:

- [ ] `/plugin marketplace add anthropics/skills` completed without an error
- [ ] `/plugin install document-skills@anthropic-agent-skills` completed and you restarted Claude Code
- [ ] Claude Code built a `skill-test.docx` file that opens correctly with real formatting

<!-- NOTE: Not Working? | If the test file won't open or looks broken, confirm the install completed in Step 3 and that you restarted the session. If it still fails, run /doctor and check the output for a plugin-related error. -->

---

<!-- CELEBRATION: Lesson Complete! | Claude Code can now read and write real Word, PDF, and PowerPoint files — everything Lesson 4.3's Word-document step needs. -->

### What's Next

**Next Lesson:** [Lesson 4.3: International Relations — Automating the Agreements Workflow](4-3_Automating_Agreements_RI_Example.md)

**Related Resources:**
- [claude.ai](https://claude.ai) — The Claude AI platform
- [code.claude.com/docs](https://code.claude.com/docs) — Official documentation
- [support.claude.com](https://support.claude.com) — Help center and troubleshooting

<!-- TIP: Delete the Test File | skill-test.docx was only there to prove the install worked. Delete it once you've confirmed it opens correctly. -->

<!-- CHILDREN -->
