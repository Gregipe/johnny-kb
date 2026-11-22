# LLMs Reproduce Human Purchase Intent via Semantic Similarity Elicitation of Likert Ratings

- URL: https://arxiv.org/pdf/2510.08338 (v3, 27 Oct 2025)
- Authors: Benjamin F. Maier, Ulf Aslak, Luca Fiaschi, Nina Rismal, Kemble Fletcher, Christian C. Luhmann, Robbie Dow, Kli Pappas, Thomas V. Wiecki (PyMC Labs + Colgate-Palmolive)
- Sent by: Greg, 2026-11-22
- Status: ingested → sources/llm-synthetic-consumers-ssr.md, concepts/synthetic-consumers.md

## Digest

Problem: consumer research costs billions/yr; LLM synthetic panels attractive, but LLMs asked directly for Likert ratings (1-5) regress to "3" — narrow distributions, almost never 1 or 5, unrealistic confidence.

Method (SSR): prompt LLM personas with demographic attributes + product concept image; elicit FREE TEXT purchase-intent statements; embed them (OpenAI text-embedding-3-small); map to a 5-point distribution via cosine similarity against 5 anchor statements (one per Likert point). Probability of each rating ∝ similarity to its anchor.

Data: 57 personal-care product concept surveys by Colgate-Palmolive (9,300 US respondents, 150-400/survey). Models: GPT-4o, Gemini-2.0-flash. Temperature 0.5-1.5 (little effect).

Results:
- Direct Likert (DLR): correlation attainment ρ≈80% but KS distribution similarity 0.26-0.39 (bad).
- Follow-up Likert (FLR, LLM-as-Likert-expert): ρ 85-90%, KS 0.59-0.72.
- SSR: ρ≈90% of maximum attainable correlation (human test-retest ceiling), KS 0.88 (GPT-4o) / 0.80 (Gem-2f). Realistic distributions recovered.
- Demographics are load-bearing: with age/income personas, synthetic consumers mirror human response patterns (concave age curve; budgetary-stress personas rate lower). WITHOUT demographics: distributions look human (KS 0.91) but correlation attainment collapses to ρ≈50% — models rate everything positively and lose product-ranking signal. Looks right, ranks wrong.
- Free-text responses double as qualitative feedback for free.
- Caveat: one category (personal care), one market (US), one corporation's data.
