<!-- HERO: Lesson 5.3: International Relations — Automating the Agreements Workflow | Check a website daily, draft the follow-up, and build a running Word document — as one packaged Claude Code plugin. -->

<!-- TOC: Overview#anchor-overview | Step 0: How a Skill and a Plugin Actually Work#anchor-step-0 | Step 1: Create the Claude Code Project#anchor-step-1 | Step 2: Dictate the Whole Workflow#anchor-step-2 | Step 3: Build the Plugin's Three Skills#anchor-step-3 | Step 4: Install and Run Your Plugin#anchor-step-4 | Step 5: Optional — Run It Automatically Every Day#anchor-step-5 | Step 6: Turning It Off#anchor-step-6 | Verification#anchor-verification -->

## Overview

This lesson builds one real, complete automation from the ground up: a desk officer's daily task of checking a government or ministry webpage for new agreements, drafting the follow-up correspondence, and keeping a single, growing Word document current with every agreement, response, and personal note. By the end, that daily task is a plugin — a packaged set of three chained skills — you trigger with one command instead of doing five things by hand.

### Why This Matters

The task itself is not complicated. It is repetitive: same website, same filter, same email pattern, same document, every single day. That repetition is exactly what a Claude Code plugin is for. You describe the job once, Claude Code builds the structure, and every future run is one command instead of a fresh explanation.

If International Relations isn't your role, the mechanic in Step 0 and Steps 3 through 6 is what to focus on — Legal, Marketing, HR, and Industrial Engineering versions of this exact shape appear in Lessons 5.5 through 5.7.

### Prerequisites

- [Lesson 5.2: Installing Anthropic Skills](5-2_Installing_Anthropic_Skills.md), completed — Step 3 of this lesson writes a Word document
- [Lesson 5.1: Your Claude Code Daily Habits](5-1_Your_Claude_Code_Daily_Habits.md) recommended, especially Step 4's rules for anything unattended before you reach Step 5 below
- The web address of the page you want to monitor (a ministry press-release page, a treaty registry, or similar)

### Time to Complete

**40 to 55 minutes**

<!-- PROGRESS: Step 0: The Mechanic | Step 1: Create the Project | Step 2: Dictate the Workflow | Step 3: Build the Three Skills | Step 4: Install and Run | Step 5: Optional Automation | Step 6: Turning It Off | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-0 -->

## Step 0: How a Skill and a Plugin Actually Work

Before the International Relations story starts, here is the mechanic underneath it, stated plainly and without any one role's example attached — the same two ideas every later lesson in this module reuses.

### What You'll Do

You will learn what a skill is, what a plugin is, and how they relate, in the abstract, before seeing them applied to one specific job.

### Instructions

1. Read the two definitions below.
2. Read the one-sentence rule for when a job needs a plugin instead of a single skill.
3. Keep this in mind through Step 3 — the International Relations details are one example of this general shape, not the shape itself.

### The Two Ideas

**A skill** is one packaged capability: a set of instructions, written for Claude rather than for a human reader, saved as a file called `SKILL.md`, that Claude follows whenever you trigger it — usually with a `/name` command. A skill does one job well: check a webpage, draft an email, build a document.

**A plugin** is several related skills bundled together under one name, so they can share rules and be installed, updated, or removed as a single unit. A plugin is the right container exactly when two or more skills need to agree on the same facts — the same priority list, the same file format, the same tone — and you don't want to maintain that agreement by hand in three separate places.

| If your job is... | Reach for... |
|---|---|
| One well-defined, standalone task | A single skill (see Lesson 5.5 for an example that stays at exactly one skill) |
| Several steps that share rules, data, or a file format | A plugin bundling multiple skills (this lesson builds one with three) |

<!-- INFO: This Is the Whole Mechanic | Everything else in this lesson — the file tree, the commands, the marketplace — is this one idea, made concrete for one specific job: checking agreements for a foreign ministry desk. -->

---

<!-- ANCHOR: anchor-step-1 -->

