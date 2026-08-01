# **Effective at Life: Static Platform Implementation Guide (V1)**

**Project:** Translate Gil OS (Private Knowledge Graph) into a Public Web Platform (effectiveatlife.com)

**Objective:** Generate pure static HTML, CSS, and JavaScript files for direct AWS S3 deployment. No build tools. No backend.

**Framework Strategy:**

1. **Vanilla Static Files:** Rely exclusively on raw .html files. Load Tailwind CSS via CDN.  
2. **Claude Code \+ frontend-design skill:** Serve as the UI developer. Execute aesthetic choices, build CSS grid layouts (Bento Box), and parse external Markdown files into static HTML.

## **Target Project Architecture (Folder Structure)**

The following tree maps the required file structure. Because there is no build step, this structure represents the exact files you will upload to AWS S3.

effectiveatlife/  
├── index.html                           \# Landing Page  
├── blog/  
│   ├── index.html                       \# Blog Hub  
│   ├── how-to-organize-your-life.html   \# Article: Trap Zone  
│   ├── weekly-review.html               \# Article: Weekly Review Process  
│   └── daily-context-engineering.html   \# Article: Context Engineering  
└── ai-for-friends/  
    ├── index.html                       \# Course Hub  
    ├── module-1/  
    │   ├── index.html                   \# Module 1 Overview  
    │   ├── lesson-1.html                \# Lesson 1 Content  
    │   ├── lesson-2.html                \# Lesson 2 Content  
    │   └── lesson-3.html                \# Lesson 3 Content  
    ├── module-2/  
    │   ├── index.html                   \# Module 2 Overview  
    │   ├── lesson-1.html                \# Lesson 1 Content  
    │   ├── lesson-2.html                \# Lesson 2 Content  
    │   └── lesson-3.html                \# Lesson 3 Content  
    └── module-3/  
        ├── index.html                   \# Module 3 Overview  
        └── lesson-1.html                \# Lesson 1 Content

### **Module Breakdown & File Descriptions:**

* **Landing Page (index.html)**: Contains the Bento Box dashboard, the Methodology Matrix, and explanations of the 7 Pillars framework. Explicitly highlights AI as the core engine powering the Effective at Life system. Incorporates personal examples extracted from Gil OS. Explains how AI and effective AI usage specially context engineering can boost productivity and help keep every aspect of our lives organized.   
* **Blog Module**:  
  * blog/index.html: The article grid serving as the central hub for all synthesized posts.  
  * blog/how-to-organize-your-life.html.html: Synthesized article detailing the "Trap Zone" and prioritizing impact over mere output.  
  * blog/weekly-review.html: Post explaining the Friday ritual for tracking numerical metrics and L1-L7 reflections.  
  * blog/daily-context-engineering.html: Post detailing how to save and structure knowledge for persistent AI context.  
* **AI For Friends Course**:  
  * ai-for-friends/index.html: The syllabus overview outlining the entire crash course.  
  * ai-for-friends/module-1/: Contains index.html to introduce the module, followed by three distinct HTML lesson files covering foundational AI concepts.  
  * ai-for-friends/module-2/: Contains index.html for the module overview and three sequential HTML lesson files detailing advanced AI interactions.  
  * ai-for-friends/module-3/: Contains index.html to introduce the final module and one final HTML lesson file covering practical application.

## **Phase 1: Global Design System Setup**

**Objective:** Establish the foundation for the project and configure the Tailwind CDN to match the Aerospace/Digital Second Brain aesthetic.

Run Claude Code in your terminal and execute the following prompt:

> Initialize a new directory named "effective-platform-v1". Create a template file named base.html to serve as the global shell for all pages.

> Execute the following design system configurations in the \<head\> of base.html:

