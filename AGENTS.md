---
version: "2026-11-22.2"
---

# Remote Vibecoding router

Start sessions in this root. Work personally by default; use subagents only with
the user's explicit permission. Route by the requested outcome and load only the
selected component's instructions and relevant sources. A narrow task does not require reading both implementations.

| Task | Read next |
| --- | --- |
| Mobile web UI, browser uploads, web access or frontend deployment | `web-vibecoding/AGENTS.md` |
| Personal non-technical notifications | `../../home/personal-notifier/AGENTS.md` |
| Vibecoding technical outcome collection or Telegram delivery | `../../infrastructure/node-tools/AGENTS.md` and `../../infrastructure/telegram-node-radar/AGENTS.md` |
| Native execution, sessions, queues, speech recognition, API, deployment or backups | `vibecoding-core/AGENTS.md` |
| A change crossing the Core/consumer boundary | Core, Node Tools and Node Radar instructions, plus their relevant API contracts |
| Workspace routing, repository layout or this entrypoint | This file and `README.md`; component rules only if their files change |

Follow the selected repository's router and applicable nested instructions before
editing. Keep product behavior and operating procedures with their existing
component owner; do not copy their documentation into this entrypoint. Root
startup must not bulk-load component docs, saved tasks or unrelated projects.

This root, its Core/Web child directories and the external Personal Notifier,
Node Tools and Node Radar checkouts are independent Git repositories. Run
Git, checks and releases in the repository that owns each change. Refresh each
selected existing checkout before work; preserve unrelated files and commits.
The child repositories are ignored directories, not submodules or pinned copies.
A cross-component task may use one session while keeping commits independent.

The root has no product version, release tags or container. Only this AGENTS.md
uses YYYY-MM-DD.N: advance it for content edits using Warsaw's date; copying it
keeps its version. Components retain their own versions and Kernel rules.

Preserve native identities, captured input, private state and independent bot
updates. Keep credentials outside Git. Write artifacts in English. Do not add
model instructions, execution approval gates or services as a side effect.
