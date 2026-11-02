# AS2R: Another Sonic 2 Remake for AmigaOS 3

Reproducible content-port tooling for running **AS2R: Another Sonic 2 Remake**
with the shared [Amiga OpenSurge](https://github.com/DalsinAI/amigaopensurge)
engine. This repository does not fork the engine or its graphics stack.

## Upstream

- Showcase: <https://sonicfangameshq.com/forums/showcase/as2r-another-sonic-2-remake-sage-22-demo.1389/>
- Expected archive SHA-256: `dd79b04d12164ff5572a0abed1f38930e3d102d498d9113f82aed00a3a9eece2`
- Expected extracted directory: `Another Sonic 2 Remake`
- Original engine: OpenSurge 0.6.0.1 / Allegro 5.2.7-1

The downloadable package contains complete OpenSurge GPLv3 engine source, but
the showcase does not grant clear redistribution permission for all bundled
game assets. Therefore this repository publishes the port recipe and metadata,
not the upstream archive or a repackaged game.

## Prepare a local port

```sh
./scripts/prepare-amiga-port.sh \
  "/path/to/Another Sonic 2 Remake" \
  ./dist/AS2R
```

Install the QPAK-enabled shared engine at `DH1:OpenSurgeRC1`, then run the
prepared port with `Execute DH1:AS2R/StartGame`. This uses OpenSurge's `--game`
compatibility path rather than copying or forking the engine.

See [PORT_STATUS.md](PORT_STATUS.md) for validation results.

