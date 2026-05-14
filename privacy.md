---
layout: page
title: Privacy Policy
permalink: /privacy/
---

**Effective date:** 2026-05-14

Kea is an email client for macOS. This Privacy Policy describes what data Kea handles, where that data goes, and what Kea does *not* do with it.

## Who we are

Kea is developed by Grant Zhang as an independent project. There is no Kea-operated company, server, or backend service.

## Summary

- **No Kea-operated servers.** Kea has no backend infrastructure. Your email never passes through a server we control.
- **Your credentials stay on your Mac.** IMAP/SMTP passwords and any AI provider API keys are stored in the macOS Keychain.
- **Your email stays on your device.** Message content, attachments, drafts, and indexes are written to local storage in `~/Library/Application Support/Kea/`.
- **AI providers are opt-in.** Cloud AI features only run when you configure a provider and explicitly invoke them.

## Data Kea handles

### Account information
You provide an email address, display name, and IMAP/SMTP server settings (auto-detected for common providers). The password is stored in the macOS Keychain. None of this is transmitted to anyone except your chosen mail server.

### Mailbox content
Kea downloads message headers, bodies, and attachments from your IMAP server and stores them locally in SwiftData. Sending mail goes through your SMTP server. No copies are sent anywhere else by Kea itself.

### Search indexes and embeddings
Kea builds a local full-text search index (SQLite FTS5). For semantic search reranking, Kea also generates vector embeddings — but only when your configured LLM provider also supplies an embedding endpoint. Specifically:

- **Apple Intelligence** or **Anthropic Claude** — no embeddings are generated; search uses local FTS5 only.
- **OpenAI** (LLM provider) — embeddings via `text-embedding-3-small`; short message snippets are sent to OpenAI during background indexing.
- **Google Gemini** (LLM provider) — embeddings via `text-embedding-005`; short message snippets are sent to Google during background indexing.
- **Ollama** (local LLM) — embeddings via `nomic-embed-text` (default; configurable); both LLM and embedding traffic stay on your local Ollama instance.

All resulting indexes are stored locally.

### AI-derived data
When you enable a cloud AI provider and invoke a feature (summarization, smart reply, compose, triage, search re-ranking), the relevant message content and your prompt are sent to that provider's API. The result is stored locally. Cloud AI providers Kea supports include: Anthropic Claude, OpenAI, Google Gemini. Each provider's own privacy policy governs what they do with that data.

If you only use Apple Intelligence (the default on supported macOS versions) or a local LLM (Ollama), no email content leaves your device.

### Writing-style profile
Kea analyzes a small sample of your sent mail to build a local "writing style" profile that improves draft quality. The profile is derived locally and stored locally. The sent-message text used for analysis may be sent to your configured cloud AI provider during the analysis step.

### User-selected folders (document indexing)
If you grant Kea access to a folder for document indexing, Kea reads files in that folder and adds their text to the local search index. This data stays local.

### Wiki / personal knowledge base
Kea may derive lightweight per-recipient and per-topic notes from your mail to improve replies. These notes are stored locally in `~/Library/Application Support/Kea/wiki-*/`.

## Data Kea does NOT collect

- **No analytics or telemetry.** Kea does not send usage data, crash reports, or diagnostics to any server.
- **No advertising identifiers.** Kea does not collect IDFA, IDFV, advertising IDs, or any device identifier.
- **No user accounts.** Kea has no sign-up, no account system, no login.
- **No tracking across apps or websites.**

## Where your data goes

| Destination | What Kea sends | When |
|-------------|---------------|------|
| Your IMAP/SMTP servers | Whatever the protocol requires (auth, fetch, send) | Whenever you sync, send, or act on mail |
| Anthropic Claude | Email content + your prompt | Only if you have configured an Anthropic API key and invoked an AI feature. No embedding traffic. |
| OpenAI | Email content + your prompt; short snippets for embeddings | Content on AI feature invocation; snippets continuously during background indexing |
| Google Gemini | Email content + your prompt; short snippets for embeddings | Content on AI feature invocation; snippets continuously during background indexing |
| Apple Intelligence | Prompts | On-device only — Apple's framework runs locally on supported devices |
| Ollama (local LLM) | Email content + prompt; embedding text | Only if you've pointed Kea at a local Ollama instance; stays on your machine |
| Apple Floodgate | Embedding text | Apple-internal only; not present in App Store builds |
| Anywhere else | Nothing | — |

## Children's privacy

Kea is not directed at children under 13. Kea does not knowingly collect any data from children.

## International users

Kea stores all data on your device. If you configure a third-party AI provider, that provider may process data on servers in the United States or other jurisdictions; consult that provider's privacy policy for details.

## Your choices

- **Disable cloud AI features** by leaving the AI provider settings empty. Kea will fall back to Apple Intelligence (on-device) where supported.
- **Delete an account** in Settings → Accounts. Removing an account also deletes the cached mail, indexes, embeddings, and per-account memory associated with that account.
- **Delete all Kea data** by quitting Kea, removing `~/Library/Application Support/Kea/`, and deleting your accounts from the macOS Keychain.

## Changes to this policy

If this policy changes materially, the effective date at the top will be updated. Material changes will also be noted in the app's release notes.

## Contact

Questions or requests about this policy: [kea@tauger.us](mailto:kea@tauger.us) — or open an issue at [github.com/tauger/kea-app](https://github.com/tauger/kea-app).
