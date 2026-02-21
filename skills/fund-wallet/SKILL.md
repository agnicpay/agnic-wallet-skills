---
name: fund-wallet
description: Get instructions for funding your AgnicPay wallet
user-invocable: true
disable-model-invocation: false
allowed-tools: ["Bash(npx agnic@latest *)"]
---

# Fund Wallet

Provide instructions for adding funds to the user's AgnicPay wallet.

## Steps

1. Check if the user is authenticated:
   ```bash
   npx agnic@latest status --json
   ```

2. Show the user's wallet address:
   ```bash
   npx agnic@latest address --json
   ```

3. Explain funding options:

   **Option 1: AgnicPay Dashboard**
   - Go to [pay.agnic.ai](https://pay.agnic.ai)
   - Navigate to your dashboard
   - Use the "Add Funds" feature to deposit USDC

   **Option 2: Direct Transfer**
   - Send USDC to your wallet address on Base network
   - The address is shown by `agnic address`
   - Use any wallet (MetaMask, Coinbase, etc.) to send USDC on Base

4. After funding, verify the balance:
   ```bash
   npx agnic@latest balance --json
   ```

## Important Notes

- AgnicPay wallets use USDC (not ETH) for payments and trading
- Base network is the primary chain
- Minimum recommended balance: $1.00 USDC for testing
