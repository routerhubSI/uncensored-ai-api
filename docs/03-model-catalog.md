# Model Catalog

RouterHub groups models by family so you can route a request to the right kind of model without managing a separate account for every provider. The families below are the ones currently represented in the platform. **Exact model IDs, versions, context limits and uncensored availability are shown in the dashboard** and can change when providers ship updates.

## Families at a glance

| Family | Strengths | Good for | Uncensored options |
|---|---|---|---|
| **Claude** | Long-form reasoning, careful writing, coding agents | Research summaries, refactoring, Claude Code | Select variants |
| **GPT** | General instruction following, tools, structured output | Assistants, extraction, function calling | Select variants |
| **Gemini** | Multimodal work, research, long context | Document analysis, mixed-media workflows | Select variants |
| **Grok** | Fast ideation, conversational style | Brainstorming, alternative viewpoints | Select variants |
| **DeepSeek** | Coding and reasoning at efficient cost | Agents, code review, batch jobs | Select variants |
| **GLM** | Agent workflows, coding, bilingual tasks | Tool-using agents, Chinese/English work | Select variants |
| **Qwen** | Long-document reading, agentic tasks | Large context workflows, research | Select variants |

## Claude

Claude models are often chosen for long-form reasoning, nuanced writing and coding-agent work. They tend to follow detailed system prompts well, which makes them a good fit for structured research and repository-scale tasks.

**Typical uses:** Claude Code, code review, technical writing, long-document analysis, planning.
**Notes:** Context limits and model IDs vary by version. Use the dashboard to confirm the current ID.

## GPT

GPT-family models are general-purpose workhorses. They are widely supported by OpenAI-compatible tooling and are a common default for chat, extraction and function-calling workflows.

**Typical uses:** assistants, structured extraction, tool calling, content generation.
**Notes:** Tool and JSON-mode support depends on the specific model. Check the model entry before relying on a feature.

## Gemini

Gemini models are useful when a workflow involves multiple modalities or very long inputs. They can be a good complement to text-only models when you need to analyze documents or mixed content.

**Typical uses:** document understanding, research, multimodal prototypes.
**Notes:** Multimodal support and input limits are model-specific.

## Grok

Grok models have a conversational, direct style that some teams prefer for ideation and alternative perspectives. They can be useful as a second opinion alongside Claude or GPT.

**Typical uses:** brainstorming, naming, critique, exploratory writing.
**Notes:** Behavior and tone vary by version.

## DeepSeek

DeepSeek models are often used for coding and reasoning where cost efficiency matters. They are a strong option for high-volume agent tasks and batch processing.

**Typical uses:** coding agents, code review, reasoning chains, batch jobs.
**Notes:** Compare output quality on your own prompts; reasoning models can be slower and more verbose.

## GLM

GLM models are used in agentic and coding workflows, including bilingual Chinese/English tasks. They can be a good fit for tool-using agents and structured workspace instructions.

**Typical uses:** coding agents, bilingual assistants, tool workflows.
**Notes:** Check the model ID and context limit in the dashboard.

## Qwen

Qwen models are known for long-document reading and agentic workflows. They can be useful when a task requires ingesting a large amount of text before answering.

**Typical uses:** long-document analysis, research, agent tasks.
**Notes:** Long-context requests consume more tokens; monitor usage.

## How to choose a model

1. **Start with the task, not the brand.** Coding, long-document analysis and creative writing stress different capabilities.
2. **Test two or three families on the same prompt set.** Keep the winner for production and the runner-up as a fallback.
3. **Check the exact model ID.** Family names move; IDs identify a specific release.
4. **Measure cost per successful task.** Token price alone is misleading if one model needs more retries.
5. **Re-evaluate after updates.** Keep a small regression suite and rerun it when a model changes.

## Model IDs and availability

The dashboard is the source of truth for:

- current model IDs;
- context and output limits;
- uncensored and abliterated variants;
- per-token input, output and cached-input prices;
- supported features such as streaming or tool calls.

If a model ID returns `404`, the most common cause is a renamed or retired version. Copy the current ID from the dashboard and retry.

## Next steps

- [Quickstart](./04-quickstart.md)
- [Pricing and limits](./08-pricing-and-limits.md)
- [Troubleshooting](./13-troubleshooting.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)
