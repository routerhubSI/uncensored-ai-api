# Contributing

Thanks for improving the uncensored AI API guide.

## What is welcome

- Corrections to model compatibility or setup steps.
- New client guides (SDKs, editors, agent frameworks).
- Clearer definitions and evaluation methods.
- Fixes for broken links.

## Rules

1. **No secrets.** Never include API keys, tokens or account credentials.
2. **No fake benchmarks.** If you add performance claims, include the date, model ID and method.
3. **No “100% uncensored” claims.** Use “reduces refusals” and “where available.”
4. **Keep the structure.** One topic per doc; link it from `docs/README.md`.
5. **Use current model IDs.** Model IDs belong in the dashboard, not hard-coded in docs unless the doc is version-pinned.

## Workflow

1. Open an issue describing the change.
2. Fork the repo and create a branch.
3. Make the smallest useful change.
4. Run the link check: `python scripts/check_links.py` (if present).
5. Open a pull request with a short description.

## Style

- Clear, direct English.
- Short paragraphs.
- Tables for comparisons.
- Code fences with language tags.
- Descriptive link text.

## License

By contributing, you agree that your contribution is licensed under the MIT License.
