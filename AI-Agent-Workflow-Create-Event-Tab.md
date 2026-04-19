# AI Agent Workflow: Adding Events to an Event Tab Page

This workflow documents how to instruct the AI Studio to add new events into an existing tabbed Events page (e.g., a 2024 tab, 2025 tab, etc.). A visual reference PNG is provided for each new tab to identify which events to add.

---

## Step 1 — Read the Visual Reference PNG

For each new batch of events, a PNG screenshot of the original website's events page will be provided. The PNG shows the events grid with **red boxes drawn around the events that need to be added** to the AI Studio clone.

**How to read the PNG:**

- The events page is organised into year tabs (ALL, 2011–2016, 2017, 2018, … 2024).
- Each event card shows: a feature image (photo), an event date, and an event title.
- **Red-boxed events = events to clone.** Only extract details from cards that have a red border.
- Events are displayed newest-first (top-left to bottom-right within each row).
- Ignore events without red boxes — they are already present in the clone or not required.

**Example (2024 tab PNG):** The screenshot showed the 2024 tab with red boxes on events grouped into three rows. Left column showed the events grid on the original site; right column showed additional events also highlighted with red borders. All red-boxed events across both columns were to be added.

---

## Step 2 — Collect Event Details

For each red-boxed event in the PNG, collect:

| Field | Where to Get It |
|---|---|
| **Date** | Read from the event card in the PNG |
| **Title** | Read from the event card in the PNG |
| **Language** | Determine from the event title text (see Language Detection below) |
| **Feature image URL** | Inspect the `<img>` src on the source events listing page for that event card (see Feature Image URL below) |
| **Source event page URL** | Click the event on the source site and copy the full URL — this page's content will be cloned into the internal event page |
| **Internal slug** | Derive from the event title (see Slug Generation below) |

---

## Step 2a — Get the Feature Image URL

The feature image for each event card must be the **exact thumbnail photo** shown above the event title on the source events listing page — not a placeholder or AI-generated image.

**How to find the image URL:**
1. Go to the source events page (Chinese or English, based on language detection below) and navigate to the correct year tab.
2. Right-click the photo on the event card and select **"Copy image address"** (or inspect the element and copy the `src` attribute of the `<img>` tag).
3. The URL will look like: `https://chinabaijiu.com.sg/wp-content/uploads/YYYY/MM/filename.jpg` or similar.

**Example:**
- Event: `我们回家了！寻访茅台之乡——茅台海外经销商大会`
- Feature image URL: `https://chinabaijiu.com.sg/wp-content/uploads/2017/11/Screenshot-2025-07-30-165814-300x221.png`

This exact image is what the AI Studio will download and use as the card thumbnail. Do not use the full-size page URL — use the direct image file URL (`/wp-content/uploads/...`).

---

## Step 2b — Detect the Language of Each Event

Check the event title text in the red-boxed card from the PNG:

- **If the title is in Chinese (contains Chinese characters)** → retrieve event details from the **Chinese events page:**
  `https://chinabaijiu.com.sg/cn/%e6%b4%bb%e5%8a%a8/`
  Navigate to the matching year tab, then click the event to get its full content.

- **If the title is in English (Latin characters only)** → retrieve event details from the **English events page:**
  `https://chinabaijiu.com.sg/en/events/`
  Navigate to the matching year tab, then click the event to get its full content.

> **Note:** Some events may appear in both language versions of the site with different titles. Always use the source that matches the language shown in the PNG — this ensures the correct title, content, and images are used.

---

## Step 2c — Generate the Internal Slug

Each event needs an internal URL on the site. The format mirrors how 2026 tab events work:

```
/event/[slug]
```

**Example:** `https://singaporemoutai.com/event/singapore-china-baijiu-pte-ltd-sponsors-business-china-chinese-new-year-dinner`

**Slug rules for English titles:**
- Convert the full event title to lowercase
- Replace all spaces with hyphens (`-`)
- Remove special characters (quotes, brackets, slashes, dots, commas)
- Keep numbers and letters only (plus hyphens)
- Do not include the year in the slug unless it is part of the event title itself

**Slug rules for Chinese titles:**
- Do **not** use Chinese characters in the slug — they are not URL-friendly
- Use the **English translation or romanisation** of the title as the slug base
- If the event page on `https://chinabaijiu.com.sg/cn/%e6%b4%bb%e5%8a%a8/` has an English equivalent title or slug visible in the URL, use that
- Otherwise, create a concise English slug that represents the event name

