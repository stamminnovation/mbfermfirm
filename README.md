# MasterBrewery Fermenter Firmware

Public firmware distribution repository for the MasterBrewery Fermenter Controller.

The repository is updated automatically from the `main` branch of
`stamminnovation/esp32-fermentationcontroller`.

Published files:

- `firmware.bin` – current ESP32 application image
- `manifest.json` – firmware version, build, SHA-256, size, source revision and download URL

Do not upload controller configuration backups or credentials to this repository.

The controller and FermenterControl use `manifest.json` to determine whether a
newer firmware version is available. Firmware installation remains an explicit
user action; updates are never installed automatically.
