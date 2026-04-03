---
name: ai-gateway
description: Access 340+ AI models through the Agnic AI Gateway. Use when the user wants to chat with AI, generate images, or list available models.
---

## Instructions

1. Check auth: `npx agnic@latest status --json`
2. List models: `npx agnic@latest ai models --json`
3. Filter by provider: `npx agnic@latest ai models --provider openai --json`
4. Chat with a model: `npx agnic@latest ai chat --model <provider/model> --prompt "<text>" --json`
5. Chat with system prompt: `npx agnic@latest ai chat --model <id> --system "<system>" --prompt "<text>" --json`
6. Generate image: `npx agnic@latest ai image --prompt "<text>" --output image.png`
7. Generate image with aspect ratio: `npx agnic@latest ai image --prompt "<text>" --aspect-ratio 16:9 --output wide.png`

Model format: `provider/model-name` (e.g., `openai/gpt-4o`, `anthropic/claude-3.5-sonnet`, `meta-llama/llama-3.3-70b`).
Free models: meta-llama, google/gemma, mistralai.

## Allowed Tools
- npx agnic@latest ai models
- npx agnic@latest ai chat
- npx agnic@latest ai image
