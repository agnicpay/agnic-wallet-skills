---
name: authenticate-wallet
description: Sign in to AgnicPay wallet via browser-based OAuth
user-invocable: true
disable-model-invocation: false
allowed-tools: ["Bash(npx agnic@latest *)"]
---

# Authenticate Wallet

Authenticate the user with their AgnicPay wallet using browser-based OAuth login.

## Steps

1. Run the login command:
   ```bash
   npx agnic@latest auth login
   ```
   This opens the user's browser to AgnicPay where they sign in and set spending limits.

2. Wait for the browser flow to complete. The CLI will show "Authenticated!" when done.

3. Verify authentication:
   ```bash
   npx agnic@latest status --json
   ```

## Expected Output

```json
{
  "authenticated": true,
  "userId": "did:privy:...",
  "email": "user@example.com",
  "walletAddress": "0x...",
  "tokenExpiry": "2026-05-22T..."
}
```

## Error Handling

- If the user cancels the browser flow, the CLI will show "Authentication failed".
- If the browser doesn't open, the CLI prints a URL the user can copy manually.
- If already authenticated, `agnic status` will confirm without re-login.

## Logout

To remove stored credentials:
```bash
npx agnic@latest auth logout
```
