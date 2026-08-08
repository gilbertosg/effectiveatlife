<!-- HERO: Module 2: Setting Up Your Computer (Optional Warm-Up) | A practice room for anyone who has never opened a terminal or a code editor. Nothing here is a prerequisite for Module 3. -->

<!-- TOC: Overview#anchor-overview | Lessons in This Module#anchor-lessons | Key Concepts#anchor-concepts | What's Next#anchor-next -->

## Overview

This module is optional. It is a low-stakes place to install a text editor and practice a few terminal commands before the real setup in Module 3. Nothing here is a prerequisite.

### Who This Module Is For

This module is for people who have never opened a terminal or a code editor and want a little practice before Module 3's install walkthrough. Treat it as a warm-up, not a requirement.

**Target roles:**
- HR professionals
- Industrial engineering professionals
- Legal professionals
- Marketing professionals

### Why This Matters

Module 3's install goes easier when the terminal is not also new. Twenty minutes here removes the unfamiliar parts, so Module 3 has only the actual install to focus on. You arrive already knowing what a prompt looks like and how to type a command.

### By the End of This Module, You Will

- Have a standalone terminal installed, if you want one outside VS Code
- Have VS Code installed and know where its Extensions panel lives
- Move between folders in a terminal using four commands
- Create a folder structure from the terminal and confirm it exists

### Prerequisites

**None.** A Windows or Mac computer and the ability to install software. No prior terminal or editor experience.

### Time to Complete

**25 minutes** across 3 lessons. All three are optional. Lesson 2.3 is the one worth doing if you only have time for one.

---

<!-- ANCHOR: anchor-overview -->

<!-- ANCHOR: anchor-lessons -->

## Lessons in This Module

| # | Lesson | Duration | What You Will Learn |
|---|--------|----------|---------------------|
| 2.1 | [Installing Windows Terminal](2-1_Installing_Windows_Terminal.md) | 5 min | How to install a standalone terminal from the Microsoft Store and set PowerShell as its default. Windows-only (Mac already has Terminal built in) — and optional either way, since Module 3 uses VS Code's built-in terminal instead. |
| 2.2 | [Installing Visual Studio Code](2-2_Installing_VS_Code.md) | 5 min | How to install VS Code and find the Extensions panel, for Windows and Mac. A lighter, earlier pass at what Module 3 covers in full. |
| 2.3 | [Navigating in the Terminal](2-3_Navigating_The_Terminal.md) | 15 min | Four commands that let you move between folders, plus a practice exercise that builds a real folder structure. Works the same way on Windows and Mac. |

<!-- WARNING: This Entire Module is Optional | Module 3 covers everything you need, including the terminal, and does not depend on anything here. If you're comfortable jumping straight into Module 3's install walkthrough, skip this module entirely. -->

<!-- TIP: If You Only Do One Lesson, Do 2.3 | Lessons 2.1 and 2.2 install software Module 3 also installs. Lesson 2.3 teaches the four terminal commands Module 3 assumes you already know. -->

<!-- NOTE: Windows and Mac | Lessons 2.2 and 2.3 cover both Windows and Mac. Lesson 2.1 is Windows-only, since Mac already ships with a terminal — Mac readers can skip straight to 2.2. -->

---

<!-- ANCHOR: anchor-concepts -->

## Key Concepts

Core terms introduced across this module's three lessons. The lesson where each term is first used is listed so you can return to the source explanation.

| Term | Defined In | Plain English Meaning |
|------|------------|-----------------------|
| **Terminal** | Lesson 2.1 | A window where you type text commands to your computer instead of clicking. |
| **PowerShell** | Lesson 2.1 | Windows' command language, used throughout this module's Windows steps. The "PS" in the prompt means PowerShell. (Mac's built-in Terminal uses zsh instead — no separate install needed.) |
| **Default Profile** | Lesson 2.1 | The shell a terminal opens by default. On Windows, this module sets it to PowerShell. |
| **VS Code** | Lesson 2.2 | Visual Studio Code, the free Microsoft text editor this course uses to view and edit files. |
| **Extension** | Lesson 2.2 | An add-on that gives VS Code new abilities. Module 3 tells you which ones to install. |
| **`pwd`** | Lesson 2.3 | Print working directory. Shows which folder you are currently in. |
| **`cd`** | Lesson 2.3 | Change directory. Moves you into a folder, or up one level with `cd ..`. |

<!-- EXPAND: Full Key Concepts Reference -->

| Term | Defined In | Plain English Meaning |
|------|------------|-----------------------|
| **Microsoft Store** | Lesson 2.1 | The official Windows app store. The safe place to install Windows Terminal. (No Mac equivalent needed — Terminal.app is pre-installed.) |
| **Windows Terminal** | Lesson 2.1 | A standalone terminal app you open on its own, separate from any editor. Windows-only. |
| **Integrated Terminal** | Lesson 2.1 | The terminal built into VS Code, opened with Ctrl + backtick (same shortcut on Mac). Module 3's default, on both platforms. |
| **Prompt** | Lesson 2.1 | The text where you type, e.g. `PS C:\Users\YourName>` on Windows or `yourname@Mac ~ %` on Mac. It waits until you press Enter. |
| **Extensions Shortcut** | Lesson 2.2 | `Ctrl + Shift + X` on Windows, `Cmd + Shift + X` on Mac — opens the Extensions panel in VS Code. |
| **`ls`** | Lesson 2.3 | List. Shows all files and folders in your current location. Identical on Windows (Git Bash/PowerShell) and Mac Terminal. |
| **`mkdir`** | Lesson 2.3 | Make directory. Creates a new folder where you currently are. Identical on Windows and Mac. |
| **Home Folder** | Lesson 2.3 | Your personal top-level folder, reached with `cd ~` on both platforms — `C:\Users\YourName` on Windows, `/Users/yourname` on Mac. |

<!-- /EXPAND -->

---

<!-- ANCHOR: anchor-next -->

## What's Next

**Next Module:** [Module 3: Claude Code - AI on Your Own Files](3-claude-code.md)

Module 3 is the real setup: it installs Claude Code, connects it to your Claude Pro account, and walks you through your first real task on a folder of documents. Since this whole module was optional, skipping straight here is fine - Module 3 covers everything you need on its own.

**Support Resources:**

| Resource | Link | Purpose |
|----------|------|---------|
| Claude | claude.ai | Sign up and use Claude in your browser |
| Claude Docs | docs.claude.com/docs | Official documentation |
| Claude Support | support.claude.com | Help center and account support |

<!-- CHILDREN -->