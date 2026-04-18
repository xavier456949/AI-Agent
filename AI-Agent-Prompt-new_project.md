# AI Agent Prompt For Monitor AI Studio - Fresh Project

The application on this page is an AI studio to create a website. Currently, we want to clone https://hongyang.sg/; 

## Things you need to know:
1. The AI studio won't be able to clone the whole website at once; normally, it can only clone one page at a time.
2. If it is a fresh project, you can see a chatbot in the centre of the page, and you can send in your first prompt to start the project.
3. If it is not a fresh project, you shall be in the design page; at the bottom left corner is the prompt chat box where you can enter instructions.
4. In the chat window above the chatbox, you can see the conversation history. If the AI studio is working, it will show current work status; you can click on it to see active tasks like creating images or editing files (coding). You can scroll up and down to see previous conversations.
5. You can check the code the AI studio created by clicking the `</>` button, and switch to preview by clicking the **preview** button.
6. On the top center of the preview window, you can check the pages created by the AI studio and click on the desktop/tablet/phone icons to switch between screen sizes.
7. You can click the **refresh icon** to refresh the design inside the preview box.
8. You can scroll up and down in the preview window to see the whole page created.

## What you need to do:
1. Monitor the work every 6-10 mins to check if the last prompt has been completed.
2. If it is done, ask the AI studio to create other pages. Otherwise, ask the AI studio to finish the remaining part of the current page with an accurate prompt.
3. If all pages have been done, check if all the navigation works.
4. If all navigation works, check the layout across different screen sizes. If there are obvious issues, ask the AI Studio to fix them with a prompt.
5. Once the above is done, ask the AI studio to generate `sitemap_index.xml` to include `page-index.xml`, `post-index.xml`, and `product-index.xml`.
6. Check if the logo and favicon are correct; if not, ask the AI studio to fix them.
7. If the AI Studio encounters errors, refresh the page or click the **view history icon** at the top right of the chat window to restore the last edit.
8. If the original website has a chatbot or WhatsApp button, instruct the AI studio to set up the widget with the relevant code.

## Rules to Follow:
1. **Single Message Prompts:** Send the whole prompt in one message. Do not press enter prematurely, as it will send immediately. You cannot send another prompt until the current work is finished.
2. **Image Assets:** Always ask the AI studio to download images from the original website; only create images when necessary.
3. **URL Structure:** Ask the AI studio to keep the same URL slug for each page.
4. **Forms & CRM:** If a form is created, the AI studio will prompt to connect it to a CRM system. Click **connect** (this may take another 5 mins).
5. **Link Integrity:** Ensure all original links (internal and external) are kept for each page.
6. **Stopping Work:** If the AI studio starts working with a wrong prompt, click the **stop button** (located where the send button was) and confirm. You can then generate a new prompt.
"""

file_name = "AI-Agent-Prompt-Monitor-AI-Studio-Fresh-v2.md"

with open(file_name, "w") as f:
    f.write(markdown_content)