# Agnic Wallet Skills

Give your AI agent a crypto wallet, payments, email, and on-chain identity.

These skills enable AI agents to authenticate, check balances, make x402 payments, access 340+ AI models, generate images, manage agent email, and verify on-chain identity using the `agnic` CLI.

## Available Skills

| Skill | Description | Side Effects |
|-------|-------------|--------------|
| **authenticate-wallet** | Sign in via browser OAuth or headless API token | None |
| **check-balance** | Check USDC balance across networks (Base, Solana) | None |
| **search-for-service** | Search for paid API services via x402 bazaar | None |
| **pay-for-service** | Make paid API requests via x402 (USDC) | Spends USDC |
| **fund-wallet** | Get instructions for adding funds to the wallet | None |
| **get-agent-identity** | Check on-chain ERC-8004 identity and trust score | None |
| **agent-email** | Send, receive, and manage agent email | Sends email |
| **ai-gateway** | Access 340+ AI models -- chat and image generation | Spends USDC |

## Installation

Install with the [Skills CLI](https://github.com/vercel/skills). Compatible with any AI coding tool that supports the SKILL.md specification — Claude Code, Cline, Cursor, Windsurf, and more.

```bash
npx skills add agnicpay/agnic-wallet-skills
```

## Authentication

### Interactive (browser available)

```bash
npx agnic@latest auth login
```

Opens a browser for OAuth sign-in. Best for local development.

### Headless (CI, servers, AI agents)

Generate an API token at [app.agnic.ai](https://app.agnic.ai) > Settings > API Tokens, then:

```bash
export AGNIC_TOKEN=<your-api-token>
npx agnic@latest status --json
```

All commands in the session will authenticate automatically. No browser required.

## Usage

Skills are automatically available once installed. The agent uses them when relevant tasks are detected.

Examples:

- `Sign in to my wallet`
- `Check my balance`
- `Find a sentiment analysis API`
- `Pay for https://api.example.com/data`
- `What's my agent identity?`
- `List available AI models`
- `Ask GPT-4o to explain quantum computing`
- `Generate an image of a sunset over mountains`
- `Check my agent email inbox`
- `Send an email to user@example.com`

## Performance

For faster CLI invocations (avoids downloading on every call):

```bash
npm install -g agnic
```

Then all `npx agnic@latest` commands run instantly from the global install.

## Contributing

To add a new skill:

1. Create a folder in `./skills/` with a lowercase, hyphenated name
2. Add a `SKILL.md` file with YAML frontmatter and instructions
3. Optionally add a `reference/` directory for detailed documentation
4. See the [Skills specification](https://github.com/vercel/skills) for the complete format

## Documentation

Full docs at [docs.agnic.ai](https://docs.agnic.ai)

## License

MIT
