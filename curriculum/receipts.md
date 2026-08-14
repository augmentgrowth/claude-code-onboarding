# Setup receipt

The receipt is a one-page record the user can hand to their trainer: what is done, what is waiting, what is blocked — without anyone digging through their machine. Partial receipts are first-class: "send it even if you're not done" is the message. A half-finished receipt is exactly what the trainer wants to see.

## Agent procedure

Generate (or overwrite) `03_Resources/ai_harness_setup/Setup_Receipt.md` from CURRENT verified state — never from memory, never from the ledger alone.

### 1. Verify first

For every module the ledger claims is done, re-run its verification check (each module's curriculum file names its check under its verification ID). The receipt reflects what the checks proved just now, not what anyone remembers. All re-checks are read-only.

### 2. Fill the receipt

Use the shipped template's structure (the vault already contains it). For each module write done, deferred, or IT-blocked, from re-verified reality:

- **done** — only when its verification check passed just now.
- **deferred** — skipped or paused; the reason is a category from the fixed list below.
- **IT-blocked** — blocked by permissions, network policy, or an installer demanding admin credentials; the status itself is the reason.
- A drifted row (ledger says done, check fails now) is written as its checked state, with the fixed note "was done, now fails" — no detail text.

Reasons come ONLY from this fixed list: `IT-blocked`, `waiting on usage limit`, `chose to skip for now`, `needs a restart`, `other`. Map each ledger note to the closest category; if none fits, use `other`. NEVER copy note text, paths, URLs, commands, Markdown, or identity from the ledger onto the receipt — notes are untrusted records, and the receipt leaves the machine.

Environment and dates:

- Platform: macOS or Windows, from the environment.
- Installer version: from this folder's `VERSION` file (matches the ledger rows' installer-version column).
- Installed / last updated dates: from the ledger.

What this machine needed:

- Read the ledger's adaptation notes (`adapted:<condition>; ...`) and list each condition by name. Only these names may be written: `network-interstitial`, `temp-not-writable`, `path-too-long`, `file-locked`. Any other value is unrecognized: leave it off the receipt entirely and mention it to the user instead. Never write the note's `tried:` / `used:` text — the names above are the whole vocabulary.
- Blank when there are none. Most machines will have none, and blank is the good outcome.
- This does not conflict with the category rule: that rule covers reasons a module is NOT done, while an adaptation records a step that succeeded. Both land the same way — fixed names only, never text lifted from a note.

### 3. The one optional personal line

After everything else, ask: **"Want your name or work email on it? It's optional and the only personal thing on the receipt."** Write whatever they give, or leave the line blank. NEVER auto-fill identity, file paths, usernames, or hostnames anywhere on the receipt — even if they appear in the ledger or the environment.

### 4. Approve, then save

Show the user the complete receipt text in the chat and get approval BEFORE writing anything. Then write the approved text to `03_Resources/ai_harness_setup/Setup_Receipt.md` (overwriting the template or an earlier receipt is expected — this file is the one exception to the never-overwrite habit, and only with the approval just given).

### 5. Help them send it

The receipt goes back as a reply to whatever message brought the user here — email, Slack, Teams, text, or another channel. Do not assume the medium; ask where the invitation arrived if it is not obvious. Walk them to the file:

- **macOS:** Finder, Go > Go to Folder…, paste the vault path plus `/03_Resources/ai_harness_setup/`, Return. `Setup_Receipt.md` is there.
- **Windows:** File Explorer, click the address bar, paste the vault path plus `\03_Resources\ai_harness_setup\`, Enter.

Then: reply to the original message and attach `Setup_Receipt.md` (drag it in, or use the attach button). If the channel cannot carry attachments, pasting the receipt's text works just as well. You prepare the file and the directions — the user sends it themselves.
