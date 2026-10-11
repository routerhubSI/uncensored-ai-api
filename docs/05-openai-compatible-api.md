# OpenAI-Compatible API

RouterHub exposes an OpenAI-compatible interface for chat completions. If your application already uses the OpenAI SDK, an OpenAI-compatible framework or a tool that accepts a custom base URL, you can switch by changing two values: the **base URL** and the **API key**.

## Configuration

```bash
export ROUTERHUB_API_KEY="sk-..."
export ROUTERHUB_BASE_URL="https://.../v1"   # copy from the RouterHub dashboard
```

```python
import os
from openai import OpenAI

client = OpenAI(
    api_key=os.environ["ROUTERHUB_API_KEY"],
    base_url=os.environ["ROUTERHUB_BASE_URL"],
)
```

The base URL shown in the dashboard is the source of truth. If your client expects the URL without a trailing slash, remove it; if it expects `/v1`, keep it. Do not mix values between providers.

## Chat completions

```python
response = client.chat.completions.create(
    model="MODEL_ID",
    messages=[
        {"role": "system", "content": "You are a careful technical editor."},
        {"role": "user", "content": "Rewrite this paragraph for clarity: ..."},
    ],
    temperature=0.4,
)

print(response.choices[0].message.content)
```

Use the exact `MODEL_ID` from the dashboard. Family names are not stable identifiers.

## Streaming

```python
stream = client.chat.completions.create(
    model="MODEL_ID",
    messages=[{"role": "user", "content": "Explain prompt caching in five bullets."}],
    stream=True,
)

for chunk in stream:
    content = chunk.choices[0].delta.content
    if content:
        print(content, end="", flush=True)
```

Streaming is model-dependent. If a model does not support it, handle the response as a normal completion.

## Tools and function calling

Tool support follows the underlying model and the compatible API surface. If you rely on tool calls:

1. Confirm the model supports tools in the dashboard or model list.
2. Send a standard OpenAI `tools` array.
3. Validate the returned `tool_calls` before executing anything.
4. Keep a non-tool fallback for models that do not support the feature.

```python
tools = [{
    "type": "function",
    "function": {
        "name": "lookup_order",
        "description": "Look up an order by ID",
        "parameters": {
            "type": "object",
            "properties": {"order_id": {"type": "string"}},
            "required": ["order_id"],
        },
    },
}]

response = client.chat.completions.create(
    model="MODEL_ID",
    messages=[{"role": "user", "content": "Where is order 1234?"}],
    tools=tools,
)
```

## Structured output

If the selected model supports JSON or structured output, use the standard OpenAI fields your SDK exposes. Always validate the result against your schema on the server side; do not assume a model will produce valid JSON on every attempt.

## Compatibility checklist

- [ ] Base URL copied exactly from the dashboard.
- [ ] API key loaded from an environment variable, not committed to code.
- [ ] Model ID copied from the dashboard, not guessed from a family name.
- [ ] Streaming disabled for models that do not support it.
- [ ] Timeouts and retries configured for your workload.
- [ ] Token usage and balance monitored in the dashboard.

## What to do when a path returns 404

The most common causes are:

1. **Wrong base URL** — the client is calling a path that does not exist on the gateway.
2. **Wrong path for the API style** — an Anthropic client is pointed at an OpenAI base URL, or the reverse.
3. **Retired model ID** — the model was renamed or removed.

Start with the base URL, then compare the model ID to the dashboard.

## Next steps

- [Anthropic-compatible API](./06-anthropic-compatible-api.md)
- [Claude Code, Cursor, OpenCode and Codex](./07-claude-code-cursor-opencode-codex.md)
- [Troubleshooting](./13-troubleshooting.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)
