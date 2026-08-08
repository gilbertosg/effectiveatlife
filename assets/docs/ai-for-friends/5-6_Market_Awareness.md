<!-- HERO: Lesson 5.6: Staying Informed — A Market-Awareness Digest | Monitor several sources, report only what's new, and get an email that keeps you current without checking anything by hand. -->

<!-- TOC: Overview#anchor-overview | Step 1: Choose Your Sources#anchor-step-1 | Step 2: Dictate the Workflow#anchor-step-2 | Step 3: Build the Two-Skill Plugin#anchor-step-3 | Step 4: Optional — Run It on a Schedule#anchor-step-4 | Verification#anchor-verification -->

## Overview

This lesson builds a market-awareness workflow: a short list of websites or public feeds gets checked regularly, only what's genuinely new gets summarized — with real context about what's already been seen — and a digest email lands in your inbox. This is the same check-something-new shape as Lesson 5.3, now aimed at staying current for content generation and market awareness, which is exactly why Marketing teams reach for this pattern most often. If Legal, HR, or Industrial Engineering is your role, this same shape fits a docket check, a compliance-portal sweep, or a nonconformance scan equally well — the "sources" are just different.

### Why This Matters

Staying informed usually means checking the same handful of sites over and over, most of the time finding nothing new. A digest that only reports genuine changes — and remembers what it already told you — turns that daily chore into a five-minute read that shows up on its own.

### Prerequisites

- [Lesson 5.3: International Relations — Automating the Agreements Workflow](5-3_International_Relations_Agreements_Workflow.md) recommended — this lesson reuses its plugin file structure without re-explaining it
- An email MCP connector from [Lesson 5.4](5-4_What_Is_An_MCP_Server.md) and [Lesson 5.5](5-5_Daily_Briefing_Email_And_Calendar.md), if you want the digest emailed rather than saved as a file

### Time to Complete

**25 to 30 minutes**

<!-- PROGRESS: Step 1: Choose Your Sources | Step 2: Dictate the Workflow | Step 3: Build the Plugin | Step 4: Optional Scheduling | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-1 -->

## Step 1: Choose Your Sources

Before building anything, pick what you're actually going to watch.

### What You'll Do

You will list a small, specific set of websites, news pages, or public feeds to monitor, and read an honest note about what this lesson does and doesn't cover.

### Instructions

1. List 3 to 6 sources that matter to your work: a competitor's press or product page, an industry news site, a regulator's announcement page, a public feed.
2. Prefer pages with a stable, predictable structure (a press-release list, a blog index) over ones that change layout constantly.
3. Read the callout below before assuming this lesson covers every social platform.

<!-- WARNING: About X/Twitter Specifically | This lesson's hands-on example uses public websites and feeds, reached with Claude Code's built-in WebFetch — the same tool proven in Lesson 5.3. Live X/Twitter content specifically is not reliably reachable this way: it requires either the paid X API or a dedicated MCP connector, which most readers won't have set up. If you have that access, the same two-skill shape below applies to X as a source — just swap the fetch step for the X tool you've connected, using the pattern from Lesson 5.4. Everyone else: the websites-and-feeds version below gets you the same outcome. -->

<!-- TIP: A Feed Beats a Page When One Exists | If a source publishes an RSS or Atom feed, fetching that is more reliable than fetching the human-facing webpage — feeds rarely change structure the way a redesigned page does. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Dictate the Workflow

Describe the whole digest in one message, the same dictate-to-setup pattern from Lesson 5.3.

### What You'll Do

You will describe your sources, topics, and desired output in one message and review what Claude Code proposes.

### Instructions

1. Create a new folder, for example `market-digest`, and open it in Claude Code.
2. Adapt and send the example dictation below.
3. Answer any clarifying questions.
4. Review the proposed `CLAUDE.md` before approving.

### Example Dictation

```text
I want to monitor a short list of websites for anything new that
matters to our marketing team. Here are the sources: [list your 3-6
URLs]. I care about mentions of these topics: our top three
competitors by name, pricing changes, and new product announcements
in our category. Ignore anything that doesn't touch one of those
topics. When something new shows up, I want it summarized with
context — if this is the second or third time a competitor has done
something similar recently, say so, don't just report it in
isolation. Once a batch of new items is ready, send me an email digest
with a short summary of each item, why it matters, and a link back to
the source. Set this up as a project with a README and a CLAUDE.md
capturing my topics and sources, and ask me anything you need first.
```

### What Claude Code Should Produce

```text
market-digest/
├── README.md Explains the workflow
├── CLAUDE.md Standing rules: sources, topics,
│ digest tone and length
├── data/
│ └── knowledge-log.md Everything already seen and reported
└── drafts/
└── digest-drafts/ Saved digests, in case email isn't set up
```

---

<!-- ANCHOR: anchor-step-3 -->

## Step 3: Build the Two-Skill Plugin

Two skills: one that watches, one that reports. This reuses the exact plugin file structure from Lesson 5.3 — `.claude-plugin/marketplace.json`, `plugins/<name>/.claude-plugin/plugin.json`, `skills/<name>/SKILL.md` — so this step focuses on what's different: the two skills themselves.

### What You'll Do

You will have Claude Code build `/scan-sources` and `/send-digest`, one at a time, and run both.

### Instructions

1. Ask Claude Code to build `/scan-sources` first, using the description below.
2. Review its `SKILL.md`, then ask for `/send-digest`.
3. Run `/scan-sources`, then `/send-digest`, and check the resulting email or draft.

### Skill 1 — `/scan-sources`

**What to tell Claude Code to build:**

