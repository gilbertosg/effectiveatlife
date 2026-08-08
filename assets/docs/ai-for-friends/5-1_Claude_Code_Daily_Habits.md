<!-- HERO: Lesson 5.1: Your Claude Code Daily Habits | The small habits that separate someone who used Claude Code once from someone who uses it every day. -->

<!-- TOC: Overview#anchor-overview | Step 1: Manage Your Session#anchor-step-1 | Step 2: Review Diffs Without Slowing Down#anchor-step-2 | Step 3: Watch Your Usage#anchor-step-3 | Step 4: Before You Automate Anything#anchor-step-4 | Verification#anchor-verification -->

## Overview

Module 3 got Claude Code installed and walked you through one hands-on tutorial. This lesson is the bridge between "I did the tutorial once" and "I open this every day." Four habits — managing your session, reviewing diffs quickly, watching your usage, and knowing what changes once you start automating — are what the rest of this module assumes you already have.

### Why This Matters

Every lesson from here on builds something: a plugin, a connection to your email, a scheduled task. None of that is safe or sustainable without the habits in this lesson first. Skipping this lesson is how people end up with a cluttered session that gives worse answers, a usage cap they hit mid-afternoon, or a scheduled task they forgot they built.

### Prerequisites

- [Module 3: Claude Code — AI on Your Own Files](3-claude-code-setup.md), completed and installed

### Time to Complete

**15 to 20 minutes**

<!-- PROGRESS: Step 1: Manage Your Session | Step 2: Review Diffs Fast | Step 3: Watch Your Usage | Step 4: Before You Automate | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-1 -->

## Step 1: Manage Your Session

A Claude Code session is a running conversation, the same way a claude.ai chat is — except you'll open and close many of these a day, on real work. Three commands cover almost everything you need to manage that.

### What You'll Do

You will learn the three session commands you'll reach for daily and when to use each one.

### Instructions

1. Read the three commands in the table below.
2. Practice each one right now in an open Claude Code session: run a small task, then try `/clear`, reopen with `/resume`, and note what carries over and what doesn't.
3. Adopt the rule in the tip below as your default: start a fresh session per task, not per day.

### The Three Session Commands

| Command | What It Does | When to Use It |
|---------|--------------|-----------------|
| `/clear` | Wipes the current conversation and starts fresh, in the same folder | Switching to an unrelated task in the same project |
| `/resume` | Reopens a previous session, with its full history | Picking back up on something you paused, later the same day or the next |
| `/compact` | Summarizes the conversation so far and keeps working with a smaller history | A long session is running slow or giving worse answers, but you're not done with the task |

<!-- INFO: Same Idea as Module 1's Context Window Lesson | A long, cluttered session is the "lost in the middle" problem from Lesson 1.1, applied to your own working session instead of one long document. /compact and /clear are how you clean the desk. -->

<!-- TIP: One Session Per Task, Not One Session Per Day | Starting a new session for each distinct task — instead of running everything in one session all day — keeps every answer sharp and makes /resume actually useful, since each session stays about one thing. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Review Diffs Without Slowing Down

Module 3 taught you that every edit arrives as a diff you approve or reject. That's correct and still your most important safety habit. Doing it fast, every time, is what makes it sustainable daily.

### What You'll Do

You will learn a two-second habit for reviewing diffs so you never end up rubber-stamping changes out of fatigue.

### Instructions

1. Read the three questions below. Ask all three, every single time a diff appears — even on the tenth diff of the day.
2. Practice on your next real edit: before you approve, answer all three out loud or in your head.
3. If any answer is "no" or "not sure," ask Claude to explain the change instead of approving.

### The Three-Question Diff Check

1. **Does this match what I asked for?** Not "does it look reasonable" — does it match your actual instruction.
2. **Is anything changed that I didn't ask about?** Scope creep in a diff is the most common way an unwanted change slips through.
3. **Would I be comfortable if this were the final version, unreviewed?** If the answer is no, you're not done reviewing yet.

<!-- WARNING: Fatigue Is the Real Risk, Not the AI | The tenth diff of the day is exactly when people start clicking "allow" without reading. That's a human failure mode, not a Claude Code one — the fix is a habit, not a setting. -->

<!-- TIP: Approve in Small Batches | If you're reviewing many similar diffs (e.g., ten résumé summaries), review and approve five, then check the actual saved files before doing the next five. Catching a pattern-level mistake early is cheaper than catching it at the end. -->

---

<!-- ANCHOR: anchor-step-3 -->

## Step 3: Watch Your Usage

