---
title: ui-service.keys development
status: reference
---

# ui-service.keys development

## Open the local Project

Run `make open` on macOS Apple Silicon. It opens this repository's `gams.json`
using `tools/gams.app`, downloaded from the latest GAMS release only when absent.
The release's accompanying notices remain in `tools/gams-release-notices/`.
An existing Host is never updated implicitly; Gatekeeper settings are not changed.
The launch explicitly sets `GAMS_APP_CWD` to this repository.

The Project selects `src/ui-plugins/keys.js` directly; there are no compiled local artifacts
or neighboring-checkout dependencies. The file browser supplies a minimal Host
workspace, not a separate demo View. Its FS/layout plugins, remaining shell UI
Services and theme are pinned to published release assets in `gams.json`.
The first launch needs network access; downloaded Units live in ignored
`gams_modules/`. Keyboard bindings are empty, so no Lua plugin is required.

## Check changes

Run `make check` (Node.js 24 and Python 3) for the existing source and release
checks. Runtime source, legal evidence and tag-publication policy are unchanged.
See the repository's `PUBLISHING.md` for packaging and release gates.

## Documentation

- `make serve-docs DOCS_PORT=8080` previews this `docs/` directory.
- `make validate-docs` validates links and wiki configuration.
- `make docs` builds the portable site in `build/site/`.

These commands download pinned `justgook/wiki` v1.4.0 and require Make, curl, Bash,
Node.js 24 and network access on the first run. `DOCS_PORT` is independent of the
Host. Every push to `release` builds with `make docs` and deploys GitHub Pages;
version-tag publication remains separate. Repository Pages must use Actions.