1. Inject the Tailwind Play CDN: \<script src="https://cdn.tailwindcss.com"\>\</script\>.  
2. Configure the Tailwind script to include the following custom colors:  
   * Backgrounds: os-deep (\#0A0F1C), os-surface (\#111827), os-surface-light (\#1F2937).  
   * Text: os-primary (\#FFFFFF), os-secondary (\#9CA3AF), os-tertiary (\#6B7280).  
   * Accents: accent-cyan (\#00F0FF), accent-teal (\#00C2D1), accent-purple (\#7B2CBF).  
3. Import Google Fonts via CDN: Space Grotesk (Headings), Inter (Body), and JetBrains Mono (Technical Data).  
4. Add a global CSS \<style\> block to enforce a dark mode background (bg-\[\#0A0F1C\]) and apply the primary text color (text-\[\#FFFFFF\]).

## **Phase 2: Landing Page Generation**

**Objective:** Build the primary Bento Box interface and pitch the E7 framework.

Activate the frontend-design skill in your Claude Code CLI and execute the following prompt:

> Apply your frontend-design skill to build index.html using base.html as the starting structure. Read the L1 through L7 folders from my external Gil OS directory at ../\[YOUR\_SECOND\_BRAIN\_PATH\]/ to extract personal examples and metrics for each pillar.

> Execute the following structural requirements:

1. Build a Bento Box UI dashboard layout using CSS Grid (gap-4 or gap-6). Apply a glassmorphism effect (bg-white/5 backdrop-blur-md border border-white/10) and rounded-2xl corners to all cards.  
2. Detail the 7 Pillars framework. Dedicate UI sections to explain each pillar, prominently featuring AI as the foundational engine, and display the personal examples extracted from my external Gil OS.  
3. Build a UI matrix component comparing methodologies (Deep Work, Atomic Habits, PARA, Winning the Week) against their Gil OS applications.  
4. Implement hover states that elevate cards (-translate-y-1) and apply a cyan glow shadow (shadow-\[0\_8px\_30px\_rgba(0,240,255,0.1)\]). Prevent generic designs; use Space Grotesk for major UI numbers.

## **Phase 3: Blog Ingestion and Generation**

**Objective:** Extract specific markdown articles from the second brain and generate static HTML pages.

Execute the following prompt in Claude Code:

> Read the 00-Raw\_Sources directory and my 2026 Weekly Reviews from my external Gil OS directory at ../\[YOUR\_SECOND\_BRAIN\_PATH\]/. Extract the core themes for three specific topics: 'Efficiency vs. Effectiveness', 'Weekly Review Process', and 'Context Engineering'.

> Execute the following tasks:

1. Create a blog/ directory.  
2. Generate three static HTML files: blog/efficiency-vs-effectiveness.html, blog/weekly-review.html, and blog/context-engineering.html using the base.html structure. Convert the markdown text into semantic HTML. Use the 'Inter' font for long-form reading.  
3. Insert an inline email capture form exactly halfway through the text of each article to convert traffic to the newsletter. Use a solid cyan button (bg-\[\#00F0FF\] text-black font-bold).  
4. Generate blog/index.html. Design a grid layout displaying links to these three articles. Use pill-shaped tags (px-3 py-1 rounded-full text-xs font-mono border) to categorize them based on their respective Gil OS pillar.

## **Phase 4: AI For Friends Course Generation**

**Objective:** Extract the AI teaching guide and split it into a multi-page HTML course.

Execute the following prompt in Claude Code:

> Read the L7-Contribute/guides/ai\_system\_guide\_for\_sister.md file from my external Gil OS directory at ../\[YOUR\_SECOND\_BRAIN\_PATH\]/. Refactor this content into a 3-part sequential mini-course designed for beginners.

> Execute the following tasks:

1. Create an ai-for-friends/ directory with three subdirectories: module-1/, module-2/, and module-3/.  
2. Generate the lesson files using base.html styling. In module-1/, generate index.html and three lesson files (lesson-1.html through lesson-3.html). In module-2/, generate index.html and three lesson files. In module-3/, generate index.html and one lesson file (lesson-1.html). Ensure every file includes navigation buttons to move to the next or previous page.  
3. Generate ai-for-friends/index.html at the root of the course folder. Design a syllabus overview layout that links out to the index files of all three modules.
