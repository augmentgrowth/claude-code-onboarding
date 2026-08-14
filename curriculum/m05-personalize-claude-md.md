# M5 · Make it yours

Claude wakes up with amnesia every session. It does not know your job, your shorthand, or what you are working on — unless your vault tells it. That is what the three context files do, and right now they are starter text. This module makes them yours, with five short questions.

Every line in these files shapes every future conversation, so short and true beats long and impressive.

## Agent procedure

Ledger row: M5. Verification ID: `context-files`.

1. **Explain the layers in three lines.** The root `CLAUDE.md` is the always-read operating manual. A project folder can carry its own smaller CLAUDE.md for project facts. And `@filename` in a message pulls in one file on demand. Do not turn this into a lesson; the user needs the shape, not the theory.
2. **Ask five questions, one at a time.** Wait for each answer before the next. "Skip" or "not sure" gets the safe default.
   1. What is your role or main type of work?
   2. What should this vault help you manage? (projects, notes, research, meetings, planning, files)
   3. How should Claude communicate by default? (safe default: concise, direct, practical)
   4. When should Claude ask before acting? (safe default: before deleting, moving many files, editing instruction files, or sending anything externally)
   5. Anything Claude should avoid storing or assuming about you? (safe default: no passwords, keys, sensitive personal details, or private client information)
   Never ask for secrets, credentials, regulated data, or private client details.
3. **Draft all three files and show them before writing.** Root `CLAUDE.md`: imports of the two resource files, the vault's purpose in one line, collaboration rules, boundaries, privacy reminders, and a self-improvement rule (suggest instruction updates when patterns repeat, never edit instruction files without approval). Keep it under about 80 lines. `About_Me.md`: role, what the vault manages, communication default, privacy reminder — durable context only. `PARA_Guide.md`: the five folders in plain language, a short decision tree, archive instead of delete. Keep everything short enough that the user understands every line.
4. **Write only after approval.** Editing instruction files always gets an explicit yes first. Show a diff or the full replacement, whichever is clearer for a beginner.
5. **Test it.** Run a small read-only context check: ask, in this session, what the context files now say about the user, and confirm the answer reflects their answers. Tell the user the fuller test — "in a fresh session at the vault, ask: what do you know about me?" — is a good habit after M3's graduation.

### Approval gates

- Every write to `CLAUDE.md`, `About_Me.md`, or `PARA_Guide.md`: drafts shown in full, approved before writing.
- No question ever asks for a secret; if the user volunteers one, do not write it, and say why.

### Verification — context-files

`CLAUDE.md`, `03_Resources/About_Me.md`, and `03_Resources/PARA_Guide.md` all exist in the vault, personalized (not the untouched starter text), plus the read-only context check above.

### Human documentation

Card for the user's browser: https://www.augmentgrowth.ai/resources/claude-code-setup/reference/how-claude-sees-files/ — and, for later, https://www.augmentgrowth.ai/resources/claude-code-setup/reference/claude-md-maintenance/ when the root file starts creeping past 100 lines.

### Record

Update the M5 ledger row: status, date, installer version, last result, card surfaced. Offer M6 or close with the four-part hand-off.
