# Port status

- [x] Upstream package acquired and checksum recorded
- [x] Complete OpenSurge game data and bundled engine source confirmed
- [x] Reproducible content-port script added
- [x] Boot tested on Cradle AmigaOS 3 target
- [x] Title screen tested
- [ ] First playable level tested
- [x] Local stored-ZIP release candidate built

Compatibility target: the shared Amiga OpenSurge 0.6.1.3 RC engine. Public
binary/data releases are withheld until asset redistribution permission is
clear.

Cradle test (2026-11-02): the SAGE splash and real AS2R menu render. The
packaging script updates the old `MenuButtonList` declaration to the entity
tags expected by OpenSurge 0.6.1.3, eliminating the visible entity-policy
warning flood; the patched package still needs its final menu retest.
The local candidate contains 1,125 files in a 114 MiB stored `game.zip` and a
fixed-path launcher. Public data redistribution remains withheld.

## Standalone RC1 (5 November 2026)

- [x] Standalone LhA with the rc3 engine inside (`scripts/package-standalone.sh`)
- [x] No game data in git or in the archive; Install-AS2R builds it from the player's download
- [x] Lab t4-opensurge (5 Nov): Install-AS2R given the downloaded zip (121434129 bytes, SHA-256 checked on the host): size checked, unpacked with GFOpenCompress, three file sizes checked, Game drawer built beside the engine, MenuButtonList patched by PatchMenu.rexx, surge.cfg added, Unpack drawer removed
- [x] Game drawer compared with the upstream folder on the host: every copied file identical except the two the port changes; the Windows program, screenshots, logfile and docs left out
- [x] StartGame: SAGE splash, menu (PLAY), quest select
- [ ] First level: in two runs the Amiga stopped while the first level loaded (after "Loading image images/aqualake_mask.png"); the second time Fast RAM was down to 49 MB free on the lab's monitor and the CPU ended at pc ffff002c (a crash, not a hang in the Installer or launcher). Blocker for a playable release; see notes

The Installer ran unattended in the lab: a lab-only copy of Install-AS2R had its requesters replaced by fixed answers (choice 0: the archive) and nothing else changed. A first attended run hung the lab Installer at the drawer requester when the host lost its connection; that copy was discarded. The archive check on the Amiga is by size; the SHA-256 is printed in the ReadMe and the Installer's first message for the player to check. The first-level stop looks like the game outgrowing memory on the 68k (AS2R's Green Hill level loads several large masks) or an engine fault there; it is the same engine build that plays Sonic The Last Hope and Aishi & Reimu. Needs an engine-side look (memory use at level load) before AS2R is called playable; the package and Installer are not the cause.

## Standalone RC2 (6 November 2026): SHA-256 check in the Installer

- [x] Tools/SHA256 (port/sha256, built by scripts/build-sha256.sh with os32-gcc16-open6; 6612 bytes, same bytes on every build) in the drawer, Licences/SHA256.txt beside the other licences
- [x] Lab t4-opensurge: Tools/SHA256 gives OK/0 for the right hash, FAILED/10 for a wrong one, 20 for a missing file; inside an Installer script `(run ... (safe))` returns those codes
- [x] All three downloads (AS2R zip, Aishi & Reimu zip, Sonic The Last Hope.rar) check OK on the Amiga, 18-25 s each in the lab
- [x] Installer texts kept under 512 characters per literal: Installer 47.19 refused Install-SonicTLH's longer first message ("Symbol or String too long")
- [x] Install-AS2R: after the size check it asks "Check the SHA-256 of Another Sonic 2 Remake Android Compatible.zip before it is unpacked?" (Check it is the default); given the folder, it asks whether the player still has the zip. Archive checked on the Amiga by Tools/SHA256 (OK); the hand-run Installer test this round was Install-SonicTLH, the same generated code
- [ ] First level: unchanged from RC1 (engine side)
