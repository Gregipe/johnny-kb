---
source: https://substack.com/home/post/p-193459470
title: "Andrej Karpathy Just Showed Us How to Build an AI Second Brain. Here's How to Do It."
author: Matt Paige (AI for the Rest of Us)
date-sent: 2026-11-06
sent-by: Greg (WhatsApp link)
---

# LLM Wiki pattern (Karpathy)

The AI incrementally builds and maintains a persistent, interlinked wiki of markdown files instead of re-reading raw documents per query (RAG). Three layers: raw sources (immutable), the wiki (AI-owned markdown), the schema (rules file). Karpathy: "Obsidian is the IDE. The LLM is the programmer. The wiki is the codebase."

Key quote: "Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass."

Workflows: ingest source → update entity/concept pages, flag contradictions; query with citations; lint for contradictions/orphans/stale claims.

Original gist: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
