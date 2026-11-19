# α6700 Playback Extras 0.6.0 experimental candidate

This folder stages the experimental playback-shortcut helper for independent review. It is not an official release and does not replace the existing `v1.0.0` release.

## Candidate scope

The package adds a separate guarded **FTP Transfer** action to the α6700 playback custom-key picker. Its offline package analysis identified one App logical byte at `0x03788dc3`; the candidate leaves the existing **FTP Trans. (This Img.)** row intact and does not read or write WBI for this action.

The package was built from private development source commit `c5b91087a60bcd613df9c8b4b159a88f6ab9a9e7`. Offline evidence for this candidate includes 10 frozen checks, a ZIP member/hash audit, and 157 focused tests.

## Evidence limits

No camera or USB operation was performed for this build. The current camera picker, assignment persistence, actual send behavior, receiver-side receipt, and transferred file hashes have not been verified with this candidate. Do not treat this experimental build as proof of end-to-end FTP or as a verified camera fix.

The camera observation that **FTP Trans. (This Img.)** was selectable while **FTP Transfer** was missing was reported by the owner; it is not a runtime observation from this build.

## Artifacts

- `SonyA6700PlaybackExtrasExperimental.exe` — SHA-256 `81c0b11f9ee577ce4380b93dc64c283c19fa034f27140603cdde4413f243fa54`
- `SonyA6700PlaybackExtrasExperimental_0.6.0-release.zip` — SHA-256 `ed0ff214c1d9e32a38c8fc3e62ff9d555bc5025f3f6b958a291f67ea7fb7d0c6`
- `BUILD.json` records source hashes, build tools, and package checks.
- `USER_GUIDE.md` documents use and limitations.

The candidate remains pending independent review. No public tag or GitHub Release has been created.