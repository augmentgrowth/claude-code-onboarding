# M11 · Your notes on your phone

Your vault already works: Claude writes notes, your computer shows them. This last module puts those same notes in your pocket — review a summary while waiting for coffee, capture a thought on a walk, find it on the computer when you sit down.

M11 is optional, honestly so. A desktop-only vault is a complete setup. Do this when you catch yourself wishing your notes were in your pocket.

## Agent procedure

Ledger row: M11. Verification ID: `m11-sync-path`. The module recommends exactly ONE path — never a comparison matrix.

1. **Re-run sync detection first (it is cheap).** Repeat the read-only sync-environment detection from the setup skill's vault-placement reference and compare against the `sync-env:` note in the ledger (written at vault build). If the note is missing, unparseable, or the environment changed (IT turned on folder backup, or the vault moved), use the fresh detection and update the note — never compute a recommendation from a stale fact.
2. **Ask three plain questions**, one at a time: What phone — iPhone or Android? Does anything at their company decide software for them (IT approval)? Would they rather pay a few dollars a month for the smoothest option, or use what they already have?
3. **Recommend exactly one path** from detection plus the answers. The iCloud path needs an iPhone; the OneDrive and Obsidian Sync paths work with either phone.
   - **OneDrive detected and the vault already lives in a synced folder** (the common Windows work-machine case): the OneDrive path. Nothing new installs. Proof step FIRST: the user opens the OneDrive app on their phone, browses to the vault folder, and opens one note. Opens and edits as formatted text? Proven — then teach the pin ("Always keep on this device" on the vault folder, so the computer always holds the real files). If the phone cannot open or edit the note, this path is not available on their account — say so calmly, and fall back to Obsidian Sync or skip. Never leave them on a path whose proof failed. If the vault is local and the user wants this path, the vault must first move into the synced Documents folder: propose the move, copy-first, verify, then retire the old copy with approval.
   - **Mac + iPhone, prefers free**: the iCloud path. The phone app only sees vaults inside Obsidian's own iCloud home, so this is a guided move, done copy-first: in Obsidian on the Mac, create a new vault with "Store in iCloud" on; copy the vault's contents in; the user opens Obsidian on the iPhone and confirms the notes are there; only after the phone shows them does the old folder retire, with approval. Update the ledger note (`vault: synced`) and tell the user plainly that their vault's home has moved. Guard against offloading: check whether "Optimize Mac Storage" is on (System Settings > Apple ID > iCloud) and, with approval, help turn it off — or explain the tradeoff in one line if they would rather keep it — otherwise the Mac can swap notes for placeholders that re-download on open.
   - **Can pay and IT allows (or no sync system detected)**: Obsidian Sync — the smoothest option, best at the moment two devices edit at once. Setup follows Obsidian's own in-app flow (account, Sync toggle, choose the vault); the vault stays exactly where it is. At work, a quick question to IT first is worth it.
   - **None fit** (IT says no, prefers not to pay, no phone interest): skip for now, recorded as a choice. Desktop-only remains a complete setup, and this module is open forever.
4. **Teach the two habits**, whichever path: don't edit the same note on two devices at the same moment (different notes at the same time are fine), and a "conflicted copy" file is a duplicate to clean up, never a lost note — the conflicted-copy card in `curriculum/troubleshooting.md` has the cleanup.
5. **Close with the cross-device proof.** The user writes one line in a note on the phone and watches it appear on the computer, or the reverse, and confirms it in plain words.

### Approval gates

- Any vault move (OneDrive local-to-synced, or the iCloud home move): copy-first, verified, and the old copy retires only with its own explicit approval.
- App installs on the phone are the user's own doing, in their app store.
- A failed proof step ends that path; never talk the user past it.

### Verification — m11-sync-path

Read the M11 row's notes for the chosen path (`onedrive`, `icloud`, `obsidian-sync`, or `skipped`), then run that path's proof: for the three sync paths, the user confirms in plain words that a note edited on the phone appeared on the computer (or the reverse); for skipped, the row simply records the choice — a recorded skip passes, a silent omission never does.

### Human documentation

Card for the user's browser: https://www.augmentgrowth.ai/resources/claude-code-setup/reference/how-claude-sees-files/

### Record

Update the M11 ledger row: status, date, installer version, last result, `path: <choice>` in notes, and the refreshed `sync-env` note if detection changed. This closes the ladder — offer the receipt (`curriculum/receipts.md`) if one has not been made, then the four-part hand-off.
