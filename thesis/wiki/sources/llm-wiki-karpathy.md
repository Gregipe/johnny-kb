# Source: LLM Wiki pattern — Karpathy / Matt Paige

**Title:** "Andrej Karpathy Just Showed Us How to Build an AI Second Brain. Here's How to Do It."
**Author:** Matt Paige ("AI for the Rest of Us")
**Date:** Nov 2026 (sent by Greg 2026-11-06)
**URL:** https://substack.com/home/post/p-193459470

## Thesis
RAG-style per-query retrieval is broken for knowledge that must accumulate. The fix: an AI-maintained, interlinked markdown wiki with three layers (raw sources / AI-owned wiki / schema), where ingestion updates entity and concept pages, flags contradictions, and compounds.

## Key claims (with dates)
- LLM Wiki vs RAG: sources get integrated into a persistent wiki rather than chunked-and-embedded; queries hit pre-built pages with citations (2026-11-06).
- "Humans abandon wikis because the maintenance burden grows faster than the value" — Karpathy (Oct 2026).
- One ingested source updates 5-15 wiki pages — the compounding effect.
- Health checks: lint for contradictions, orphans, stale claims.

## Data points cited
- Author ingested 56 of his own Substack articles in ~1 hour → 56 interconnected wiki pages.
- Setup time claimed: ~15 minutes with Claude Code + Obsidian.

## Entities mentioned
- Andrej Karpathy (`entities/andrej-karpathy`)
- Claude Code / Anthropic (`entities/anthropic`)
- Obsidian (markdown vault + graph view + web clipper)

## Connections
- Concept page: `concepts/llm-wiki`
- Related frames: `concepts/commanding-heights` (data flywheel), Mostaque's (`entities/emad-mostaque`) Intelligence Inversion (`concepts/intelligence-inversion`).
