# AgnicPay Agentic Wallet Skills

Agent Skills for crypto wallet operations. These skills enable AI agents to authenticate, check balances, send USDC, trade tokens, make x402 payments, and verify on-chain identity using the `agnic` CLI.

## Available Skills

| Skill | Description |
|-------|-------------|
| **authenticate-wallet** | Sign in to the wallet via browser OAuth |
| **check-balance** | Check USDC balance across networks (Base, Solana) |
| **send-usdc** | Send USDC to Ethereum wallet addresses |
| **trade-tokens** | Swap/trade tokens on Base (USDC, ETH, WETH, cbETH, DAI, AERO) |
| **search-for-service** | Search for paid API services via x402 |
| **pay-for-service** | Make paid API requests via x402 |
| **fund-wallet** | Get instructions for adding funds to the wallet |
| **get-agent-identity** | Check on-chain ERC-8004 identity and trust score |

## Installation

Install with Vercel's [Skills CLI](https://github.com/vercel/skills):

```bash
npx skills add agnicpay/agnic-wallet-skills
```

## Usage

Skills are automatically available once installed. The agent will use them when relevant tasks are detected.

Examples:

- `Sign in to my wallet`
- `Check my balance`
- `Send 10 USDC to 0x742d35Cc6634C0532925a3b844Bc9e7595f0bEb7`
- `Swap 5 USDC for ETH`
- `Find a sentiment analysis API`
- `Pay for https://api.example.com/data`
- `What's my agent identity?`

## Contributing

To add a new skill:

1. Create a folder in `./skills/` with a lowercase, hyphenated name
2. Add a `SKILL.md` file with YAML frontmatter and instructions
3. See the [Agent Skills specification](https://github.com/vercel/skills) for the complete format

### Updating the agnic version

All skills pin `agnic@latest` via `npx agnic@latest`. When testing against a specific version:

```bash
# Install a specific version
npm install -g agnic@2.0.0
```

## Documentation

Full docs at [docs.agnic.ai/docs/agnicpay-features/skills](https://docs.agnic.ai/docs/agnicpay-features/skills)

## License

MIT
