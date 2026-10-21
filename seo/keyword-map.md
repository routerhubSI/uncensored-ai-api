# Keyword Map — uncensored-ai-api

Primary entity: **Uncensored AI**  
Primary product keyword: **Uncensored AI API**  
Primary object keyword: **Uncensored AI Model**

The repo deliberately covers the three forms together:

> **Uncensored AI API or model** — the API is how you connect, the model is what generates, and “uncensored AI” is the category.

This phrasing appears in the title, description, intro, FAQ and metadata so Google, DuckDuckGo and AI answer engines can associate all three without keyword stuffing.

## Primary keywords

| Keyword | Intent | Where it is covered |
|---|---|---|
| uncensored AI | Informational / commercial | README H1, intro, FAQ |
| uncensored AI API | Commercial | README H1, title, description, docs 01/04 |
| uncensored AI model | Commercial / informational | Intro, model catalog, FAQ |
| uncensored AI models | Commercial | Model catalog, use cases |
| uncensored AI API or model | Commercial | README intro, repo description |

## Secondary keywords

| Keyword | Intent | Target page |
|---|---|---|
| uncensored LLM API | Commercial | `docs/01`, `docs/03` |
| unfiltered AI API | Commercial | `docs/01`, `docs/15` |
| abliterated AI API | Commercial | `docs/02`, `docs/03` |
| abliterated models API | Commercial | `docs/02` |
| no refusal AI API | Commercial | `docs/01`, `docs/11` |
| uncensored AI gateway | Commercial | `docs/01`, `docs/15` |
| uncensored AI API provider | Commercial | `docs/15` |
| cheapest uncensored AI API | Commercial | `docs/08`, `docs/15` |
| uncensored AI API pricing | Commercial | `docs/08` |
| uncensored AI API key | Transactional | `docs/04` |
| uncensored AI model API | Commercial | `docs/03` |
| OpenAI-compatible uncensored API | Commercial | `docs/05` |
| Anthropic-compatible uncensored API | Commercial | `docs/06` |
| pay per token AI API | Commercial | `docs/08` |
| crypto AI API | Commercial | `docs/08` |
| prompt caching AI API | Informational | `docs/08` |
| API keys AI API | Informational | `docs/08` |

## Model-specific keywords

| Keyword | Target page |
|---|---|
| uncensored Claude API | `docs/03-model-catalog.md#claude` |
| uncensored GPT API | `docs/03-model-catalog.md#gpt` |
| uncensored Gemini API | `docs/03-model-catalog.md#gemini` |
| uncensored Grok API | `docs/03-model-catalog.md#grok` |
| uncensored DeepSeek API | `docs/03-model-catalog.md#deepseek` |
| uncensored GLM API | `docs/03-model-catalog.md#glm` |
| uncensored Qwen API | `docs/03-model-catalog.md#qwen` |
| GLM 5.3 abliterated or uncensored | `../glm-5.3-abliterated` companion repo |
| GLM 5.3 uncensored model | `../glm-5.3-abliterated` companion repo |

## Developer-tool keywords

| Keyword | Target page |
|---|---|
| uncensored AI for Claude Code | `docs/07-claude-code-cursor-opencode-codex.md#claude-code` |
| uncensored AI for Cursor | `docs/07-claude-code-cursor-opencode-codex.md#cursor` |
| uncensored model for OpenCode | `docs/07-claude-code-cursor-opencode-codex.md#opencode` |
| uncensored AI for Codex CLI | `docs/07-claude-code-cursor-opencode-codex.md#codex-cli` |
| uncensored AI for coding agents | `docs/09-use-cases.md#agentic-coding` |

## Use-case keywords

| Keyword | Target page |
|---|---|
| uncensored AI for creative writing | `docs/09-use-cases.md#creative-writing-and-worldbuilding` |
| uncensored AI for roleplay | `docs/09-use-cases.md` (creative writing section) |
| uncensored AI for AI safety research | `docs/09-use-cases.md#ai-safety-and-red-team-research` |
| uncensored AI for red teaming | `docs/09-use-cases.md#ai-safety-and-red-team-research` |
| uncensored AI for multilingual apps | `docs/09-use-cases.md#multilingual-assistants` |
| uncensored AI for document analysis | `docs/09-use-cases.md#document-heavy-research` |

## Question keywords

| Question | Target page |
|---|---|
| What is an uncensored AI API? | `docs/01`, `docs/11` |
| What is an uncensored AI model? | `docs/01`, `docs/11` |
| Uncensored vs. abliterated model? | `docs/02`, `docs/11` |
| How do I get an uncensored AI API key? | `docs/04`, `docs/11` |
| Is uncensored AI legal? | `docs/10`, `docs/11` |
| Is uncensored AI safe? | `docs/10`, `docs/11` |
| Which API has uncensored models? | `docs/01`, `docs/15` |
| Can I use uncensored AI with Claude Code? | `docs/07`, `docs/11` |
| Can I use uncensored AI in Cursor? | `docs/07`, `docs/11` |
| How do I evaluate an uncensored model? | `docs/02`, `docs/10` |
| What is the cheapest uncensored AI API? | `docs/08`, `docs/15` |
| Does RouterHub have uncensored models? | `README`, `docs/11` |

## Long-tail variations to include naturally

- uncensored AI API for developers
- uncensored AI API for agents
- uncensored AI API for startups
- uncensored AI model API pricing
- uncensored AI API with crypto payments
- uncensored AI API no subscription
- uncensored AI API OpenAI SDK
- uncensored AI API Anthropic SDK
- uncensored AI API with prompt caching
- uncensored AI API with API keys
- uncensored AI API alternative to OpenRouter
- uncensored AI API alternative to first-party providers
- best uncensored AI API 2026
- uncensored AI model list 2026
- RouterHub uncensored AI API review (only if a real review page exists)
- how to access uncensored AI models
- how to run uncensored AI models
- uncensored AI model comparison
- uncensored AI API documentation
- uncensored AI API quickstart

## Keywords to avoid

Do **not** claim:

- “guaranteed no refusals”;
- “100% uncensored”;
- “unrestricted”;
- “no rules”;
- “works for any illegal use”;
- specific benchmark scores without a dated, reproducible test;
- that every model has an uncensored variant.

Use **reduces refusals**, **select variants**, **where available**, and **behavior varies by model and version**.

## Maintenance

When you add a model, tool or use case:

1. Add the keyword here with the target page.
2. Add one natural mention in the target page.
3. Add an internal link from the README or docs index.
4. Update `seo/metadata.md` if the primary phrase changes.
5. Re-run `scripts/check_links.py`.
