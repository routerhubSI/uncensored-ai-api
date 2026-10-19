# Glossary

Plain-language definitions for the terms used across this repository.

**Abliteration** — A weight-level technique that reduces a model’s refusal direction without full retraining. Results vary by model and method.

**API** — Application Programming Interface. A contract that lets one program call another. In this repo, the contract is an HTTP endpoint that returns model completions.

**API gateway** — A service that sits between your app and one or more model providers. It handles auth, routing, billing and model selection.

**Anthropic-compatible** — An API that accepts the Anthropic Messages request shape (`/messages`, top-level `system`, `max_tokens`). Used by Claude Code and the Anthropic SDK.

**Base URL** — The root URL your SDK sends requests to. For OpenAI-style clients it often includes `/v1`; use the exact value from the RouterHub dashboard.

**Cached input** — Input tokens that a provider serves from a prompt cache. Usually billed at a lower rate than fresh input.

**Chat completion** — The OpenAI-style response format with a `choices` array. Used for conversational and instruction-following requests.

**Completion** — The model’s generated output for a prompt.

**Context window** — The maximum number of tokens a model can consider in one request, including input and output.

**Function calling / tool use** — A feature that lets a model return a structured call to an external function instead of, or in addition to, text. Support is model-dependent.

**Inference** — Running a trained model to produce output.

**LLM** — Large Language Model. A neural network trained on text to predict and generate language.

**Model ID** — The exact identifier you send in the `model` field. IDs change when providers release or retire versions.

**Model family** — A group of related models from one provider, such as Claude, GPT, Gemini, Grok, DeepSeek, GLM or Qwen.

**OpenAI-compatible** — An API that accepts the OpenAI chat completions shape (`/chat/completions`, `messages` array). Works with the OpenAI SDK and many third-party tools.

**Pay per token** — Billing based on the number of input and output tokens used, with no subscription.

**Prompt** — The text and instructions sent to the model.

**Prompt caching** — Reusing a previously processed prefix so repeated requests cost less and run faster.

**Prompt injection** — An attack where untrusted text tries to override the system’s instructions. Evaluate models for this before deploying agents.

**Rate limit** — A cap on requests or tokens over a time window.

**Refusal** — A model’s decision to decline or deflect a request. Uncensored variants reduce this behavior but do not eliminate it.

**Streaming** — Receiving a response incrementally as tokens are generated.

**API key** — A credential used to authenticate requests. Create separate keys for teammates, projects or clients.

**System prompt** — High-level instructions that set the model’s role and rules for a conversation.

**Token** — The unit models use to process text. Roughly, one token is a short word or part of a word; token counts vary by language and tokenizer.

**Top-up** — Adding balance to the account. RouterHub supports crypto top-ups.

**Uncensored model** — A model variant trained or tuned to refuse less often than a standard release. The term describes behavior, not a guarantee.

## Related

- [What is an uncensored AI API?](./01-what-is-uncensored-ai-api.md)
- [Uncensored vs. abliterated](./02-uncensored-vs-abliterated-models.md)
- [FAQ](./11-faq.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)
