# AI Angle & Scalability Architecture — Metabolic Transformation Play (Oct 18, 2026)

Follow-up to /root/thesis/health-india-opportunity-2026-10.md. Question: what is the AI/tech angle, and
how does this become extremely scalable instead of a services model?

## The core inversion: productize the coach, don't rent coaches

Traditional health = services (human coaches), capped by people. The inversion: the AI IS the coach;
humans become exception handlers and trust anchors. Scale limit moves from headcount to compute.

## Layer 1 — AI coaching engine (the product)

- WhatsApp voice/text daily check-ins: Hindi/English voice agent (Hunar's exact infra: Baileys voice
  notes, STT via Scribe/Whisper, TTS incl. open-source Drama 3 etc.). India ignores app notifications;
  it answers voice notes.
- The copilot loop: intake → daily nudges (protein, workouts, sleep, med adherence) → weekly plan
  adaptation from longitudinal data → escalation rules (red flags, stalls >2wk, non-adherence).
- Multi-modal inputs: voice notes → structured logs; food photos → macro estimation (vision LLM);
  wearables (Google Fit/Health Connect); InBody scan CSV → trend analysis; labs via partner APIs/OCR.
- Guardrails (from ARA's voice-safety experience): hard-coded escalation rules, no free-form clinical
  claims, every medical statement sourced to physician-approved protocol templates, doctor-in-loop.

## Layer 2 — Physician copilot (how the network scales)

- Doctors stay the Rx layer (GLP-1 legality) and trust layer. AI drafts: intake summaries, progress
  reports, dose-adjustment suggestions, flag lists. Doctor review = minutes not hours.
- One physician handles 10x patients through the platform → the network is not a favor you ask, it's a
  throughput machine you offer. Doctors get pre-screened, protocol-ready, paying patients.
- The hospital/clinic gets an outsourced adherence layer — the #1 reason GLP-1 scripts fail is drop-off.

## Layer 3 — Data flywheel (the real moat)

- Every member generates outcomes data: adherence, body-comp deltas (DEXA/InBody), lab deltas, protocol
  variants. Structured capture = the first India-scale metabolic transformation dataset (incl. the
  GLP-1 + muscle-preservation cohort nobody has yet).
- Predictive models: who stalls, who rebounds, who needs escalation — intervene before churn.
- Protocol IP compounds: data → better protocols → better outcomes → more customers.

## Layer 4 — Scalable distribution

- B2B2C: corporate wellness budgets (one deal = hundreds of members; AI delivery means CAC doesn't scale
  with headcount). Insurance partnerships later (wellness-linked premiums already emerging).
- Pharma: GLP-1 makers need adherence/retention programs (global playbook: Noom Med, WW Clinic). India
  has no one doing this yet. Generic makers will fight on price — adherence programs are their retention
  weapon.
- Clinics/hospitals: prescription → program handoff.
- Greg's LinkedIn → authority content → inbound B2B2C.

## Unit economics flip (vs services model)

- AI coach cost/member/month: LLM + STT/TTS + infra ≈ tens of rupees; human coach minutes/member <10-15
  at mass tier (vs ~1:50-100 ratio humans-only → 1:300-500 AI-first).
- No owned clinics/gyms: partner scan points (InBody/DEXA rev-share), partner coaches directory.
- Target gross margin 60-70% (services models stuck at 30-40%). Biopeak's trap is per-customer clinic
  capital; ours is per-customer compute, trending to zero.

## Product positioning: "the copilot, not the clinic"

Sell the verified outcome (fat lost, muscle kept, scan-proven) not service hours. Tiers: mass
₹2-4K/mo cohort (AI + community + monthly scan), affluent ₹8-15K/mo (AI + physician + quarterly DEXA +
human escalation), HNI concierge later.

## Honest risks

- AI in health = zero tolerance for hallucination. Safety architecture is the product, not a feature.
  Stay in coaching/nutrition/fitness scope legally; prescriptions remain with physicians.
- Engagement is the hard part and the prerequisite for the data flywheel — but that's the one thing
  Hunar already does well.
- Multi-tenant platform quality bar: the copilot must feel personal at 10K members, not templated.

## Sequencing

1. v1: program + AI coach + human escalation in one metro (Kerala/Telangana metabolic hotspot).
2. v2: physician copilot + corporate B2B2C + pharma adherence partnerships.
3. v3: platform/API — license the copilot to other clinics, hospitals, gyms chains.