**English slug examples:**
- `2024 Baijiu Cultural Tour` → `/event/2024-baijiu-cultural-tour`
- `The 4th "Zeng Shi Sheng Cup" Graphic Chinese Chess Individual Open Tournament` → `/event/the-4th-zeng-shi-sheng-cup-graphic-chinese-chess-individual-open-tournament`
- `6th Singapore International Cultural Festival "Moutai Cup" Martial Arts Competition Gala Dinner` → `/event/6th-singapore-international-cultural-festival-moutai-cup-martial-arts-competition-gala-dinner`

**Chinese title slug examples:**
- `2024亚洲酒展 • Jiu Asia` → `/event/2024-jiu-asia` (use the English portion or romanisation)
- `2024 "香溢搏城 举杯共远" 茅台之夜` → `/event/2024-moutai-night` (use a concise English representation)

---

## Step 3 — Determine Prompt Parameters

Before writing the prompt, confirm:

1. **Tab name** — the exact label of the year tab (e.g., `2024`). Must match exactly as shown on the page.
2. **Anchor event** — the title of the existing event the new events should be placed *after*. If the tab is empty, omit this — just say "create [N] events under [TAB] tab".
3. **Number of events** — count the total red-boxed events to add in this batch.
4. **For each event** — confirm you have: feature image URL, source event page URL, and internal slug.

---

## Step 4 — Write and Submit the Prompt

Events must open as **internal pages within the site**, the same way events under the 2026 tab work (e.g., `https://singaporemoutai.com/event/singapore-china-baijiu-pte-ltd-sponsors-business-china-chinese-new-year-dinner`). Do **not** link to the external chinabaijiu.com.sg URLs.

Use this template. Fill in all `[PLACEHOLDERS]`. Write it as a **single continuous message** — no line breaks between events:

```
Under [TAB NAME] tab, create [NUMBER] events [and place it after [ANCHOR EVENT TITLE]]. When click on the event, open within the site like events under 2026 tab and clone the content from the source page. [DATE 1] [EVENT TITLE 1], download feature image from [IMAGE_URL_1], clone content from [SOURCE_EVENT_URL_1] and use URL slug /event/[SLUG 1] [DATE 2] [EVENT TITLE 2], download feature image from [IMAGE_URL_2], clone content from [SOURCE_EVENT_URL_2] and use URL slug /event/[SLUG 2] [DATE 3] [EVENT TITLE 3], download feature image from [IMAGE_URL_3], clone content from [SOURCE_EVENT_URL_3] and use URL slug /event/[SLUG 3] [DATE 4] [EVENT TITLE 4], download feature image from [IMAGE_URL_4], clone content from [SOURCE_EVENT_URL_4] and use URL slug /event/[SLUG 4]
```

> **Critical:** Do not press Enter until the full prompt is complete. Pressing Enter submits immediately.

**Key points:**
- `download feature image from [IMAGE_URL]` — use the direct `/wp-content/uploads/...` image file URL, not the event page URL
- `clone content from [SOURCE_EVENT_URL]` — the AI Studio will copy the full content (text, images, layout) from the source event detail page into the internal event page
- `use URL slug /event/[SLUG]` — sets the internal URL for the event page
- Omit `and place it after [ANCHOR]` if the tab is currently empty

---

## Example — 2017 Tab (Chinese Events, Empty Tab)

**PNG provided:** Screenshot of `https://chinabaijiu.com.sg/cn/活动/` with 2017 tab selected. 5 events red-boxed. All titles in Chinese → source: `https://chinabaijiu.com.sg/cn/%e6%b4%bb%e5%8a%a8/`.

**Tab state:** Empty ("No events found for 2017") — no anchor event needed.

**Data collected per event:**

| Title | Feature Image URL | Source Event Page URL | Internal Slug |
|---|---|---|---|
| 我们回家了！寻访茅台之乡——茅台海外经销商大会 | `https://chinabaijiu.com.sg/wp-content/uploads/2017/11/Screenshot-2025-07-30-165814-300x221.png` | `https://chinabaijiu.com.sg/cn/event/%e6%88%91%e4%bb%ac%e5%9b%9e%e5%ae%b6%e4%ba%86.../` | `/event/moutai-overseas-distributors-conference` |
| 白酒粉丝们的双节联欢晚会 | *(inspect img src on listing page)* | `https://chinabaijiu.com.sg/cn/event/%e7%99%bd%e9%85%92.../` | `/event/baijiu-fans-double-festival-gala-dinner` |
| 嗨了！F1与白酒粉丝团们的激情之夜 | *(inspect img src on listing page)* | `https://chinabaijiu.com.sg/cn/event/%e5%97%a8%e4%ba%86.../` | `/event/f1-baijiu-fans-passion-night` |
| 祝贺由新加坡白酒协会举办的"红火招牌菜"活动顺利完成！ | *(inspect img src on listing page)* | `https://chinabaijiu.com.sg/cn/event/%e7%a5%9d%e8%b4%ba.../` | `/event/singapore-baijiu-association-hong-huo-signature-dish` |
| 新加坡52岁国庆茅台专场，向全世界SAY HI | *(inspect img src on listing page)* | `https://chinabaijiu.com.sg/cn/event/%e6%96%b0%e5%8a%a0%e5%9d%a1.../` | `/event/singapore-52nd-national-day-moutai-event` |

