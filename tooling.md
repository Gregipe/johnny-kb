# Tooling manifest — what runs where, and why

Rule: applications are installed **per-host by role**. Nothing is blanket-synced across hosts.
Intent (this file) is shared; installs are applied per-host by Johnny. Never install a
server-only app on the Mac or vice versa without updating this file.

## Mac (workstation — GUI, browser tools, local editing)

- Hermes CLI/TUI (johnny + other profiles)
- LaunchAgents: `com.greg.johnny-kb-sync` (:15), `com.greg.johnny-skills-sync` (:45)
- SSH keys: `id_github` (GitHub user key); `id_ed25519` = ara-vps box key (not for GitHub)
- WhatsApp bridge: **intentionally NOT running** — the server owns the WhatsApp session;
  starting it on the Mac kicks the server bridge (same session creds)
- Browser automation, Apple-ecosystem tools

## Hetzner VPS 46.224.132.99 (headless, always-on)

- Hermes gateway + WhatsApp bridge + cron (systemd: `hermes-gateway-johnny`)
- ARA stack: ara-server :8766, voice bot.py :7860
- Caddy reverse proxy (dashboard :8081), ufw
- Crontab (root): kb-sync :00, skills-sync :30, ara-backup daily 03:00
- SSH key: `johnny-kb` (GitHub user key, valid for any repo)

## Sync infrastructure (both hosts)

- **johnny-kb** (public): thesis / commitments / trips. Hourly, pull-before-push.
  Server :00, laptop :15.
- **johnny-skills** (private): only `~/.hermes/profiles/johnny/skills/` — profile root is
  gitignore-hardened so secrets/state can never stage. Hourly. Server :30, laptop :45.
- Scripts: `/root/kb-sync.sh`, `/root/skills-sync.sh` (server); `~/kb-sync.sh`,
  `~/skills-sync.sh` (laptop). Logs: `/var/log/*-sync.log` (server),
  `~/Library/Logs/*-sync.log` (laptop).
- Conflict rule: abort + log + retry next hour; resolved manually by Johnny
  (last-writer-wins by mtime when deciding between sides).
- Commit convention: `<side> <timestamp>`.
