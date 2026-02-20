---
name: authenticate-wallet
description: Sign in to AgnicPay wallet. Use when the user wants to log in, authenticate, or when any command fails with auth errors.
---

## Instructions

1. Run `npx agnic status` to check current auth state
2. If not authenticated, ask user for their email
3. Run `npx agnic auth login <email>` — sends OTP code to their email
4. Ask user for the 6-digit code from their email
5. Run `npx agnic auth verify <flowId> <otp>`
6. Confirm with `npx agnic status`

## Allowed Tools
- npx agnic status
- npx agnic auth login
- npx agnic auth verify
