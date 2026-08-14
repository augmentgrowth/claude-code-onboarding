# M9 · Routines

A routine is a workflow you already proved in M8, run on a rhythm. The weekly review you keep meaning to do. The inbox that fills up. The meeting notes that pile up unread. This is where the system starts working for you, not just with you.

The mistake to avoid: automating first. A routine earns automation by working a few times with you watching. Start with a saved prompt and a calendar nudge; scheduled runs come later, deliberately.

## Agent procedure

Ledger row: M9. Verification ID: `m9-routine-exists`. M9 comes after M10 in the canonical order.

1. **Pick one recurring chore — one.** Good candidates: a weekly review (what moved, what stalled, what needs a decision), inbox processing (file everything in `00_Inbox` with a summary of what went where), or a meeting-notes sweep (the week's action items into one list). Pick the one the user already wishes were happening. Resist building five.
2. **Write the routine prompt as a vault file**, for example `03_Resources/routines/weekly-review.md`, following the four-beat pattern: read the current state, do the small repeatable thing, write the results into the vault (a dated log the prompt names, such as `03_Resources/routines/logs/`), report what changed. Show the draft and get approval before writing it.
3. **Run it once, now, by hand.** Execute the routine in this session with the user watching, with the usual approvals for any moves. The output must land where the prompt says it should. Then spend two minutes on tuning: was anything wrong, missing, or noisy? Edit the prompt file with approval.
4. **Set the human rhythm.** Suggest a recurring calendar block (Friday afternoon works for most). When it fires, the user opens Claude at the vault and says: run the routine in `@03_Resources/routines/weekly-review.md`. That is the whole habit.
5. **Scheduling comes later, and only deliberately.** Manual-first is the rule: no scheduled or automated execution until the user has run the routine by hand at least once, and then only with explicit approval. Scheduling options change and differ in what they can reach — some scheduled runs happen in the cloud and cannot see the local vault at all — so the user checks the current official scheduling documentation in their own browser before choosing, and any routine that touches the vault must run where the vault lives. Record whatever gets enabled in the ledger with what it does, when it runs, and where it logs.

### Approval gates

- Writing or editing the routine prompt file: draft shown, approved first.
- Anything the routine moves or files during the manual run: normal per-move approvals.
- Enabling any scheduled execution: its own explicit approval, never bundled with the manual run.

### Verification — m9-routine-exists

Read the routine prompt path recorded in the M9 ledger row's notes, confirm the prompt file exists in the vault, then check the output or log location that prompt declares: logged output from at least one run must exist there. A prompt with no proven run is not a pass.

### Human documentation

Card for the user's browser: https://www.augmentgrowth.ai/resources/claude-code-setup/reference/tokens-and-cost/

### Record

Update the M9 ledger row: status, date, installer version, last result, the prompt file's path in notes. One optional module remains: M11, notes on the phone. Offer it or close with the four-part hand-off.
