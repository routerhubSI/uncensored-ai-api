# Safety and Responsible Use

Uncensored models reduce refusal behavior. They do not remove your responsibility. This page is the practical checklist we recommend before putting an uncensored API into a product or an automated workflow.

## The short version

1. Use the API for lawful purposes.
2. Follow the terms of the model providers and of RouterHub.
3. Evaluate the exact model and version you deploy.
4. Add human review where output matters.
5. Protect data, keys and user privacy.
6. Keep logs that let you investigate incidents.

## Lawful use

You are responsible for what you generate and how you use it. Uncensored access is not permission to produce illegal content, infringe rights, harass people, distribute malware or bypass security controls. If a request would be illegal with a standard model, it is still illegal with an uncensored one.

## Provider terms

Model providers set their own usage policies. RouterHub provides access; it does not override those terms. Check the policy that applies to the model family you use, especially for commercial products, regulated industries and content distribution.

## Evaluation before deployment

Keep a small, representative evaluation set:

- normal requests your users will send;
- edge cases that previously caused refusals;
- attempts at prompt injection and instruction conflict;
- outputs that require factual accuracy;
- sensitive topics that need a defined policy.

Measure refusal rate, quality, latency and cost per successful task. Re-run the suite when the provider updates a model.

## Guardrails

Even with uncensored models, production systems benefit from guardrails:

- **Input checks** for prohibited content and prompt injection.
- **Output checks** for policy violations, PII leakage and unsafe code.
- **Allowlists** for tools and external actions.
- **Human approval** for irreversible actions.
- **Rate limits** and budget caps per user or API key.

Guardrails are not a contradiction of “uncensored.” They are how you keep a powerful tool aligned with your product’s rules.

## Data and privacy

- Send only the data you are allowed to process.
- Avoid secrets, credentials and sensitive personal data in prompts.
- Use separate API keys to separate projects and revoke access cleanly.
- Check retention and logging practices for the models you use.
- Document data flows for your own compliance review.

## Age and audience

If your product is available to minors or a general audience, define age gates and content policies before enabling uncensored variants. “The model will answer” is not a content policy.

## Incident response

Have a simple plan:

1. Identify the model ID, prompt and account involved.
2. Disable the API key or model if the issue is ongoing.
3. Preserve relevant logs.
4. Notify the right person internally.
5. Update the prompt, guardrail or model choice.
6. Re-test before re-enabling.

## Reporting and support

For account, billing or model-access issues, contact support through [Telegram](https://t.me/routerhubsi). For security issues in your own integration, follow your organization’s disclosure process.

## A practical rule

> Use uncensored models to reduce unnecessary friction, not to remove accountability.

If you cannot explain why a request is lawful, ethical and appropriate for your audience, do not send it — regardless of what the model will answer.

## Next steps

- [Use cases](./09-use-cases.md)
- [FAQ](./11-faq.md)
- [Troubleshooting](./13-troubleshooting.md)
- [Get an API key](https://routerhub.si/?utm_source=github&utm_medium=docs&utm_campaign=uncensored-ai-api)
