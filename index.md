---
layout: home
title: Kea
---

Kea is an AI-native email client written in Swift for Mac, iPhone, and iPad. It connects to your existing IMAP/SMTP accounts (iCloud, Gmail, Outlook, Yahoo, and custom providers) and adds AI-assisted reading, drafting, and search. Kea stores its mailbox cache and indexes locally and has no operated backend. If you configure a cloud AI provider, relevant content is sent directly to that provider; OpenAI and Gemini can also receive brief message snippets for search embeddings.

## Features

- Multi-account IMAP/SMTP mail for iCloud, Gmail, Outlook, Yahoo, and custom providers
- Fast cached navigation, offline reading, full-text search, and on-device semantic ranking
- Today's Attention Queue, email triage by intent, urgency, and category, and follow-up tracking
- AI-assisted summaries, smart replies, and compose, with personal-document and email context
- On-device Apple Intelligence support where available
- Optional cloud AI providers (Anthropic Claude, OpenAI, Google Gemini) using your own API key
- Threaded conversations with cross-folder enrichment and IMAP IDLE push updates
- User-controlled Report Spam / Not Spam actions and deterministic header-based bulk-mail filtering in attention surfaces

Personal-document indexing is currently available on Mac.

## System Requirements

- macOS 15.0 (Sequoia) or later, or iOS/iPadOS 18.0 or later

## Support

Found a bug or have a question?

- **Open an issue:** [github.com/tauger/kea-app/issues](https://github.com/tauger/kea-app/issues)
- **Email:** [kea@tauger.us](mailto:kea@tauger.us)

When reporting a bug, please include:

- OS version and device
- Kea version (Settings → About)
- Email provider (iCloud, Gmail, etc.)
- Steps to reproduce

## Privacy

See the [Privacy Policy](privacy/) for details on what data Kea handles and where it goes.

Short version: account credentials live in Apple Keychain, and Kea stores its mailbox cache and indexes on your device. Nothing is sent to a Kea-operated server because Kea has no servers. Configured cloud AI providers receive content when you invoke an AI feature; OpenAI and Gemini can also receive brief message snippets while generating search embeddings.
