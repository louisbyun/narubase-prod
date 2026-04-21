<div align="center">

<img src="logo.png" alt="PilotOPS logo" width="96" height="96" />

# PilotOPS™

**The local-first multi-cloud control panel for indie operators.**

One desktop app to manage your servers across Vultr, DigitalOcean, and more — with a built-in AI assistant, no subscription, and zero telemetry.

[![Status](https://img.shields.io/badge/status-pre--release-orange)]() [![License](https://img.shields.io/badge/license-Proprietary-blue)]() [![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey)]()

</div>

---

## Why PilotOPS™

If you're a solo maker, freelance DevOps, or running a small SaaS, you probably juggle 2–4 cloud provider dashboards. You want to see all your servers in one place, manage them quickly, and keep your data private. The existing options are either AWS-console-bloated enterprise tools or cloud-stored SaaS dashboards that ask for your API keys. Neither fits.

PilotOPS™ is a **lightweight desktop app** that runs entirely on your machine. Your cloud API keys live in your **OS keychain**. We never see your servers, your bills, or your data.

## Three things that make us different

🔒 **Local-only** — No cloud sync. No accounts. No telemetry. Ever. Everything you do stays on your machine.

💳 **One-time purchase** — **$99 lifetime** for v1.x. No subscription, no feature paywall, no nickel-and-diming.

🤖 **BYO AI key** — Bring your own Claude / OpenAI / Gemini API key. We never proxy your AI traffic, so you stay in control of cost and privacy.

## Features today

- **Unified server list** across Vultr and DigitalOcean — IP, region, status, OS, plan, $/month, all in one sortable table
- **Per-server detail panel** — vCPUs, RAM, disk, hostname, internal IP, tags, creation date
- **Total cost** at a glance — see your monthly spend across providers in the status bar
- **Local SQLite cache** — app opens instantly with last-known state, refreshes in the background
- **Auto-refresh every 5 minutes** — your view stays current without manual reloads
- **OS-keychain storage** — Windows Credential Manager / macOS Keychain / Linux Secret Service via the `keyring` crate
- **Multi-key Settings** — add / update / remove provider keys per cloud, with connection badges
- **Built-in Contact form** — feature requests and bug reports go straight to the developer
- **Cross-platform** — Windows (x64), macOS (Apple Silicon + Intel), Linux (x64)

## Coming soon

- 🚀 **SSH terminal with tabbed sessions** — click any server to open a real interactive shell, multiple at once
- 🤖 **AI assistant** — multi-provider, with confirm-before-execute on risky commands (`rm -rf`, `dd`, `DROP TABLE`, etc.)
- 💰 **Cost dashboard** — historical spend chart per cloud, per server
- ☁️ **More providers** — Hetzner and Linode in v1.1
- 🔐 **SSH key management** — generate, import, store keys in the OS keychain

## Privacy & security

- All data stored **locally** on your machine
- API keys go to your **OS keychain** (encrypted by your operating system)
- **No telemetry**, no analytics, no third-party SaaS
- **No external server** between you and your cloud provider — the app talks directly to provider APIs

The only network traffic the app makes:

| Destination | When | Why |
|---|---|---|
| Your cloud provider's API (api.vultr.com, api.digitalocean.com, …) | When you refresh / open the app | Fetch your server list and metadata |
| Your AI provider's API (Anthropic, OpenAI, etc.) | When you use the AI assistant | Forward your prompt + receive response |

That's it. No analytics endpoint. No license-server ping. No telemetry.

## Tech stack

| Layer | Technology |
|---|---|
| Desktop shell | Tauri 2 |
| Frontend | React 19 + TypeScript + Tailwind CSS v4 |
| Backend | Rust (`reqwest` + `rustls`, `keyring`, `rusqlite` bundled SQLite, `lettre` SMTP) |
| Bundle size | ~5–10 MB (vs ~150 MB for Electron equivalents) |

## Pricing

**$99 one-time purchase** for v1.x.

- Lifetime updates within v1
- Use on all your machines (per-user license)
- Major-version upgrade (v2, if/when released) at $39

No subscription. No "Pro tier". No usage caps.

## Status

**Pre-release (v0.1)** — actively under development. Installer downloads and the buy button are not yet live. Star this repo or [reach out](#contact) to be notified when v1.0 ships.

Installer files (`.exe`, `.dmg`, `.AppImage`) and the user manual will be published here in this repository as releases land.

## Contact

Feature requests, bug reports, beta access:
- **Email:** aiswingx.com@gmail.com
- **In-app:** Open PilotOPS™ → **Contact** tab

Built by **Louis Byun** · Powered by **ai Swing X™**

## License

PilotOPS™ binaries are proprietary, distributed under a one-time-purchase license. This repository contains marketing materials, screenshots, and downloadable installer artifacts only — **not source code**.

---

<div align="center">

© 2026 PilotOPS™ · Powered by **ai Swing X™**

</div>
