---
name: search-term-review
description: Runs Pipeyield's free Google Ads search-term review. Use when the user wants their Google Ads search terms report reviewed, asks which searches or keywords spend money on the wrong people (job seekers, people wanting something free, students), or wants to find off-target search spend.
---

# Google Ads search-term review

Pipeyield reads a Google Ads search terms report and sorts the searches with the most spend into exclude, keep and check by hand, each with its spend and a reason, and builds the list of negatives to add. The report is uploaded on Pipeyield's page, never in this chat.

## Steps

1. Call the `start_review` tool from the `pipeyield` server. It takes no arguments.
2. Give the user the link it returns. Tell them to open it, upload their Google Ads search terms report there (the last 30–90 days, exported as CSV or Excel), and come back when it's done. The link works for 24 hours.
3. When the user says it's uploaded, call `get_review` with the `grant` from step 1.
   - `waiting`: not uploaded yet. Remind the user of the link and wait for them.
   - `working`: call `get_review` again in about 30 seconds. If it says it's taking longer than usual, tell the user they can leave an email on the review page to get the result by email.
   - `done`: show the review to the user as it is. Don't change the numbers or add your own figures.
   - `expired`: call `start_review` for a new link.

## Rules

- Never ask the user to paste or attach the report in the chat, and never pass search terms or files to the tools. The file goes only to Pipeyield's page, which runs a robot check.
- It reads the words, clicks and conversions in the file, not who became a customer, so check high-spend rows before you exclude them. Say so if the user asks.
- The negatives file is on the review page the user uploaded on; point them there.
- If the user asks what's kept: Pipeyield keeps the file and the review for 24 hours, or 7 days if they ask for the review by email, and then their email address is kept with it for those 7 days.
