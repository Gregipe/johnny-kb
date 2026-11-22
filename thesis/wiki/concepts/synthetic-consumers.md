# Synthetic Consumers

- First filed: 2026-11-22 (from sources/llm-synthetic-consumers-ssr.md)

## Definition

LLMs impersonating survey respondents — prompted with demographic attributes, shown the same stimulus (product concept), asked the same questions. Used to simulate consumer panels at near-zero marginal cost.

## Why it matters to Greg

1. It is a productizable capability on the Hunar conduit: conversational agents already collect demographic + preference context; running concept tests for consumer brands becomes a service, not just research. (2026-11-22)
2. It compresses the demand-validation loop for SMBs: a small Indian brand can test five package designs or pricing tiers in an afternoon for pennies instead of a panel it can't afford. Direct overlap with the SMB "get me found, chosen, answered" need. (2026-11-22)
3. It proves a methodological rule with broad applicability: LLMs give bad NUMBERS but good TEXT; elicit text, then map to numbers via embedding anchors. Any scoring/NPS/sentiment pipeline should follow SSR's pattern. (2026-11-22)

## Key mechanics (from SSR paper)

- Direct numeric elicitation fails: models regress to scale center, distributions unrealistically narrow.
- Working recipe: persona + stimulus → free-text response → embed → cosine similarity to one anchor statement per scale point → probability distribution over the scale.
- Demographics are load-bearing: without personas, distributions look realistic but ranking signal collapses (KS 0.91 yet ρ≈50%).
- Benchmark against the human test-retest ceiling, not truth: SSR hits ~90% of maximum attainable correlation; human panels are the noise ceiling.

## Open questions / to watch

- Does it replicate outside US personal care — especially Indian vernacular markets? Unvalidated as of 2026-11-22.
- Product-category generalization: purchase intent for FMCG may be easier than for durables/services.
- Brand-side adoption speed: Colgate-Palmolive is a co-author — corporates are already running this internally.

## Cross-references

- sources/llm-synthetic-consumers-ssr.md
- concepts/intelligence-inversion.md (interaction data as scarce asset)
- concepts/commanding-heights.md (own the conduit, sell the crossing)
- sources/smb-needs-comparative.md, sources/smb-ai-capability-gap.md (demand generation pain)
- concepts/llm-wiki.md (structured knowledge from unstructured LLM output)
