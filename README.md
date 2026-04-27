# Defenix Content Bot

AI-powered content publishing workflow built with **n8n**, **Telegram**, **LinkedIn**, and **Facebook**.

This bot lets a user generate a post draft, review it inside Telegram, regenerate if needed, and publish it directly to LinkedIn or Facebook after approval.

## What it does

- Starts from Telegram
- Lets the user choose a platform
- Lets the user choose a content type
- Calls an AI draft generation workflow
- Sends the draft back for review
- Supports:
  - Publish
  - Regenerate
  - Cancel
- Publishes approved content to:
  - LinkedIn
  - Facebook Page

## Workflow overview

1. User sends `/start` in Telegram
2. Bot asks for platform
3. Bot asks for post type
4. AI generates a grounded draft
5. User reviews the draft in Telegram
6. User can:
   - publish it
   - regenerate it
   - cancel it
7. Approved content is posted to the selected platform

## Platforms supported

- LinkedIn
- Facebook

## Main features

- Telegram-first approval flow
- Human-in-the-loop publishing
- Regenerate support for better drafts
- Direct LinkedIn posting via API
- Direct Facebook Page posting via Graph API
- Callback-driven workflow logic in n8n
- Platform-aware publishing path selection

## Tech stack

- **n8n**
- **Telegram Bot API**
- **LinkedIn Posts API**
- **Facebook Graph API**
- **OAuth2**
- AI draft generation through a connected workflow

## Node flow

Main workflow includes logic for:

- Telegram trigger
- Callback detection
- Platform selection
- Post type selection
- Draft generation call
- Draft preview
- Approve / regenerate / cancel handling
- LinkedIn publishing
- Facebook publishing
- Published confirmation messages

## Example user flow

- Choose platform: LinkedIn or Facebook
- Choose content type: Educational / Informational / Security / Awareness
- Review generated draft
- Click:
  - Approve
  - Regenerate
  - Cancel

## Why this project matters

This project turns social publishing into a structured approval workflow instead of a manual copy-paste task.

It is useful for teams that want:
- faster content operations
- approval before publishing
- platform-based routing
- cleaner internal publishing workflows
- AI assistance without losing human control

## Current improvements implemented

- LinkedIn posting fixed through HTTP Request node
- Facebook posting fixed through Graph API and Page access token flow
- Platform context preserved across regenerate/approve actions
- Cleaner Telegram UX with better callback handling
- Success messages after publishing

## Future improvements

- Long-lived Facebook token automation
- Better Telegram UI and compact preview cards
- Full draft / preview toggle
- Post history and audit trail
- Multi-user support
- More platforms
- Scheduling support
- Retry and failure notifications
- Better content variation to avoid duplicate post issues on LinkedIn

## Setup notes

To run this workflow, you need:

- A Telegram bot
- n8n workflow environment
- LinkedIn OAuth2 app
- Facebook app
- Facebook Page access token
- Proper API permissions for publishing

## Status

Working MVP.

The workflow currently supports end-to-end generation, approval, regeneration, and publishing to LinkedIn and Facebook.

---
Built as a practical AI content operations workflow for Defenix.
