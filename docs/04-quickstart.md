# Quickstart

Get from zero to your first uncensored AI API request in a few minutes.

## 1. Create an account

Go to **[routerhub.si](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)** and create an account. The account is key-based: your API key is the login, so store it in a password manager or secrets manager immediately.

## 2. Copy two values

From the dashboard overview, copy:

1. **API key** — starts with `sk-`.
2. **Base URL** — the exact gateway URL for your account.

The base URL matters. Some clients expect it with a version prefix (for example `/v1`), while Anthropic-style clients expect the Anthropic base URL shown in the dashboard. Do not guess the path; copy the value.

```bash
export ROUTERHUB_API_KEY="sk-..."
export ROUTERHUB_BASE_URL="https://.../v1"
```

## 3. Send an OpenAI-compatible request

```python
import os
from openai import OpenAI

client = OpenAI(
    api_key=os.environ["ROUTERHUB_API_KEY"],
    base_url=os.environ["ROUTERHUB_BASE_URL"],
)

response = client.chat.completions.create(
    model="MODEL_ID",
    messages=[
        {"role": "system", "content": "You are a concise technical assistant."},
        {"role": "user", "content": "List three trade-offs of routing multiple model families through one API."},
    ],
)

print(response.choices[0].message.content)
```

Replace `MODEL_ID` with a current ID from the dashboard.

## 4. Send an Anthropic-compatible request

```python
import os
from anthropic import Anthropic

client = Anthropic(
    api_key=os.environ["ROUTERHUB_API_KEY"],
    base_url=os.environ["ROUTERHUB_BASE_URL"],
)

message = client.messages.create(
    model="MODEL_ID",
    max_tokens=512,
    messages=[{"role": "user", "content": "Write a one-paragraph project summary."}],
)

print(message.content[0].text)
```

Use the Anthropic base URL shown in the dashboard if it differs from the OpenAI base URL.

## 5. Test with cURL

```bash
curl "$ROUTERHUB_BASE_URL/chat/completions" \
  -H "Authorization: Bearer $ROUTERHUB_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "MODEL_ID",
    "messages": [{"role": "user", "content": "Hello from RouterHub."}]
  }'
```

## 6. Stream a response

OpenAI-compatible streaming:

```python
stream = client.chat.completions.create(
    model="MODEL_ID",
    messages=[{"role": "user", "content": "Count from 1 to 10 slowly."}],
    stream=True,
)

for chunk in stream:
    delta = chunk.choices[0].delta.content
    if delta:
        print(delta, end="", flush=True)
```

Streaming support depends on the model. If a model does not stream, the request still returns a normal response.

## 7. Choose an uncensored variant

In the dashboard, look for the model entry marked as uncensored or abliterated. Copy its exact ID and use it in the `model` field. Keep a standard model as a fallback so your application can retry if a variant is unavailable.

## Common first-run issues

| Symptom | Likely cause | Fix |
|---|---|---|
| `401 Unauthorized` | Missing, revoked or mistyped key | Copy the key again; check the `Authorization` header |
| `404 model_not_found` | Old or renamed model ID | Copy the current ID from the dashboard |
| `404` on every path | Wrong base URL | Use the exact base URL shown in the dashboard |
| `429 Too Many Requests` | Rate or balance limit | Check usage and balance; retry with backoff |
| Empty stream | Model does not support streaming | Disable streaming for that model |

## Next steps

- [OpenAI-compatible API](./05-openai-compatible-api.md)
- [Anthropic-compatible API](./06-anthropic-compatible-api.md)
- [Claude Code, Cursor, OpenCode and Codex](./07-claude-code-cursor-opencode-codex.md)
- [Troubleshooting](./13-troubleshooting.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)
