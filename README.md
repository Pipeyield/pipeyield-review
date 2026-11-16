# Pipeyield search-term review for Claude

Get Pipeyield's free Google Ads search-term review without leaving Claude. Ask for a review, open the link Claude gives you, upload your Google Ads search terms report on Pipeyield's page, and the result comes back into the chat:

- what the account sells, read from its own campaigns and keywords, and the buyer terms it protects
- the searches to exclude, with their spend a month and the reason for each
- the searches to watch, and the buyer terms to keep
- a negatives file for Google Ads Editor, from the review page

Your top 500 searches by spend are reviewed; the review says how many smaller ones weren't. It reads the words people searched and the clicks and conversions in your file. It can't see who became a customer, so check any high-spend row before you exclude it.

## Install in Claude Code

Add the marketplace and install the plugin:

```
/plugin marketplace add pipeyield/pipeyield-review
/plugin install pipeyield-review@pipeyield
```

Then ask, for example: "Review my Google Ads search terms."

The plugin adds the `pipeyield` MCP server (`https://app.pipeyield.com/mcp`) and a skill that tells Claude when and how to use it. To add only the server, without the skill:

```
claude mcp add --transport http pipeyield https://app.pipeyield.com/mcp
```

## Add it to Claude as a custom connector

On claude.ai or the Claude desktop app:

1. Open **Settings**, then **Connectors**.
2. Choose **Add custom connector**.
3. Name it `Pipeyield` and enter the URL `https://app.pipeyield.com/mcp`. There's no sign-in.
4. In a chat, turn the connector on and ask for a review of your Google Ads search terms.

On Team and Enterprise plans, an owner may need to add the connector for the organization first.

## How it works

The server has two tools:

- `start_review` makes a one-time link to Pipeyield's review page. The link works for 24 hours.
- `get_review` answers with the state of that review: waiting for the upload, still working, the finished review, or expired.

## What data goes where

- **Your report goes only to Pipeyield's page.** You upload it in your browser, on pipeyield.com, behind a robot check. It never goes through the chat, and the tools don't accept files or search terms.
- **The chat gets the finished review.** Claude receives the same review the page shows you, including your top searches and their spend, so it can show it to you. What Claude does with chat content is covered by your Claude plan's terms.
- **Pipeyield keeps the file and the review for 24 hours**, or 7 days if you ask us to email the review, then deletes them. An email address you give on the review page is kept with them for that time. Pipeyield's privacy notice: https://pipeyield.com/privacy
- **Nothing about you is needed.** No sign-in and no email to see the review. Each link is a random code that works for 24 hours.

## Questions

Email hello@pipeyield.com.
