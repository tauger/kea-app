---
layout: home
title: Kea
---

Kea is an AI-native email client for macOS. It connects to your existing IMAP/SMTP accounts (iCloud, Gmail, Outlook, Fastmail, Yahoo, custom) and adds AI-assisted reading, drafting, and search — with email content staying on your device unless you explicitly enable a cloud AI provider.

## Features

- Standard IMAP/SMTP — works with any mainstream provider
- On-device search (full-text + semantic ranking)
- AI-assisted summaries, smart replies, and compose — opt-in, runs locally via Apple Intelligence by default
- Optional cloud AI providers (Anthropic Claude, OpenAI, Google Gemini) — bring your own API key
- Three-layer spam filtering — header heuristics + sender reputation + optional local LLM classifier
- Email triage by intent / urgency / category
- Threaded conversations with cross-folder enrichment
- IDLE push for real-time new mail

## System Requirements

- macOS 15.0 (Sequoia) or later
- Apple Silicon recommended

## Support

Found a bug or have a question?

- **Open an issue:** [github.com/tauger/kea-app/issues](https://github.com/tauger/kea-app/issues)
- **Email:** [kea@tauger.us](mailto:kea@tauger.us)

When reporting a bug, please include:
- macOS version
- Kea version (Settings → About)
- Email provider (iCloud, Gmail, etc.)
- Steps to reproduce

## Privacy

See the [Privacy Policy](privacy/) for details on what data Kea handles and where it goes.

Short version: account credentials live in macOS Keychain, email content stays on your device, and nothing is sent to a Kea-operated server because Kea has no servers. Cloud AI providers only receive email content when you explicitly enable them and invoke an AI feature.
