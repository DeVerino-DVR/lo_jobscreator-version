# lo_jobscreator — version

Public version manifest for the **lo_jobscreator** RedM resource.

This repo intentionally contains **no source code** — only:

- `version.txt` — the current released version
- `CHANGELOG.md` — patch notes per version

The resource reads these files on server start (`server/version.lua` →
`Config.VersionCheck`) and prints a notice if a newer version is available.
