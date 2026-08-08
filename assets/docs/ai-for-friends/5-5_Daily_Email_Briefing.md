<!-- HERO: Lesson 5.5: Daily Briefing from Email and Calendar | Connect Claude Code to your inbox and calendar, then read one morning summary instead of two apps. -->

<!-- TOC: Overview#anchor-overview | Step 1: Connect an Email and Calendar MCP Server#anchor-step-1 | Step 2: Dictate What "Day Ahead" Means to You#anchor-step-2 | Step 3: Build the Daily-Briefing Skill#anchor-step-3 | Step 4: Optional — Run It Automatically Every Morning#anchor-step-4 | Verification#anchor-verification -->

## Overview

This lesson connects Claude Code to your real email and calendar, then builds one skill that reads both and hands you a single, structured briefing: today's schedule, what to know before each meeting, and anything urgent sitting in your inbox. Where Lesson 5.3 built a three-skill plugin, this one shows the other end of the range — sometimes one well-built skill is the whole job.

### Why This Matters

Most mornings start with opening two apps and piecing together the same picture by hand: what's on the calendar, what needs a reply, what's actually urgent versus just unread. That's a pattern this course has already covered — checking something repetitive and turning it into a summary — applied to a data source everyone already has.

### Prerequisites

- [Lesson 5.4: What Is an MCP Server?](5-4_What_Is_An_MCP_Server.md), completed — this lesson assumes you already know the `claude mcp add` command and `/mcp` and won't re-explain them
- [Lesson 5.3: International Relations — Automating the Agreements Workflow](5-3_International_Relations_Agreements_Workflow.md) recommended — this lesson assumes you already know how a `SKILL.md` and the dictate-to-setup pattern work and won't re-explain them in full
- An email account and calendar you're allowed to connect an AI tool to (check with your organization first if this is a work account)

### Time to Complete

**20 to 25 minutes**

<!-- PROGRESS: Step 1: Connect Email and Calendar | Step 2: Dictate What You Need | Step 3: Build the Skill | Step 4: Optional Scheduling | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-1 -->

## Step 1: Connect an Email and Calendar MCP Server

Claude Code has no built-in access to your email or calendar. It needs an MCP connection — the mechanism from Lesson 5.4 — before it can read a single message or event.

### What You'll Do

You will identify which connector matches your provider, add it using the pattern from Lesson 5.4, and confirm it's connected.

### Instructions

1. Identify your provider: Google Workspace (Gmail + Google Calendar) or Microsoft 365 (Outlook Mail + Outlook Calendar) are the two most common.
2. Check `code.claude.com/docs`, claude.ai's Connectors settings, or type `/mcp` inside Claude Code to see whether a ready-made connector exists for your provider today — Lesson 5.4, Step 4 covers what to do if it doesn't yet.
3. Add the connector using the `claude mcp add --scope user --transport <type> <name> <address>` pattern from Lesson 5.4, Step 3, filling in the real name and address you found.
4. Approve the sign-in prompt that opens in your browser.
5. Run `/mcp` to confirm it connected and see the tools it provides.

| Provider | What You're Connecting | Where to Check the Current Setup |
|---|---|---|
| Google Workspace | Gmail + Google Calendar | `/mcp` inside Claude Code, claude.ai Connectors, or code.claude.com/docs |
| Microsoft 365 | Outlook Mail + Outlook Calendar | `/mcp` inside Claude Code, claude.ai Connectors, or code.claude.com/docs |

<!-- WARNING: Check With Your Organization First | Connecting an AI tool to a work email or calendar account may need IT or security approval, depending on your employer's policy. Confirm before connecting a work account — a personal account is a safer place to practice this lesson first. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Dictate What "Day Ahead" Means to You

With the connector in place, describe the briefing you actually want — in one long message, the same dictate-to-setup approach from Lesson 5.3.

### What You'll Do

You will describe your ideal morning briefing in one message and let Claude Code propose the project folder, `README.md`, and `CLAUDE.md`.

### Instructions

1. Create a new folder, for example `daily-briefing`, and open it in Claude Code.
2. Adapt and send the example dictation below.
3. Answer any clarifying questions Claude Code asks.
4. Review the proposed `CLAUDE.md` before approving it.

### Example Dictation

```text
I want a daily briefing that pulls together my calendar and my email
so I don't have to check two apps every morning. For today's calendar,
I want every meeting listed with the time, the attendees, and one line
on what I need to know or prepare before it. For email, I only care
about messages from the last 24 hours that are unread or flagged —
summarize what's actually urgent and skip routine notifications and
anything already read. If an email is from someone who's also on
today's calendar, connect the two — mention it next to that meeting
instead of as a separate item. Keep the whole briefing short enough to
read in two minutes. Set this up as a project with a README and a
CLAUDE.md capturing these rules, and ask me anything you need first.
```

### What Claude Code Should Produce

```text
daily-briefing/
├── README.md Explains the briefing and how to run it
├── CLAUDE.md Standing rules: what counts as urgent, how
│ long the briefing should be, how to cross-
│ reference meetings and email
└── output/
└── todays-briefing.md Where each day's briefing lands
```

<!-- TIP: Keep This One Simple | Not every workflow needs a three-skill plugin. This lesson builds toward exactly one skill — the shape should match the job, not the other way around. -->

