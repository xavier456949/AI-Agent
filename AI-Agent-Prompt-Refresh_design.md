# AI Agent Prompt For Monitor AI Studio - Website Design Refresh

working url: place_holder_url of app.1cloudai.com
how often to check: screenshot to check every 30 seconds
Work Details: The application on this page is an AI studio designed to refresh the design of an existing website: `<PLACEHOLDER_URL>`. We aim to redesign it to mirror a specific reference site (`<REFERENCE_SITE_URL>`) or to adopt a distinct design aesthetic. **IMPORTANT: Please choose and keep only ONE style instruction in your prompt (e.g., choose between Apple style, Minimalism, Neo-Brutalism, or Bento Grid layout) to maintain a consistent design direction.**

## Things you need to know:
1. The AI studio typically applies redesigns one page at a time rather than updating the entire website simultaneously.
2. At the bottom left corner of the design page is the prompt chat box where you can provide detailed instructions on styling and layout. Inside the chat box, there is a "Ask AI..." placeholder text.
3. The conversation history window displays current work status. You can click on active tasks to view specific actions like code edits or component updates.
4. You can inspect the generated code by clicking the `</>` button and the globe icon beside the code inspection button to switch to preview.
5. The preview window allows you to switch between pages and view layouts across desktop, tablet, and phone screen sizes using the respective icons.
6. You can refresh the current design by clicking the **refresh icon** within the preview box.
7. You can view the entire generated page by scrolling up and down within the preview window.

## What you need to do:
1. Monitor the work progress and verify if the styling prompt has been fully executed.
2. Review the redesigned page. If it matches the desired aesthetic, ask the AI studio to apply this design system to the remaining pages. If not, provide an accurate prompt to adjust the typography, layout, or colors.
3. Once all pages are redesigned, ensure that all internal and external navigation links function correctly.
4. Verify the new layout across different screen sizes. The design must be fully responsive; report any layout breakages to the AI studio with a prompt to fix them.
5. Confirm that the selected aesthetic (e.g., Minimalism, Neo-Brutalism) is applied consistently throughout the site (spacing, borders, fonts, and colors).
6. Request the AI to generate a `sitemap_index.xml` that includes `page-index.xml`, `post-index.xml`, and `product-index.xml`.
7. Check if the logo, favicon, and other brand assets are appropriately adapted to the new style.
8. If errors occur during the styling changes, refresh the page or step back using the **view history icon** at the top right of the chat window to restore the last stable state.
9. If the original website had widgets (e.g., a chatbot or WhatsApp button), verify that they are integrated harmoniously into the new UI.
10. check if all the buttons, links are connected to the correct pages.
11. Check if all the menu item are connected to the correct pages. If any menu item got no pages, create it.
12. If got blog/event/media page, make sure each blog got its own page, and all the links are connected to the correct pages. Click on the image and title shall also be able to enter the post page.
13. If user has provided company contact, address, emails, check all the contact details are updated in the contact page and footer.

## Rules to Follow:
1. **Single Message Prompts:** Avoid pressing "Enter" until the prompt is finished, as it will send immediately; you can create prompts without new lines to prevent this.
2. **Be Specific with Styles:** Clearly state the target aesthetic. For example, instruct the AI to "Implement a Bento Grid layout for the feature section" or "Use Neo-Brutalism with high-contrast borders and stark shadows."
3. **Preserve Functionality:** Always instruct the AI to maintain existing functional elements (forms, menus) and just update their visual appearance.
4. **URL Structure:** Instruct the AI studio to keep the original URL slugs for every page.
5. **Asset Handling:** Focus on styling existing content. If new images are required to match the style, instruct the AI to create them according to the target aesthetic.
6. **Stopping Work:** If the AI studio begins applying an incorrect or undesirable design direction, click the **stop button** immediately to halt the process, then provide a corrected prompt.
