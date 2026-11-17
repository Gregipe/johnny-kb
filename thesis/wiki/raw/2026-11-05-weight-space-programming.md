---
source: Screenshot sent by Greg 2026-11-05 (X post by Alex @Alex_tra_memory, FluidInference; quoted post by Jacob Lauritzen, Legora CTO)
title: "Weight-space programming — hand-written neural nets (CiteNet)"
date-sent: 2026-11-05
sent-by: Greg (screenshot, read via MiniMax-M3 vision after fix)
---

# Weight-space programming post (digest)

Content: Claude Fable hand-wrote every weight of a legal-citation checker neural network — zero training. Compiled to CoreML, runs on Apple Neural Engine.

Numbers (web-verified against Hugging Face model card FluidInference/citenet-coreml):
- 397,250-param net, 13,871 non-zero weights, written by the model.
- LePhantomCite held-out: 31/31 fakes caught, 1/983 real flagged.
- ~50 µs per citation; ~1.8M citations/sec on M5 Pro; 3.3 GB case law in 2.3 s.
- Quoted (Jacob Lauritzen): hand-written 100K-param net 97.8% test accuracy vs trained 76.5–94.6% (trained on up to 8,192 examples).

Why it matters: frontier models can author specialised working networks by pure reasoning — better than trained ones, on-device, private, free to run. Follows MIT CSAIL's weight-space programming work. Early demo, narrow task — but the first convincing evidence of a new way models get built.
