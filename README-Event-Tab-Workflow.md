# Event Tab Workflow — Quick Start Guide

This guide explains how to add events to a year tab on the singaporemoutai.com clone site using the AI agent.

---

## What You Need to Provide

**1. The tab name**
The year tab you want to add events to. Example: `2017`, `2025`.

**2. The event list**
A list of events to add, one per line, in this exact format:
```
DD MM月, YYYY, Event Title
```

**3. Anchor event (only if the tab already has events)**
The title of the last existing event in that tab. New events will be placed after it. If the tab is empty, skip this.

---

## How to Start

Just paste a message to the AI in this format:

> Add these events to the **[YEAR] tab**. The tab [is empty / already has events — last event is "[ANCHOR TITLE]"].
>
> [Your event list]

The AI will then:
1. Parse the dates and titles from your list
2. Detect the language (Chinese or English) to find the right source page
3. Navigate to chinabaijiu.com.sg to find each event's feature image URL and source page URL
4. Generate an internal URL slug for each event
5. Produce a ready-to-paste prompt for AI Studio

---

## Example

**Your message to the AI:**

> Add these events to the **2017 tab**. The tab is empty.
>
> 24 11月, 2017, 我们回家了！寻访茅台之乡——茅台海外经销商大会
> 6 10月, 2017, 白酒粉丝们的双节联欢晚会
> 15 9月, 2017, 嗨了！F1与白酒粉丝团们的激情之夜
> 18 8月, 2017, 祝贺由新加坡白酒协会举办的"红火招牌菜"活动顺利完成！
> 9 8月, 2017, 新加坡52岁国庆茅台专场，向全世界SAY HI

**What the AI produces:**

A single prompt ready to paste into AI Studio — no further editing needed. Example output:

> Under 2017 tab, create 5 events. When click on the event, open within the site like events under 2026 tab and clone the content from the source page. For all images (feature images and all inline images inside the cloned content), download them from the source and upload to our site's media library — do not hotlink from the original site. Process image downloads and uploads in batches of 5 at a time before moving to the next batch. November 24, 2017 我们回家了！..., download feature image from https://chinabaijiu.com.sg/..., upload to our site, clone content from https://chinabaijiu.com.sg/cn/event/..., re-upload all inline images in the content to our site, and use URL slug /event/moutai-overseas-distributors-conference [... and so on for all 5 events]

**Then in AI Studio:**
1. Open the AI Studio for singaporemoutai.com
2. Paste the full prompt into the chat
3. Press Enter and wait for it to finish — do not interrupt

---

## After AI Studio Finishes — What to Check

- Events appear under the correct year tab
- Events are in the correct order (newest first)
- Each event card shows the correct thumbnail image
- Clicking an event opens an internal page (URL starts with `singaporemoutai.com/event/...`)
- Right-click any image on the event page → the image URL should be on `singaporemoutai.com`, not `chinabaijiu.com.sg`

---

## Notes

- **Chinese titles** → AI fetches from `chinabaijiu.com.sg/cn/活动/`
- **English titles** → AI fetches from `chinabaijiu.com.sg/en/events/`
- All images (thumbnails + body images) are downloaded and uploaded to the clone site — no hotlinking
- Image uploads are processed in batches of 5 to avoid overloading the server
- Do not mix events from different year tabs in one prompt
