# Vault placement

Where the vault lives, how to propose it, and what to do when the spot is
already taken. Detection here is always a read — nothing changes on the
machine until the user approves the build.

## 1. Orientation (two or three lines, before any question)

Open with the two-folders picture, in your own words:

> Here's the shape of what we're doing: this folder is the setup kit, and
> your vault — the folder your actual notes live in — gets built outside it,
> somewhere sensible on your computer. When we're done, this kit is safe to
> delete, though keeping it makes coming back easier.

## 2. Sync detection (read-only)

Find out what this machine already backs up to the cloud, so the vault can
land somewhere that gets that for free.

**Windows (PowerShell):**
- Check whether `$env:OneDrive` or `$env:OneDriveCommercial` is set.
- Get the real Documents path: `[Environment]::GetFolderPath('MyDocuments')`.
- If Documents resolves under a OneDrive root, this machine backs Documents
  up automatically. When both OneDrive variables exist, the root that
  actually contains the real Documents path is the one that counts.

**macOS:**
- Check whether `~/Library/Mobile Documents/com~apple~CloudDocs` exists
  (iCloud Drive is on), and whether `~/Documents` physically resolves under
  it (Desktop & Documents sync is on).

## 3. Propose the vault home

One proposal, in plain words, and the user can always choose differently —
no choice is warned against:

- **Windows, Documents backed up by OneDrive:** propose
  `Documents\Vaults\second-brain` — "your computer already backs this spot
  up for free, and it sets you up for reading notes on your phone later."
- **Windows, no OneDrive redirection:** propose `Vaults\second-brain` under
  the user profile (`~\Vaults\second-brain`).
- **macOS:** propose `~/Vaults/second-brain`. (A synced Documents folder buys
  a Mac nothing on mobile — the phone path later uses Obsidian's own iCloud
  home — so plain and local is calmest.)
- **Both OneDrive roots present but Documents under neither:** propose the
  user-profile home; if the user wants a synced spot instead, ask which
  account (work or personal) should hold their notes and use that root.

Keep what was detected as a plain fact for the ledger's M0/M2 notes later,
shaped `sync-env: onedrive-business` / `onedrive-personal` / `icloud` /
`none`, plus `vault: synced` or `local`. Never write a path, username, or
computer name into that note.

## 4. The named-folder question

Then ask one question:

> I'd like to create your vault at [full path]. The last part is its name —
> `second-brain` — and you can call it anything you like. Want that name and
> that spot, or would you rather change one?

Wait for the answer. One question, one answer, then move.

## 5. If the proposed path is occupied

If a folder already exists at the agreed path, never touch it silently.
Look inside just enough to describe it honestly ("there's already a folder
there with about 40 files in it — it looks like it might be an earlier
vault" / "it has photos and documents in it"). Then offer exactly this
structured choice:

> That spot's taken. Here are your options:
>
> 1. **Use it as-is** — if it's already your vault from before, we skip
>    building and just continue from where it left off.
> 2. **Fresh, next door** — build a brand-new vault at a different name or
>    spot, leaving that folder completely alone.
> 3. **Rename the old one, then build fresh** — I move the existing folder
>    aside (for example to `second-brain-old`), with your approval, then
>    build clean at the original spot.
> 4. **Adopt it** — keep everything that's in it and only add the starter
>    pieces it's missing. I never change or replace anything already there.
> 5. **Something else** — tell me what you'd prefer.

What each option means in practice:

- **Use it as-is (skip-here):** verify it actually is a vault (PARA folders +
  `03_Resources/ai_harness_setup/Setup_Ledger.md`). If yes, record it in
  `.setup-state.json` and switch to resume mode. If it isn't really a vault,
  say so plainly and re-offer the remaining options.
- **Fresh:** re-run the named-folder question with a new name or location.
- **Rename, then fresh:** the rename is a move — it gets its own explicit
  approval, stating the exact old and new names, before it happens. Then
  build clean at the original path.
- **Adopt — strictly additive, no exceptions:**
  - Compare the existing folder against `templates/` and list exactly which
    files and folders are missing.
  - Show the user that exact add-list and get approval before creating
    anything.
  - Create only what is missing. Never modify, overwrite, rename, or delete
    anything already present — not even a file that differs from the
    template version. A file that exists is left alone, full stop.
  - If a ledger already exists, never rewrite it; it may only ever be
    appended to, and only with approval.
  - After adding, verify each added file matches its template copy, then
    record the vault in `.setup-state.json`.
- **Other:** listen, restate the plan in one line, confirm, then apply the
  matching branch above.

### When the rename or the move won't go through

Renaming or moving a folder can fail. Two different things cause it, and the
right answer is different for each. Read what the failure actually says
before you speak. Never force the operation, never look for or stop programs
that might be holding the folder, and never ask for an administrator
password.

**The folder is busy.** The failure mentions "resource busy", "in use by
another program", or the rename simply refuses while something has the
folder open. Say what is happening in plain words:

> Something on your computer is holding that folder open right now, so it
> can't be moved. Usually that's another Claude session, or an app like
> Obsidian with the folder still loaded. Fully quit any other Claude windows
> or sessions, close any app that's using that folder, then tell me to try
> again.

Wait for the user to say they've done it. Then retry the same approved move
once. If it fails the same way again, offer the "Fresh, next door" option
instead — a different name or spot works without touching that folder at all.

**The folder is protected.** The failure is a permission or ownership one
(`EPERM`, `EACCES`, "permission denied"), or the path sits somewhere the
system guards. Stop here. Closing apps will not help, so do not suggest it.
Say instead:

> That folder is protected by your computer, so I can't move or rename it.
> That's not something to work around. Let's put your vault somewhere else
> instead.

Then go back to the named-folder question in section 4 and pick a new spot.
