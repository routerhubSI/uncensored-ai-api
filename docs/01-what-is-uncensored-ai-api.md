# What Is an Uncensored AI API?

An **uncensored AI API** is a programmatic interface that gives your application access to model variants with fewer built-in refusals than standard hosted models. You send a request with an API key, choose a model, and receive a completion — the same basic contract as any LLM API, but with model options that are less likely to stop a response because of a policy layer.

The phrase describes **access**, not a guarantee. A model marketed as uncensored can still refuse, hedge or change behavior after an upstream update. The useful question is not “is it truly uncensored?” but “which model, at which version, with which prompt, gives me the behavior I need?”

## How an uncensored AI API works

Most applications talk to a model through one of two compatible formats:

1. **OpenAI-compatible** — `POST /chat/completions` with a `model` field and a `messages` array.
2. **Anthropic-compatible** — `POST /messages` with a system prompt and a `messages` array.

An API gateway sits between your app and the model providers. It handles authentication, routing, billing and model selection. Your code keeps using the SDK it already has; you change the base URL and the model ID.

```text
Your app / agent / SDK
        │
        ▼
  Uncensored AI API gateway
        │
        ├── Claude family
        ├── GPT family
        ├── Gemini family
        ├── Grok family
        ├── DeepSeek family
        ├── GLM family
        └── Qwen family
```

With **RouterHub**, the gateway exposes uncensored and abliterated variants next to standard frontier and open-weight models. One key covers every family, and billing is pay-per-token rather than a subscription.

## Who it is for

- **AI safety researchers** comparing refusal behavior across model versions.
- **Red teams** testing prompt injection, instruction conflicts and policy boundaries.
- **Creative writers** who need fewer interruptions during long-form work.
- **Agent builders** who want one key for coding and reasoning models.
- **Product teams** evaluating several model families before committing to one provider.

## Who it is not for

An uncensored API is not a way to avoid responsibility. It does not make harmful requests acceptable, it does not override provider terms, and it does not remove the need for human review. If your use case depends on guaranteed output, regulated advice or safety-critical decisions, add evaluation and guardrails before shipping.

## What to look for in a provider

| Requirement | Why it matters |
|---|---|
| **Compatibility** | Works with the SDK or client you already use |
| **Model coverage** | One key for multiple families, not one key per provider |
| **Transparent billing** | Per-token pricing, visible usage, no surprise subscription |
| **Caching** | Repeated system prompts should cost less |
| **API keys** | Separate budgets for projects, teammates or clients |
| **Payment options** | Card and crypto where you need them |
| **Support** | A real channel for model and billing issues |

## Uncensored API vs. self-hosting

Self-hosting an open-weight model gives you maximum control, but you pay in GPUs, operations, uptime and model maintenance. A hosted uncensored API is usually better when you want to evaluate several families quickly, avoid infrastructure work, or route between providers without rebuilding your stack.

Many teams use both: a hosted API for fast iteration and a self-hosted model for workloads that cannot leave their infrastructure.

## Start with RouterHub

RouterHub provides one OpenAI- and Anthropic-compatible endpoint for Claude, GPT, Gemini, Grok, DeepSeek, GLM and Qwen, including select uncensored and abliterated variants. Create an account, copy the base URL from the dashboard, and send your first request.

- [Quickstart](../docs/04-quickstart.md)
- [OpenAI-compatible API](../docs/05-openai-compatible-api.md)
- [Anthropic-compatible API](../docs/06-anthropic-compatible-api.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)

**Next:** [Uncensored vs. abliterated models →](./02-uncensored-vs-abliterated-models.md)
