# Entity: MiniMax

**What:** Chinese lab; M-series models. Used in Greg's stack for all auxiliary slots (compression, titles, vision, etc.).

**Why it matters to Greg:**
- Config migrated 2026-11-05: all text aux slots + provider default → MiniMax-M3.1-Flash (latest, Oct 19); vision → MiniMax-M3 (multimodal flagship). Same key/endpoint — name-only swap.
- The M3 swap fixed the broken vision pipeline (screenshots now read in seconds).

**Key facts:**
- Model line: M2.1 → M2.5 → M2.7 (Mar 2026) → M3 (Jun 2026, native multimodal, 1M ctx) → M3.1-Flash (Oct 19, 2026).
- Live API serves: M3.1-Flash, M3, M2.7(-highspeed), M2.5(-highspeed), M2.1 (verified Nov 5).
- Old vision model M2.5 was the cause of the Nov 5 screenshot-reading failure (30+ min OCR workaround).

**Cross-references:** `sources/model-audit-pricing`, `concepts/llm-wiki` (the infra this enabled).
