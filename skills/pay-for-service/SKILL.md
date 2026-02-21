---
name: pay-for-service
description: Make paid requests to x402-enabled APIs
user-invocable: true
disable-model-invocation: false
allowed-tools: ["Bash(npx agnic@latest *)"]
---

# Pay for Service

Make a paid x402 request to an API endpoint. AgnicPay handles the payment automatically.

## Steps

1. Verify authentication:
   ```bash
   npx agnic@latest status --json
   ```

2. Check balance to ensure sufficient funds:
   ```bash
   npx agnic@latest balance --network base --json
   ```

3. Make the x402 payment request:
   ```bash
   npx agnic@latest x402 pay "<url>" --json
   ```

4. For POST requests with a body:
   ```bash
   npx agnic@latest x402 pay "<url>" --method POST --body '{"key": "value"}' --json
   ```

## Parameters

- `<url>` — Full URL of the x402-enabled API endpoint
- `--method` — HTTP method (default: GET)
- `--body` — Request body as JSON string (for POST/PUT)

## Example

```bash
npx agnic@latest x402 pay "https://api.example.com/analysis" \
  --method POST \
  --body '{"query": "latest market data"}' \
  --json
```

## Expected Output

```json
{
  "status": 200,
  "cost": "0.001",
  "network": "base",
  "transactionHash": "0xabc123...",
  "data": { "result": "..." }
}
```

## Error Handling

- If not authenticated: prompt user to run `npx agnic@latest auth login`
- If balance is insufficient, inform the user and suggest funding
- If the API returns an error, show the status code and response body
- The `--body` flag must be valid JSON; if invalid, the CLI will report the parse error
