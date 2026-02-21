---
name: search-for-service
description: Search for x402-enabled APIs and services
user-invocable: true
disable-model-invocation: false
allowed-tools: ["Bash(npx agnic@latest *)"]
---

# Search for Service

Discover x402-enabled APIs that can be paid for using AgnicPay.

## Steps

1. Search for APIs matching the user's query:
   ```bash
   npx agnic@latest x402 search "<query>" --json
   ```

2. Optionally filter by category:
   ```bash
   npx agnic@latest x402 search "<query>" --category AI --json
   ```

3. Present the results to the user with names, descriptions, prices, and URLs.

## Parameters

- `<query>` — Search term (e.g., "sentiment analysis", "weather data")
- `--category` — Filter by category: AI, Crypto, Data, Trading, Finance, Weather
- `--limit <n>` — Max results (default: 10)

## Example

```bash
npx agnic@latest x402 search "sentiment analysis" --category AI --json
```

## Expected Output

```json
{
  "apis": [
    {
      "name": "Sentiment Pro",
      "description": "Real-time sentiment analysis",
      "price": "0.001",
      "url": "https://api.example.com/sentiment"
    }
  ]
}
```

## Error Handling

- If no results found, suggest broadening the search or trying different keywords
- Authentication is NOT required for search (it's a public endpoint)
