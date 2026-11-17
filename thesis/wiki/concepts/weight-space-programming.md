# Concept: Weight-Space Programming

**Definition:** Frontier models authoring the weights of specialised neural networks directly by reasoning — no training data, no backpropagation — producing small, fast, auditable, on-device models that can outperform trained ones on narrow tasks.

**Provenance:**
- Jacob Lauritzen (Legora) X post Nov 3; Alex (FluidInference) replication Nov 4. Source: `sources/weight-space-programming`.
- Preceded by MIT CSAIL's weight-space programming paper (2026).

**Core claims:**
1. Claude (`entities/anthropic`) hand-wrote a 100K-param legal-citation classifier: 97.8% vs 76.5–94.6% trained (Nov 2026).
2. Compiled to Apple Neural Engine: 50 µs/cite, 1.8M cites/s, fully private (Nov 2026).
3. The model becomes a compiler — specialised intelligence gets authored on demand (Nov 2026).

**Caveats:** demonstrated on narrow, rule-heavy tasks so far; not proven for open-ended problems (as of Nov 2026).

**Why it matters to Greg:**
- On-device SLMs for the voice stack just became far more viable (edge STT/turn-detection layer).
- One more force shrinking the labs' moat → strengthens the `concepts/commanding-heights` play: value in problem/data/trust ownership, not models.
