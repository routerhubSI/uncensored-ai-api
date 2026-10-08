# Uncensored vs. Abliterated Models

“Uncensored” and “abliterated” are often used interchangeably, but they describe different things. Knowing the difference helps you choose the right model and set realistic expectations.

## Uncensored models

An **uncensored model** is a model variant trained or fine-tuned to refuse less often. The training data, instruction tuning or alignment recipe has been adjusted so the model is more willing to follow prompts that a standard release might decline.

Uncensored variants can be produced in several ways:

- fine-tuning on instruction-following data with fewer refusal examples;
- removing or rebalancing safety-focused preference data;
- merging a standard model with a less restricted variant;
- applying a system prompt or persona layer that changes refusal behavior.

The result is a model that is usually more permissive, but not uniformly so. It may still refuse some requests, especially those involving clearly illegal or harmful content, and behavior can change when the provider updates the base model.

## Abliterated models

**Abliteration** is a weight-level technique. Researchers identify a direction in the model’s activations that correlates with refusal behavior, then modify the weights to reduce the influence of that direction. The goal is to remove the model’s tendency to refuse without retraining it from scratch.

In practice, abliteration can produce a model that is notably less likely to refuse, while preserving much of the original model’s knowledge and style. It is also less predictable than a carefully fine-tuned uncensored variant: the same intervention can affect other behaviors, and results vary by model architecture and method.

## Key differences

| | Uncensored | Abliterated |
|---|---|---|
| **Level** | Training / fine-tuning / prompting | Model weights |
| **Typical method** | Curated data, preference tuning, merges | Refusal-direction removal |
| **Predictability** | Varies by recipe | Varies by model and method |
| **Knowledge retention** | Usually high | Usually high, but side effects possible |
| **Refusal behavior** | Reduced, not eliminated | Often strongly reduced |
| **Best for** | General creative and research work | Experiments where refusal is the main blocker |

## What “uncensored” does not mean

- **It does not mean illegal content is allowed.** Laws and provider terms still apply.
- **It does not mean the model is always correct.** Removing refusals does not improve reasoning or factual accuracy.
- **It does not mean behavior is stable.** Upstream model updates can change results.
- **It does not remove the need for evaluation.** Test the exact model and version you plan to use.

## How to evaluate an uncensored or abliterated model

1. **Build a representative prompt set.** Include normal requests, edge cases and prompts that previously triggered refusals.
2. **Test the exact model ID.** A family name is not enough; versions behave differently.
3. **Measure both refusal rate and quality.** A model that never refuses but produces poor output is not useful.
4. **Check side effects.** Abliteration can change tone, instruction following or safety behavior outside the target area.
5. **Re-test after updates.** Keep a small regression suite and rerun it when the provider ships a new version.

## Using uncensored models responsibly

Uncensored access is most valuable when it is paired with clear internal rules: who can use which model, what data can be sent, how outputs are reviewed and what happens when a model produces something unexpected. The API gives you the capability; your process determines whether it is used well.

## Try both categories on RouterHub

RouterHub exposes standard, uncensored and abliterated variants across supported model families. Availability changes by model and version, so check the dashboard for the current list.

- [Model catalog](./03-model-catalog.md)
- [Safety and responsible use](./10-safety-and-responsible-use.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)

**Next:** [Model catalog →](./03-model-catalog.md)
