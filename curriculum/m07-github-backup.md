# M7 · Back it up

Your vault is becoming the record of your work, which means losing it now has a real cost. This module gives it a private backup on GitHub: every version of every file, recoverable, and ready to put on a second computer.

One thing to be clear about: this is history and recovery, not phone sync. Phone sync is M11, a different job. They coexist happily.

This is also the one module where files leave your computer. That is why the order below is strict: the privacy review happens before anything is even lined up to send.

## Agent procedure

Ledger row: M7. Verification ID: `m7-backup-pushed`. The order of steps 2–6 is fixed and privacy-critical. Do not reorder.

1. **Git presence check.** On Windows, git normally already exists — the desktop app requires Git for Windows to run local sessions, so its absence means M1 ran through an unusual recovery path. Verify with `git --version` first. If missing: guide the official Git for Windows installer per the can't-type card in `curriculum/troubleshooting.md` (ten or more screens, every default correct, all the way to Finish), then have the user fully quit Claude Desktop via the system-tray icon (closing the window is not quitting; the app only sees new installs at a fresh start), reopen, and resume from the ledger. On macOS, git arrived with M1's Command Line Tools.
2. **GitHub CLI and sign-in.** Check `gh --version`; if missing, propose installing it via the official installer for their platform, with approval. Then `gh auth login` — it walks a browser confirmation; GitHub.com and the defaults are right. The user needs a free GitHub account; if they do not have one, they create it themselves in their browser. Never print a token, ever.
3. **Privacy review — before anything is staged.** Ask the user to confirm nothing secret or regulated lives in the vault: passwords, keys, financial or medical records, confidential client material. Anything that should not be in a backup moves out or gets excluded. Then create the `.gitignore` at the vault root **before anything is staged**, excluding the noisy workspace files (`.obsidian/workspace.json`, `.obsidian/workspace-mobile.json`, `.trash/`, `.DS_Store`). State the decision plainly: the repository will be private, non-negotiable.
4. **Stage, then STOP at the list.** `git init`, `git add -A`, then show the user the full staged list (`git status --short`) and stop. This list is every file about to enter the backup — it is their last look before anything can leave the machine, and it is the approval gate. Nothing proceeds to a commit until they approve the list. If anything on it fails the privacy review, remove it or extend `.gitignore`, re-stage, and show the list again.
5. **Commit.** Only after the list is approved: the initial commit. (The repository creation push fails with zero commits, so the commit must come first.)
6. **Create and push, with explicit approval.** Propose it plainly — "this is the moment files leave your computer, to a private space only your account can see" — then, on yes: `gh repo create <name> --private --source=. --remote=origin --push`. Record the repo name in the M7 ledger row's notes.
7. **From here on, plain English.** Tell the user they never need to think in git again: "commit and push my changes" at the end of a meaningful session is the whole habit.

### Approval gates

- The staged-list stop in step 4 is the load-bearing gate: no commit until the user approves the exact list.
- The push in step 6 gets its own explicit approval.
- Admin-credential demands from any installer: defer with an it-blocked note, never work around.
- If GitHub access is blocked entirely, record the module deferred and move on.

### Verification — m7-backup-pushed

Three parts, all required: `gh repo view <owner>/<repo> --json isPrivate` shows private (repo name from the M7 notes); `git remote -v` in the vault shows origin matching it; then `git fetch --prune origin` and compare `git rev-parse HEAD` with `git rev-parse refs/remotes/origin/<branch>` for the vault's current branch — the comparison must be against origin specifically, not whatever upstream the branch tracks. The local snapshot actually reached that remote. `gh-auth` passing alone is never evidence of a backup.

### Human documentation

Card for the user's browser: https://www.augmentgrowth.ai/resources/claude-code-setup/reference/github-backup/ — the full sequence including second-computer setup.

### Record

Update the M7 ledger row: status, date, installer version, last result, repo name in notes. Offer M8 or close with the four-part hand-off.
