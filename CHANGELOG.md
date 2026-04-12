# Changelog

## [2.0.0] - 2026-04-12

### Breaking Changes
- Removed `agnic` unified meta-skill. Use individual skills instead.
- `pay-for-service` now requires explicit user invocation (`disable-model-invocation: true`). Claude will no longer auto-invoke payments.
- Removed all deprecated root-level `.md` skill files. Only `skills/*/SKILL.md` format is supported.
- `agent-email` migrated from legacy `.md` format to `agent-email/SKILL.md`.

### Added
- **Headless authentication** via `AGNIC_TOKEN` env var and `--token` flag. AI agents, CI pipelines, and servers can now authenticate without a browser.
- `agent-email/SKILL.md` — full production-quality skill with proper frontmatter, input validation, and error handling.
- `context: fork` on `pay-for-service` and `ai-gateway` for execution isolation.
- Progressive disclosure: `reference/` directories for `ai-gateway` and `pay-for-service` with extracted reference material.

### Changed
- All skills: standardized authentication section with dual-mode support (browser OAuth + headless token).
- All skills: optimized descriptions for AI agent discovery with front-loaded trigger keywords.
- All skills: scoped `allowed-tools` patterns (no wildcards).
- Rebranded "AgnicPay" references to "Agnic" throughout.
- Install command uses `agnicpay/agnic-wallet-skills` (matching GitHub org).
- Updated npm keywords: added `claude-code`, `cline`, `cursor`, `windsurf`, `erc-8004`, `headless-auth`; removed `agnicpay`, `vercel-ai`.

### Fixed
- **Security**: `pay-for-service` could be auto-invoked by Claude, spending real USDC without explicit user consent.
- **Headless auth**: AI agents in non-interactive environments now have a working authentication path.
- `agent-email` had no proper `SKILL.md` — only a deprecated `.md` file with no `allowed-tools` or frontmatter fields.
