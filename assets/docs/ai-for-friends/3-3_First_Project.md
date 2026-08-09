<!-- HERO: Lesson 3.3: Creating Your First Project | Name it, describe it, and write the standing instructions. That is the whole setup. -->

<!-- TOC: Overview#anchor-overview | Step 1: Create the Project#anchor-step-1 | Step 2: Write Your Custom Instructions#anchor-step-2 | Step 3: Use the Template for Your Role#anchor-step-3 | Verification#anchor-verification -->

## Overview

By the end of this lesson, you will have a working Project on claude.ai with a name, a description, and custom instructions written for your role. Creating a Project is mostly one meaningful step: writing the standing instructions. Everything else is a name and a short description.

### Why This Matters

The custom instructions are the Project's job description. They tell Claude who it is and how to behave in every chat inside the Project. Write them once and you stop re-explaining your role, your rules, and your preferred format. This single setup step saves you time on every conversation that follows.

### Prerequisites

- [Lesson 3.2: What Is a Claude Project?](3-2_Claude_Code_Project_Basics.md)
- A Claude account (claude.ai)

### Time to Complete

**15 minutes**

<!-- PROGRESS: Step 1: Create the Project | Step 2: Write Instructions | Step 3: Use Your Template | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-1 -->

## Step 1: Create the Project

Creating a Project takes four clicks and two short text fields. This step gets the empty Project on your screen. The next two steps fill it with instructions.

### What You'll Do

You will create a new, empty Project on claude.ai and give it a name and a one-line description.

### Instructions

1. Go to **claude.ai** and log in.
2. Click **Projects** in the left sidebar.
3. Click **Create project**.
4. Give it a name and a short description of its purpose, then save.

### What You Should See

```text
Projects (left sidebar)
└─ Recruiting Assistant ← your new Project

Recruiting Assistant
├─ Name: Recruiting Assistant
├─ Description: Candidate summaries and outreach
├─ Custom instructions: (empty — you fill this in Step 2)
└─ Project knowledge: (empty — you add files in Lesson 3.4)
```

<!-- TIP: Description Is for You, Not Claude | The description helps you recognize the Project in your sidebar. Keep it to one line. Claude works from the custom instructions, not the description. -->

<!-- NOTE: Everything Is Editable Later | The name, description, and instructions can all be changed at any time. Nothing you set now is permanent, so do not overthink the first draft. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Write Your Custom Instructions

The custom instructions are the one step that matters. They are the Project's standing orders, written in plain language. Good instructions cover four things: who Claude is, what it does, your context, and how you want answers formatted.

### What You'll Do

You will learn the four sections of a strong set of custom instructions before you fill in the template in Step 3.

### Instructions

1. Read the four sections in the table below.
2. Note that each section answers one plain question about how Claude should work.
3. Write in plain sentences, the way you would brief a new assistant.
4. Keep these four sections in mind as you fill in your template in Step 3.

### Key Concepts

| Section | What Goes There | Why |
|---------|----------------|-----|
| **Identity** | "You are my ___ assistant." | Sets Claude's role for every chat in the Project |
| **Responsibilities** | A numbered list of the standing jobs it handles | Tells Claude what work to expect and do |
| **My context** | The bracketed blanks about your role, systems, and preferences | Grounds Claude's answers in your real situation |
| **Output format** | Your default format (table, bullets) and any required fields | Produces answers you can use without reformatting |

<!-- INFO: This Is the One Step That Matters | Name and description take seconds. The custom instructions do the real work. Time spent here pays off in every chat you run inside the Project. -->

<!-- TIP: Write in Plain Sentences | Write your instructions the way you would brief a new assistant on their first day. Plain sentences work better than keywords or shorthand. -->

---

<!-- ANCHOR: anchor-step-3 -->

## Step 3: Use the Template for Your Role

Do not write instructions from scratch. Copy the template that fits your role, fill in the bracketed blanks with your own details, and paste it into the custom instructions field. The HR template is below. The Legal, Marketing, Industrial Engineering, and International Relations templates are in the expandable section beneath it.

### What You'll Do

You will copy the template for your role, fill in every bracket, and save it as your Project's custom instructions.

### Instructions

1. Copy the template that matches your role.
2. Fill in every bracketed blank with your own details.
3. Paste the completed template into the Project's custom instructions field.
4. Save. Start a new chat inside the Project and confirm the instructions are already in effect.

### HR Template

```
You are my recruiting assistant. Your responsibilities:

1. Summarize candidate profiles from interview notes into structured tables.
2. Draft outreach messages for passive candidates (professional, concise, warm).
3. Track pipeline status when I share updates.
4. Format all outputs in clean markdown tables or bullet points.

My context:
- I recruit for: [role types, e.g., engineers, sales, operations]
- My ATS (applicant tracking system) is: [system name]
- My hiring managers are: [names, if helpful]

When I share interview notes, always extract: Name, Role Applied,
Years of Experience, Key Strengths, Concerns, Compensation
Expectations, Availability, and Next Steps.
```

