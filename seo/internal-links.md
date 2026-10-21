# Internal Linking Map

Use descriptive anchors. Every doc links back to the README and to the next logical step.

## Hub

`README.md` links to:

- every doc in `docs/`
- the companion `glm-5.3-abliterated` repo
- RouterHub website, Telegram channel and bot
- the `ai-jailbreaks` repo

## Doc links

| From | To | Anchor |
|---|---|---|
| README | `docs/01` | What is an uncensored AI API? |
| README | `docs/02` | Uncensored vs. abliterated models |
| README | `docs/03` | Model catalog |
| README | `docs/04` | Quickstart |
| README | `docs/05` | OpenAI-compatible API |
| README | `docs/06` | Anthropic-compatible API |
| README | `docs/07` | Claude Code, Cursor, OpenCode, Codex |
| README | `docs/08` | Pricing and limits |
| README | `docs/09` | Use cases |
| README | `docs/10` | Safety and responsible use |
| README | `docs/11` | FAQ |
| README | `docs/12` | Glossary |
| README | `docs/13` | Troubleshooting |
| README | `docs/14` | API reference |
| README | `docs/15` | Alternatives |

## Cross-links between docs

- `01` → `02`, `03`, `04`, `10`
- `02` → `01`, `03`, `10`, `11`
- `03` → `04`, `05`, `06`, `08`, `13`
- `04` → `05`, `06`, `07`, `13`
- `05` → `06`, `07`, `13`, `14`
- `06` → `05`, `07`, `14`
- `07` → `04`, `05`, `06`, `13`
- `08` → `03`, `09`, `13`
- `09` → `03`, `08`, `10`
- `10` → `09`, `11`, `13`
- `11` → `01`, `02`, `04`, `07`, `08`, `10`
- `12` → `01`, `02`, `11`
- `13` → `04`, `11`, `14`
- `14` → `05`, `06`, `13`
- `15` → `03`, `08`, `10`

## Companion repo links

- `uncensored-ai-api` → `glm-5.3-abliterated`: “GLM 5.3 abliterated or uncensored guide”
- `glm-5.3-abliterated` → `uncensored-ai-api`: “uncensored AI API or model access”
- Both → `ai-jailbreaks`: “prompt research collection”

## Rules

- One contextual link per concept per page is enough.
- Do not repeat the same anchor dozens of times.
- Use the target page’s primary keyword as the anchor.
- Link to the companion repo only where it is genuinely relevant (GLM, uncensored models, model selection).
