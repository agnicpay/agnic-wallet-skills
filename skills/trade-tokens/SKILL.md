---
name: trade-tokens
description: Trade/swap tokens on Base (USDC, ETH, WETH, cbETH, DAI, AERO)
user-invocable: true
disable-model-invocation: false
allowed-tools: ["Bash(npx agnic@latest *)"]
---

# Trade Tokens

Swap tokens on Base mainnet using AgnicPay's DEX integration.

## Steps

1. Verify authentication:
   ```bash
   npx agnic@latest status --json
   ```

2. Check balance to ensure sufficient funds:
   ```bash
   npx agnic@latest balance --network base --json
   ```

3. Preview the trade (optional but recommended):
   ```bash
   npx agnic@latest trade <amount> <sell_token> <buy_token> --dry-run --json
   ```

4. Confirm with the user: amount, tokens, and estimated output.

5. Execute the trade:
   ```bash
   npx agnic@latest trade <amount> <sell_token> <buy_token> --json
   ```

## Supported Tokens

USDC, ETH, WETH, cbETH, DAI, AERO (case-insensitive)

## Parameters

- `<amount>` — Amount of the sell token
- `<sell_token>` — Token to sell (e.g., `usdc`)
- `<buy_token>` — Token to buy (e.g., `eth`)
- `--slippage <percent>` — Max slippage (default: `1.0`)
- `--dry-run` — Show quote without executing

## Example

```bash
# Preview
npx agnic@latest trade 10 usdc eth --dry-run --json

# Execute
npx agnic@latest trade 10 usdc eth --json
```

## Expected Output

```json
{
  "success": true,
  "sellAmount": "10",
  "sellToken": "USDC",
  "buyAmount": "0.00396",
  "buyToken": "ETH",
  "price": "2525.25",
  "transactionHash": "0xabc123...",
  "explorerUrl": "https://basescan.org/tx/0xabc123..."
}
```

## Error Handling

- Always preview with `--dry-run` first to show the user expected output
- If slippage is too high, suggest a lower amount or higher slippage tolerance
- Trading is only available on Base mainnet
