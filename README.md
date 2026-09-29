# MasterBrewery Fermenter Firmware

Public firmware distribution repository for the MasterBrewery Fermenter Controller.

This repository is updated automatically from the `main` branch of
`stamminnovation/esp32-fermentationcontroller`.

## Published files

- `firmware.bin` – current stable ESP32 application image
- `manifest.json` – release metadata used by the controller and FermenterControl

The controller and FermenterControl use `manifest.json` to determine whether a
newer stable firmware build is available. Firmware installation is always an
explicit user action; the repository does not enable unattended automatic
installation.

## Manifest schema

Example:

```json
{
  "schemaVersion": 1,
  "channel": "stable",
  "target": "riprapt",
  "board": "esp-wrover-kit",
  "version": "0.1.123",
  "build": 123,
  "gitHash": "1234abcd",
  "sourceCommit": "1234abcd...",
  "publishedAt": "2026-09-29T12:00:00Z",
  "firmwareUrl": "https://raw.githubusercontent.com/stamminnovation/mbfermfirm/main/firmware.bin",
  "sha256": "...",
  "size": 1234567
}
```

The source workflow builds `riprapt`, calculates the exact firmware SHA-256 and
size, then publishes both files in one commit to this repository.

## Source

Firmware source:

```text
https://github.com/stamminnovation/esp32-fermentationcontroller
```

The publishing workflow is:

```text
.github/workflows/publish-firmware.yml
```

Only successful builds from the source repository's `main` branch are
published here.

## Security note

The SHA-256 in the manifest protects against accidental corruption and lets the
controller verify that the received image matches the published release.
The current development stage does not yet use an asymmetrically signed
firmware image or signed manifest. Do not place credentials, controller
configuration files, or private keys in this public repository.
