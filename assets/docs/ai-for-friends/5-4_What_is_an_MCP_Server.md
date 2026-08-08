<!-- HERO: Lesson 5.4: What Is an MCP Server? | The one concept that lets Claude reach past your files and chats into your real, live accounts — on the web and in Claude Code. -->

<!-- TOC: Overview#anchor-overview | Step 1: The Concept, Made Concrete#anchor-step-1 | Step 2: Adding a Connector on claude.ai#anchor-step-2 | Step 3: Adding an MCP Server in Claude Code#anchor-step-3 | Step 4: Checking, Removing, and Being Honest About What Exists#anchor-step-4 | Verification#anchor-verification -->

## Overview

Lesson 1.1 defined MCP in one line: "a live connection between your AI assistant and another app or system." This lesson makes that concrete. You will see exactly what an MCP connection looks like on claude.ai and in Claude Code, add one yourself, and learn the honest limits of what's available today — before Lesson 5.5 asks you to connect your email and calendar.

### Why This Matters

Every lesson so far in this module worked with things Claude Code can already reach on its own: files in a folder, a public webpage. Your email, your calendar, and most other real accounts are not reachable that way. An MCP connection is the one mechanism that changes that — and it's worth understanding on purpose, once, rather than picking up piecemeal from a command you're told to copy.

### Prerequisites

- [Lesson 5.1: Your Claude Code Daily Habits](5-1_Your_Claude_Code_Daily_Habits.md), completed
- A claude.ai account, for Step 2

### Time to Complete

**20 minutes**

<!-- PROGRESS: Step 1: The Concept | Step 2: Connectors on claude.ai | Step 3: MCP in Claude Code | Step 4: Checking and Removing | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-1 -->

## Step 1: The Concept, Made Concrete

An MCP server is a bridge. On one side is Claude — on claude.ai or in Claude Code. On the other side is a real system: your email, your calendar, a database, a project tracker. MCP is the protocol that lets the two talk, so Claude can read real, current data instead of guessing from what it was trained on.

### What You'll Do

You will see the shape of an MCP connection and where it fits next to the tools you already know from this course.

### Instructions

1. Read the before/after comparison below.
2. Note the three things every MCP connection needs: a name, a way to reach it (an address or a local program), and your permission.
3. Keep the distinction in the table in mind: some things Claude already does without any connection at all.

### Before and After

| Without an MCP Connection | With One Added |
|---|---|
| Claude only sees files you've opened or pasted, or a public webpage it fetched directly | Claude can read and act on a real, live system — your inbox, your calendar, a company database |
| "What's on my calendar today" gets a guess or a request to paste it in | "What's on my calendar today" gets a real answer, read live |
| Every session starts from nothing outside your files | The connection persists across sessions once it's set up |

| Already works with no connection | Needs an MCP connection |
|---|---|
| Reading files in your open folder (Module 3) | Reading your email |
| Fetching a public webpage (Lesson 5.3) | Reading your calendar |
| Reading files uploaded to a claude.ai Project (Lesson 4.3) | Posting to a team chat tool |

<!-- INFO: This Is Not the Same as Uploading a File | Uploading a file to a Project (Lesson 4.3) is a one-time snapshot. An MCP connection is live — Claude reads the current state of the system every time, not a copy you made once. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Adding a Connector on claude.ai

On the web, MCP connections are called **Connectors**. This is the no-terminal, click-based way to give Claude access to a real app.

### What You'll Do

You will find the Connectors setting on claude.ai and understand what turning one on actually does.

### Instructions

1. On claude.ai, open **Settings** and look for a **Connectors** (sometimes labeled **Integrations**) section. Menu names and exact locations change over time — if it's not where this lesson says, search Settings for "connector" or check the current location in claude.ai's own help center.
2. Browse the available connectors. What's offered changes over time and by plan (Free, Pro, Team, Enterprise) — check what's actually listed for your account rather than assuming a specific app is there.
3. To connect one, click it and complete the sign-in flow — this is a standard OAuth login into your own account, the same kind of "Sign in with Google" flow you've used elsewhere. You are not sharing a password with Claude.
4. If you use claude.ai Projects (Module 4), check whether a connector can be scoped to a specific Project rather than your whole account — this determines whether a Project that has a connector enabled can now reach that live app, correcting a point from Lesson 4.3.

<!-- WARNING: Verify What's Current, Don't Trust a Screenshot | Which apps have a ready-made connector, and whether a given connector is available on your specific plan, both change over time. This lesson deliberately doesn't promise a fixed list — check Settings on your own account for the current, real answer. -->

<!-- NOTE: Correcting Lesson 4.3 | Lesson 4.3 stated that a Project cannot reach your email or any other app or account. That was true when written and still describes the *default* — nothing reaches a Project automatically. The correction: if you explicitly turn on a Connector for a Project, that Project can then reach that connected app going forward. The core rule hasn't changed — you decide what a Project can see — but a Connector is now one of the ways you can extend that reach, not just an uploaded file. -->

---

<!-- ANCHOR: anchor-step-3 -->

## Step 3: Adding an MCP Server in Claude Code

In the terminal, the same idea has a command instead of a settings page.

