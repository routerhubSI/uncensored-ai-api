# FAQ

Answers to the questions developers ask most often about uncensored AI APIs and RouterHub.

## What is an uncensored AI API?

An uncensored AI API gives your application access to model variants with fewer built-in refusals than standard hosted models. You send a request through a compatible API, choose a model, and receive a completion. RouterHub provides this through one OpenAI- and Anthropic-compatible gateway.

## What is an abliterated model?

Abliteration is a weight-level technique that reduces a model’s refusal direction. It is different from fine-tuning an uncensored variant: the goal is to remove refusal behavior without retraining the whole model. Results vary by model and method.

## Is RouterHub OpenAI-compatible?

Yes. Set the OpenAI SDK’s `base_url` to the RouterHub base URL and use your RouterHub key. Any client that accepts a custom OpenAI-compatible base URL can connect.

## Is RouterHub Anthropic-compatible?

Yes. Anthropic-style clients, including Claude Code, can use the Anthropic-compatible endpoint. Use the Anthropic base URL shown in the dashboard.

## Do I need a subscription?

No. RouterHub is pay-per-token. You top up a balance and spend it across models. There is no monthly subscription or seat fee.

## Can I pay with crypto?

Yes. RouterHub supports card and crypto top-ups.

## Are all models uncensored?

No. Standard frontier and open-weight models are available alongside select uncensored and abliterated variants. Availability changes by model and version; check the dashboard.

## Will an uncensored model never refuse?

No. Uncensored and abliterated variants reduce refusal behavior, but they do not eliminate it. Model behavior depends on the version, the prompt and the provider’s policy. Test the exact model you plan to use.

## Which model should I use for coding?

Claude models are strong for careful refactors, DeepSeek and GLM are cost-efficient for agent loops, and GPT models often have broad tool support. Test on your repository and keep a fallback model.

## Can I use RouterHub with Claude Code?

Yes. Set `ANTHROPIC_BASE_URL` and the auth token, then start Claude Code. See the [client guide](./07-claude-code-cursor-opencode-codex.md#claude-code).

## Can I use RouterHub with Cursor?

Yes. Add your RouterHub key as an OpenAI key, enable the custom base URL, and add the model ID. See the [Cursor section](./07-claude-code-cursor-opencode-codex.md#cursor).

## How do I find the model ID?

Copy it from the RouterHub dashboard. Family names are not stable IDs; a `404 model_not_found` usually means the ID was renamed or retired.

## Why am I getting 401 Unauthorized?

The key is missing, revoked or mistyped. Copy it again, confirm the `Authorization` header, and make sure you are using the key for this account.

## Why am I getting 404 on every request?

The base URL is usually wrong. Copy the exact URL from the dashboard. Also check that an OpenAI-style client is not pointed at the Anthropic endpoint, or the reverse.

## Why am I getting 429?

You hit a rate or balance limit. Check usage and balance in the dashboard, add exponential backoff, or contact support.

## Does prompt caching work?

Prompt caching is supported where the model/provider supports it. Keep the cached prefix stable to benefit. Cached input is billed at a lower rate.

## Can I share access with a teammate?

Use a separate API key. It can be tracked separately and revoked without rotating your main key.

## Is RouterHub affiliated with the model providers?

No. RouterHub is an independent gateway. Model names and trademarks belong to their respective owners.

## Where can I get support?

Use the [Telegram channel](https://t.me/routerhubsi) for updates and support.

## Next steps

- [What is an uncensored AI API?](./01-what-is-uncensored-ai-api.md)
- [Uncensored vs. abliterated](./02-uncensored-vs-abliterated-models.md)
- [Quickstart](./04-quickstart.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)
