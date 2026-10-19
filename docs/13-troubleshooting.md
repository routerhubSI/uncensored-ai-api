# Troubleshooting

Fast fixes for the problems developers hit most often when connecting to RouterHub.

## 401 Unauthorized

**Cause:** missing, revoked or mistyped API key.

**Fix:**

1. Copy the key again from the dashboard.
2. Confirm the header is `Authorization: Bearer sk-...`.
3. Check that the key belongs to the account you are billing.
4. If the key was rotated, update every client and environment variable.

## 404 on every path

**Cause:** wrong base URL.

**Fix:** copy the exact base URL from the dashboard. Do not add or remove `/v1` unless the dashboard shows it. An OpenAI-style client and an Anthropic-style client may use different base URLs.

## 404 model_not_found

**Cause:** model ID was renamed, retired or typed incorrectly.

**Fix:** copy the current ID from the dashboard. Family names such as “Claude” or “GLM” are not valid model IDs.

## 400 Bad Request

Common causes:

- missing `messages` array;
- `max_tokens` missing on an Anthropic-style request;
- invalid role names;
- a field the selected model does not support.

Compare your payload with the examples in the [API reference](./14-api-reference.md).

## 429 Too Many Requests

**Cause:** rate limit or balance limit.

**Fix:**

- check usage and balance in the dashboard;
- add exponential backoff with jitter;
- reduce concurrency;
- move batch work to a slower queue;
- contact support if the limit looks wrong.

```python
import random, time

def backoff(attempt: int) -> None:
    time.sleep(min(30, (2 ** attempt) + random.random()))
```

## Streaming returns nothing

**Cause:** the model does not support streaming, or the client is reading the wrong field.

**Fix:** disable streaming and confirm a normal completion works. If it does, keep streaming off for that model or switch to a model that supports it.

## Empty or truncated output

- Increase `max_tokens` if the response is cut off.
- Check the model’s output limit.
- Some reasoning models spend tokens on internal reasoning; leave headroom.
- If the prompt is very long, confirm the context window.

## Tool calls fail

- Confirm the model supports tools.
- Validate the JSON schema you send.
- Check the returned `tool_calls` before executing anything.
- Keep a non-tool fallback for models without tool support.

## Requests time out

- Use a longer client timeout for long generations.
- Reduce prompt size or output length.
- Retry idempotent requests with backoff.
- Check your network and proxy configuration.

## CORS errors in the browser

Do not call the API directly from browser JavaScript with a secret key. Use a backend proxy that adds the key server-side. This protects the key and avoids CORS issues.

## Claude Code ignores the custom URL

- Confirm the environment variables are set in the shell that launches Claude Code.
- Check whether your version expects `ANTHROPIC_AUTH_TOKEN` or `ANTHROPIC_API_KEY`.
- Verify the Anthropic base URL from the dashboard.
- Test the key with a direct request before debugging the tool.

## Cursor returns 404

The base URL is usually wrong. Use the exact OpenAI-compatible URL, including the version prefix if shown. Make sure you are not using the Anthropic URL in an OpenAI-style field.

## Still stuck?

Collect:

- the request path and method;
- the HTTP status and error body;
- the model ID;
- the client or SDK version;
- a timestamp.

Then contact support through [Telegram](https://t.me/routerhubsi). Do not send your full API key in a support message.

## Next steps

- [Quickstart](./04-quickstart.md)
- [API reference](./14-api-reference.md)
- [FAQ](./11-faq.md)
