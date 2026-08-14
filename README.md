# Second-brain starter

A guided installer for a plain-text personal knowledge vault, built for and driven by [Claude Code](https://code.claude.com). You clone this repository, open it in Claude, and type one command; the setup runs as a conversation, one approved step at a time, and builds a clean [PARA](https://fortelabs.com/blog/para/)-structured vault **outside** this folder.

## How it works

1. **Clone this repository** at its latest release tag (the entry prompt on the guide site does this for you).
2. **Open the cloned folder** in Claude Code or the Claude desktop app.
3. **Type `/setup`.** The setup skill proposes each step — where the vault should live, what gets copied, what to verify — and waits for your approval before doing anything.

The vault it builds contains only your own content: five PARA folders, a `CLAUDE.md` with house rules, a short filing guide, and a setup ledger that lets any later session resume where you stopped. No installer machinery, no skills, no git history ever lands in the vault.

## What is in this repository

| Path | Purpose |
| --- | --- |
| `templates/` | The vault payload — exactly what a finished vault starts as |
| `curriculum/` | The module-by-module setup and learning procedures |
| `.claude/skills/` | The user-invoked setup and refresh skills (they never auto-trigger) |
| `START_HERE.md` | The one-page human orientation |

## Provenance and versioning

This repository is generated and published from a single source of truth with a fail-closed build pipeline (deterministic builds, content policy checks, secret scanning). Each release is a **tagged version**; the entry prompt clones the latest tag, never bare `main`. The `VERSION` file in this folder names the release you have. To update later, type `/refresh-materials` — updating is always something you invoke, never something that happens in the background.

This folder is deletable after setup. Keeping it just makes resume and refresh one step shorter.

Full guide, troubleshooting, and human documentation: <https://www.augmentgrowth.ai/resources/claude-code-setup/>

## License

This repository is source-available, not open source. It is licensed under the
[PolyForm Noncommercial License 1.0.0](LICENSE.md) with additional grants: you may
read, clone, and use it for any noncommercial purpose; Augment Growth team
members, clients, and invited trainees may also use it for internal business
purposes; and anything you build in your own vault from these templates is
entirely yours, for any purpose. What you may not do is resell, redistribute
commercially, or deploy this onboarding system as a product or service for
others. To license it commercially, contact Augment Growth.
