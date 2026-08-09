<!-- HERO: Lesson 3.4: Giving Your Project Reference Material | Upload your templates and style guides once. Every chat in the Project can use them. -->

<!-- TOC: Overview#anchor-overview | Step 1: Upload Your Reference Files#anchor-step-1 | Step 2: Choose the Right Files for Your Role#anchor-step-2 | Step 3: Know What a Project Cannot Reach#anchor-step-3 | Verification#anchor-verification -->

## Overview

By the end of this lesson, you will have uploaded reference files to your Project and will know exactly what a Project can and cannot reach. Custom instructions tell Claude how to work. Project knowledge gives it the material to work from.

### Why This Matters

Without reference files, you paste your template into every chat. With them, "draft an offer letter for this candidate" or "review this contract against our standard positions" works with nothing attached. You also need to know the Project's limits: it reaches only what you upload, which protects your confidential material.

### Prerequisites

- [Lesson 3.3: Creating Your First Project](3-3_First_Project.md)
- Two or three reference files for your role (templates, style guides, glossaries)

### Time to Complete

**15 minutes**

<!-- PROGRESS: Step 1: Upload Files | Step 2: Choose the Right Files | Step 3: Know the Limits | Verification -->

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-step-1 -->

## Step 1: Upload Your Reference Files

Project knowledge is a set of documents you upload to a Project so Claude can reference them when it answers. This step gets your files into the Project. Once they are there, you never re-attach them.

### What You'll Do

You will upload your first reference files to the Project knowledge section.

### Instructions

1. Open your Project on claude.ai.
2. Find the **Project knowledge** section.
3. Upload your files.
4. Confirm each file appears in the list.

### What You Should See

```text
Recruiting Assistant
└─ Project knowledge
├─ interview_scorecard_template.docx
├─ job_description_format.docx
└─ offer_letter_template.docx

Any chat in this Project can now reference these files.
```

<!-- NOTE: You Never Re-Attach | Once a file is in Project knowledge, every chat inside the Project can reference it automatically. You do not attach it again, in this chat or any future one. -->

<!-- TIP: Start With Three Files | You do not need to upload everything at once. Start with the three files you reach for most. Add more when a chat needs material you have not uploaded yet. -->

---

<!-- ANCHOR: anchor-step-2 -->

## Step 2: Choose the Right Files for Your Role

The right files turn common requests into one-line prompts. This step shows which files each role should upload and what each set unlocks.

### What You'll Do

You will identify the reference files that fit your role and understand what they let Claude do without you pasting anything.

### Instructions

1. Find your role in the table below.
2. Gather the listed files from your own work.
3. Upload them to Project knowledge, following Step 1.
4. Note the "What It Unlocks" column. That is the payoff for uploading.

### Files by Role

| Role | Files to Upload | What It Unlocks |
|------|----------------|-----------------|
| Legal | Standard contract templates, defined-terms glossary, past redlines or precedent language | "Review this contract against our standard positions" works against your real positions |
| Marketing | Brand style guide, past campaign briefs, approved messaging and claims list | Drafts arrive already in your brand voice |
| Industrial Engineering | Standard-work template, nonconformance report format, time-study log | "Draft standard work for this operation" works with no template pasted, and defect summaries land in your real report format |
| International Relations | Briefing-memo template, protocol and etiquette reference, agreement-tracking log | "Draft a briefing memo on this agreement" arrives in your house format and already checked against protocol |
| HR (Recruiting) | Interview scorecard template, standard job-description format, offer-letter template | "Draft an offer letter for this candidate" works with no template pasted |

<!-- INFO: Instructions vs. Knowledge | Custom instructions tell Claude how to work. Project knowledge gives it what to work from. Instructions are the method; the uploaded files are the source material. -->

---

<!-- ANCHOR: anchor-step-3 -->

## Step 3: Know What a Project Cannot Reach

A Project references only what you explicitly upload to it, and this stays true by default. It has no live access to your email, your applicant tracking system, your document management system, or any other app or account — unless you deliberately turn one on. This limit is a confidentiality feature: you control exactly what Claude can see.

### What You'll Do

You will learn precisely what a Project can and cannot reach, and what to check before uploading sensitive material.

### Instructions

1. Read the two columns in the table below.
2. Note that every item on the "Can Reach" side is something you put there yourself.
3. Note that no app or account connects to the Project automatically — connecting one is always something you choose to turn on.
4. Read both callouts before uploading anything sensitive.

### What a Project Can and Cannot Reach

| Can Reach | Cannot Reach (Unless You Connect It) |
|-----------|--------------|
| Files you explicitly uploaded | Your email |
| Text you paste into a chat | Your applicant tracking system |
| Its own custom instructions | Your document management system |
| An app you've turned on a Connector for (Lesson 4.4) | Any other app or account you haven't connected |
| | Anything you have not uploaded or connected |

<!-- WARNING: Check Before You Upload Sensitive Material | A personal claude.ai plan has no corporate data agreement. Check your employer's IT or Legal guidance before uploading employee records, privileged client files, or confidential campaign data. -->

<!-- INFO: This Limit Is a Feature | Nothing reaches a Project on its own — you upload a document, or you choose to connect it. That second option, Connectors, does exist on claude.ai today (Module 4, Lesson 4.4 covers it in full), and once you turn one on for a Project, that Project can reach that connected app going forward. The rule that matters hasn't changed: you decide what a Project can see, whether by uploading or by connecting — it never happens without your choice. -->

---

<!-- ANCHOR: anchor-verification -->

## Verification

You have completed all three steps. Confirm your setup by checking each item below:

- [ ] At least one reference file appears in your Project knowledge
- [ ] A chat answers using an uploaded file without you attaching it
- [ ] You can state what a Project cannot reach by default, what would change that, and what you would check before uploading sensitive material

<!-- NOTE: Not Working? | If a chat ignores an uploaded file, confirm the file appears in the Project knowledge list from Step 1. If you are unsure about what is safe to upload, the table and warning in Step 3 are your reference. -->

---

<!-- CELEBRATION: Lesson Complete! | Your Project now has reference material every chat can use, and you know exactly what the Project can and cannot reach. -->

### What's Next

**Next Lesson:** [Lesson 3.5: Keeping Your Standing Instructions Current](3-5_Project_Instructions.md)

**Related Resources:**
- [claude.ai](https://claude.ai) — The Claude AI platform
- [Claude documentation](https://code.claude.com/docs) — Official documentation
- [Claude support](https://support.claude.com) — Help center and troubleshooting

<!-- TIP: Prove It Works | Upload one template, then ask a chat to use it by name without attaching anything. When it draws on the file, your Project knowledge is working. -->

<!-- CHILDREN -->