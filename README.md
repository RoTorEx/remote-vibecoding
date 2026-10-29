# Remote Vibecoding

One entrypoint for work across three independently versioned components:

- [Telegram Vibecoding](https://github.com/RoTorEx/telegram-vibecoding): notification-only Telegram companion with web-chat links and read-only activity statistics.
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
git clone git@github.com:RoTorEx/telegram-vibecoding.git
git clone git@github.com:RoTorEx/vibecoding-core.git
git clone git@github.com:RoTorEx/web-vibecoding.git
```

All four Git histories are independent. The children are ignored by the root;
there are no submodules or pinned component revisions. Fetch/pull and commit in
the selected repository. The root has no application version or release process;
its agent router has a date/revision header. Each component owns its checks,
semantic versions and releases.

## Operation owners

One Compose project runs Core and Telegram in two containers. The independently
installed web-vibecoding systemd service uses the existing Core Unix API; its
release/deployment belongs to web-vibecoding/docs/operations.md. Compose, shared Make targets and the
workspace manifest remain owned by Core and are linked here. `docs` and `TASK.md`
also link to Core; read only what the task needs. Root `AGENTS.md`, `README.md`
and `.gitignore` belong to this repository.

Run common operations from this directory and component checks from their owner.
For configuration, deployment and recovery use `vibecoding-core/docs/operations.md`.
Keep `.env`, host credentials and runtime state outside Git. Personal agent
defaults belong to the installed user configuration, not this public repository.
