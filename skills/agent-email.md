---
name: agent-email
description: Manage your agent's email address. Use when the user asks about agent email, sending email, checking inbox, or email setup.
---

## Instructions

1. Check if agent has an email: `npx agnic@latest email address --json`
2. If no email exists, create one: `npx agnic@latest email setup --json`
3. For inbox: `npx agnic@latest email inbox --limit 20 --json`
4. To send: `npx agnic@latest email send --to <address> --subject "<subject>" --body "<body>"`
5. To reply: `npx agnic@latest email reply --message-id <id> --body "<reply>"`

Each agent gets a unique address like `agent-123@agnic.ai`. Emails are stored with 30-day retention.

## Allowed Tools
- npx agnic@latest email address
- npx agnic@latest email setup
- npx agnic@latest email inbox
- npx agnic@latest email send
- npx agnic@latest email reply