## Step 1: Create the Claude Code Project

Every Claude Code plugin needs a home folder. This step creates it and confirms Claude Code is running inside it before you describe anything.

### What You'll Do

You will create a new, empty project folder and open it in Claude Code.

### Instructions

1. Create a new folder, for example `ir-agreements-tracker`, anywhere you keep working files (not inside a folder with unrelated confidential material — see the confidentiality warning in Module 3).
2. Open that folder in VS Code (**File → Open Folder**, or right-click the folder → **Open with Code**).
3. Open the integrated terminal (**Ctrl + `**).
4. Type `claude` and press Enter to start Claude Code inside this folder.

### What You Should See

```text
ir-agreements-tracker/ ← empty, just created

Claude Code prompt is active in the terminal, scoped to this folder only.
```

<!-- NOTE: An Empty Folder Is the Right Starting Point | You are not building anything by hand yet. Step 2 hands Claude Code a full description and lets it build the structure. -->

<!-- WARNING: Scope This Folder Tightly | Claude Code can only see files inside the folder you open. Keep this folder dedicated to this one workflow — do not open a parent folder that also contains unrelated sensitive material. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Dictate the Whole Workflow

This is the unusual part of this lesson: instead of typing a short instruction and iterating, you describe the entire workflow in one long message, as if you were briefing a new staffer on their first day. You can type this, or speak it using your operating system's built-in dictation (Windows: press **Win + H** to start dictating into any text box, including the Claude Code prompt. Mac: open **System Settings → Keyboard → Dictation** to turn it on, then press **Fn** twice to start dictating) — either way, the words land in the prompt as plain text and Claude Code treats them exactly the same.

### What You'll Do

You will give Claude Code one long, detailed description of the whole workflow and let it design the folder structure, `README.md`, and `CLAUDE.md` on its own.

### Instructions

1. Read the example dictation below. It is written to be spoken aloud — plain sentences, no special syntax.
2. Adapt it with your real website, your real priority topics, and your real accountable areas.
3. Paste or dictate the whole thing as one message to Claude Code.
4. Let Claude Code ask clarifying questions if it has any, and answer them.
5. Review what it proposes before approving — Claude Code should describe a folder structure, a `README.md`, and a `CLAUDE.md` for your approval, not write files silently.

### Example Dictation (Adapt and Read Aloud, or Paste as Typed)

```text
I want to set up a project that automates something I do every day by
hand. Each morning I go to the Ministry of Trade's public agreements
page and check whether any new agreements have been posted since
yesterday. I only care about agreements that touch trade cooperation,
regional security, or cultural exchange — those are the topics the
foreign minister and the chancellor track closely. Everything else on
that page I ignore.

When I find a new agreement that matters, I need three things to
happen. First, I need a short summary of the agreement, including its
title, the counterpart ministry, the date, and why it matters to our
priority topics. Second, I need a follow-up email drafted to send to
the department here that is accountable for that topic — for trade
agreements that's our Trade Directorate, for security it's our Security
Cooperation Office, and for cultural exchange it's our Cultural Affairs
desk. Third, once I've sent that follow-up and gotten a response back
from the accountable department, I need all of it — the agreement
summary, the follow-up email, their response, and any notes I add
myself — captured in one running Word document that keeps growing over
time, with each new agreement added in a consistent format at the top,
never overwriting what's already there.

I want this set up as a proper folder structure with a README
explaining what it does and a CLAUDE.md with our standing rules — our
priority topics, our accountable-department mapping, and our tone for
follow-up emails. I'll build out the actual steps as a plugin after
this is set up. For now, just get the folder, the README, and the
CLAUDE.md in place, and ask me anything you need to know first.
```

### What Claude Code Should Produce

After a short back-and-forth (expect it to ask what the website's address is, how "new" should be judged the first time there's no history yet, and what tone you want for the follow-up emails), Claude Code proposes something close to this:

```text
ir-agreements-tracker/
├── README.md Explains the workflow in plain language
├── CLAUDE.md Standing rules: priority topics, accountable
│ departments, email tone, document format
├── data/
│ └── agreements-log.md Running log of every agreement seen so far
├── drafts/ Follow-up emails land here before sending
└── output/
└── agreements-record.docx The running Word document (created in Step 3)
```

**A sample `CLAUDE.md` Claude Code might draft:**

```markdown
# IR Agreements Tracker — Standing Rules

## Priority Topics
Only agreements touching these topics are in scope:
- Trade cooperation
- Regional security
- Cultural exchange

## Accountable Departments
- Trade cooperation → Trade Directorate
- Regional security → Security Cooperation Office
- Cultural exchange → Cultural Affairs desk

## Follow-Up Email Tone
Professional, concise, and warm. Always confirm receipt and name the
specific next step or document being requested.

## Document Format
Newest agreement always goes at the top of agreements-record.docx.
Never overwrite or delete a previous entry.
```

<!-- INFO: Why Dictate the Whole Thing at Once | Claude Code makes better structural decisions with full context up front than with five short, disconnected instructions. This is the same "front-load context" principle from Lesson 1.2, applied to project setup instead of a single prompt. -->

<!-- TIP: Review Before You Approve | Claude Code should describe this plan and ask before creating files (this is Plan Mode behavior from Module 3). Read the proposed CLAUDE.md carefully — it becomes the standing rule for every future run. -->

---

<!-- ANCHOR: anchor-step-3 -->

## Step 3: Build the Plugin's Three Skills

With the folder, README, and CLAUDE.md in place, the next step packages the actual workflow — the plugin idea from Step 0, made concrete.

### What You'll Do

You will understand why this workflow is a plugin and not three loose commands, then have Claude Code build the plugin's file structure and its three chained skills.

### Instructions

1. Read why a plugin fits this task better than three separate commands.
2. Review the target file structure below.
3. Ask Claude Code to build it, one skill at a time, describing each skill's job precisely (the three descriptions below are ready to use).
4. Review each `SKILL.md` Claude Code writes before moving to the next skill.

### Why a Plugin, Not Three Loose Commands

Three separate one-off commands — one to check the website, one to draft an email, one to build the document — could each work alone. But they share the same priority-topics list, the same accountable-department mapping, and the same document format. Three loose commands mean writing (and later fixing) that shared logic three times, and nothing stops a fourth, unrelated command from claiming a similar name later. A plugin groups all three under one name, with the shared rules written once and referenced by all three — exactly the rule from Step 0's table.

<!-- INFO: One Namespace, Shared Rules | A plugin's three skills all live under one plugin name and can all read the same rules file. Fix a rule once — the accountable-department mapping, for instance — and every skill that depends on it is corrected at the same time. -->

### The Target File Structure

```text
ir-agreements-tracker/
├── .claude-plugin/
│ └── marketplace.json Catalog entry pointing at the plugin below
├── plugins/
│ └── agreements-tracker/
│ ├── .claude-plugin/
│ │ └── plugin.json Plugin manifest: name, version, description
│ ├── skills/
│ │ ├── check-agreements/
│ │ │ └── SKILL.md /check-agreements
│ │ ├── draft-followup/
│ │ │ └── SKILL.md /draft-followup
│ │ └── build-agreement-doc/
│ │ └── SKILL.md /build-agreement-doc
│ ├── rules/
│ │ └── priority-topics.md Shared: topics + accountable departments
│ └── references/
│ └── document-template.md Shared: the Word document's required format
├── data/
│ └── agreements-log.md
├── drafts/
└── output/
└── agreements-record.docx
```

### Skill 1 — `/check-agreements`

**What to tell Claude Code to build:**

```text
Build a skill called check-agreements. Its job: fetch the Ministry of
Trade agreements page I give you, compare what's listed against
data/agreements-log.md (today's file, if any exist yet, is the
history), and identify only the agreements not already in that log.
Of those new agreements, keep only the ones matching our priority
topics in rules/priority-topics.md. For each one that qualifies,
append it to data/agreements-log.md with its title, counterpart,
date, and which priority topic it matches. Report back a short list
of what's new and in scope — nothing else needs to happen yet.
```

**What this produces (`skills/check-agreements/SKILL.md`, abbreviated):**

```markdown
---
name: check-agreements
description: Fetch the Ministry of Trade agreements page, compare
against the existing log, and append any new agreement matching a
priority topic. Use when the user says "check for new agreements" or
"/check-agreements."
---

# check-agreements

1. Fetch the agreements page at the URL on file in CLAUDE.md.
2. Read data/agreements-log.md. If it doesn't exist, treat every
agreement on the page as new — this is the first run.
3. Compare the page's list of agreements against the log. Identify only
titles not already present.
4. For each new agreement, check it against rules/priority-topics.md.
Discard any that match no priority topic.
5. Append each qualifying agreement to data/agreements-log.md: title,
counterpart, date, matched topic, and a status of "new."
6. Report the list of newly logged agreements to the user.
```

### Skill 2 — `/draft-followup`

**What to tell Claude Code to build:**

```text
Build a skill called draft-followup. Its job: look at
data/agreements-log.md for any agreement still marked "new," and for
each one, draft a follow-up email to the accountable department listed
in rules/priority-topics.md for that agreement's topic. Save each
draft as a file in drafts/, named after the agreement. Use the tone
described in CLAUDE.md. Once a draft is saved, update that agreement's
status in the log to "follow-up drafted."
```

**What this produces (`skills/draft-followup/SKILL.md`, abbreviated):**

```markdown
---
name: draft-followup
description: Draft a follow-up email to the accountable department for
every agreement in the log still marked "new." Use when the user says
"draft follow-ups" or "/draft-followup."
---

# draft-followup

1. Read data/agreements-log.md. Find every entry marked "new."
2. For each one, look up its topic's accountable department in
rules/priority-topics.md.
3. Draft a short email to that department: confirm receipt of the
agreement, summarize it in two sentences, and request their
position or next-step input. Use the tone rule in CLAUDE.md.
4. Save the draft to drafts/<agreement-title>-followup.md.
5. Update that agreement's status in the log to "follow-up drafted."
6. Report which drafts were created and where to find them.
```

### Skill 3 — `/build-agreement-doc`

**What to tell Claude Code to build:**

```text
Build a skill called build-agreement-doc. Its job: use the docx skill
to create output/agreements-record.docx if it doesn't exist yet, or
update it if it does. For every agreement in data/agreements-log.md
marked "follow-up drafted" or further along, add an entry at the TOP
of the document — never overwrite older entries — following the
format in references/document-template.md. Each entry should combine:
the agreement summary, the follow-up email text from drafts/, the
department's response (I will paste that in when I have it), and any
notes I add. If no response or notes exist yet for an agreement, leave
those sections marked "pending" rather than skipping the entry.
```

**What this produces (`skills/build-agreement-doc/SKILL.md`, abbreviated):**

```markdown
---
name: build-agreement-doc
description: Create or update output/agreements-record.docx, adding
each ready agreement at the top in the standard format. Use when the
user says "update the agreement doc," "add this response," or
"/build-agreement-doc."
---

# build-agreement-doc

1. If output/agreements-record.docx doesn't exist, create it using the
docx skill, following references/document-template.md.
2. For every agreement in data/agreements-log.md marked "follow-up
drafted" or later, check whether it already has an entry in the
document.
3. For any agreement missing an entry, insert one at the very top of
the document (never remove or reorder existing entries):
- Agreement summary (title, counterpart, date, topic)
- The follow-up email sent (from drafts/)
- The department's response, if the user has provided it — else
"Response: pending"
- The user's own notes, if any — else omit that section
4. Save the document and confirm it still opens correctly.
5. Report which entries were added or updated.
```

<!-- WARNING: Build One Skill at a Time | Ask Claude Code for one SKILL.md, review it, then ask for the next. Building all three in one instruction makes mistakes harder to spot and fix. -->

<!-- TIP: ${CLAUDE_PLUGIN_ROOT} Keeps Paths Portable | Inside a skill, references to rules/ or references/ files use the ${CLAUDE_PLUGIN_ROOT} variable rather than a hardcoded path, so the plugin still works if it's ever moved or shared. Claude Code handles this automatically when it writes the skill files — you don't need to write that syntax yourself. -->

---

<!-- ANCHOR: anchor-step-4 -->

## Step 4: Install and Run Your Plugin

A plugin sitting in a folder isn't active yet. This step registers it with Claude Code as a local marketplace and installs it, so the three commands are available in every future session.

### What You'll Do

You will register your project folder as a marketplace, install the plugin from it, and run all three skills against a real agreement.

### Instructions

1. Register the local marketplace, pointing at your project folder.
2. Install the plugin from that marketplace.
3. Restart Claude Code.
4. Run the three commands in order.

### The Commands

```text
/plugin marketplace add /path/to/ir-agreements-tracker
/plugin install agreements-tracker@ir-agreements-tracker
```

Then, after restarting Claude Code inside the project folder:

```text
/check-agreements
/draft-followup
/build-agreement-doc
```

### What You Should See

```text
/check-agreements → "1 new agreement in scope: Framework Agreement on
Cross-Border Logistics Cooperation (Trade
cooperation). Logged."

/draft-followup → "Drafted 1 follow-up email: drafts/framework-
agreement-on-cross-border-logistics-cooperation-
followup.md, addressed to the Trade Directorate."

/build-agreement-doc → "Added 1 entry to output/agreements-record.docx.
Response: pending — paste it in when it arrives
and re-run this skill to fill it in."
```

<!-- NOTE: Pasting In the Response Later | When the accountable department replies, paste their response into your next message and ask Claude Code to run /build-agreement-doc again — it updates that entry's "Response: pending" line instead of creating a duplicate. -->

<!-- INFO: This Is the Whole Point | One instruction — /check-agreements — replaces opening a browser, scanning a webpage by eye, and remembering what you already saw yesterday. Three commands replace an entire morning routine. -->

---

<!-- ANCHOR: anchor-step-5 -->

## Step 5: Optional — Run It Automatically Every Day

Everything above still requires you to type three commands each morning. This step is entirely optional: it makes `/check-agreements` run on its own, on a schedule, with no one at the keyboard.

### What You'll Do

You will learn the realistic, non-developer way to run this daily without opening Claude Code yourself — after confirming you've applied Lesson 5.1's four rules for anything unattended.

### Instructions — Windows

1. Before proceeding, revisit [Lesson 5.1, Step 4](5-1_Your_Claude_Code_Daily_Habits.md#anchor-step-4) — this step assumes you've run `/check-agreements` by hand several times already and trust its output.
2. Open **Windows Task Scheduler** (search for it in the Start menu).
3. Create a new basic task, set to run daily at a time of your choosing.
4. Set the action to run a program, pointing at the `claude` command with the check-agreements skill as its instruction.
5. Save the task.

### The Scheduled Command — Windows

```text
claude -p "/check-agreements" --cwd "C:\path\to\ir-agreements-tracker"
```

### Instructions — Mac

1. Before proceeding, revisit [Lesson 5.1, Step 4](5-1_Your_Claude_Code_Daily_Habits.md#anchor-step-4) — this step assumes you've run `/check-agreements` by hand several times already and trust its output.
2. Open **Terminal** and run `crontab -e` to open your personal schedule (opens in the `nano` editor by default).
3. Add one line for a daily 8am run, then save (`Ctrl+O`, Enter, `Ctrl+X` in nano).

### The Scheduled Command — Mac

```text
0 8 * * * claude -p "/check-agreements" --cwd "$HOME/ir-agreements-tracker"
```

<!-- WARNING: Mac — Grant Full Disk Access | cron jobs on macOS often fail silently unless the terminal app running them has Full Disk Access. Go to System Settings → Privacy & Security → Full Disk Access and enable it for Terminal (or your terminal app) — this is the most common reason a scheduled Mac task appears to do nothing. -->

<!-- WARNING: This Step Is Optional | Everything in Steps 1 through 4 already works by typing three commands yourself. Only set this up if you specifically want the check to run unattended, with no one watching. -->

<!-- NOTE: Drafting and the Document Still Need You | Scheduling only automates the check step. Drafting a follow-up and adding a response to the document still need a person to review the output and paste in real replies — that judgment stays yours by design. -->

---

<!-- ANCHOR: anchor-step-6 -->

## Step 6: Turning It Off

Anything you can turn on in this lesson, you should know how to turn off — the fourth rule from Lesson 5.1, Step 4.

### What You'll Do

You will learn where to disable the scheduled task and how to disable the plugin itself, without deleting your project folder or its data.

### Instructions

1. To stop the daily schedule on **Windows**: open **Windows Task Scheduler**, find the task by the name you gave it in Step 5, and either **Disable** it (keeps it, stops it running) or **Delete** it (removes it entirely).
2. To stop the daily schedule on **Mac**: run `crontab -e`, delete or comment out (add a `#` at the start of) the line you added, then save.
3. To disable the plugin without removing your files: open your Claude Code settings file and find the `enabledPlugins` entry for `agreements-tracker`; set it to `false`. The plugin's commands stop appearing, but nothing in your project folder is touched.
4. To remove the plugin entirely: ask Claude Code, "uninstall the agreements-tracker plugin," and review what it proposes before confirming — it should remove the plugin's registration, not your `data/`, `drafts/`, or `output/` folders.

<!-- NOTE: Your Data Outlives the Plugin | agreements-log.md and agreements-record.docx are ordinary files in your project folder. Disabling or removing the plugin does not delete them — only the /check-agreements, /draft-followup, and /build-agreement-doc commands stop working until you reinstall. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed all five required steps (Step 5 is optional; Step 6 only applies once you want to stop). Confirm your setup by checking each item below:

- [ ] You can state the difference between a skill and a plugin in one sentence each
- [ ] The project folder has a `README.md` and `CLAUDE.md` describing the workflow and standing rules
- [ ] The plugin has three skills — `check-agreements`, `draft-followup`, `build-agreement-doc` — each with its own `SKILL.md`
- [ ] The plugin is installed and all three commands run without an error
- [ ] `output/agreements-record.docx` opens correctly and shows the newest agreement at the top
- [ ] You know where you'd disable the scheduled task and the plugin if you needed to

<!-- NOTE: Not Working? | If a command isn't recognized, confirm the plugin installed correctly in Step 4 and that you restarted Claude Code afterward. If the Word document won't build, confirm Lesson 5.2's document skills are installed. -->

---

<!-- CELEBRATION: Lesson Complete! | You have built a real, three-step automated workflow from a plain-language description to a working plugin, and you know how to turn it off. -->

### What's Next

**Next Lesson:** [Lesson 5.4: What Is an MCP Server?](5-4_What_Is_An_MCP_Server.md)

This lesson checked a website — something Claude Code could already do with no extra setup. The next lesson covers what changes when the data source is something Claude Code can't reach on its own, like your email or calendar, before the next three lessons build on that.

**Related Resources:**
- [claude.ai](https://claude.ai) — The Claude AI platform
- [code.claude.com/docs](https://code.claude.com/docs) — Official documentation
- [support.claude.com](https://support.claude.com) — Help center and troubleshooting

<!-- TIP: Reuse This Shape for Any Role | Check something new, draft a response, assemble a document — swap the website for a court docket, a competitor's press page, or a supplier's compliance portal, and the same three-skill shape still fits. -->

<!-- CHILDREN -->