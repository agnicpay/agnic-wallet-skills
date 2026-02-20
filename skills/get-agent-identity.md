---
name: get-agent-identity
description: Check agent's on-chain identity, trust score, and KYA credentials. Use when the user asks about agent identity, trust, reputation, or credentials.
---

## Instructions

1. Check auth status: `npx agnic status --json`
2. If authenticated, show the agent's wallet address and identity info
3. Explain what ERC-8004 agent identity provides:
   - On-chain identity (NFT-based)
   - Trust score and reputation
   - KYA (Know Your Agent) credentials for identity verification
   - Delegation credentials for authorized actions
4. Direct user to https://pay.agnic.ai for full identity management

## Allowed Tools
- npx agnic status
- npx agnic address
