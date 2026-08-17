# Claude Code onboarding

A guided installer for a plain-text personal knowledge vault, built for and driven by [Claude Code](https://code.claude.com). You clone this repository, open it in Claude, and type one command; the setup runs as a conversation, one approved step at a time, and builds a clean [PARA](https://fortelabs.com/blog/para/)-structured vault **outside** this folder.

## How it works

The whole picture in two sentences: the entry message downloads this one folder — the setup kit — into Documents, and nothing in it runs until you type `/setup`. That command starts a conversation that builds your notes vault in a separate folder with your OK at each step; nothing here runs on its own, in the background, or after you close the app.

1. **Start with the guided setup message** at <https://www.augmentgrowth.ai/resources/claude-code-setup/> — pasted into a Claude Code session, it clones this repository for you at its latest official release tag.
2. **When the clone finishes, start a new session** in the Claude Desktop app's **Code** tab.
3. **Click "Select folder"** in the message box at the bottom, open **Documents**, and choose **claude-code-onboarding**.
4. **Type `/setup`.** The setup skill proposes each step — where the vault should live, what gets copied, what to verify — and waits for your approval before doing anything.

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

Keep this folder while you are working through (or may come back to) the learning modules — it holds the curriculum, `/setup` resume, and `/refresh-materials`. Your vault is always safe if you delete it, but continuing the modules later would mean cloning a fresh copy. Delete it only when you're done with the modules for good.

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
