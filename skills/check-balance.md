---
name: check-balance
description: Check USDC balance across networks. Use when the user asks about their balance, funds, or how much they have.
---

## Instructions

1. Run `npx agnic balance --json` to get balances across all networks
2. If user asks about a specific network, use `npx agnic balance --network <network> --json`
3. Present the balance in a clear format with network and amount

Supported networks: base, solana, base-sepolia, solana-devnet

## Allowed Tools
- npx agnic balance
