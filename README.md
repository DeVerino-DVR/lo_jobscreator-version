# lo_jobscreator — version

Public version manifest for the **lo_jobscreator** RedM resource.

This repo intentionally contains **no source code** — only:

- `version.txt` — the latest released version
- `patchnote.txt` — that version's patch notes (the text inside `<patchnote> ... </patchnote>`)

The resource compares its `fxmanifest.lua` `version` field against `version.txt`
here on server start (`server/version.lua` → `Config.VersionCheck`) and prints a
notice + these patch notes if a newer version is available.
