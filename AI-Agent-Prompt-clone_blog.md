# AI Agent Prompt For Monitor AI Studio Blog Clone - non-Fresh Project

working url: place_holder_url of app.1cloudai.com
how often to check: screenshot to check every 30 seconds
Work Details: The application is an AI studio designed to clone blog content from the sitemap listed below into an existing project; this is not a fresh project. The placeholder below represents the sitemap of the blog pages to be migrated.

blog sitemap: `<PLACEHOLDER_BLOG_SITEMAP_URL>`

## Things you need to know:
* The AI studio typically clones one page at a time rather than the entire website simultaneously.
* For existing projects, use the prompt chat box located in the bottom left corner of the design page to provide instructions. Inside the chat box, there is a "Ask AI..." placeholder text.
* The conversation history window displays current work status.
* You can click on tasks in the history to see specific actions, such as code edits or image creation.
* Previous conversations can be viewed by scrolling up and down in the chat window.
* Use the `</>` button to inspect the generated code and the globe icon beside the code inspection button to switch to preview.
* The preview window allows you to check different pages and switch between desktop, tablet, and phone views.
* You can refresh the design within the preview box using the refresh icon.
* The whole created page can be viewed by scrolling within the preview window.
* The sitemap is the source of truth for the list of blog pages that must be migrated.

## What you need to do:
* Monitor progress and verify if the last prompt is finished.
* Read the blog sitemap and identify all blog URLs that need to be cloned.
* Instruct the AI studio to clone blog posts one by one, sending one complete instruction at a time for each blog page.
* Before migrating each blog, do a one-time slug check: compare the slug shown on the source blog main page against the slug from the sitemap.
* If the blog main page slug does not match the sitemap slug, instruct AI Studio to fix the slug first, then proceed with the migration.
* Keep the same slug for every migrated blog page as listed in the sitemap.
* If a blog page is unfinished, provide accurate prompts to complete the remaining sections.
* After each blog is created, verify that the blog listing page links to the correct post page.
* Ensure the image, title, and any "read more" button on the listing page all link to the correct blog post.
* Check that all navigation functions correctly once all blog pages are built.
* Verify the layout on different screen sizes and prompt the AI to fix any obvious issues.
* Request the AI to generate or update the relevant sitemap files so the migrated blog pages are included correctly.
* Ensure the logo and favicon are correct; if they are not, ask the AI to fix them.
* If errors occur, refresh the page or use the view history icon at the top right of the chat window to restore the last edit.
* If the original site had a chatbot or WhatsApp button, instruct the AI to set up the widget using the relevant code.
* Check if all buttons and links are connected to the correct pages.
* Check if all menu items are connected to the correct pages. If any menu item has no page, create it.

## Rules to Follow:
* Send prompts as a single, complete message.
* Avoid pressing "Enter" until the prompt is finished, as it will send immediately; you can create prompts without new lines to prevent this.
* Wait for the current task to finish before sending a new prompt.
* Always prioritize downloading images from the original website, creating new ones only when necessary.
* Always migrate blog pages one by one, never batch multiple blog pages into a single prompt.
* Before each blog migration, verify the source blog slug against the sitemap slug.
* If the slug is wrong, instruct AI Studio to fix the slug before continuing.
* Ensure each migrated blog page maintains the same URL slug as the original sitemap entry.
* Keep all original internal and external links for every blog page.
* If a form is created, click "connect" to link it to the CRM system; this setup may take approximately 5 minutes.
* If the AI starts working with an incorrect prompt, use the stop button to cancel the action and then generate a new prompt.
