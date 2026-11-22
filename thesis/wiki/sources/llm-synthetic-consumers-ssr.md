# LLM Synthetic Consumers via Semantic Similarity Rating (SSR)

- Type: research paper (arXiv 2510.08338, PyMC Labs × Colgate-Palmolive)
- Ingested: 2026-11-22 (sent by Greg)
- Raw: raw/2026-11-22-llm-synthetic-consumers-ssr.md
- Concepts: [synthetic-consumers](../concepts/synthetic-consumers.md)

## Thesis

LLMs can serve as valid synthetic consumers for purchase-intent concept testing — but ONLY with textual elicitation + semantic-similarity rating (SSR), never direct numeric elicitation. SSR recovers ~90% of human test-retest reliability and realistic response distributions (KS similarity > 0.85) across 57 real personal-care surveys (9,300 humans).

## Key claims (dated)

- 2025-10 (paper): Direct Likert elicitation makes LLMs regress to the scale center ("3"); almost never 1 or 5; distributions unrealistically narrow (KS 0.26-0.39).
- 2025-10: SSR = free-text response → embedding → cosine similarity to 5 anchor statements → probability distribution over Likert scale. GPT-4o: ρ=90%, KS=0.88. Gemini-2.0-flash: ρ≈90%, KS=0.80.
- 2025-10: Correlation attainment (ρ = synthetic-human Pearson R ÷ human test-retest ceiling) is the right benchmark — the ceiling is human noise, not truth.
- 2025-10: Demographics are load-bearing: without persona prompting, distributions look human-like (KS 0.91) but ρ collapses to 50% — synthetic panels that "look realistic" can still carry no ranking signal.
- 2025-10: Synthetic consumers mirror human age/income response patterns (concave age curve; budget-stress → lower purchase intent).
- 2025-10: Free-text elicitation yields qualitative consumer feedback as a byproduct.
- Caveat: single category (personal care), single market (US), Colgate-Palmolive data.

## Data points

- 57 surveys, 9,300 human responses, 150-400 per survey, 5-point purchase-intent Likert.
- Human mean purchase intent: 4.0 ± 0.1 (narrowly distributed, skewed positive).
- Direct-Likert KS similarity: 0.26 (GPT-4o), 0.39 (Gem-2f).
- SSR KS similarity: 0.88 (GPT-4o), 0.80 (Gem-2f).
- No-demographics control: KS 0.91 but ρ≈50% vs 92% with demographics (Gem-2f).

## Connections

- Hunar conduit: voice/WhatsApp conversational channel could run synthetic consumer testing at cents per concept vs lakhs for panels — a monetization angle on the conduit + interaction data (see intelligence-inversion).
- Indian SMB angle: small brands can't afford panels; synthetic concept testing in vernacular = productizable demand-validation for the SMB segment (see smb-needs-comparative, smb-ai-capability-gap).
- Method generalizes beyond surveys: any pipeline that needs a score/distribution from an LLM should elicit text + map via anchors, not ask for numbers. Same family as structured-output fixes (see weight-space-programming / llm-wiki).
- Epistemics: "looks realistic" ≠ signal. Validation must test RANKING correlation against ground truth, not distributional similarity alone.