```text
Build a skill called scan-sources. Its job: fetch each website listed
in CLAUDE.md, extract anything published or updated since the last
run, and compare it against data/knowledge-log.md. Keep only items
matching our topics in CLAUDE.md. For each new, on-topic item, append
it to the log with its source, date, topic match, and a one-line
summary, marked "new — not yet digested."
```

**What this produces (`skills/scan-sources/SKILL.md`, abbreviated):**

```markdown
---
name: scan-sources
description: Fetch each monitored source, keep only new items matching
our topics, and log them. Use when the user says "check my sources"
or "/scan-sources."
---

# scan-sources

1. Read the source list and topic list from CLAUDE.md.
2. Fetch each source with WebFetch.
3. Read data/knowledge-log.md — everything already logged, ever.
4. Identify content on each source not already in the log.
5. Keep only new items matching a topic from CLAUDE.md; discard the rest.
6. Append each kept item to the log: source, date, topic, one-line
summary, status "new — not yet digested."
7. Report how many new, on-topic items were found.
```

### Skill 2 — `/send-digest`

**What to tell Claude Code to build:**

```text
Build a skill called send-digest. Its job: find every item in
data/knowledge-log.md still marked "new — not yet digested." For each
one, check the log for earlier entries on the same topic or
competitor, and note the pattern if this is a repeat — for example,
"third pricing mention from this competitor in two weeks." Compose one
email digest: each item with its summary, its context note if there
is one, and a link back to the source. Send it using the email
connector if one is set up, or save it to drafts/digest-drafts/ if
not. Mark each included item "digested" in the log.
```

**What this produces (`skills/send-digest/SKILL.md`, abbreviated):**

```markdown
---
name: send-digest
description: Compile every undigested item into one contextual email
digest and send it, or save a draft if no email connector exists.
Use when the user says "send my digest" or "/send-digest."
---

# send-digest

1. Read data/knowledge-log.md. Find every item marked "new — not yet
digested."
2. For each item, scan the rest of the log for earlier entries on the
same topic or competitor. If found, note the pattern (e.g., "third
mention this month").
3. Compose one digest: item summary, context note if any, and source
link, grouped by topic.
4. Send the digest via the connected email tool. If none is connected,
save it to drafts/digest-drafts/<date>-digest.md instead.
5. Mark every included item "digested" in the log.
```

### Sample Digest

```text
Subject: Market Digest — Tuesday

**Competitor Pricing**
Aria Corp dropped its entry-tier price by 15% (announced today). This
is the third pricing move from Aria in the last two weeks — worth
flagging to the pricing team. [source]

**New Product Announcements**
Northwind Labs announced a beta for a feature similar to ours,
launching next month. No prior mentions from Northwind on this topic.
[source]
```

<!-- INFO: What Made This Fast | The digest didn't just list two facts — it flagged that Aria's move was the third in two weeks. That context only exists because scan-sources kept logging every prior mention, not just the newest one. -->

<!-- TIP: Install It Like 5.3 | The marketplace-add and plugin-install commands from Lesson 5.3, Step 4 work exactly the same way here — register the project folder as a local marketplace, install the plugin, restart Claude Code. -->

---

<!-- ANCHOR: anchor-step-4 -->

## Step 4: Optional — Run It on a Schedule

Once the two skills work, running them without you is the same pattern from Lessons 5.3 and 5.5.

### What You'll Do

You will schedule `/scan-sources` and `/send-digest` to run automatically, back to back.

### Instructions

1. Before proceeding, revisit [Lesson 5.1, Step 4](5-1_Your_Claude_Code_Daily_Habits.md#anchor-step-4) — confirm you trust both skills' output from manual runs first.
2. Open **Windows Task Scheduler**.
3. Create a task that runs both commands in sequence, on whatever cadence fits — daily for fast-moving topics, weekly for slower ones.

### The Scheduled Commands

```text
claude -p "/scan-sources" --cwd "C:\path\to\market-digest"
claude -p "/send-digest" --cwd "C:\path\to\market-digest"
```

<!-- WARNING: This Step Is Optional | Running both commands yourself, on whatever cadence you choose, already works. Only automate this if you want the digest to show up without you starting it. -->

<!-- NOTE: Turning It Off | Disable or delete the scheduled task in Windows Task Scheduler, and disable the plugin the same way shown in Lesson 5.3, Step 6, if you want to stop entirely. data/knowledge-log.md stays exactly as it is either way. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed all three required steps (Step 4 is optional). Confirm your setup by checking each item below:

- [ ] `data/knowledge-log.md` grows with each `/scan-sources` run and doesn't re-log the same item twice
- [ ] `/send-digest` produces a digest that references at least one earlier entry as context, not just the newest item in isolation
- [ ] You understand why this lesson uses websites and feeds rather than live X/Twitter content, and what would need to change to add that source

<!-- NOTE: Not Working? | If every run reports everything as "new," confirm scan-sources is actually reading and checking against data/knowledge-log.md before appending, not just appending blindly. -->

---

<!-- CELEBRATION: Lesson Complete! | You built a workflow that doesn't just report facts — it remembers what it already told you and says so. -->

### What's Next

**Next Lesson:** [Lesson 5.7: From Sources to Story — A Content-Generation Pipeline](5-7_From_Sources_To_Story_Content_Generation.md)

**Related Resources:**
- [claude.ai](https://claude.ai) — The Claude AI platform
- [code.claude.com/docs](https://code.claude.com/docs) — Official documentation
- [support.claude.com](https://support.claude.com) — Help center and troubleshooting

<!-- TIP: The Knowledge Log Is the Real Asset | Once this runs for a few weeks, data/knowledge-log.md becomes a searchable history of everything you've tracked — useful on its own, even before the next digest goes out. -->

<!-- CHILDREN -->