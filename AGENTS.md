# VibeScale Docs — Agent Instructions

Documentation site for [VibeScale](https://app.vibescale.run), built on [Mintlify](https://mintlify.com).

## Local preview

```bash
mint dev          # preview locally
mint broken-links # check for broken links
```

## Structure

- `docs.json` — Mintlify config (navigation, theme, i18n, integrations)
- `*.mdx` / `*/*.mdx` — pt-BR pages (primary locale, lives at root)
- `en/**/*.mdx` — English pages (mirror of pt-BR tree under `en/`)
- `logo/`, `images/`, `favicon.svg` — static assets

## Language policy

- **pt-BR is the source of truth.** All new pages are written in pt-BR first.
- **en/ is a translation mirror.** Every pt-BR file has a corresponding `en/` file. When you create or update a pt-BR page, update the matching `en/` page in the same commit.
- MDX structure (components, frontmatter keys, hrefs) stays identical across locales — only human-readable values are translated.
- `en/` hrefs use the `en/` path prefix (e.g., `/en/security/overview`, not `/seguranca/visao-geral`).

## Terminology

| pt-BR | English |
|-------|---------|
| Achado(s) | Finding(s) |
| Análise de Oportunidade / OSR | Opportunity Analysis / OSR |
| Autoral(is) | Authored |
| Herdado(s) | Inherited |
| Ruído | Noise |
| Verificação de Segurança | Security Check |
| Relatório de Segurança | Security Report |
| Grade | Grade (keep as-is, A–E letter scale) |
| Re-Check | Re-Check (keep as-is) |
| Alinhamento | Alignment |
| Carteira de créditos | Credits wallet |
| Caixa de Entrada | Inbox |
| Kanban de tarefas | Task Kanban |

## Public information filter

**ALWAYS ask: "Should the public know this?"** before writing any content.

Never document:
- Admin or owner-only pages (`/admin/*`, `/owner/*`)
- Edge function names, Supabase internals, or pipeline architecture
- LLM prompts or scoring weights beyond what is shown in the UI
- GitHub Actions internals or CI/CD pipeline details
- Any credentials, secrets, or environment variable values
- Internal tooling used only by the VibeScale team

Document only what a paying customer or prospect would interact with directly.

## Style

- Active voice, second person ("you")
- One idea per sentence
- Sentence case for headings
- Bold for UI elements: Click **Settings**, then **Save**
- No filler phrases like "As you can see" or "It's worth noting"
- Product name: **VibeScale** (capital V, capital S, one word)
- App URL: `app.vibescale.run` — docs URL: `docs.vibescale.run`
- Support email: `suporte@vibescale.run`

## Mintlify components

Use built-in components generously — they render properly in both locales:

- `<Note>` / `<Tip>` / `<Warning>` / `<Info>` — callout boxes
- `<Steps>` / `<Step>` — numbered procedures
- `<Card>` / `<CardGroup cols={2}>` — visual navigation and feature grids
- `<AccordionGroup>` / `<Accordion>` — expandable Q&A
- `<Frame>` — screenshots and images with border

## Navigation

If you add a new page, register it in `docs.json` under the correct group in **both** the `pt-BR` and `en` language entries. pt-BR paths have no prefix; `en` paths are prefixed with `en/`.
