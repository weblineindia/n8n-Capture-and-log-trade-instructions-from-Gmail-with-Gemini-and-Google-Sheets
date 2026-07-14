## Quick Overview

This workflow watches Gmail for emails with the subject **"Trade Instruction"**, uses Google Gemini to extract structured trade fields, validates the result, logs valid trades to Google Sheets, replies to the sender with a confirmation, and alerts an ops user in Slack on success or failure.

## How it works

1. Triggers every minute when a new Gmail message arrives matching the search filter `subject:"Trade Instruction"`.
2. Captures the email snippet and sender information and sends the email text to Google Gemini to extract asset, quantity, price, and client as JSON.
3. Enforces a structured JSON schema for the extracted trade details.
4. Validates that the extracted asset is present and the quantity is greater than zero.
5. Appends valid trades to a Google Sheets master ledger with a timestamp, replies to the original Gmail thread with a confirmation, and sends a Slack success notification.
6. Sends a critical Slack alert to the ops user when extraction or validation fails so the trade can be handled manually.

## Requirements to Use This Workflow

- [**n8n account** (Self-hosted or Cloud)](https://n8n.partnerlinks.io/om1efg2qgvwi)
- **Gmail** account with OAuth2 credentials
- **Google Sheets** account with read/write access
- **Google Gemini API** credentials for AI-powered trade extraction
- **Slack** workspace with OAuth credentials for notifications
- Basic understanding of **n8n workflows** and Google Workspace integrations

## Setup

1. Connect credentials for Gmail, Google Sheets, Slack, and Google Gemini (PaLM/Gemini API).
2. Update the Gmail trigger query (or align your inbound email subject/filters) so trade instruction emails match `subject:"Trade Instruction"`.
3. Select the target Google Sheets document and sheet, and ensure it has columns for **Asset**, **Quantity**, **Price**, **Client**, and **Timestamp**.
4. Configure the Slack connection and set the target user/channel for both success and failure notifications.
5. Confirm the Gmail reply action is permitted for the mailbox and that replies should go back to the original sender/thread.

## Need Help?

If you need assistance setting up this workflow, customizing it for your trading operations, or building advanced AI-powered automation, our team at **WeblineIndia** is here to help.

We can assist you with:

- Workflow setup and customization
- Google Gemini integration and prompt optimization
- Gmail, Google Sheets, and Slack integrations
- AI-powered trade processing and validation
- Enterprise workflow automation
- Custom n8n workflow development
- Process automation and system integrations

**Useful Resources:**

- **Contact Us:** https://www.weblineindia.com/contact-us.html
- **n8n Automation Services:** https://www.weblineindia.com/n8n-automation/
- **Process Automation Solutions:** https://www.weblineindia.com/process-automation-solutions.html
- **Hire n8n Developers:** https://www.weblineindia.com/hire-n8n-developers/

Our experts can help you build, customize, and scale intelligent automation workflows tailored to your business requirements.
