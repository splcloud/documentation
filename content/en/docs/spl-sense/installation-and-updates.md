---
title: Installation and updates
linkTitle: Installation and updates
weight: 10
description: >-
  Windows, macOS and Linux, updates and where SPL Sense stores its data.
---

## Platforms

| Platform | Operation |
|---|---|
| Windows | Desktop app |
| macOS (Apple silicon and Intel) | Desktop app |
| Linux on ARM and ARM64, e.g. Raspberry Pi | Web server: operated in the browser, also from a tablet or phone on the same network |

The features are the same everywhere. The only exception: you can [calibrate]({{< relref "sensor-and-calibration" >}})
the sensor only in the desktop app.

## Installation

| Platform | Download |
|---|---|
| Windows (64-bit) | [SPLSenseSetup.exe](https://r.spl.swiss/dl/splsense/win-x64/SPLSenseSetup.exe) |
| macOS with Apple chip (M1 and newer) | [SPLSense-osx-arm64-Setup.pkg](https://r.spl.swiss/dl/splsense/osx-arm64/SPLSense-osx-arm64-Setup.pkg) |
| macOS with Intel processor | [SPLSense-osx-x64-Setup.pkg](https://r.spl.swiss/dl/splsense/osx-x64/SPLSense-osx-x64-Setup.pkg) |
| Linux (Raspberry Pi) | see [SPL Sense for Linux]({{< relref "/docs/linux" >}}) |

Open the downloaded file and follow the installer. To find out which Mac you have, go to Apple menu › **About This
Mac**: "Chip" means Apple chip, "Processor" means Intel.

## First start

On first start, SPL Sense shows a privacy notice. **Accept and Continue** proceeds, **Close Application** closes
SPL Sense.

## Updates

SPL Sense checks by itself whether a new version is available. If so, the notice **Update available** appears on the
overview with the buttons **Update** and **Remind me later**.

1. Stop a running measurement. No update can be installed during a measurement.
2. Click **Update** and then **Update and restart**.
3. SPL Sense downloads the new version, installs it and restarts.

If SPL Sense does not restart by itself after the update, start it manually. After a restart, no measurement is active
unless [autonomous mode]({{< relref "autonomous-mode" >}}) is switched on.

The current version and the version history are under **Settings** › **About**.

## Where the data is stored

SPL Sense stores all measurements locally on the computer:

| Platform | Folder |
|---|---|
| Windows | `%AppData%\SPLSense` |
| macOS | `~/Library/SPLSense` |
| Linux | `~/.SPLSense` |

Back up this folder regularly or switch on the [Cloud Uplink]({{< relref "settings#spl-cloud" >}}) for your
measurements. You back up individual measurements as `.splsense` files, see
[Import and export]({{< relref "measurements#import-and-export" >}}).
