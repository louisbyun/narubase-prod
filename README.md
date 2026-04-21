<div align="center">

<img src="logo.png" alt="NaruBase Cloud logo" width="96" height="96" />

# NaruBase™ Cloud

**The local-first multi-cloud control panel with AI built in.**

One desktop app to manage your servers across Vultr, DigitalOcean, Hetzner, and Linode — with an AI assistant that can actually run commands (with your approval) right next to the terminal.

[![Version](https://img.shields.io/badge/version-1.0.0-success)](https://github.com/louisbyun/narubase-prod/releases/latest)
[![License](https://img.shields.io/badge/license-Proprietary-blue)]()
[![Platforms](https://img.shields.io/badge/platform-Windows-lightgrey)]()
[![Price](https://img.shields.io/badge/price-%2499%20one--time-0ea5e9)]()

### [⬇ Download for Windows](https://github.com/louisbyun/narubase-prod/releases/latest) · [📖 Install guide](INSTALL.md)

**14-day free trial, then $99 one-time. No subscription. Ever.**

</div>

---

<div align="center">
<img src="screenshots/servers.png" alt="NaruBase Cloud — Servers view" width="900" />
</div>

## Why NaruBase™ Cloud?

If you run servers on more than one cloud, you know the pain:

- **4 dashboards, 4 logins, 4 different UIs** to remember
- **No unified view** of what you own or what it costs per month
- AWS console is way too much. Lens / Portainer are Kubernetes-only. Termius only does SSH.
- Cloud-based control panels want your API keys **on their servers**. No thanks.

**NaruBase Cloud** is a lightweight desktop app that runs entirely on your machine. Your cloud API keys live in your **OS keychain**. Your SSH keys never leave your device. We never see your servers, your bills, or your data.

## Three things that make us different

🔒 **Local-only** — No cloud sync. No accounts. No telemetry. Ever.

💳 **One-time purchase** — $99 lifetime for v1.x. No subscription. No feature paywall. No "Pro tier".

🤖 **AI that actually does things** — Bring your own Claude / GPT / Gemini key. The AI sits beside the terminal, knows your current server, and can execute commands (with your explicit approval) without you copy-pasting.

---

## Features

### 🌩 Multi-cloud server list

Four clouds, one sortable table. See IP, region, status, OS, plan, and monthly cost at a glance.

**Supported providers:** Vultr · DigitalOcean · Hetzner Cloud · Linode (Akamai)

<div align="center">
<img src="screenshots/servers.png" alt="Unified server list across providers" width="800" />
</div>

---

### 🖥 SSH terminal with AI Assist beside it

Click any server → a full interactive terminal opens in its own window. Paste passwords, run commands, use `vim` and `htop` just like any shell. **And on the right side, the AI sees which server you're on and can help — live.**

<div align="center">
<img src="screenshots/terminal_ai.png" alt="Terminal with AI Assist sidebar" width="900" />
</div>

The AI Assist panel can:

- Answer questions in context of the current server (`"why is disk full on this box?"`)
- **Run diagnostic commands for you** — `df -h`, `ps aux`, `journalctl` — with a Run/Skip button on every single call
- Highlight destructive commands (`rm -rf`, `mkfs`, `shutdown`) in red with an extra confirmation
- Suggest fixes and offer a **→ Terminal** button to inject the command into your live shell
- Cap at 5 iterations so the AI never runs wild

Three color themes (Slate / Sky / Mint / Lavender / Peach), three font sizes, two layouts (Right / Bottom).

---

### ⚙️ Bring-your-own AI key

Add your Claude, GPT, or Gemini API key once. The app talks to the provider directly — we don't proxy your traffic or charge per-token. You pay the provider. We charge $99 once for the software.

<div align="center">
<img src="screenshots/settings.png" alt="Settings — cloud and AI providers" width="800" />
</div>

---

### 🔐 Local license, offline verification

Purchase → get your license key by email → paste it into the app. Ed25519-signed, verified offline. No phone-home. No license server that can die and lock you out.

<div align="center">
<img src="screenshots/about.png" alt="About page with license status" width="800" />
</div>

---

## Privacy & security

- All data stored **locally** on your machine
- Cloud API keys and AI keys live in your **OS keychain** (Windows Credential Manager / macOS Keychain / Linux Secret Service)
- SSH private keys **never leave your device**
- **No telemetry.** No analytics. No third-party SaaS between you and your servers

The only network traffic NaruBase Cloud makes:

| Destination | When | Why |
|---|---|---|
| Your cloud provider's API (Vultr / DO / Hetzner / Linode) | When you open the app or refresh | Fetch your server list |
| Your AI provider's API (Anthropic / OpenAI / Google) | When you chat with the AI Assist | Forward your prompt + receive reply |
| `raw.githubusercontent.com/louisbyun/narubase-prod/...` | Once a day | Check for updates + license revocation list |

That's it. No analytics endpoint. No license-server heartbeat. No telemetry.

---

## How it works

1. **Install** — download the `.msi` and run it (`c:\Program Files\NaruBase Cloud`)
2. **Connect clouds** — paste your Vultr / DigitalOcean / Hetzner / Linode API tokens in Settings
3. **Connect AI** — paste your Claude, GPT, or Gemini API key
4. **Pick a server** — click any row, hit "Open Terminal", start working
5. **Ask the AI** — use the sidebar to investigate, diagnose, and fix issues in context

---

## Pricing

**$99 one-time purchase.** Lifetime updates within v1.

- ✅ Use on all your own machines
- ✅ All v1.x updates free forever
- ✅ 14-day free trial, no credit card
- ✅ No subscription. No usage caps. No tiers.

Major version upgrade (v2, if ever) at $39.

### [Buy Now — $99](#) · [Try free for 14 days ⬇](https://github.com/louisbyun/narubase-prod/releases/latest)

*(Buy link activates at public launch)*

---

## Tech stack

| Layer | Technology |
|---|---|
| Desktop shell | Tauri 2 |
| Frontend | React 19 + TypeScript + Tailwind CSS v4 |
| Backend | Rust — reqwest (rustls-tls), keyring, rusqlite (bundled SQLite), russh (SSH client), lettre (SMTP) |
| Cryptography | Ed25519 (license signing) — ed25519-dalek |
| Bundle size | ~8 MB installer · ~35 MB RAM idle |

Compare to Electron alternatives at 150+ MB install and 300+ MB RAM.

---

## System requirements

- **Windows 10 or later, 64-bit** (tested on Windows 11)
- macOS and Linux builds coming in v1.1

---

## FAQ

**Q. Does NaruBase Cloud see my servers / API keys / SSH credentials?**
A. No. Everything runs on your machine. Your keys sit in your OS keychain. The app connects directly to Vultr / DO / Hetzner / Linode and to your AI provider — never through our servers.

**Q. What happens when my trial expires?**
A. The app keeps showing your server list (so you don't lose data), but SSH and AI features lock until you activate a license.

**Q. Can I use this on multiple machines?**
A. Yes. One license = one person, any number of your own devices.

**Q. What if I refund?**
A. License gets added to a public revocation list within 24 hours. The app checks it once a day and unlocks trial-mode again.

**Q. Does the AI see my SSH keys?**
A. No. When the AI runs a command, it uses the same SSH session you already have open, opened through your existing credentials. The AI only sees command output you approve.

**Q. When will macOS / Linux ship?**
A. v1.1 — targeted for Q3 2026. Sign up at the bottom to be notified.

---

## Contact

- **Email:** aiswingx.com@gmail.com
- **Issues / feature requests:** [open an issue](https://github.com/louisbyun/narubase-prod/issues)
- **In-app:** About tab → Contact form (goes straight to the developer)

---

## License

NaruBase™ Cloud binaries are proprietary, distributed under a one-time-purchase license. This repository contains marketing materials, screenshots, release artifacts, and the public update manifest — **not source code**.

---

<div align="center">

**NaruBase™ Cloud** · Powered by **ai Swing X™**

© 2026 · $99 one-time · no subscription · local-first

[⬇ Download v1.0.0](https://github.com/louisbyun/narubase-prod/releases/latest) · [📖 Install guide](INSTALL.md) · [📧 Contact](mailto:aiswingx.com@gmail.com)

</div>
