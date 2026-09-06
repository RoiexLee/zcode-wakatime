# zcode-wakatime

[WakaTime][wakatime] plugin for [ZCode][zcode] — automatic, per-project time tracking for AI coding sessions.

## How it works

The plugin registers ZCode lifecycle hooks:

| Event | Action |
|---|---|
| `SessionStart` | Installs/updates [wakatime-cli][wakatime-cli] into `~/.wakatime/` |
| `UserPromptSubmit` | Sends a project-directory heartbeat (60s throttle) |
| `PostToolUse` (edit tools) | Sends a file heartbeat for the edited file |
| `Stop` | Sends a final project-directory heartbeat (60s throttle) |

Heartbeats are tagged with category `ai coding` and plugin `zcode-wakatime`, so they show up separately on your [WakaTime dashboard][wakatime].

## Install

In ZCode: **Settings → Plugins → Create → Add marketplace**, then add this repository:

```
RoiexLee/zcode-wakatime
```

Install the `zcode-wakatime` plugin from it. Plugin hooks are picked up automatically — nothing is written to your ZCode `config.json`.

Requirements:

- Node.js available on `PATH` (the hook entrypoint is a Node script)
- A WakaTime account with the API key in `~/.wakatime.cfg` (any official WakaTime plugin sets this up)

## Configuration

The plugin reads standard WakaTime settings from `~/.wakatime.cfg`, including `proxy` and `debug`.

## License

[BSD-3-Clause](plugins/zcode-wakatime/LICENSE) — Copyright (c) 2026 WakaTime.

Ported from [wakatime/codex-cli-wakatime][upstream]: the wakatime-cli installer is retained from upstream, and the heartbeat core is adapted for ZCode.

[wakatime]: https://wakatime.com
[zcode]: https://zcode.z.ai
[wakatime-cli]: https://github.com/wakatime/wakatime-cli
[upstream]: https://github.com/wakatime/codex-cli-wakatime
