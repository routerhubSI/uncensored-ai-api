# Use Cases

Uncensored and abliterated models are tools, not a license. The most successful teams use them where standard models create unnecessary friction, and keep a review process around the output.

## AI safety and red-team research

Researchers need to compare how model versions respond to instruction conflicts, prompt injection and policy boundaries. A gateway with several families makes it easier to run the same prompt set across Claude, GPT, Gemini, Grok, DeepSeek, GLM and Qwen without rebuilding the harness.

**Good practice:** keep a labeled prompt suite, record the exact model ID and version, and separate “refused” from “answered badly” in your results.

## Creative writing and worldbuilding

Long-form fiction often runs into mid-scene refusals that break immersion. Uncensored variants can reduce that friction for adult, dark or morally complex fiction while the author remains responsible for the content.

**Good practice:** keep a style guide, use a standard model for planning and an uncensored variant for drafting, and review sensitive material before publishing.

## Agentic coding

Coding agents benefit from one key across families. Claude models are strong for careful refactors, DeepSeek and GLM are cost-efficient for agent loops, and GPT models often have broad tool support. Routing between them lets you match the model to the task.

**Good practice:** pin model IDs, keep a fallback model, and log which model produced each change.

## Multilingual assistants

Different families have different strengths in Chinese, English and other languages. Testing the same prompt across GLM, Qwen, Claude and GPT can reveal which model handles your domain vocabulary best.

**Good practice:** evaluate on real examples from your audience, not only on translated benchmarks.

## Document-heavy research

Qwen and Gemini models are often used for long-document reading. A gateway keeps ingestion, billing and model selection in one place while you compare context limits and output quality.

**Good practice:** measure cached vs. uncached input cost; long documents are expensive when they are resent on every request.

## Privacy-conscious prototyping

Centralizing keys and billing reduces the number of provider accounts and secrets in your stack. Separate API keys let you give a contractor a budget without sharing your main key.

**Good practice:** use separate API keys, rotate them when a project ends, and never send data you are not allowed to process.

## Developer tooling and evaluation

If you build a tool that lets users choose a model, a gateway simplifies the integration: one OpenAI-compatible adapter, one Anthropic-compatible adapter, and a model list from the dashboard.

**Good practice:** show the model name and version in your UI, and let users switch without losing their prompt.

## What not to use it for

- Generating content that violates the law or the rights of others.
- Producing malware, fraud, harassment or targeted abuse.
- Bypassing security controls or consent.
- Making safety-critical decisions without human review.

See [Safety and responsible use](./10-safety-and-responsible-use.md) for the full checklist.

## Next steps

- [Model catalog](./03-model-catalog.md)
- [Pricing and limits](./08-pricing-and-limits.md)
- [Safety and responsible use](./10-safety-and-responsible-use.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)
