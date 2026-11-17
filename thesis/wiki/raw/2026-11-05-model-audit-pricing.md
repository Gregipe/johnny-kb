---
source: Conversation research 2026-10-31/11-05 (web searches: Artificial Analysis, vendor rate cards, Epoch)
title: "Model audit & pricing data — Oct/Nov 2026"
date-sent: 2026-10-31 (Greg asked for audit of open-weights + frontier models)
sent-by: Greg
---

# Model audit & pricing (Oct-Nov 2026)

AA Intelligence Index v5 (as of ~Oct 27-Nov 4, 2026):
- Claude Opus 5.5: 58 · Claude Sonnet 5.5: 56 · Kimi K3.1 Pro: 55 · Gemini 4 Argon: 53 · Claude Fable 5.1: 53 · GPT-6 Astra: 53 · GPT-6.1 Sol: 52 · GPT-6.1 Terra: 51 · DeepSeek V4 Pro 0813 (max): 53 · DeepSeek V4 Flash 0731: 52 · DeepSeek V4 Pro (April, max): 45.

Pricing ($/M in/out, standard):
- GPT-6 Astra & Claude Fable 5.1: $10/$50 (worst value — below Sonnet 5.5 at 5x price)
- Claude Opus 5.5: $4/$20 · Gemini 4 Argon: intro $2/$10 until Nov 30 → $4/$20
- Claude Sonnet 5.5 / GPT-6.1 Sol: $2/$10 · Kimi K3.1 Pro API: $2/$10 (open weights Nov 4)
- GPT-6.1 Terra: $1/$5 ($0.05 cached) · DeepSeek V4 Pro 0813: $0.66/$1.98 off-peak, ×2 peak, $0.022 cached
- DeepSeek V4.1 Flash 1017: $0.30/$1.20 · GPT-6 Luna: $0.10/$0.50

Verdicts (Greg's audit): best capability-per-rupee = Kimi K3.1 Pro + Claude Sonnet 5.5; budget = GPT-6.1 Sol; volume = DeepSeek V4.1 Flash; Astra/Fable are trophy pricing.
Stack note: `deepseek-v4-pro` endpoint serves the 0813 build since Aug 16 (silent swap, no ID change). MiniMax aux slots moved M2.5 → M3.1-Flash, vision → M3 on 2026-11-05.
