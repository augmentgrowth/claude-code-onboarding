# Preflight list — Claude Code setup

Version: 1.3.0

One list, three consumers, zero drift: the reachability preflight an agent runs before fetching the starter pack, the copy inside the pack itself, and the IT clearance page on the guide site are all built from this table. The site build fails if any copy drifts.

Check each `domain` row is reachable from the trainee's network, each `installer` row is permitted to run, and each `setting` row holds true. Rows marked `optional` unlock later modules; the setup completes without them.

| item | kind | required | purpose |
| --- | --- | --- | --- |
| claude.ai | domain | required | Claude app, sign-in, and agent fetches |
| www.augmentgrowth.ai | domain | required | Guide, spec, and starter pack downloads |
| code.claude.com | domain | optional | Official Claude Code docs |
| nodejs.org | domain+installer | optional | Node.js for some later tools |
| git-scm.com | domain+installer | required (Windows) | Git for Windows — the Claude desktop app requires Git to run local sessions, so this installs on day one on Windows (macOS gets git from Apple's Command Line Tools instead); also used by the GitHub backup module (M7) |
| github.com | domain | optional | GitHub backup module |
| obsidian.md | domain+installer | optional | Obsidian, the desktop vault viewer (M2); also the account/service for Obsidian Sync if chosen in M11 |
| Obsidian mobile app via the phone's app store | installer | optional | Mobile review & capture (M11) — iCloud and Obsidian Sync paths |
| OneDrive mobile app via the phone's app store | installer | optional | Mobile review & capture (M11) — OneDrive path; often already on work phones |
| Claude Desktop installer | installer | required | The desktop app the setup starts from |
| Claude Code CLI installer via claude.ai/install.sh | installer | required | The terminal agent the guide sets up |
| No administrator credentials | setting | required | No step requires administrator credentials; installers that demand one are skipped and reported |