### What You'll Do

You will learn the `claude mcp add` command, the difference between adding a connection for one project versus every project, and the command that shows you what's connected.

### Instructions

1. Read the command pattern and the two scope options below.
2. Practice on any MCP server you have a real address or command for — if you don't have one yet, skip practicing and come back to this step when Lesson 5.5 gives you one to add.
3. Use `/mcp` inside any Claude Code session to see what's currently connected and what tools each connection provides.

### The Command Pattern

```text
claude mcp add --transport <type> <name> <address-or-command>
```

| Piece | What Goes There |
|---|---|
| `<type>` | How Claude talks to the server: `stdio` for a local program Claude runs itself, `sse` or `http` for a remote, hosted server reached by address |
| `<name>` | A short label you choose — this becomes the name shown in `/mcp` |
| `<address-or-command>` | A web address for `sse`/`http`, or the command that starts the local program for `stdio` |

**Example — a remote, hosted server:**

```text
claude mcp add --transport sse project-tracker https://mcp.example.com/sse
```

### Two Scopes, One Important Difference

| Scope | Command | Where It's Available |
|---|---|---|
| Project (default) | `claude mcp add --transport sse project-tracker https://mcp.example.com/sse` | Only inside the folder you ran this from |
| User (global) | `claude mcp add --scope user --transport sse project-tracker https://mcp.example.com/sse` | Every Claude Code project on your computer |

<!-- TIP: Add "--scope user" for Anything You'll Use Daily | If a connection is specific to one project's job (a database only that project touches), leave it project-scoped. If it's something you'd want in every session — your email, your calendar — add --scope user so you don't repeat the setup per project. -->

### Checking and Approving

The first time you use a connection that needs a sign-in, a browser window opens for the same kind of OAuth login as Step 2 — you're approving Claude Code's access to your account, not handing over a password.

```text
/mcp
```

Running this inside any session lists every connected server and the tools it provides — your first stop whenever something isn't working.

<!-- INFO: The File Alternative | Advanced users can also define MCP servers directly in a project's `.mcp.json` file, or globally in `~/.claude.json`, instead of using the add command. For a first Claude Code MCP connection, the command above is the simpler path — the files exist mainly so a whole team can check a shared `.mcp.json` into version control and get the same connections automatically. -->

---

<!-- ANCHOR: anchor-step-4 -->

## Step 4: Checking, Removing, and Being Honest About What Exists

Before Lesson 5.5 asks you to connect your real email and calendar, one honest caveat and one piece of housekeeping.

### What You'll Do

You will learn what to do when the exact connector you want doesn't exist ready-made, and how to remove a connection you no longer want.

### Instructions

1. Read the caveat below before assuming a specific app has a one-line, ready-made connector.
2. To remove a connection in Claude Code, ask Claude directly — "remove the project-tracker MCP server" — and confirm what it proposes, or check `/mcp` for the exact removal command it reports.
3. To remove a Connector on claude.ai, return to Settings → Connectors and disconnect it the same way you'd revoke access from any other "Sign in with Google"-style connection.

<!-- WARNING: Not Every App Has a Ready-Made, First-Party Connector | Anthropic, Google, and Microsoft all publish some hosted MCP connectors, and the list grows over time — but there is no guarantee that a first-party, one-line connector exists yet for every specific app, including major ones like Gmail or Outlook. If Settings → Connectors or a documented address doesn't show what you need, that's a real gap, not something you're doing wrong. Lesson 5.5 shows you where to check for the current state before assuming access exists. -->

<!-- NOTE: This Changes, Faster Than This Course Does | Connector availability is one of the fastest-moving parts of Claude. Treat what you find in Settings or the docs on the day you read this as the real answer — not any specific name or address printed in a course like this one. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed all three steps. Confirm your understanding by checking each item below:

- [ ] You can explain what an MCP connection adds that a plain file upload does not
- [ ] You know where to find Connectors on claude.ai and what an OAuth sign-in there does and doesn't share
- [ ] You can write the `claude mcp add` command pattern from memory, including the `--scope user` option
- [ ] You know that `/mcp` shows what's connected, and that not every app has a ready-made connector yet

<!-- NOTE: Not Working? | If /mcp shows nothing after adding a server, confirm you restarted Claude Code and that the address or command you used is correct — a typo in an address is the most common cause. -->

---

<!-- CELEBRATION: Lesson Complete! | You now understand MCP well enough to add a real connection on either surface — and to tell the difference between a genuine gap and something you're doing wrong. -->

### What's Next

**Next Lesson:** [Lesson 5.5: Daily Briefing from Email and Calendar](5-5_Daily_Briefing_Email_And_Calendar.md)

**Related Resources:**
- [claude.ai](https://claude.ai) — Check Settings → Connectors
- [code.claude.com/docs](https://code.claude.com/docs) — Official documentation, including current MCP server availability
- [support.claude.com](https://support.claude.com) — Help center and troubleshooting

<!-- TIP: Come Back Here When Something's Not Connecting | If a later lesson's MCP step doesn't work, the fix is almost always in this lesson: wrong scope, no /mcp check, or a connector that isn't actually available yet. -->

<!-- CHILDREN -->