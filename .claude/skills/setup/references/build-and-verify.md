# Build and verify

The mechanical heart of a fresh setup: one folder grant, a copy, a check that
the copy is perfect, and the records that make resume work. Nothing here runs
before the user approved the path and (if it was occupied) chose a branch in
`vault-placement.md`.

## 1. The one folder grant

Creating the vault means working outside this installer folder, so the app
will show one permission pop-up. Give the three-line context first:

> In a second you'll see a pop-up asking if I can create and work in
> [full path]. That single folder is the only new place this gives me —
> it's your vault being created. Yes is the answer that builds it.

The grant is scoped to the vault folder itself — do not ask for the parent
directory, the whole Documents folder, or anything broader. If the pop-up the
platform offers is broader than the vault folder, say so and let the user
decide.

## 2. Create and copy

1. Create the vault folder at the approved path.
2. Copy the full contents of this installer's `templates/` directory into it.
   Copy contents only — the `templates` folder name itself does not appear in
   the vault, and nothing outside `templates/` is ever copied. No `.git`, no
   `.claude`, no skills, no curriculum, no state files. The vault is the
   user's own content and nothing else.

## 3. Verify — trust the diff, not the copy command

Prove the copy is perfect before saying it is:

- Run `diff -rq <installer>/templates <vault>` (macOS), or an equivalent
  per-file comparison on Windows (`Get-ChildItem -Recurse` both sides,
  compare the file lists, then `Get-FileHash` each pair).
- The result must be: every template file present in the vault, byte-for-byte
  identical, and nothing extra beyond them.
- Any difference: report it plainly, fix by re-copying the affected file with
  approval, and re-verify. Never declare the vault built while the
  comparison fails.

Tell the user the outcome in one line: "37 files copied and every one
verified identical."

## 4. Write the records

1. **`.setup-state.json`** — in the installer folder (this file is local to
   this machine and never published; the installer's `.gitignore` already
   covers it). Write:

   ```json
   {
     "vault_path": "/absolute/path/to/vault",
     "created": "2026-01-01T00:00:00Z",
     "installer_version": "<contents of VERSION>"
   }
   ```

   On later runs, update a `last_seen` timestamp rather than rewriting
   `created`.

2. **The ledger** — the vault now contains
   `03_Resources/ai_harness_setup/Setup_Ledger.md`, shipped pre-seeded by the
   copy. Update its M0 row: status `in progress`, today's date, and the
   sync-environment note from vault placement (`sync-env: ...; vault: ...`).
   Update rows in place; never recreate the file.

## 5. The build hand-off

This is the most important stopping point in the whole kit. The vault is
built — the user is **done**, and they must hear that plainly. Open with the
completion line, then give the four-part hand-off (see SKILL.md §5):

> ✅ Done for today — your vault is built, verified, and ready to use.
> Everything else in this kit is optional learning modules; stopping here is
> completely fine.
>
> Your vault lives at: [absolute vault path]
>
> Next time: open Claude, go to the Code tab, click **Select folder** in the
> message box at the bottom, and choose this setup folder.
>
> Then type: /setup

Never end this step with anything vague about coming back "when you need
more setup." They don't need more setup. The vault works.

If the user is continuing right now, keep the first line — they've earned
it — then skip the reopen steps and offer the first module instead: "✅ Your
vault is built and verified; you're done with the required part. Ready for
the first short optional module whenever you are — just say go."
