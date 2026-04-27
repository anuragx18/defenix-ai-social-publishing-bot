# Defenix AI Social Publishing Bot

![Defenix AI Social Publishing Bot](assets/defenix-social-publishing-overview-v2.png)

AI-powered, human-approved social publishing workflow built with **n8n**, **Telegram**, **LinkedIn Posts API**, and **Facebook Graph API**.

This project turns Telegram into a lightweight content command center: generate AI drafts, review them, regenerate when needed, and publish approved posts directly to LinkedIn or Facebook.

---

## Why this project exists

Social media publishing often becomes a messy manual process:

- generating content in one tool
- copying it into another platform
- editing it again
- switching between LinkedIn and Facebook
- manually tracking what was approved or posted

This workflow solves that by creating a simple approval-based publishing system where AI helps with drafting, but the user stays in control before anything goes live.

---

## Demo

### Telegram approval flow

![Telegram Approval Flow](assets/telegram-approval-flow.png)

The user starts the bot, chooses a platform, selects a content type, reviews the generated draft, and then approves, regenerates, or cancels.

---

## System Architecture

![System Architecture](assets/architecture-v2.png)

The project is split into two connected workflows:

### 1. Telegram Intake & Publishing Workflow

This is the main workflow. It handles the user-facing Telegram experience and publishing logic.

It manages:

- Telegram trigger events
- callback button routing
- platform selection
- content type selection
- draft preview
- approve / regenerate / cancel actions
- LinkedIn publishing
- Facebook Page publishing
- post-publish confirmation messages

### 2. AI Draft Generator Workflow

This workflow generates the actual post draft.

It handles:

- fetching approved Defenix source content
- extracting and cleaning webpage text
- preparing the AI prompt
- generating a platform-specific post
- returning the draft to the Telegram workflow

---

## Workflow Screenshots

### Main n8n workflow

![Main n8n Workflow](assets/main-n8n-workflow.png)

This workflow manages the complete user journey from Telegram interaction to final publishing.

### AI draft generator workflow

![AI Draft Generator Workflow](assets/ai-draft-generator-workflow.png)

This workflow generates grounded post drafts from approved source content.

---

## Publishing Proof

![Publishing Proof](assets/publishing-proof.png)

Approved posts are published directly to the selected platform using official APIs.

---

## What it does

- Starts from Telegram
- Lets the user choose a platform
- Lets the user choose a content type
- Calls an AI draft generation workflow
- Sends the generated draft back to Telegram
- Lets the user approve, regenerate, or cancel
- Publishes approved content to LinkedIn or Facebook Page
- Sends a success confirmation after publishing

---

## Supported platforms

| Platform | Integration |
|---|---|
| LinkedIn | LinkedIn Posts API |
| Facebook Page | Facebook Graph API |

---

## Core features

- Telegram-first approval flow
- Human-in-the-loop publishing
- AI-generated platform-specific drafts
- Regenerate support for improved drafts
- Cancel option before publishing
- Direct LinkedIn publishing through HTTP Request node
- Direct Facebook Page publishing through Graph API
- Callback-driven workflow logic in n8n
- Platform-aware routing
- Publishing confirmation messages
- Modular two-workflow design

---

## Tech stack

| Tool | Purpose |
|---|---|
| n8n | Workflow orchestration |
| Telegram Bot API | Chat interface and approval UI |
| AI Draft Generator | Content generation |
| LinkedIn Posts API | LinkedIn publishing |
| Facebook Graph API | Facebook Page publishing |
| OAuth2 | Authentication |
| HTTP Request nodes | Direct API calls |

---

## High-level user flow

```text
/start
  ↓
Choose platform
  ↓
Choose content type
  ↓
Generate AI draft
  ↓
Review in Telegram
  ↓
Approve / Regenerate / Cancel
  ↓
Publish to selected platform
  ↓
Send success confirmation
