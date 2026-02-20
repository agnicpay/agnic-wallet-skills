---
name: fund-wallet
description: Get instructions for funding your AgnicPay wallet. Use when the user needs to add funds, deposit, or top up.
---

## Instructions

1. Check current balance: `npx agnic balance --json`
2. Show the wallet address: `npx agnic address`
3. Provide funding instructions:
   - Visit https://pay.agnic.ai to fund via the dashboard
   - Or send USDC directly to the displayed wallet address on Base or Solana
4. After funding, verify with `npx agnic balance --json`

## Allowed Tools
- npx agnic balance
- npx agnic address