<!-- EXPAND: Templates for Legal, Marketing, Industrial Engineering, and International Relations -->

**For Legal:**
```
You are my contract review assistant. Your responsibilities:

1. Review contract language clause by clause and summarize each in plain English.
2. Flag risk in a redline style — quote the exact language, never paraphrase.
3. Track defined terms and note when they are used inconsistently.
4. Categorize each finding as High, Medium, or Low risk.

My context:
- I review: [contract types, e.g., NDAs, vendor agreements, MSAs]
- My jurisdiction is: [state / country]
- My standard positions are: [e.g., liability cap must be >= contract value]

Always flag: indemnity language, liability caps, auto-renewal terms, and
termination-for-convenience clauses. Present findings in a table with
columns: Clause Reference, Plain-English Summary, Risk Level.
```

**For Marketing:**
```
You are my content assistant. Your responsibilities:

1. Repurpose one piece of content into variants for each of my channels.
2. Enforce brand voice on everything you draft.
3. Summarize campaign performance and highlight what drove results.
4. Produce one clearly labeled section per channel when repurposing.

My context:
- My brand voice is: [description, e.g., confident, plain-spoken, never hype]
- My primary channels are: [list, e.g., LinkedIn, email, blog, X]
- Words we never use: [banned words, e.g., synergy, game-changer, revolutionary]

When repurposing, keep the core message identical across channels but adapt
length and tone to each. Always respect the banned-words list.
```

**For Industrial Engineering:**
```
You are my process and work-order assistant. Your responsibilities:

1. Summarize nonconformance reports into a root-cause-and-disposition table.
2. Draft standard work instructions from my rough notes, in our required format.
3. Track work-order status when I share updates from the floor.
4. Flag any recurring defect type across three or more reports in the same period.

My context:
- My work centers are: [list, e.g., final assembly, machining, inspection]
- My standard work format requires: [sections, e.g., purpose, tools, steps, safety notes]
- My escalation threshold is: [e.g., any nonconformance tied to a safety-critical part]

When I share nonconformance reports, always extract: Part Number, Work Order,
Defect Description, Root Cause (if known), Disposition, and Recurrence Flag.
```

**For International Relations:**
```
You are my diplomatic affairs assistant. Your responsibilities:

1. Draft briefing memos on incoming agreements, meetings, or delegations in our house format.
2. Flag any item relevant to the chancellor or foreign minister's priority topics.
3. Track agreements and their follow-up status as I share updates.
4. Check draft correspondence against our protocol and tone conventions before I send it.

My context:
- My priority topics are: [list, e.g., trade, security cooperation, cultural exchange]
- My counterpart ministries or missions are: [list]
- My house format for briefing memos requires: [sections, e.g., summary, stakeholders, recommended position]

When I share a new agreement or cable, always extract: Title, Counterpart,
Date, Summary, Relevance to Priority Topics, and Recommended Next Step.
```

<!-- /EXPAND -->

<!-- TIP: Fill In Every Bracket | A bracket left blank is a rule Claude cannot follow. Replace each [bracketed blank] with your own details before you save. -->

<!-- WARNING: Do Not Paste Sensitive Detail Into Instructions | Role types and system names are fine in your instructions. Employee records and client identifiers are not. Lesson 3.4 covers what a Project can and cannot reach, and what to check before uploading sensitive material. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed all three steps. Confirm your setup by checking each item below:

- [ ] A Project exists in your claude.ai sidebar
- [ ] The Project has a name and a one-line description
- [ ] Your custom instructions are saved with every bracket filled in
- [ ] A new chat inside the Project follows the instructions without you repeating them

<!-- NOTE: Not Working? | If a new chat ignores your instructions, confirm you saved them in the custom instructions field, not in a message. The template in Step 3 shows exactly what belongs there. -->

---

<!-- CELEBRATION: Lesson Complete! | You now have a working Project with custom instructions written for your role, and a new chat inside it already follows them. -->

### What's Next

**Next Lesson:** [Lesson 3.4: Giving Your Project Reference Material](3-4_Project_Material.md)

**Related Resources:**
- [claude.ai](https://claude.ai) — The Claude AI platform
- [Claude documentation](https://code.claude.com/docs) — Official documentation
- [Claude support](https://support.claude.com) — Help center and troubleshooting

<!-- TIP: Test It Right Now | Open a new chat inside your Project and ask it to do one of its listed responsibilities. If it behaves as instructed, your setup works. -->

<!-- CHILDREN -->