Lesson 1.4 taught you how to pick a model based on cost. That lesson was written for claude.ai chat. Claude Code draws from the same plan, and daily use makes usage awareness a habit worth having, not a one-time lesson.

### What You'll Do

You will learn where to check your usage and the one command that keeps a single session lean.

### Instructions

1. Check your current usage under **Settings → Usage** on claude.ai — the same account, the same limits, whether you're in a browser chat or a Claude Code session.
2. Use `/clear` between unrelated tasks (Step 1) — this is your single biggest lever for staying under a session's usage cap, since a long, cluttered session burns more tokens per answer than a fresh, focused one.
3. If you're running the same task daily (the whole point of this module), notice its typical cost once, so a sudden spike is easy to spot later.

<!-- INFO: One Pool, Two Surfaces | claude.ai chat and Claude Code are not separate budgets. A heavy afternoon in one affects what's left for the other. -->

<!-- TIP: Cost Awareness Compounds in Module 5 | Once a skill runs on a schedule (starting in Lesson 5.3), it uses your plan's usage every time it fires, whether or not you're watching. Get comfortable checking Settings → Usage now, before anything runs unattended. -->

---

<!-- ANCHOR: anchor-step-4 -->

## Step 4: Before You Automate Anything

The rest of this module builds real automations: plugins, live connections to your email and calendar, and tasks that run on a schedule without you at the keyboard. One thing changes the moment something runs unattended: you're no longer there to review the diff. This checklist is what to have in place before that happens, so you only need to read it once.

### What You'll Do

You will read four rules that apply to every scheduled or unattended task in this module, and commit to checking all four before you turn any of them on.

### Instructions

1. Read the four rules below.
2. Notice that none of them are optional footnotes — they're the actual safety model for automation, replacing the diff-review habit from Step 2 for anything that runs without you watching.
3. Return to this step before you complete Step 4 or 5 in any later lesson in this module that mentions scheduling.

### The Four Rules for Anything Unattended

1. **Plan Mode's diff review does not apply here.** Nobody is at the keyboard to approve or reject a change when a scheduled task fires. Only automate a skill you have already run, reviewed, and trusted by hand, several times, first.
2. **A silent failure looks identical to nothing happening.** If a scheduled task fails, you usually get no error — you just don't get the output you expected. Check the actual result the first several times a schedule runs, not just "did it seem to work."
3. **Unattended tasks still cost usage every time they run.** A daily schedule that costs a small amount per run adds up over a month. Know roughly what a task costs (Step 3) before putting it on a schedule that runs without your attention.
4. **Know how to turn it off.** Before you turn any schedule on, find where you'd turn it off — later lessons in this module show exactly where. A habit you can't stop isn't a habit, it's a liability.

<!-- WARNING: This Checklist Applies to Every Later Lesson's Scheduling Step | Lessons 5.3, 5.5, 5.6, and 5.7 each have an optional "run this automatically" step. Every one of them assumes you've internalized these four rules first — they won't repeat this checklist in full each time. -->

<!-- NOTE: Uninstalling and Disabling | Later lessons show exactly how to remove a scheduled task and disable a plugin once you no longer need it. Rule 4 above is why that guidance is there — not as an afterthought, but as part of the same trust model as the diff review itself. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed all four steps. Confirm your understanding by checking each item below:

- [ ] You can name the three session commands (`/clear`, `/resume`, `/compact`) and when to use each
- [ ] You can state the three-question diff check from memory
- [ ] You know where to check your usage and why `/clear` helps keep it under control
- [ ] You can state all four rules for anything unattended, especially that Plan Mode's diff review doesn't apply once a task runs without you

<!-- NOTE: Not Working? | If any of this feels abstract, that's normal before you've automated anything. Come back and re-read Step 4 specifically once you reach the first scheduling step in Lesson 5.3 — it will make more sense with a real task in front of you. -->

---

<!-- CELEBRATION: Lesson Complete! | You now have the daily habits this entire module assumes — session hygiene, fast diff review, usage awareness, and the safety rules for anything unattended. -->

### What's Next

**Next Lesson:** [Lesson 5.2: Installing Anthropic Skills](5-2_Installing_Anthropic_Skills.md)

**Related Resources:**
- [claude.ai](https://claude.ai) — Check Settings → Usage
- [code.claude.com/docs](https://code.claude.com/docs) — Official documentation
- [support.claude.com](https://support.claude.com) — Help center and troubleshooting

<!-- TIP: Practice Today, Not Later | Run /clear, /resume, and /compact at least once each in your next real session. Reading about them is not the same as knowing what they feel like to use. -->

<!-- CHILDREN -->
