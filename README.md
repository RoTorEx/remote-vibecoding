# Remote Vibecoding

One entrypoint for work across two independently versioned components:

- [Telegram Vibecoding](https://github.com/RoTorEx/telegram-vibecoding): Telegram interface, menus, formatting and media transport.
- [Vibecoding Core](https://github.com/RoTorEx/vibecoding-core): native host agents, state, speech recognition, API and operations.

Start agent sessions in this directory and follow `AGENTS.md`. It routes a narrow
task to its owner without loading the other component's implementation. Home and
this project root are separate launch locations in the Telegram bot.

## Checkouts

Clone this repository, then clone each component into its matching child folder:

```sh
git clone git@github.com:RoTorEx/remote-vibecoding.git
cd remote-vibecoding
git clone git@github.com:RoTorEx/telegram-vibecoding.git
git clone git@github.com:RoTorEx/vibecoding-core.git
```

All three Git histories are independent. The children are ignored by the root;
there are no submodules or pinned component revisions. Fetch/pull and commit in
the selected repository. The root has no application version or release process;
its agent router has a date/revision header. Each component owns its checks,
semantic versions and releases.

## Operation owners

One Compose project runs two containers. Compose, shared Make targets and the
workspace manifest remain owned by Core and are linked here. `docs` and `TASK.md`
also link to Core; read only what the task needs. Root `AGENTS.md`, `README.md`
and `.gitignore` belong to this repository.

Run common operations from this directory and component checks from their owner.
For configuration, deployment and recovery use `vibecoding-core/docs/operations.md`.
Keep `.env`, host credentials and runtime state outside Git. Personal agent
defaults belong to the installed user configuration, not this public repository.
