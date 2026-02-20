# @agnic/wallet-skills

Pre-built AI agent skills for [AgnicPay](https://pay.agnic.ai) — x402 payments, token trading, and identity.

Compatible with the [Vercel AI SDK](https://sdk.vercel.ai) skills system.

## Install

```bash
npx skills add @agnic/wallet-skills
```

## Available Skills

| Skill | Trigger Phrases | What It Does |
|-------|-----------------|--------------|
| **authenticate-wallet** | "log in", "sign in" | Email OTP login flow |
| **check-balance** | "check balance", "how much do I have" | USDC balance across networks |
| **send-usdc** | "send", "transfer", "pay someone" | Send USDC to a wallet |
| **trade-tokens** | "trade", "swap", "buy ETH" | Swap tokens on Base |
| **search-for-service** | "find an API", "search for" | Discover x402-enabled APIs |
| **pay-for-service** | "call this API", "use this service" | Make x402 payment requests |
| **fund-wallet** | "add funds", "deposit" | Instructions for funding |
| **get-agent-identity** | "agent identity", "trust score" | ERC-8004 identity & credentials |

## Prerequisites

Skills use the `agnic` CLI under the hood:

```bash
npm install -g agnic
agnic auth login you@example.com
```

## How It Works

Each skill is a markdown instruction file that teaches AI assistants how to complete wallet tasks using CLI commands. When a user's request matches a skill, the AI follows the instructions automatically.

**Example:** User says "swap 10 USDC for ETH" → `trade-tokens` skill runs:
```bash
agnic balance --network base --json
agnic trade 10 usdc eth --json
```

## Unique: Agent Identity

The `get-agent-identity` skill has no equivalent in other wallet tools. It lets AI agents check their on-chain [ERC-8004](https://eips.ethereum.org/EIPS/eip-8004) identity, trust score, and KYA credentials.

## Documentation

Full docs at [docs.agnic.ai/docs/agnicpay-features/skills](https://docs.agnic.ai/docs/agnicpay-features/skills)

## License

MIT
