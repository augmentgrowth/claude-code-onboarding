# M1 · Get Claude

Good news: most of this module is already done, because you are reading this inside a working Claude session. What is left is small: check your settings, learn the two commands worth knowing, and set up the terminal version of Claude so both ways of working are ready.

The terminal is just another window where Claude runs. You will not need to learn it. Setting it up now means later features, like scheduled routines, can use it.

## Agent procedure

Ledger row: M1. Verification ID: `cli-version`.

1. **Confirm the typeable session.** The user is typing into a local Code session right now, which is M1's real pass condition. Say so in one line. If the user reports another machine or window where they cannot type at all (a locked message box, a "Git is required for local sessions" error), use the can't-type card in `curriculum/troubleshooting.md` — that situation cannot be fixed from inside a session that cannot type.
2. **Windows note (usually nothing to do).** On Windows, Git is normally already installed, because the desktop app requires Git for Windows before it will run any local session — the fact that the user can type proves it. Verify quietly with `git --version`. Only if it is somehow missing, walk the official Git for Windows installer per the can't-type card: set the expectation first (ten or more screens of questions, every default is correct, keep clicking Next to Install and then Finish; stopping partway leaves Git not installed even though the download happened), then the tray-quit ritual — fully quit Claude from the system-tray icon (closing the window is not quitting; the app only notices new installs at a fresh start) and reopen. A UAC "allow changes" prompt is a normal Yes. A demand for an administrator password the user does not have is an IT block: stop that step, mark the module deferred with an it-blocked note, and continue with what works. Never work around a credential wall.
3. **macOS note.** The Command Line Tools prompt (it mentions `xcrun`) is allowed to run — local sessions genuinely need it. It is a big download and can look frozen; that is normal. Never install Homebrew or another package manager as a workaround.
4. **Never route to a remote or Cloud environment.** The vault lives on this machine. If a dialog offers a cloud session, the answer for setup is no.
5. **Plan and model check.** Ask what Claude plan they are on (it cannot be detected from here; their claude.ai account page shows it). Ask them to type `/model` and read it out; the default model at default effort is right for setup. Teach `/cost` in one line as the habit for checking usage. A usage-limit stop later is a normal pause, not a failure: record true state in the ledger and give the hand-off.
6. **Privacy settings, briefly.** Suggest they review Settings > Privacy in the Claude app before putting sensitive work in, and that anything regulated at work deserves a question to IT first. This is their reading, not a step you perform.
7. **Set up the `claude` terminal command.** Propose it in plain words: "one official installer adds a `claude` command so the terminal version is ready too; you won't need to use it yet." After approval, run the official one-line installer yourself through your shell (macOS: `curl -fsSL https://claude.ai/install.sh | bash`; Windows PowerShell: `irm https://claude.ai/install.ps1 | iex`) and show the result. This is a user-approved install action, not an instruction fetch. If your shell genuinely cannot run it, walk the user through pasting it, one breath of explanation first. If an installer demands administrator credentials, apply the safety rule: explain, defer with an it-blocked note, continue with Desktop Code.

### Approval gates

- The installer run in step 7 happens only after a plain-words proposal and a yes.
- Any Git install in step 2 gets the three-line just-in-time context before its dialogs appear.
- Administrator credentials are never requested, received, or typed. No exceptions.

### Verification — cli-version

Run `claude --version` in a newly spawned shell yourself. Pass: it exits cleanly and prints a version. If it fails only with command-not-found, the shell may predate the install: walk the user through one fresh-terminal check in plain words before recording a fail.

### Human documentation

Cards for the user's own browser, optional reading: https://www.augmentgrowth.ai/resources/claude-code-setup/reference/models-effort/ (models and effort) and https://claude.com/pricing (current plan details).

### Record

Update the M1 ledger row: status, date, installer version, last result. A deferred CLI install gets a plain-English reason in notes. Offer M2 or close with the four-part hand-off.
