# AI Agent Prompts for 1CloudAI Studio

This repository is a curated library of **prompts, monitoring guides, and workflows** for operating [1CloudAI's Vibe Studio](https://app.1cloudai.com) — an AI-powered website builder. Each document serves a specific purpose in the website creation pipeline, from kicking off a new project to quality-checking the final result.

---

## 📁 Document Directory

### 🚀 Phase 1: Starting a Project

---

#### [`AI-Agent-Prompt-1st prompt to create site.md`](./AI-Agent-Prompt-1st%20prompt%20to%20create%20site.md)

**Purpose:** The very first prompt you paste into AI Studio when starting a brand-new project.

**How to use:**
1. Open a new project in AI Studio (you'll see a chatbot in the centre of the screen).
2. Fill in the placeholders:
   - `[Company Name]` — the client's company name.
   - `[Reference Website URL]` — a reference website for the design style.
3. Attach 3 images **before** sending:
   - **1st image**: Company letterhead (used to extract address, contacts, emails).
   - **2nd image**: Company logo (used as the website logo).
   - **3rd image**: Icon/favicon (used as the browser tab icon).
4. Paste the completed prompt and press Enter.

> **Note:** This is a one-time kickoff prompt. After this, switch to one of the **Monitoring guides** below.

---

#### [`AI-Agent-Prompt-brand new design with Reference site.md`](./AI-Agent-Prompt-brand%20new%20design%20with%20Reference%20site.md)

**Purpose:** An **AI Agent monitoring guide** for when the AI Studio is actively designing or redesigning a website based on a reference site. Paste the `working url` of your AI Studio project and hand this entire document to an AI agent to monitor the work.

**How to use:**
1. Replace `working url` with your actual AI Studio project URL (from `app.1cloudai.com`).
2. Replace `<REFERENCE_SITE_URL>` with the URL of the design you want to mirror.
3. Provide this file to your AI monitoring agent. The agent will:
   - Take a screenshot every 30 seconds to track progress.
   - Follow the step-by-step checklist after completion.
   - Verify navigation, menus, blog/event links, contact details, and responsive layout.

---

### 🔄 Phase 2: Monitoring an Ongoing Project

These guides are used when a project is **already in progress** inside AI Studio. Provide the relevant file to an AI agent to oversee the work.

---

#### [`AI-Agent-Prompt-new_project.md`](./AI-Agent-Prompt-new_project.md)

**Purpose:** Monitoring guide for a **fresh project where AI Studio is building the full site from scratch**, referencing a design from another site.

**When to use:** The project has just started, all pages still need to be built, and the AI Studio chatbot is visible in the centre of the screen (not yet in design mode).

**How to use:**
1. Replace `working url` with the live AI Studio project URL.
2. Update `Work Details` with the specific reference site URL and instructions for the current session.
3. Hand the document to an AI agent — it will monitor progress every 30 seconds and run through the full quality checklist.

---

#### [`AI-Agent-Prompt-clone_project.md`](./AI-Agent-Prompt-clone_project.md)

**Purpose:** Monitoring guide for **cloning an existing website** into AI Studio. The AI replicates pages from the original site one at a time.

**When to use:** The project's goal is to replicate a source website, and the project is already inside the AI Studio design view (not a fresh chatbot screen).

**How to use:**
1. Replace `working url` with the live AI Studio project URL.
2. Replace `<PLACEHOLDER_URL>` in Work Details with the source website being cloned.
3. Hand to an AI agent — it will monitor cloning progress, verify all pages, and run the quality checklist.

---

#### [`AI-Agent-Prompt-Refresh_design.md`](./AI-Agent-Prompt-Refresh_design.md)

**Purpose:** Monitoring guide for **redesigning an existing site** already built in AI Studio using a new aesthetic (e.g., Minimalism, Neo-Brutalism, Bento Grid, Apple-style).

**When to use:** The project already has pages, but the visual design needs to be overhauled to match a new style or reference.

**How to use:**
1. Replace `working url` with the live AI Studio project URL.
2. Update Work Details with the original site URL and the target reference or style.
3. Choose **one** design style only — do not mix styles in a single prompt session.
4. Hand to an AI agent — it will monitor progress, confirm style consistency, and verify all links, menus, and contact details.

---

### 🗓 Phase 3: Specific Feature Workflows

---

#### [`README-Event-Tab-Workflow.md`](./README-Event-Tab-Workflow.md)

**Purpose:** A concise **quick-start guide** for adding events to a tabbed Events page (e.g., adding events under a "2017" tab on a site like singaporemoutai.com).

**How to use:**
1. Provide the AI agent with:
   - The **tab name** (e.g., `2017`).
   - A list of events in the format: `DD MM月, YYYY, Event Title`.
   - The **anchor event** (the last existing event in that tab), or state "the tab is empty".
2. The agent will generate a ready-to-paste AI Studio prompt. Paste it and press Enter.
3. After completion, follow the verification checklist in the document.

---

#### [`AI-Agent-Workflow-Create-Event-Tab.md`](./AI-Agent-Workflow-Create-Event-Tab.md)

**Purpose:** The **full technical reference** for the event tab workflow. Used by an AI agent to understand exactly how to parse event lists, detect language, find feature images, generate slugs, and construct prompts.

**How to use:** This file is meant to be read by an AI agent, not edited manually. It contains the complete decision logic for every step of the event creation process, including fix prompts for common issues (hotlinked images, blank event pages, etc.).

---

#### [`2017-tab-prompt.md`](./2017-tab-prompt.md) / [`2025-tab-prompt.md`](./2025-tab-prompt.md)

**Purpose:** Pre-built, ready-to-paste AI Studio prompts for specific event batches (2017 and 2025 tabs). These are **output artifacts** generated by the Event Tab Workflow for the singaporemoutai.com project.

**How to use:** Copy the prompt text directly into the AI Studio chat for the relevant project and press Enter. No modification needed.

---

## ✅ Universal Quality Checklist

All monitoring guides share the following final verification steps:

| # | Check |
|---|-------|
| 1 | Take a screenshot every 30 seconds to verify AI is still working |
| 2 | Confirm all pages are built and navigation links function correctly |
| 3 | Check all buttons and links point to the correct pages |
| 4 | Verify all menu items connect to existing pages; create pages for any gaps |
| 5 | For Blog/Event/Media pages: each post must have its own page; images and titles must be clickable |
| 6 | Verify company contact details, address, and emails are correct in the contact page and footer |
| 7 | Check responsiveness on desktop, tablet, and mobile views |
| 8 | Confirm logo and favicon are correct |
| 9 | Generate `sitemap_index.xml` including `page-index.xml`, `post-index.xml`, `product-index.xml` |
| 10 | If a chatbot or WhatsApp widget exists, verify it is integrated correctly |

---

## 💡 Key Rules

> **Single Message Prompts:** Never press "Enter" mid-prompt — it sends immediately. Write your full prompt first, then paste and submit.

> **Image Assets:** Always instruct the AI to download images from the original site. Only generate new images when the original is unavailable or a style refresh calls for it.

> **Stop Incorrect Work:** If the AI starts on the wrong track, click the **Stop button** (where the Send button used to be), confirm, and then send a corrected prompt.

---

## 🔄 Syncing with Upstream

This repository is forked from an upstream source. To pull the latest updates:

```bash
git fetch upstream
git pull upstream main
```
