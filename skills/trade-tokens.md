---
name: trade-tokens
description: Trade/swap tokens on Base. Use when the user wants to buy, sell, swap, trade, or exchange tokens like ETH, USDC, DAI, AERO, cbETH.
---

## Instructions

1. Confirm which tokens to trade and the amount
2. Check balance: `npx agnic balance --network base --json`
3. Optionally preview: `npx agnic trade <amount> <sellToken> <buyToken> --dry-run --json`
4. Execute trade: `npx agnic trade <amount> <sellToken> <buyToken> --json`
5. Report results: tokens received, price, transaction hash

Supported tokens: USDC, ETH, WETH, cbETH, DAI, AERO

Optional flags:
- `--slippage <percent>` — max slippage percentage (default: 1.0)
- `--dry-run` — show quote without executing

## Allowed Tools
- npx agnic balance
- npx agnic trade
