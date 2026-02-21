# @agnic/wallet-skills

Pre-built [Vercel AI SDK](https://sdk.vercel.ai/) skills for the [AgnicPay](https://pay.agnic.ai) wallet. Give any AI assistant the ability to check balances, send payments, trade tokens, and call x402-enabled APIs.

## Installation

```bash
npx skills add agnicpay/agnic-wallet-skills
```

## Prerequisites

The agent must be authenticated with the `agnic` CLI:

```bash
npx agnic@latest auth login
# Opens browser → sign in → set spending limits → done
```

## Available Skills

| Skill | Description |
|-------|-------------|
| **authenticate-wallet** | Browser-based OAuth login |
| **check-balance** | USDC balance across networks |
| **send-usdc** | Send USDC to a wallet address |
| **trade-tokens** | Swap tokens on Base (USDC, ETH, etc.) |
| **search-for-service** | Discover x402-enabled APIs |
| **pay-for-service** | Make x402 payment requests |
| **fund-wallet** | Instructions for funding your wallet |
| **get-agent-identity** | ERC-8004 on-chain identity and trust score |

## How It Works

Each skill is a markdown file (`SKILL.md`) that instructs the AI assistant on how to use the `agnic` CLI. When a user's request matches a skill, the AI follows the instructions to execute the right commands.

## Documentation

Full docs at [docs.agnic.ai/docs/agnicpay-features/skills](https://docs.agnic.ai/docs/agnicpay-features/skills)