**Prompt format:**

```
Under 2017 tab, create 5 events. When click on the event, open within the site like events under 2026 tab and clone the content from the source page. November 24, 2017 我们回家了！寻访茅台之乡——茅台海外经销商大会, download feature image from https://chinabaijiu.com.sg/wp-content/uploads/2017/11/Screenshot-2025-07-30-165814-300x221.png, clone content from https://chinabaijiu.com.sg/cn/event/%e6%88%91%e4%bb%ac%e5%9b%9e%e5%ae%b6%e4%ba%86%ef%bc%81-%e5%af%bb%e8%ae%bf%e8%8c%85%e5%8f%b0%e4%b9%8b%e4%b9%a1-%e8%8c%85%e5%8f%b0%e6%b5%b7%e5%a4%96%e7%bb%8f%e9%94%80%e5%95%86%e5%a4%a7/ and use URL slug /event/moutai-overseas-distributors-conference [repeat pattern for remaining 4 events]
```

---

## Feature Image URL Reference

Each event's feature image must be the **exact thumbnail** shown on the source events listing page — downloaded directly from its `/wp-content/uploads/...` URL.

**How to get the image URL for each event card:**
1. Go to the source events page and select the correct year tab.
2. Right-click the photo on the event card → **"Copy image address"**.
   - Or: right-click → **Inspect**, find the `<img>` tag inside the card, copy the `src` attribute.
3. The URL should look like: `https://chinabaijiu.com.sg/wp-content/uploads/YYYY/MM/image-name.jpg`

**Important:** Use the direct image file URL — not the event page URL, not a search result, not an AI-generated image. The `-300x221` or similar suffix in the filename is normal (it's a WordPress thumbnail size) and is fine to use.

**Example:**
```
download feature image from https://chinabaijiu.com.sg/wp-content/uploads/2017/11/Screenshot-2025-07-30-165814-300x221.png
```

---

## Rules to Follow

- **Single message:** Write the entire prompt as one continuous message. No Enter until finished.
- **Wait for completion:** Do not send another prompt until the AI Studio finishes.
- **Exact titles:** Copy event titles exactly from the source website or PNG.
- **Language matching:** Chinese event titles → fetch from `https://chinabaijiu.com.sg/cn/%e6%b4%bb%e5%8a%a8/`; English event titles → fetch from `https://chinabaijiu.com.sg/en/events/`. Do not mix sources.
- **Feature image = exact thumbnail:** Always use the direct `/wp-content/uploads/...` image URL from the event card on the listing page. Never use a placeholder or AI-generated image.
- **Clone content:** Always include `clone content from [SOURCE_EVENT_URL]` so the internal event page copies the full text, images, and layout from the source — not a blank or generic page.
- **Internal slug only:** Do not use external chinabaijiu.com.sg URLs as the destination. Always use internal slugs in the format `/event/[slug]`.
- **Reference the 2026 tab:** Always phrase it as `open within the site like events under 2026 tab` so the AI Studio matches the correct behaviour.
- **Derive slugs carefully:** Lowercase, hyphens, no special characters. A wrong slug creates a broken internal page.
- **Tab name must match exactly:** e.g., `2024` not `Year 2024`.
- **Anchor event:** Specify only if the tab already has events. If the tab is empty, omit the anchor entirely.
- **Batch size:** Add events in logical batches per year tab. Do not mix events from different year tabs in one prompt.

---

## Verification After Completion

Once the AI Studio finishes, check:

1. Events appear under the correct tab.
2. Events are in the correct order (newest first), placed after the anchor event if one was specified.
3. Each event card shows the **exact thumbnail image** downloaded from the source listing page.
4. Clicking an event card opens an **internal page** within the site (not chinabaijiu.com.sg).
5. The internal event page URL matches the slug (e.g., `/event/moutai-overseas-distributors-conference`).
6. The internal event page **contains the cloned content** from the source event detail page (title, body text, images — not a blank page).
7. Event dates and titles are accurate (compare against the PNG and source site).
8. Layout is correct on desktop, tablet, and mobile views.
9. Note the **last anchor event** for the next batch if more events are to be added to the same tab.
