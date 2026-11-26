# Hunar Dynamic Voice Agent — Design (v1, built 2026-11-26)

Personal outreach, not mass outreach: the same agent identity, a purpose-built context for every conversation, and a closed loop that turns captured requests into real action.

## Architecture

```
contact dossier (contacts/<slug>.json)
    + static identity block (persona rules)
    + recent history tail (call-log/<slug>.jsonl summaries)
    + per-call objective + extra context
        -> dynamic reference_information built per call
        -> Hunar POST /calls/ (agent_id fixed, guardrails 08:00-21:00 IST)
        -> call completes: result {summary, action_items} + recording_url
        -> `hunar-voice.py digest` downloads recording, transcribes locally (Scribe),
           appends transcript+summary to the contact's history
        -> next call for that contact is richer than the last (compounding loop)
```

## Principles

1. **One identity, many contexts.** The persona (John, Greg's CoS, English, no fabrication, no commitments without approval, repeat-back, short turns) is static. Regenerating it per call risks drift and buys nothing.
2. **The per-call dynamic layer is context, not personality.** Who is on the call, what the last conversation decided, what this call is for, what's still open. That is what makes a call feel personal.
3. **History is the moat.** Every call appends to the contact's history; the tail is injected into the next call's context. Call N+1 knows what call N decided. Mass dialers can't do this.
4. **Closed loop.** Captured requests must become actions in Johnny's real context (commitments tracker, chat follow-up). Capture without action is a dialer, not a chief of staff.

## Enrichment levers (per call)

- Open with the open thread, never a cold "one item" question when history exists.
- Hold ONE objective; don't present a menu.
- Recall what was already decided — never re-ask what the history answers.
- End with a concrete next step owned by a name and a time.

## Platform facts (verified against the live API)

- Guardrail window is 08:00–21:00 (API rejects 07:00 and 22:00).
- Org caller ID: +918031708403 (org default; GET /numbers/ returns empty for this org).
- The call object has NO transcript field — only result {summary, action_items} + recording_url (S3). Transcripts come from pulling the recording and transcribing locally.
- Custom variables are short per-call scalars; the persona/context block belongs in reference_information.
- Voice persona: SAM (Greg's pick). Agent id: a49669c6-59c6-41e7-a6de-61b2f636c60e (code GR04).
- Legacy agent_prompt/result_prompt format is removed 2027-01-15; we use the details format.

## Tool

`~/.hermes/profiles/johnny/scripts/hunar-voice.py` — contacts / call / status / digest.
Key from profile .env (HUNAR_VOICE_API_KEY), never in any repo.

## Next (v2, when Greg asks)

- Webhook receiver (call_summary) instead of manual digest — but needs a public HTTPS endpoint.
- Per-contact action routing: digest result -> commitments.md / chat action automatically.
- Barge-in and streaming partials are explicitly deferred; Hunar runs its own inference.
