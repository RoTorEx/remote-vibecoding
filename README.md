# Remote Vibecoding

One entrypoint for work across three independently versioned components:

- [Personal Notifier](https://github.com/RoTorEx/personal-notifier): independent outbound-only personal event feed for its current non-technical sources; it no longer collects or delivers Vibecoding outcomes.
- Web Vibecoding (private repository): iPhone-first web chats, media and agent overview inside the owner VPN.
- [Vibecoding Core](https://github.com/RoTorEx/vibecoding-core): native host agents, state, speech recognition, API and operations.

Start agent sessions in this directory and follow `AGENTS.md`. It routes a narrow
task to its owner without loading the other component's implementation. Home and
this project root remain separate registered launch locations in the private web
workspace. Telegram cannot start or control native agent sessions.

## Checkouts

Clone this repository, then clone each component into its matching child folder (web access requires the private repository):

```sh
git clone git@github.com:RoTorEx/remote-vibecoding.git
cd remote-vibecoding
git clone git@github.com:RoTorEx/personal-notifier.git /path/to/personal/projects/home/personal-notifier
git clone git@github.com:RoTorEx/vibecoding-core.git
git clone git@github.com:RoTorEx/web-vibecoding.git
```

All four Git histories are independent. The children are ignored by the root;
there are no submodules or pinned component revisions. Fetch/pull and commit in
the selected repository. The root has no application version or release process;
its agent router has a date/revision header. Each component owns its checks,
semantic versions and releases.

## Operation owners

Core and Personal Notifier have independent Compose projects. Personal Notifier owns its service in `/srv/personal-notifier`; Core does not start the retired shared bot. Node Tools collects Vibecoding technical outcomes through Core's read-only API, and Node Radar delivers them. The independently
installed web-vibecoding systemd service uses the existing Core Unix API; its
release/deployment belongs to web-vibecoding/docs/operations.md. Compose, shared Make targets and the
workspace manifest remain owned by Core. The workspace Makefile includes the
Core targets directly. Use [Core docs](vibecoding-core/docs/) and the
[Core task queue](vibecoding-core/TASK.md). The Compose manifest, workspace
manifest and environment example are under `vibecoding-core/deployment/workspace/`. Root `AGENTS.md`, `README.md`
and `.gitignore` belong to this repository.

Run common operations from this directory and component checks from their owner.
For configuration, deployment and recovery use `vibecoding-core/docs/operations.md`.
Keep `.env`, host credentials and runtime state outside Git. Personal agent
defaults belong to the installed user configuration, not this public repository.

## Installed host room

Development checkouts keep their registered cwd paths. Production uses
`/srv/remote-vibecoding/{runtime,config,data,logs}` with core/notifier/web component
directories. The installed remote-vibecoding operator uses `runtime/core/ops.py`;
no snapshot timer is installed. Only source builds consult this developer workspace.
Native Codex identities and user-wide credentials remain in their native home
locations. Core owns the operational installation contract.

Core, Personal Notifier and Web run in separate containers and independent application projects. The operator stays native;
Web owns its independent image and Compose controls. See each component's
operations documentation for mounts, first cutover and recovery.
