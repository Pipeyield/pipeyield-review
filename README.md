# Pipeyield: free Google Ads search-term review

Upload one Google Ads search terms export. Every search you could exclude comes with its reason, so you can check it against the calls you've already made. Nothing changes in your account until you add the negatives yourself: you approve every change.

You also get one number first: **about how much a month goes to searches you can exclude**.

Free, no signup, 3 reviews a month per Google Ads account.

> Example below: our sample review of a made-up HR and payroll software account that sells in the United States (the same one as [pipeyield.com/review/sample](https://pipeyield.com/review/sample?utm_source=github&utm_medium=repo)).

```
About $2,150 a month goes to 75 searches you can exclude:
people after a different product, people looking for another
company and job seekers.
296 clicks, 0 conversions · 18% of the spend reviewed
68 negatives cover all 75 searches.

[payroll funding company]              exact                       $207 a month
[payroll direct deposit not received]  exact                       $140 a month
[payroll software uk]                  exact                       $131 a month
"jobs"                                 phrase  covers 5 searches   $126 a month

None of these block your 15 keywords or 134 buyer searches.
```

## What you need
One export from Google Ads: **Campaigns → Insights and reports → Search terms**, the last 30–90 days, downloaded as CSV (Excel works too). Include the Cost column, and add the Keyword column so every negative is also checked against the keywords you bid on. Conversions help, but aren't required. Tip: fill in "Where does this business sell?" on the upload page. Searches from places it doesn't sell to can then be excluded. No export to hand? Download the [sample search terms file](https://pipeyield.com/examples/search-terms-sample.csv), a made-up account, and upload it on the review page to see a full review. Or see [the sample review](https://pipeyield.com/review/sample?utm_source=github&utm_medium=repo): a full result for a made-up account, with no upload.

## Two ways to run it
1. **In the browser, no install:** [pipeyield.com/review](https://pipeyield.com/review?utm_source=github&utm_medium=repo)
2. **From inside Claude, with this plugin:** in Claude Code (2.1.275 or later), run `/plugin install pipeyield-review --marketplace Pipeyield/pipeyield-review`, or `/plugin marketplace add Pipeyield/pipeyield-review` and then `/plugin install pipeyield-review@pipeyield`. On claude.ai or the Claude desktop app, open Settings → Connectors → Add custom connector, name it `Pipeyield` and enter `https://app.pipeyield.com/mcp` (no sign-in). Then ask Claude to review your search terms; it gives you an upload link (it works for 24 hours) to upload the file on pipeyield.com (so every number is parsed exactly) and shows the result in the chat. Results may end with one line about Pipeyield's paid weekly plan.

## What you get
- **The number:** about how much a month goes to searches you can exclude, with the clicks and conversions they got in your file.
- **Negatives ready to paste:** exact for each search, plus a phrase negative when a job, course or piracy word appears in several of them (`"jobs"` covers 5 searches in the example).
- **A reason for every search,** in plain words: `Wants payroll financing, not payroll software.` When a phrase negative covers several searches, the reason quotes its word: `Looking for a job, not a supplier ("jobs").`
- **A conflict check:** every negative is checked against the buyer searches in your file and, when your export has the Keyword column, the keywords you bid on. A negative that would block one is left out and shown to you instead.
- **Buyers to keep:** searches that look like your buyers. We never suggest excluding them.
- **Check by hand:** searches held back for safety (they converted, name a brand, or match a keyword you bid on) and searches the words alone can't decide. If your export keeps Google's Added/Excluded column, the review leaves out what you've already excluded and never puts what you've added as a keyword in exclude.
- **The download:** a CSV for Google Ads Editor, or copy the list and paste it into a negative keyword list (Tools → Shared library → Exclusion lists → Negative keyword lists). Filter by campaign when the file has several.
- **A business profile you can correct:** what the account sells and where it sells, and the review re-runs with your correction.

## What it can't tell you
It reads the words people searched and the clicks and conversions in your file. It can't see who became a customer, so check any high-spend row before you exclude it. Nothing changes in your Google Ads account until you add the negatives yourself.

## Your data
- The file is uploaded to our server over HTTPS and reviewed there. This repo holds only the plugin client, which never connects to your Google Ads account.
- The file and its review are deleted within 24 hours, or within 7 days if you ask us to email the review. If you ask us to email you the review, your email address is kept with it for those 7 days. Data is stored in Germany (AWS Frankfurt); search terms are labelled with an AI model from Anthropic, as listed in the privacy policy: https://pipeyield.com/privacy
- The review's AI step uses Anthropic's Claude on text only: the search terms, campaign names and keywords, plus where you sell if you type it, never spend or other figures. Anthropic never uses it for training, and keeps it for up to 30 days for safety checks only, then deletes it.
- Only upload data you're allowed to share. Search terms can contain names typed by searchers.

## Every week, for client accounts (paid)
Next week, only the new searches: the ones you've excluded or kept don't come back. A short Google Ads script, added once in your manager account or in each account in a few guided steps, collects the data automatically. The weekly plan covers up to 10 Google Ads accounts and costs $199 a month. Our first 10 customers pay $149 a month, locked for 12 months while they stay subscribed. Tax included. More than 10? Email us. Weekly reviews are opening soon, with a 14-day free trial, no card.

## License and feedback
License: MIT (see [LICENSE](LICENSE)). Issues welcome here, or hello@pipeyield.com.
