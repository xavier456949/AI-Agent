# AI Agent Prompts for AI Studio Monitoring

This repository contains a curated collection of prompts and workflows designed to effectively instruct and monitor AI Studio for website creation, cloning, and redesign tasks.

## 🚀 Getting Started

These prompts are designed to be used in the AI Studio chat interface. For best results, follow the [Best Practices](#-best-practices) below.

---

## 🗂 Prompt Library

The prompts are categorized based on the phase of the project:

### 1. Project Initiation
These prompts are intended for the very first message sent to the AI Studio.
- **[1st Prompt to Create Site](file:///d:/Projects/pixel%20warriors/AI%20Agent%20Prompt%20John/AI-Agent-Prompt-1st%20prompt%20to%20create%20site.md)**: Concise baseline prompt for starting a project with specific assets (Logo, Favicon, Letterhead).
- **[Brand New Design with Reference Site](file:///d:/Projects/pixel%20warriors/AI%20Agent%20Prompt%20John/AI-Agent-Prompt-brand%20new%20design%20with%20Reference%20site.md)**: Instructions for creating or refreshing a site based on a reference URL.

### 2. Monitoring & Quality Control
Use these prompts during the development phase to ensure the AI Studio remains focused and follows project requirements.
- **[Fresh Project Monitoring](file:///d:/Projects/pixel%20warriors/AI%20Agent%20Prompt%20John/AI-Agent-Prompt-new_project.md)**: Standard monitoring workflow for new builds.
- **[Website Cloning Monitor](file:///d:/Projects/pixel%20warriors/AI%20Agent%20Prompt%20John/AI-Agent-Prompt-clone_project.md)**: Specialized checklist for cloning existing sites.
- **[Design Refresh Monitor](file:///d:/Projects/pixel%20warriors/AI%20Agent%20Prompt%20John/AI-Agent-Prompt-Refresh_design.md)**: Guidelines for tracking redesign progress.

---

## 🛠 Specific Workflows

For more complex, recurring tasks, refer to our detailed workflow documentation:

- **[Event Tab Workflow](file:///d:/Projects/pixel%20warriors/AI%20Agent%20Prompt%20John/README-Event-Tab-Workflow.md)**: Detailed guide for adding events to tabbed pages.
- **[Workflow Guide (Full)](file:///d:/Projects/pixel%20warriors/AI%20Agent%20Prompt%20John/AI-Agent-Workflow-Create-Event-Tab.md)**: Comprehensive technical documentation for the event tab process.

---

## ✅ The Unified Monitoring Checklist

All monitoring prompts in this repository follow a standardized verification process. Always check the following:

1.  **Work Progress**: Verify if prompts have been fully executed (recommended check: **screenshot every 30 seconds**).
2.  **Responsiveness**: Check layout breaks across desktop, tablet, and mobile.
3.  **Navigation**: All buttons, internal links, and external links must function correctly.
4.  **Menu Items**: Ensure all menu items connect to the correct pages; create missing pages if necessary.
5.  **Dynamic Content**: For Blog, Event, or Media pages, ensure every item has its own page and titles/images navigate correctly.
6.  **Contact Details**: Verify that company contacts, addresses, and emails are updated in the contact page and footer.
7.  **Sitemaps & Assets**: Ensure `sitemap_index.xml` is generated and Favicon/Logo are correct.

---

## 💡 Best Practices

> [!IMPORTANT]
> **Single Message Prompts**: Always send your complete prompt in one message. Avoid pressing "Enter" until the prompt is finished, as it sends immediately. You can write your prompt in a separate document and paste it to prevent accidental submission.

> [!TIP]
> **Asset Handling**: Prioritize downloading original images. Only use AI generation when original assets are unavailable or a style refresh is explicitly requested.

---

## 🔄 Updating and Synchronizing

This repository is synced with an upstream source. To pull latest updates:
```bash
git fetch upstream
git pull upstream main
```
