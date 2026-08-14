# M2 · Your vault, verified

Your vault was built and checked when you typed `/setup`. This module proves it again in front of you, walks you through what each piece is for, and offers a nice extra: a free app called Obsidian that shows your notes as clean, readable pages.

Why check twice? Because the habit matters more than the folders. A setup you have seen verified is a setup you trust.

## Agent procedure

Ledger row: M2. Verification ID: `m2-pack-scaffold`.

1. **Re-verify the scaffold in front of the user.** Run the m2-pack-scaffold check below and narrate the outcome in one line ("all five folders, your context files, and the ledger — present and correct"). If anything is missing, fix it by re-copying the affected file from this folder's `templates/` with approval, then re-check. Never declare the vault healthy while a check fails.
2. **One-minute tour of the context files.** Open `CLAUDE.md`, `About_Me.md`, and `PARA_Guide.md` and explain each in a line: the always-read rules file, the who-you-are file, and the where-things-go file. They are starter text now; M5 personalizes them.
3. **Offer Obsidian — never require it.** Two lines: "Obsidian is a free app that shows these same files as clean formatted pages. Want it, the download page for your own browser is obsidian.md/download; choose Open folder as vault and pick your vault folder itself." The user downloads and installs apps themselves in their browser; you never download applications for them. Skipping Obsidian entirely is a fine choice.
4. **A read-only demonstration.** With approval for the read, summarize the vault in a few lines without editing anything: what folders exist, what the sample project is, what the ledger says. This shows the user what "Claude can see your vault" means.
5. **Offer M3 in the same session.** Say the next step is a small, approved rescue of one of their real folders, and ask whether to continue now or stop here.

### Approval gates

- Any repair copy in step 1 is proposed first (which file, from where, to where).
- The summary in step 4 is a read; say so, and do not edit anything during it.

### Verification — m2-pack-scaffold

Installer-adapted composite check, run in the vault: the five PARA folders exist (`00_Inbox`, `01_Projects`, `02_Areas`, `03_Resources`, `04_Archives` — 04_Archives is the one most often missing), plus `CLAUDE.md`, `VAULT_VERSION`, and `03_Resources/ai_harness_setup/Setup_Ledger.md`. Also run `context-files`: `CLAUDE.md`, `03_Resources/About_Me.md`, and `03_Resources/PARA_Guide.md` all exist. Note: this vault deliberately contains no hidden `.claude` machinery and no pack manifest — a clean vault is the design, so their absence is a pass condition here, not a gap.

### Human documentation

Card for the user's browser: https://www.augmentgrowth.ai/resources/claude-code-setup/reference/how-claude-sees-files/ — how Claude sees files and folders.

### Record

Update the M2 ledger row: status `done` on pass, date, installer version, last result, card surfaced. Keep the sync-environment note (`sync-env: ...; vault: ...`) exactly as written during the build — M11 reads it later. Then offer M3 or close with the four-part hand-off.
