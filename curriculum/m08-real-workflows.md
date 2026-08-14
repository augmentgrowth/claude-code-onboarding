# M8 · Real work, three ways

Time to use the system on actual work. Not tutorials with sample data — your notes, your projects. A good first workflow is narrow, backed by real sources, and easy to check with your own eyes. Each of the three below produces something you would have wanted anyway.

## Agent procedure

Ledger row: M8. Verification ID: `m8-artifact`. Run at least one workflow to completion; the user picks which. Connector-free workflows complete this module on their own — only the research workflow needs a connector, and a missing connector defers that one workflow, never the module.

1. **Offer the three workflows** in a line each, and let the user pick one:
   - **Research and save** (needs the M4 connector or another approved source): a narrow question the user cares about, answered with sources, saved to the right PARA folder. Warn in one line that web research spends real usage, and check `/cost` after.
   - **Meeting notes to action items**: real notes from this week (pasted, or referenced from a vault file with `@filename`), turned into a task list with owners and dates where mentioned. Verify the extracted items against the source.
   - **Project scaffolding**: a real active project. Read what exists, ask how they plan to work before proposing anything, then propose a folder structure and create it after approval.
2. **Preserve originals.** For notes and scaffolding, the original stays untouched; show a short manifest of what will be created before saving anything, and get approval.
3. **Verify with their eyes.** After the workflow runs, have the user open the result themselves — the file in their file manager or Obsidian. Seeing the artifact land is the point of the module.
4. **Record the output path** in the M8 ledger row's notes.
5. **Two habits worth one line each.** For bigger asks later: a plan-first mode (Claude drafts the plan, they approve, then it builds) catches misunderstandings before wasted effort. And when a conversation gets long and confused, a fresh session pointed at the saved files beats pushing on.

### Approval gates

- The research workflow: approved before it runs (it spends usage).
- Any file creation: manifest shown, approved first.
- Nothing in this module moves or deletes originals.

### Verification — m8-artifact

Read the workflow output path recorded in the M8 notes and open it. Pass: the approved workflow artifact (research note, action list, or project scaffold) exists at the recorded path.

### Human documentation

Card for the user's browser: https://www.augmentgrowth.ai/resources/claude-code-setup/reference/tokens-and-cost/ — what work costs and how to keep it cheap.

### Record

Update the M8 ledger row: status, date, installer version, last result, output path in notes. Next in the ladder is M10 (the tail runs M10 before M9 on purpose — a routine automates a workflow already proven). Offer it or close with the four-part hand-off.
