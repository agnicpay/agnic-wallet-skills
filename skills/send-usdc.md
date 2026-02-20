---
name: send-usdc
description: Send USDC to a wallet address. Use when the user wants to send, transfer, or pay someone USDC.
---

## Instructions

1. Confirm the recipient address and amount with the user
2. Check balance first: `npx agnic balance --network base --json`
3. If sufficient funds, execute: `npx agnic send <amount> <address> --json`
4. Report the transaction hash and explorer link

Optional flags:
- `--network <network>` — default is "base"
- `--memo <text>` — attach a memo to the transaction

## Allowed Tools
- npx agnic balance
- npx agnic send
