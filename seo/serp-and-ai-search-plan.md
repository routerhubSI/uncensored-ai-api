# SERP and AI Search Plan

Goal: rank for **uncensored AI**, **uncensored AI API** and **uncensored AI model** on Google and DuckDuckGo, and be cited by AI answer engines (Google AI Overviews, ChatGPT, Perplexity, Copilot, Gemini).

## Search intent map

| Query | Intent | Asset |
|---|---|---|
| uncensored AI | Informational | README + `docs/01` |
| uncensored AI API | Commercial | README + `docs/04` |
| uncensored AI model | Commercial/informational | `docs/03` |
| uncensored AI API or model | Commercial | README intro + metadata |
| uncensored AI API pricing | Commercial | `docs/08` |
| uncensored AI API key | Transactional | `docs/04` |
| uncensored AI API OpenAI compatible | Commercial | `docs/05` |
| uncensored AI API Anthropic compatible | Commercial | `docs/06` |
| GLM 5.3 abliterated or uncensored | Commercial | companion repo |
| best uncensored AI API | Commercial investigation | `docs/15` |

## On-page rules

1. **First 100 words** contain the primary phrase and a plain-language definition.
2. **One H1** per page; H2s phrased as questions where natural.
3. **Short answer first**, then detail. AI engines quote the first two sentences.
4. **Tables** for model families, compatibility and pricing.
5. **FAQ** with 40–60 word answers and a `FAQPage` schema.
6. **Internal links** from README to every doc and back to the repo.
7. **External links** only to RouterHub, Telegram and the companion repo.
8. **No keyword stuffing.** Repeat the primary phrase where it reads naturally.
9. **Dated content.** Add “Last updated” to major docs.
10. **Consistent entity name.** Always “RouterHub” in body copy.

## DuckDuckGo specifics

DuckDuckGo uses Bing’s index plus its own ranking signals. To rank:

- keep the repo public and indexable;
- use the exact phrase in the repo name, description and H1;
- get at least a few external links to the repo (RouterHub site, Telegram, companion repo, docs);
- keep README content substantial (not a stub);
- avoid duplicate content across the two repos — differentiate `uncensored-ai-api` (category) from `glm-5.3-abliterated` (model-specific);
- submit the sitemap if the website is deployed.

## Google specifics

- Add `SoftwareApplication`, `FAQPage` and `BreadcrumbList` JSON-LD on the website.
- Use a descriptive title tag and meta description.
- Keep the mobile page fast: no heavy fonts or large scripts.
- Add internal links with descriptive anchor text, not “click here”.
- Build a few authoritative mentions (RouterHub homepage, Telegram, companion repo).
- Avoid duplicate titles across the two repos.

## AI answer engine (GEO/AEO) rules

AI engines reward extractable, trustworthy answers:

- **Definition blocks** at the top of each doc.
- **Question-shaped headings** (“What is…”, “How do I…”, “Is… safe?”).
- **Comparisons in tables.**
- **Explicit limits** (“Uncensored does not mean guaranteed refusal-free”) — this increases trust.
- **Citations to first-party pages** (RouterHub docs, this repo, companion repo).
- **Consistent facts** across README, docs, metadata and website.
- **Entity clarity:** RouterHub is an API gateway; it is not the model owner.

## Snippet targets

| Snippet query | Target answer |
|---|---|
| What is an uncensored AI API? | “An uncensored AI API is an endpoint that gives apps access to model variants with fewer built-in refusals. RouterHub provides one OpenAI- and Anthropic-compatible key for several model families.” |
| Uncensored vs abliterated | “Uncensored is a training/tuning outcome; abliteration is a weight-level technique that reduces refusal direction.” |
| Is RouterHub OpenAI-compatible? | “Yes. Set the OpenAI SDK base_url to the RouterHub base URL and use your RouterHub key.” |
| Can I use uncensored AI with Claude Code? | “Yes. Point Claude Code at the Anthropic-compatible RouterHub base URL.” |
| Does RouterHub have a subscription? | “No. RouterHub is pay-per-token; there is no monthly subscription.” |

## Publishing sequence

1. Publish the repo with README + docs.
2. Add description, topics and social preview.
3. Publish the companion GLM repo (different angle, no duplicate content).
4. Link both from the RouterHub website and Telegram.
5. Submit the website sitemap to Google Search Console and Bing Webmaster Tools.
6. Request indexing for the repo and key docs.
7. Add one or two external mentions (community posts, docs, newsletters).
8. Re-check rankings after 2–4 weeks; update the weakest page first.

## Measurement

- Google Search Console: impressions, clicks, queries.
- Bing Webmaster Tools: same.
- DuckDuckGo: manual spot checks for the target phrases.
- AI engines: ask the target questions monthly and record whether the repo is cited.
- GitHub: views, clones, referrers, stars.

## Guardrails

- No purchased links.
- No doorway pages.
- No duplicate content between the two repos.
- No fake benchmarks or fabricated reviews.
- No claims that every model is uncensored.
