# WIKI.md — Greg's Knowledge Wiki Schema

This wiki follows the LLM Wiki pattern (Karpathy, Oct 2026). It is maintained by Johnny (the Hermes agent), not by hand.

## The Three Layers

1. **raw/** — Immutable source documents: clipped articles, links, transcripts, PDFs. The agent reads these; never modifies them. Every source gets a short provenance header on ingest (url, date, who sent it).
2. **wiki pages** — AI-owned, AI-maintained markdown in `entities/`, `concepts/`, `sources/`, `explorations/`. Humans read; the agent writes.
3. **This schema** — The rules the agent follows when ingesting, answering, or linting.

## Page Types

- **sources/<slug>.md** — One page per ingested source: title, author, date, URL, thesis, key claims, data points cited, entities mentioned, contradictions with existing pages.
- **entities/<slug>.md** — One page per durable thing: company, person, product, model. Sections: What it is, Why it matters to Greg, Key facts (with dates), Cross-references, Open questions.
- **concepts/<slug>.md** — One page per idea/frame: definition, provenance (which sources introduced it), how it connects to Greg's ventures, contradictions/variants.
- **explorations/<slug>.md** — Substantial answers/syntheses Greg asked for, filed for reuse.

## Ingest Workflow (when Greg sends a link, document, or article)

1. Save the source (or its extraction) into `raw/` with provenance header.
2. Read it. Write/update `sources/<slug>.md`.
3. Create/update every `entities/` and `concepts/` page it touches.
4. Flag contradictions: note "supersedes" / "conflicts with" with dates, cross-link both pages.
5. Update `index.md` (list of all pages + last-touched dates).
6. Report to Greg: what changed, what connects to his existing map, one line.

## Query Workflow

Answers synthesise from wiki pages first, cite pages in the reply, and file substantial new syntheses into `explorations/`.

## Lint Workflow (weekly cron)

Scan for: contradictions, orphan pages, stale claims superseded by newer sources, missing cross-references. Report by severity; fix the mechanical ones.

## Conventions

- Filenames: lowercase, hyphenated slugs.
- Every claim in wiki pages carries a source page reference and date.
- Keep pages dense and current — the wiki is a working brain, not an archive.
- Language: English.
