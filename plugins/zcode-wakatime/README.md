# zcode-wakatime

[WakaTime][wakatime] plugin for [ZCode][zcode]. Installs [wakatime-cli][wakatime-cli] into `~/.wakatime/`, checks for wakatime-cli updates on session start, and records AI coding heartbeats on user prompts, file-edit tool completions and session end.

## Install

In ZCode: **Settings → Plugins → Create → Add marketplace** → add `RoiexLee/zcode-wakatime` → install **zcode-wakatime**.

## Configuration

The plugin reads standard WakaTime settings from `~/.wakatime.cfg`.

Useful settings:

```ini
[settings]
debug = true                  ; verbose plugin logging to ~/.wakatime/zcode.log
proxy = https://127.0.0.1:8080 ; optional, used for wakatime-cli downloads
```

## License

BSD-3-Clause — Copyright (c) 2026 WakaTime. See [LICENSE](LICENSE).

Ported from [wakatime/codex-cli-wakatime][upstream].

[wakatime]: https://wakatime.com
[zcode]: https://zcode.z.ai
[wakatime-cli]: https://github.com/wakatime/wakatime-cli
[upstream]: https://github.com/wakatime/codex-cli-wakatime
