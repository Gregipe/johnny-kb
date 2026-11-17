# Concept: LLM Wiki

**Definition:** A persistent, interlinked set of AI-maintained markdown pages that compounds over time, replacing per-query RAG. Raw sources are immutable; the wiki layer is AI-owned; a schema file governs structure and workflows.

**Provenance:**
- Introduced by Andrej Karpathy (`entities/andrej-karpathy`) on X, late Oct 2026 (gist: karpathy/442a6bf5).
- Popularised for practitioners by Matt Paige, "AI for the Rest of Us" Substack, Nov 2026. Source: `sources/llm-wiki-karpathy`.

**Core claims:**
1. RAG is stateless per query; wikis accumulate — the wiki is the compounding asset (2026-11-06).
2. Maintenance burden, not comprehension, is why humans abandon knowledge bases; LLMs maintain for free (2026-11-06).
3. Contradiction-flagging and cross-referencing are the differentiators vs. plain note-taking (2026-11-06).

**Why it matters to Greg:**
- Direct implementation substrate for his standing rule: "hold what I'm reading, connect the dots."
- Editorial-brain use case maps to his LinkedIn 100K content engine — essays become interlinked, citable, compounding assets.
- Aligns with Commanding Heights thesis: the wiki is the data flywheel ("inventory of activity") that compounds while models commoditise. See `concepts/commanding-heights`.

**Implementation state (2026-11-06):**
- Scaffolded at /root/thesis/wiki with WIKI.md schema; this page is source #1 dogfooding.
- Backlog cleared 2026-11-06: `sources/commanding-heights`, `sources/the-last-economy`, `sources/financial-freedom-essay`, `sources/model-audit-pricing`, `sources/india-labour-market`, `sources/anthropic-s1` — all ingested (see `index.md`).

**Contradictions/variants:**
- vs. Hermes memory/skills: memory is tiny and always-on; skills are procedural. The wiki adds unbounded, interlinked, citable knowledge synthesis. Complementary, not competing.