---

<!-- ANCHOR: anchor-step-3 -->

## Step 3: Build the Daily-Briefing Skill

One skill, using both the calendar and email tools your connector provides.

### What You'll Do

You will ask Claude Code to build a single `/daily-briefing` skill and review the result.

### Instructions

1. Ask Claude Code to build the skill, describing its job precisely (the description below is ready to use).
2. Review the `SKILL.md` it produces.
3. Run `/daily-briefing` and check the output against what you actually needed to know this morning.

### What to Tell Claude Code to Build

```text
Build a skill called daily-briefing. Its job: pull today's calendar
events using the calendar tool, and pull unread or flagged email from
the last 24 hours using the email tool. Cross-reference the two — if
an email sender is also an attendee on a meeting today, mention that
email next to that meeting instead of as a separate item. Produce one
short briefing: a schedule block listing each meeting with attendees
and a one-line prep note, followed by a short list of anything urgent
left in email that doesn't tie to a meeting. Save it to
output/todays-briefing.md and show it to me.
```

### What This Produces (`skills/daily-briefing/SKILL.md`, abbreviated)

```markdown
---
name: daily-briefing
description: Pull today's calendar and recent email into one morning
briefing, cross-referencing meeting attendees with email senders. Use
when the user says "give me my briefing," "what's today look like,"
or "/daily-briefing."
---

# daily-briefing

1. Fetch today's calendar events using the connected calendar tool.
2. Fetch email from the last 24 hours that is unread or flagged, using
the connected email tool.
3. For each meeting, check whether any attendee also sent a fetched
email. If so, fold a one-line summary of that email into that
meeting's entry instead of listing it separately.
4. Write the schedule block: time, attendees, and one prep line per
meeting.
5. Write a short "Flagged in Email" section for anything urgent that
didn't tie to a meeting.
6. Save the result to output/todays-briefing.md and display it.
```

### Sample Output

```text
**Today's Briefing — Tuesday**

09:00 — Budget Review (with Marcus Chen, Priya Nair)
Marcus emailed last night asking to move the Q3 numbers earlier in
the agenda — worth confirming before the meeting starts.

11:30 — Vendor Call (with external: Aria Logistics)
No related email. First call with this vendor — no history yet.

**Flagged in Email**
- IT: password reset required by end of week (not tied to a meeting)
```

<!-- INFO: What Made This Fast | The cross-reference step — connecting Marcus's email to the 9:00 meeting — is the entire value of asking one skill to look at two sources together instead of checking each app separately. -->

---

<!-- ANCHOR: anchor-step-4 -->

## Step 4: Optional — Run It Automatically Every Morning

Everything above still requires opening Claude Code and typing `/daily-briefing`. This step is optional: it runs the briefing before you sit down.

### What You'll Do

You will schedule the skill to run automatically each morning using Windows Task Scheduler — the same approach from Lesson 5.3.

### Instructions

1. Before proceeding, revisit [Lesson 5.1, Step 4](5-1_Your_Claude_Code_Daily_Habits.md#anchor-step-4) — confirm you trust `/daily-briefing`'s output from several manual runs first.
2. Open **Windows Task Scheduler**.
3. Create a basic task set to run daily, for example at 7:00 AM.
4. Point the action at the command below.

### The Scheduled Command

```text
claude -p "/daily-briefing" --cwd "C:\path\to\daily-briefing"
```

<!-- WARNING: This Step Is Optional | Typing /daily-briefing yourself each morning already works. Only automate this if you specifically want the file waiting for you before you sit down. -->

<!-- NOTE: Turning It Off | To stop the schedule, open Windows Task Scheduler, find the task by name, and Disable or Delete it — the same two options as Lesson 5.3, Step 6. Your connected MCP server and your CLAUDE.md rules are untouched either way. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed all three required steps (Step 4 is optional). Confirm your setup by checking each item below:

- [ ] An email and calendar MCP connector is added and confirmed working with `/mcp`
- [ ] The project folder has a `README.md` and `CLAUDE.md` describing your briefing rules
- [ ] `/daily-briefing` runs and produces a briefing that correctly cross-references at least one meeting and one email

<!-- NOTE: Not Working? | If the calendar or email tool isn't found, confirm the connector shows as connected in /mcp and that you restarted Claude Code after adding it. Lesson 5.4 covers this connection in full if you skipped it. -->

---

<!-- CELEBRATION: Lesson Complete! | You connected Claude Code to real, live data outside your files for the first time, and built one skill that reads two sources together. -->

### What's Next

**Next Lesson:** [Lesson 5.6: Staying Informed — A Market-Awareness Digest](5-6_Staying_Informed_Market_Awareness_Digest.md)

**Related Resources:**
- [claude.ai](https://claude.ai) — The Claude AI platform
- [code.claude.com/docs](https://code.claude.com/docs) — Official documentation
- [support.claude.com](https://support.claude.com) — Help center and troubleshooting

<!-- TIP: One Skill Is Often Enough | Before building a multi-skill plugin, ask whether the job is really one step done well. This lesson's single skill replaced two apps and a mental cross-reference — that was the whole win. -->

<!-- CHILDREN -->