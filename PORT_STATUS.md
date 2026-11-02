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

