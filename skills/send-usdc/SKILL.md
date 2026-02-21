---
name: send-usdc
description: Send USDC to a wallet address on Base or Solana
user-invocable: true
disable-model-invocation: false
allowed-tools: ["Bash(npx agnic@latest *)"]
---

# Send USDC

Send USDC from the user's wallet to a recipient address.

## Steps

1. Verify authentication:
   ```bash
   npx agnic@latest status --json
   ```

2. Check balance to ensure sufficient funds:
   ```bash
   npx agnic@latest balance --network base --json
   ```

3. Confirm with the user: the amount, recipient address, and network.

4. Send USDC:
   ```bash
   npx agnic@latest send <amount> <recipient_address> --network base --json
   ```

## Parameters

- `<amount>` — Amount in USDC (e.g., `5.00`)
- `<recipient_address>` — Destination wallet address (0x... for EVM)
- `--network` — Network to send on (default: `base`)
- `--memo` — Optional transaction memo

## Example

```bash
npx agnic@latest send 5.00 0x742d35Cc6634C0532925a3b844Bc9e7595f0bEb7 --network base --json
```

## Expected Output

```json
{
  "amount": "5.00",
  "to": "0x742d35Cc...",
  "network": "base",
  "transactionHash": "0xabc123...",
  "explorerUrl": "https://basescan.org/tx/0xabc123..."
}
```

## Error Handling

- If balance is insufficient, inform the user and suggest funding their wallet
- Always confirm the recipient address and amount before sending
- If the transaction fails, show the error message from the API
