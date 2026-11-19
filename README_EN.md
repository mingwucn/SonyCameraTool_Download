# Sony Camera Tool v1.0.1

> This package contains camera App write functionality. Validation so far covers offline code, build, and packaging only; it is not a safety or feature acceptance result for any camera.

## Download and integrity

| File | Size | SHA-256 |
|---|---:|---|
| [`SonyCameraTool_v1.0.1.zip`](https://github.com/mingwucn/SonyCameraTool_Download/releases/download/v1.0.1/SonyCameraTool_v1.0.1.zip) | 32,106,759 bytes | `79bbc64148f88c2bb974d40420910035696e0af87fe3cd83ab3e9d3f3f4ec419` |
| `SonyCameraTool_v1.0.1_BUILD_MANIFEST.json` | supplied as a release asset | Records version, source state, executable and ZIP hashes, and source/hash data for 49 bundled payloads |

## v1.0.1 changes

- Fixes the restore-direction bug reported in [SonyCameraTool_Download issue #2](https://github.com/mingwucn/SonyCameraTool_Download/issues/2): restore now writes and verifies the planned destination bytes.
- Logs each target's read offset, observed bytes, desired bytes, and write/skip decision. Transaction backups distinguish camera pre-read values from planned targets.
- Bounds the Windows font-change notification so a hung top-level window cannot block application startup indefinitely.
- Scopes the UI to selected App targets and removes the “100% restore” claim, the unverified 60-second flash-commit instruction, and any driver-rebind instruction based only on a status message.

## α6700 Playback FTP status

The owner reports that Network FTP is configured and working. In the latest owner-reported C1/C2 Playback Custom Key picker check, **FTP Trans. (This Img.)** was selectable and **FTP Transfer** was missing from the list. v1.0.1 does not enable or fix the latter action; its App candidate remains an uninstalled, unverified offline reference. Assignment persistence and end-to-end FTP receipt have not been tested for this candidate.

## Verification limits

- Built with Python 3.10.20 and PyInstaller 6.22.3; all 8 `camera_tool_backend` tests passed.
- Frozen `--self-check`, `--describe`, and `--gui-self-check` passed; hashes for all 49 carried-forward payloads match the recorded source inventory.
- No camera was connected; no service/native camera helper was run; no App or WBI was changed; no FTP transfer was performed; no CI/CD was triggered.
- Offline build results do not replace independent code review or camera acceptance. Issue #2 remains open pending independent review and device acceptance. Check the release page before treating this candidate as published.

The current public download page is [SonyCameraTool_Download](https://github.com/mingwucn/SonyCameraTool_Download). Use the version and checksums shown on the release page.
