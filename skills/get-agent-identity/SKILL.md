---
name: get-agent-identity
description: Check your agent's on-chain ERC-8004 identity and trust score
user-invocable: true
disable-model-invocation: false
allowed-tools: ["Bash(npx agnic@latest *)"]
---

# Get Agent Identity

Check the user's on-chain ERC-8004 agent identity, trust score, and KYA credentials.

## Steps

1. Verify authentication:
   ```bash
   npx agnic@latest status --json
   ```

2. Check agent identity:
   ```bash
   npx agnic@latest agent-identity --json
   ```
   Note: If `agent-identity` is not available, use the API directly:
   ```bash
   npx agnic@latest x402 pay "https://api.agnic.ai/api/agent/identity" --method GET --json
   ```

## What is ERC-8004?

ERC-8004 ("Trustless Agents") is an Ethereum standard that gives AI agents:
- **On-chain identity** — An NFT representing the agent
- **Reputation score** — Trust score based on transaction history
- **Verifiable credentials** — KYA (Know Your Agent) credentials for identity verification

## Expected Output

```json
{
  "agentId": 373,
  "ownerAddress": "0x046906b3...",
  "status": "active",
  "registeredAt": "2024-12-15T...",
  "trustScore": 85,
  "categories": ["payment", "general"]
}
```

## Error Handling

- If the user doesn't have an agent identity, they can create one via the AgnicPay dashboard
- Agent identity is automatically created during OAuth sign-up
