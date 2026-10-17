# Pricing and Limits

RouterHub uses **pay-per-token** billing. There is no monthly subscription, no seat fee and no minimum commitment. You add balance, use models, and pay for the tokens you consume.

## How billing works

- **Input tokens** are charged at the model’s input rate.
- **Output tokens** are charged at the model’s output rate.
- **Cached input** is billed at the lower cached-input rate when the provider supports prompt caching.
- **Prices vary by model** and can change when providers update their rates.

Live prices are listed in the RouterHub dashboard. Always confirm the current rate before running a large job.

## Top-ups and payment methods

RouterHub supports card and crypto top-ups. Your balance is credited after a payment is confirmed; the exact confirmation time depends on the method.

## Prompt caching

Prompt caching reduces the cost of repeated prefixes. It is most useful when:

- the same system prompt is sent on every request;
- a long document is reused across many questions;
- an agent replays the same repository or instructions repeatedly.

To benefit, keep the cached prefix stable. Changing the beginning of the prompt invalidates the cache for that request.

## API keys

Separate API keys let you isolate projects without splitting your account:

- create a key for a teammate, project or client;
- track usage per key in the dashboard;
- revoke a key without rotating the others.

This is useful for agencies, small teams and anyone who needs per-project budgets.

## Limits

Limits depend on your account, balance and the model you call. The dashboard is the source of truth for:

- available models and context limits;
- rate limits and concurrency;
- request and output limits;
- current pricing.

If you receive `429 Too Many Requests`, slow down, add exponential backoff, or contact support through [Telegram](https://t.me/routerhubsi).

## Cost-control checklist

- [ ] Set a budget for each project or API key.
- [ ] Monitor usage in the dashboard during the first week.
- [ ] Use prompt caching for repeated system prompts and documents.
- [ ] Cap `max_tokens` for tasks that do not need long outputs.
- [ ] Log token usage per request so you can attribute cost.
- [ ] Re-test model choice after pricing changes.
- [ ] Use a cheaper model for classification, extraction and routing.

## A simple cost model

```text
cost = (input_tokens  × input_price)
     + (output_tokens × output_price)
     + (cached_tokens × cached_input_price)
```

Because prices are per model, compare **cost per successful task**, not just the sticker price. A cheaper model that needs three retries can cost more than a stronger model that succeeds once.

## Next steps

- [Model catalog](./03-model-catalog.md)
- [Use cases](./09-use-cases.md)
- [Troubleshooting](./13-troubleshooting.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)
