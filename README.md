# ui-service.keys

Dispatches configured keyboard shortcuts to GAMS actions. A UI Service for [GAMS](https://github.com/kkgams/gams); Host APIs and separately configured Units are not bundled.

| Service | Source / deployed entry | Screenshot | License | Original work |
| --- | --- | --- | --- | --- |
| `ui.keys` | [`src/ui-plugins/keys.js`](src/ui-plugins/keys.js) → `ui-plugins/keys.js` | Not applicable | [Apache-2.0](LICENSE), [NOTICE](NOTICE) | [Romāns Potašovs / GAMS](https://github.com/justgook/gamectl) |

## Development

Requires Make, Node.js 24, Python 3, curl, zip/unzip and shasum. Documentation downloads pinned justgook/wiki v1.4.0 on first use. Local launch requires macOS Apple Silicon and network access for the released Host and pinned supporting Units.

| Command | Purpose |
| --- | --- |
| `make open` | Open local `gams.json` using the released Host; preserve existing Host tools. |
| `make check` | Check service JavaScript syntax. |
| `make package` | Build the stable-name ZIP and `SHA256SUMS` under `build.nosync/`. |
| `make serve-docs DOCS_PORT=8080` | Preview the wiki on an independent port. |
| `make docs` | Build the wiki under `build.nosync/site/`. |
| `make validate-docs` | Validate wiki configuration and links. |
| `make clean` | Remove entire `build.nosync/`, `tools/` and `gams_modules/`, including unmarked tools/caches; refuse tracked files and symlinks in all targets before deleting anything. |

The local Project loads canonical service source, with supporting published Units pinned in `gams.json`. `make open` explicitly sets `GAMS_APP_CWD` and `GAMS_CONFIG`; no sibling checkout is required. Clean leaves files outside those three directories untouched. No Host GUI validation is implied by syntax checks.
