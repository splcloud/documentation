---
title: Autonomous mode
linkTitle: Autonomous mode
weight: 70
description: >-
  SPL Sense starts a measurement automatically as soon as it runs.
---

In autonomous mode, SPL Sense activates and starts a specific measurement by itself as soon as SPL Sense starts. This is
intended for permanently installed systems, for example in a club or on a Raspberry Pi: after a power failure or
restart, the system continues measuring without intervention.

## Setup

1. **Settings** › **Autonomous Mode**.
2. Set **Automatically run a measurement when running** to **On**.
3. Choose the **Measurement**. Only open measurements are offered.
4. **Save**. If SPL Sense is stopped and a sensor is connected, SPL Sense offers to start the measurement right away.

## Behaviour

- **When SPL Sense starts:** the chosen measurement is activated and started. If no sensor is connected, the
  measurement is **Interrupted** and starts recording as soon as the sensor is there.
- **Stopping:** you can stop the measurement at any time. It then stays stopped until SPL Sense starts the next time.
- **Completing:** when the measurement is completed, autonomous mode switches itself off.
- **Calibration:** with the automatic start, SPL Sense does not ask, even if the calibration has expired. The events
  show the reason **Automatically started as autonomous measurement**.

## For unattended operation

Combine autonomous mode with:

- an [operator PIN]({{< relref "settings#operator-pin" >}}), so that nobody changes the settings
- the [live screen in kiosk mode]({{< relref "live-screen#full-screen-and-kiosk" >}}) as a display
- the [cloud uplink]({{< relref "settings#spl-cloud" >}}), so you can see the measurement remotely, and with Pro
  [alarms]({{< relref "/docs/spl-cloud-pro/alarms" >}}) in case the measurement fails
