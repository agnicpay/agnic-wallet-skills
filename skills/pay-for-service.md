---
name: pay-for-service
description: Make a paid request to an x402-enabled API. Use when the user wants to call, use, or pay for an API service.
---

## Instructions

1. Confirm the API URL and HTTP method with the user
2. Check balance: `npx agnic balance --network base --json`
3. Execute: `npx agnic x402 pay <url> --method <METHOD> --json`
4. If the request needs a body, add `--body '{"key":"value"}'`
5. Present the API response and cost to the user

## Allowed Tools
- npx agnic balance
- npx agnic x402 pay
