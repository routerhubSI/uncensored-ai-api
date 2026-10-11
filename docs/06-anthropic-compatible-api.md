# Anthropic-Compatible API

RouterHub exposes an Anthropic-compatible Messages API for clients that expect the Anthropic request shape. This is the path used by Claude Code and by applications built on the Anthropic SDK.

## Configuration

```bash
export ROUTERHUB_API_KEY="sk-..."
export ROUTERHUB_BASE_URL="https://.../v1"   # use the Anthropic base URL from the dashboard
```

```python
import os
from anthropic import Anthropic

client = Anthropic(
    api_key=os.environ["ROUTERHUB_API_KEY"],
    base_url=os.environ["ROUTERHUB_BASE_URL"],
)
```

Anthropic-style clients use the `/messages` endpoint. OpenAI-style clients use `/chat/completions`. If you point a client at the wrong base URL or path style, you will usually see a `404`.

## Messages request

```python
message = client.messages.create(
    model="MODEL_ID",
    max_tokens=1024,
    system="You are a precise research assistant. Cite uncertainty explicitly.",
    messages=[
        {"role": "user", "content": "Summarize the trade-offs of one API gateway for multiple model families."}
    ],
)

print(message.content[0].text)
```

- `max_tokens` is required for Anthropic-style requests.
- `system` is a top-level parameter, not a message role.
- Use the exact model ID from the dashboard.

## Streaming

```python
with client.messages.stream(
    model="MODEL_ID",
    max_tokens=512,
    messages=[{"role": "user", "content": "List five evaluation criteria for LLM APIs."}],
) as stream:
    for text in stream.text_stream:
        print(text, end="", flush=True)
```

Streaming support depends on the model. Disable streaming if a model does not support it.

## Claude Code

Claude Code uses Anthropic-style environment variables. A typical setup is:

```bash
export ANTHROPIC_BASE_URL="https://.../v1"
export ANTHROPIC_AUTH_TOKEN="sk-..."   # some versions use ANTHROPIC_API_KEY
export ANTHROPIC_MODEL="MODEL_ID"
```

Then start Claude Code as usual. If authentication fails, confirm which variable your Claude Code version expects and that the base URL matches the Anthropic endpoint from the dashboard.

See the [client guide](./07-claude-code-cursor-opencode-codex.md#claude-code) for the full setup and troubleshooting checklist.

## System prompts and long context

Anthropic-style requests are often used for long system prompts and repository-scale instructions. Two practical rules:

1. **Keep the system prompt stable** so prompt caching can help with repeated prefixes.
2. **Measure long-context usage** — long documents consume input tokens on every request unless caching applies.

## Tool use

If the underlying model supports Anthropic-style tool use, send the standard `tools` array and validate every tool call before execution. Not every model on the gateway supports every feature; check the model entry in the dashboard.

## Next steps

- [OpenAI-compatible API](./05-openai-compatible-api.md)
- [Claude Code, Cursor, OpenCode and Codex](./07-claude-code-cursor-opencode-codex.md)
- [API reference](./14-api-reference.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)
