# XGate Check

Self-hosted network diagnostics for **XGate VPN** support.

- **Upstream:** [jason5ng32/MyIP](https://github.com/jason5ng32/MyIP) (MIT)
- **GitHub:** https://github.com/WormAlien/xgate-check
- **Prod URL (planned):** https://check.xgate.online
- **Wiki:** `wiki/deliverables/CheckXGate — self-hosted diagnostics.md` (vault)

## Why

Client opens check page **with VPN on** → one screen with exit IP, country, DNS/WebRTC leak, latency, speed. Support: «открой check.xgate.online → скинь отчёт».

## Quick start (upstream image)

```bash
cp .env.example .env
# optional: MaxMind free keys → better geo
docker compose up -d
# → http://localhost:18966
```

## XGate roadmap (this fork)

1. Rebrand (black/white, logo, site name)
2. Badge «Active XGate node?» by exit IP ranges (SPB/NL/DE/FI/CH)
3. «Copy support report» button
4. Connectivity targets → xgate.online + node hostnames
5. Deploy: Caddy on NL/CH → `check.xgate.online`

Do **not** host on the primary SPA exit if it loops timing tests through the same node.

## Remotes

```text
origin   → https://github.com/WormAlien/xgate-check.git
upstream → https://github.com/jason5ng32/MyIP.git
```

Sync:

```bash
git fetch upstream
git merge upstream/main
```

## Related (fleet CLI, not this product)

Internal SSH/node probes live in the vault monorepo (`scripts/xgate_net_probe.py`) — ops tooling for nodes, not the client-facing check page.
