# johnny-kb

Greg's shared knowledge base — synced between the Hermes server and Greg's laptop via GitHub.

## Layout

- `thesis/` — research, thesis files, wiki (`thesis/wiki/`), commitments tracker (`thesis/commitments.md`)
- `trips/` — trip itineraries and travel records

## How sync works

**Server side** (automatic): a cron job runs `kb-sync.sh` every hour — pulls any laptop changes, commits and pushes any server changes.

**Laptop side** (manual, one line): after finishing research locally,

```bash
cd ~/johnny-kb && git pull --rebase && git add -A && git commit -m "laptop $(date +%F)" && git push
```

Or pull server changes only:

```bash
cd ~/johnny-kb && git pull --rebase
```

## Ground rules

- Never commit secrets, keys, tokens or `.env` files.
- Both sides pull before pushing; conflicts resolve in favour of the side that edits a file most recently — if in doubt, ask Johnny.
- The server is the source of truth for `thesis/commitments.md` (CoS check-ins edit it).
