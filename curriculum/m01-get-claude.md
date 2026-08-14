# M1 · Get Claude

Good news: this module is mostly already done, because you are reading this inside a working Claude session. What is left is small: confirm the session is healthy, glance at one setting, and know where the privacy controls live.

## Agent procedure

Ledger row: M1. Verification ID: `typeable-session`.

1. **Confirm the typeable session.** The user is typing into a local Code session right now, which is M1's real pass condition. Say so in one line. If the user reports another machine or window where they cannot type at all (a locked message box, a "Git is required for local sessions" error), use the can't-type card in `curriculum/troubleshooting.md` — that situation cannot be fixed from inside a session that cannot type.
2. **Windows note (usually nothing to do).** On Windows, Git is normally already installed, because the desktop app requires Git for Windows before it will run any local session — the fact that the user can type proves it. Verify quietly with `git --version`. Only if it is somehow missing, walk the official Git for Windows installer per the can't-type card: set the expectation first (ten or more screens of questions, every default is correct, keep clicking Next to Install and then Finish; stopping partway leaves Git not installed even though the download happened), then the tray-quit ritual — fully quit Claude from the system-tray icon (closing the window is not quitting; the app only notices new installs at a fresh start) and reopen. A UAC "allow changes" prompt is a normal Yes. A demand for an administrator password the user does not have is an IT block: stop that step, mark the module deferred with an it-blocked note, and continue with what works. Never work around a credential wall.
3. **macOS note.** The Command Line Tools prompt (it mentions `xcrun`) is allowed to run — local sessions genuinely need it. It is a big download and can look frozen; that is normal. Never install Homebrew or another package manager as a workaround.
4. **Never route to a remote or Cloud environment.** The vault lives on this machine. If a dialog offers a cloud session, the answer for setup is no.
5. **Quick model check.** Point at the small model selector in the bottom-right corner of the box where they type, next to the send button. The standard setting — usually Sonnet at its default effort — is the right tool for setup. If it shows something else, help them switch it back using that same control. If they can't find the label, keep going; this check never blocks setup. Don't detour into plans, pricing, or usage commands here — a usage-limit stop later is a normal pause, not a failure: record true state in the ledger and give the hand-off.
6. **Privacy settings, briefly.** Suggest they review Settings > Privacy in the Claude app before putting sensitive work in, and that anything regulated at work deserves a question to IT first. This is their reading, not a step you perform.
7. **No terminal setup.** The Desktop Code tab is everything the vault and every module here needs. Do not install the terminal version of Claude during setup, and never run or paste a fetch-and-execute install command. If a much later capability genuinely requires the terminal version, that module explains it then, as its own separately approved step.

### Approval gates

- Any Git install in step 2 gets the three-line just-in-time context before its dialogs appear.
- Administrator credentials are never requested, received, or typed. No exceptions.

### Verification — typeable-session

The user is typing into a local (not cloud) Code session and messages get answered — which this conversation itself demonstrates. Pass: confirmed in this session, plus `git --version` succeeding quietly. There is nothing to install and nothing else to check.

### Human documentation

Cards for the user's own browser, optional reading: https://www.augmentgrowth.ai/resources/claude-code-setup/reference/models-effort/ (models and effort) and https://claude.com/pricing (current plan details).

### Record

Update the M1 ledger row: status, date, last result. Offer M2 or close with the four-part hand-off.
