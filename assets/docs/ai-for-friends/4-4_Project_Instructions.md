<!-- HERO: Lesson 4.4: Keeping Your Standing Instructions Current | Your custom instructions are the Project's memory. Keeping them current is one edit, not a feature to manage. -->

<!-- TOC: Overview#anchor-overview | Step 1: How a Project Actually Remembers#anchor-step-1 | Step 2: Update the Instructions When Facts Change#anchor-step-2 | Verification#anchor-verification -->

## Overview

By the end of this lesson, you will know where a Project's memory lives and how to keep it current. A Project's custom instructions are its memory. There is no separate memory feature running in the background, so keeping a Project current means editing its instructions when a fact changes.

### Why This Matters

People expect Claude to "learn" their preferences over time. A Project does not work that way. Anything that should always be true has to live in the custom instructions. Once you know this, you stop repeating the same correction in every chat and make one edit instead.

### Prerequisites

- [Lesson 4.2: Creating Your First Project](4-2_Creating_Your_First_Project.md)
- A Project with custom instructions already saved

### Time to Complete

**10 minutes**

<!-- PROGRESS: Step 1: How It Remembers | Step 2: Update When Facts Change | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-1 -->

## Step 1: How a Project Actually Remembers

A Project's custom instructions are what persist across every conversation inside it. There is no separate memory to manage and no learned-preference feature. If something should always be true, it lives in the custom instructions.

### What You'll Do

You will learn exactly what carries over between chats in a Project and what does not.

### Instructions

1. Read the two columns below.
2. Note that only the instructions and uploaded knowledge persist.
3. Note that anything said inside a single chat is gone when that chat ends.
4. Use this to decide what belongs in the instructions versus a one-time message.

### What Persists and What Does Not

<!-- COLUMNS: 50/50 -->

**Persists across every chat in the Project:**

- Your custom instructions.
- Your uploaded Project knowledge.

<!-- COLSEP -->

**Does not persist:**

- Anything said in one chat.
- Mid-conversation corrections.
- Preferences you assume Claude picked up.

<!-- /COLUMNS -->

<!-- INFO: There Is No Hidden Memory | A Project does not quietly learn your preferences between chats. The custom instructions and uploaded files are the entire memory. If a fact is not written there, the next chat will not know it. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Update the Instructions When Facts Change

When a standing fact changes, open the Project and edit the custom instructions. Every future chat uses the updated version immediately. This step shows the kinds of facts worth keeping current and how to update them.

### What You'll Do

You will add one standing fact to your Project's custom instructions and confirm it takes effect.

### Instructions

1. Open your Project and edit the custom instructions.
2. Add or change the standing fact.
3. Save.
4. Start a new chat inside the Project and confirm the updated fact is in effect.

### Facts Worth Keeping Current

| Role | Standing Fact | Add It When |
|------|--------------|-------------|
| HR | "My default output format is a table, one row per item." | You want a consistent format on every answer |
| HR | "My lead hiring manager is now [Name]; address candidate summaries to them." | The lead hiring manager changes |
| Legal | "Our jurisdiction changed to [State]; assume that governing law when none is stated." | The governing jurisdiction changes |
| Marketing | "We added [term] to the banned-words list; never use it in public copy." | The banned-words list is updated |
| Industrial Engineering | "The owner of [work center] is now [Name]; route escalations to them." | A work-center owner changes |
| International Relations | "Our counterpart contact at [ministry] is now [Name/title]; address correspondence to them." | A counterpart contact or protocol rule changes |

<!-- TIP: The Repeat-Correction Rule | If you correct Claude the same way in every chat, that correction belongs in the custom instructions. Put it there once and you stop repeating it. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed both steps. Confirm your understanding by checking each item below:

- [ ] You can state where a Project's memory lives (the custom instructions)
- [ ] You have added one standing fact and confirmed it takes effect in a new chat

<!-- NOTE: Not Working? | If a new chat does not use your updated fact, confirm you saved the change in the custom instructions field. The columns in Step 1 show what persists and what does not. -->

---

<!-- CELEBRATION: Lesson Complete! | You now know where a Project's memory lives and how to keep it current with a single edit to the custom instructions. -->

### What's Next

**Next Lesson:** [Lesson 4.5: Using Your Project to Design More Projects](4-5_Designing_More_Projects.md)

**Related Resources:**
- [claude.ai](https://claude.ai) — The Claude AI platform
- [Claude documentation](https://code.claude.com/docs) — Official documentation
- [Claude support](https://support.claude.com) — Help center and troubleshooting

<!-- TIP: Fix the Correction You Repeat Most | Think of the one thing you correct in every chat. Add it to your custom instructions today and confirm the next chat gets it right on its own. -->

<!-- CHILDREN -->