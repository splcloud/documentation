---
title: Operation
linkTitle: Operation
weight: 40
description: >-
  Network access, kiosk display and operation as an unattended permanent measuring station.
---

## Addresses

With port `8080` from the [installation]({{< relref "installation" >}}):

| | Address |
|---|---|
| Web interface | `http://<ip-address>:8080` |
| Live screen | `http://<ip-address>:8080/measurement/live` |
| Live screen in kiosk mode | `http://<ip-address>:8080/measurement/live?kiosk` |
| [SPL Sense API]({{< relref "/docs/developers/sense-api" >}}) | `http://<ip-address>:8080/api` |

On the Raspberry Pi itself, you can use `localhost` instead of the IP address.

## Kiosk display

For a permanent display, for example a screen at the DJ booth, the browser opens the live screen directly in kiosk mode,
for example with Chromium:

```bash
chromium-browser --kiosk "http://localhost:8080/measurement/live?kiosk"
```

Kiosk mode only shows the widgets and a narrow status bar and adapts to the screen size. See
[Live screen and kiosk]({{< relref "/docs/spl-sense/live-screen#full-screen-and-kiosk" >}}).

## Unattended permanent measuring station

1. Switch on [autonomous mode]({{< relref "/docs/spl-sense/autonomous-mode" >}}): the measurement starts by itself
   after every restart, for example after a power failure.
2. Set an [operator PIN]({{< relref "/docs/spl-sense/settings#operator-pin" >}}): without the PIN, only the live screen
   is accessible, also in the browser of other devices.
3. Connect to [SPL Cloud]({{< relref "/docs/spl-sense/settings#spl-cloud" >}}) and switch on the cloud uplink.
4. Optionally with Pro: [alarms]({{< relref "/docs/spl-cloud-pro/alarms" >}}) on failure and
   [remote control]({{< relref "/docs/spl-cloud-pro/remote-control" >}}).

## Limitation

You cannot calibrate the sensor on Linux. For that you need SPL Sense for Windows or macOS.
