# Changelog — lo_jobscreator

All notable changes to this resource are listed here, newest first.
The version on each line matches `version.txt` and the `version` field in `fxmanifest.lua`.

The server prints a notice on start if a newer version is available on GitHub
(`Config.VersionCheck`). Set `Config.VersionCheck.enabled = false` to disable it.

---

## 2.0.0

- Multi-framework: VORP / RSG / QBR / QR / RPX / RedEM — everything goes through
  the `Framework_*` bridge (`modules/editable/framework.lua`), no hardcoded calls.
- Admin panel rewrite (Vue NUI): jobs, gangs, public interactions, item creator,
  custom blips / peds / props / markers / vehicles, templates, backups, audit log,
  server config, in-game preferences.
- Placement modes: `raycast` (mouse pointing) and `gizmo` (3D drag/rotate, needs jo_libs).
- Interaction types: stash, farm, sell, process, craft, shop, vehicle garage,
  stable, duty, boss menu, teleport, clothing store / wardrobe, phone, dispatch.
- Dispatch / witness system using ox_lib's real dispatch UI (pinned notifications
  with accept/decline keys), with the default menu shipped and a customizable
  override in `modules/editable/client.lua`.
- Internal Discord log module (categories: jobs / gangs / public / items / actions
  / dispatch) — no `lo_logs` dependency, all strings localized.
- Internal usable-items system (eat / drink / shot / injection / horse stimulant…)
  with screen FX, drunk effect, stat modifiers and editable hooks.
- Leveled console logger (`Logger.trace/debug/info/warn/error`, `Config.LogLevel`,
  `/jc_loglevel <level>` to change live on server + clients).
- Languages: drop a `locales/<code>.json` file with a `"language"` key and a
  button appears automatically in the panel — add as many as you want.
- Exports for other resources (`getJobIsBoss`, `getJobSalary`, `GetCreatedJobs`,
  `GetCountByType`, `IsDutyActive`, `dispatchAlert`, …) — see `DOCUMENTATION.md`.
- RedM-safe throughout: native control hashes, no `os` on client, real key system
  via `lo_keysMapper` / internal `RegisterJcKey`, broken-ped detection & on-screen
  warning, horse/wagon spawn with long model timeouts.
