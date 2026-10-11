# API Reference

RouterHub exposes two compatible API surfaces: OpenAI-style chat completions and Anthropic-style messages. Use the base URL shown in the dashboard; the examples below show the request shapes, not a hard-coded host.

## Authentication

Send the key as a bearer token:

```http
Authorization: Bearer sk-...
Content-Type: application/json
```

Keys are shown once at creation. Store them in an environment variable or secrets manager.

## OpenAI-compatible chat completions

```http
POST {OPENAI_BASE_URL}/chat/completions
```

```json
{
  "model": "MODEL_ID",
  "messages": [
    {"role": "system", "content": "You are a concise assistant."},
    {"role": "user", "content": "Hello."}
  ],
  "temperature": 0.7,
  "stream": false
}
```

Response (abridged):

```json
{
  "id": "chatcmpl-...",
  "object": "chat.completion",
  "choices": [
    {
      "index": 0,
      "message": {"role": "assistant", "content": "Hello."},
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 12,
    "completion_tokens": 3,
    "total_tokens": 15
  }
}
```

### Common fields

| Field | Type | Notes |
|---|---|---|
| `model` | string | Required; use the current ID from the dashboard |
| `messages` | array | Required; roles: `system`, `user`, `assistant` |
| `temperature` | number | Optional; model-dependent range |
| `max_tokens` | integer | Optional for OpenAI-style; caps output |
| `stream` | boolean | Optional; model-dependent |
| `tools` | array | Optional; model-dependent |
| `tool_choice` | string/object | Optional; model-dependent |

## Anthropic-compatible messages

```http
POST {ANTHROPIC_BASE_URL}/messages
```

```json
{
  "model": "MODEL_ID",
  "max_tokens": 1024,
  "system": "You are a precise research assistant.",
  "messages": [
    {"role": "user", "content": "Summarize the key trade-offs."}
  ]
}
```

Response (abridged):

```json
{
  "id": "msg_...",
  "type": "message",
  "role": "assistant",
  "content": [{"type": "text", "text": "..."}],
  "stop_reason": "end_turn",
  "usage": {"input_tokens": 24, "output_tokens": 80}
}
```

### Differences from the OpenAI shape

- `system` is a top-level field, not a message role.
- `max_tokens` is required.
- The response uses a `content` array.
- The endpoint is `/messages`, not `/chat/completions`.

## Streaming

Both surfaces support streaming where the underlying model supports it. Use the SDK’s streaming API instead of parsing raw chunks manually. If a model does not stream, disable streaming for that model.

## Errors

| Status | Meaning | Action |
|---|---|---|
| `400` | Invalid request | Check required fields and model support |
| `401` | Unauthorized | Re-copy the key; check the header |
| `403` | Forbidden | Check account or model access |
| `404` | Wrong path or model | Check base URL and model ID |
| `429` | Rate or balance limit | Back off; check usage and balance |
| `5xx` | Upstream/provider error | Retry with backoff; contact support if persistent |

## Model IDs

Model IDs are not documented here because they change. Copy the current ID from the dashboard. If an ID returns `404`, it was likely renamed or retired.

## Versioning

The compatible API surface is stable; model behavior is not. Pin model IDs in production, keep a fallback, and re-run your evaluation when a provider updates a model.

## Next steps

- [OpenAI-compatible API](./05-openai-compatible-api.md)
- [Anthropic-compatible API](./06-anthropic-compatible-api.md)
- [Troubleshooting](./13-troubleshooting.md)
