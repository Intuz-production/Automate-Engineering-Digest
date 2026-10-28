*Intuz — Your automation partner, one workflow at a time.*

<p align="center">
  <picture>
    <img alt="Banner Image" src="https://github.com/user-attachments/assets/210f97fc-0fce-404a-b647-7dfe1302cd37" />
  </picture>
</p>

[Intuz](https://www.intuz.com) helps organizations orchestrate AI, automation, and enterprise systems through scalable workflows. Our repository showcases proven implementations across healthcare, operations, customer support, document processing, sales, and back-office functions, enabling teams to accelerate automation initiatives without starting from scratch.

[N8N Creator](https://n8n.io/creators/intuz/) · [Agentic AI Solution Development](https://www.intuz.com/ai-agents-for-business-automation/) · [AI Consulting Company](https://www.intuz.com/company/) · [For Custom Workflow Automation](https://www.intuz.com/get-started/)

# Send engineering daily digest to Slack with Jira, GitHub, OpenAI, and Google Sheets

## Quick overview

This workflow runs every weekday at 9 AM to collect the last 24 hours of Jira issue updates and GitHub pull request activity, uses OpenAI to summarize the results, posts a Block Kit digest to Slack, and optionally logs the digest outcome to Google Sheets.

## How it works

1. Runs on a weekday 9:00 AM schedule trigger.
2. Pulls Jira issues updated in the last 24 hours and finds “In Progress” Jira issues that have not been updated for the configured stale-day threshold.
3. Splits the configured GitHub repository list and, for each repo, fetches recent pull requests and searches for open pull requests with no reviews.
4. Normalizes and merges the Jira and GitHub results into a single digest payload.
5. Sends the digest payload to OpenAI Chat Completions to generate a strict-JSON summary (what moved, what shipped, what’s blocked, needs review, and sprint health).
6. Builds a Slack Block Kit message with ticket/PR links and optional @mentions based on a Jira/GitHub-to-Slack user map, then posts it to the configured Slack channel.
7. If Google Sheets logging is enabled, appends a row with the posting result details to the configured spreadsheet tab.

## Setup

1. Add credentials for Jira Software Cloud, GitHub, OpenAI, and Slack (and Google Sheets if you enable logging).
2. Update the Config values for your Jira base URL and project key, GitHub repositories list, stale thresholds, Slack channel, and the OpenAI model.
3. Invite the Slack app/bot to the target channel and ensure it has permission to post messages.
4. If sheet logging is enabled, set the Google Sheets document and tab to use and ensure the sheet has columns that match the appended fields (ok, channel, message, message_timestamp).
5. (Optional) Populate the user map in Config with Jira account IDs and GitHub logins mapped to Slack user IDs to enable @mentions in the digest.

## Requirements

- n8n credentials: Jira Cloud, GitHub, OpenAI, Slack; Google Sheets only if logging is on
- Access to the Jira project (e.g. PTN) and listed GitHub repos
- A Slack channel the bot can post in
- Fine-grained GitHub token needs repo + pull-request read (Search for review:none)

## FAQ

**What data sources does this workflow integrate?**  
It integrates Jira issue updates, GitHub pull request activity, OpenAI for summarization, Slack for posting, and optionally Google Sheets for logging.

**When does the workflow run and what does it do?**  
It runs every weekday at 9 AM, collects recent Jira and GitHub updates, summarizes them using OpenAI, posts a digest to Slack, and optionally logs results to Google Sheets.

**What credentials are required to set up this workflow?**  
Credentials for Jira Software Cloud, GitHub, OpenAI, Slack, and optionally Google Sheets if logging is enabled.

## Related n8n templates from Intuz

- [Color Picker for Android](https://github.com/Intuz-production/ColorPicker-Android)
- [Automatically generate LinkedIn post text with Google Gemini, a matching image with DALL-E, and SEO-optimized hashtags — a complete post draft, ready to review.](https://github.com/Intuz-production/AI-Powered-LinkedIn-Post-Image-Generator)
- [aws devops scripts](https://github.com/Intuz-production/aws-devops-scripts)

[See all of Intuz's free n8n templates](https://www.intuz.com/n8n-workflow-automation-templates/)

## Connect with us

Intuz is a USA-based AI & workflow automation company with 16+ years of experience building custom AI-enabled workflow automations for SMBs and Enterprises, specializing in agentic AI, LLM integrations, and CRM/ERP sync across Healthcare, FinTech, eCommerce, Manufacturing, and Real Estate.

* **Website:** [https://www.intuz.com](https://www.intuz.com)
* **Email:** [getstarted@intuz.com](mailto:getstarted@intuz.com)
* **LinkedIn:** https://www.linkedin.com/company/intuz/
* **Get Started:** https://n8n.partnerlinks.io/intuz

## For Custom Workflow Automation

[Click here - Get Started](https://www.intuz.com/get-started/)
