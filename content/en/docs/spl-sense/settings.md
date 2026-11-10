---
title: Settings
linkTitle: Settings
weight: 80
description: >-
  Operator PIN, connection to SPL Cloud and remote control, API, language.
---

Open the settings with the gear at the top right. Each row shows the current state.

| Group | Settings |
|---|---|
| **Measuring** | [Value Profiles]({{< relref "value-profiles" >}}), [Live Screens]({{< relref "live-screen" >}}), [Autonomous Mode]({{< relref "autonomous-mode" >}}) |
| **Device** | [Sensor Information]({{< relref "sensor-and-calibration" >}}), [Leveler]({{< relref "leveler#setting-up-the-l1-itself" >}}), [Update]({{< relref "installation-and-updates#updates" >}}) |
| **Access and connections** | Operator PIN, Cloud, API, Language |
| **About** | Version, release notes, contact, privacy, open source licenses |

## Operator PIN

An operator PIN protects SPL Sense against changes. Without a PIN, anyone with access to SPL Sense can change
everything.

1. **Settings** › **Operator PIN**.
2. Enter a **New PIN** (4 to 8 digits) and repeat it.
3. **Save**.

With a PIN set:

- all pages except the live screen are locked. SPL Sense shows **SPL Sense is locked** and asks for the PIN.
- SPL Sense also asks for the PIN when leaving the live screen and full screen.
- the PIN applies in the app and in the browser (web server mode).

**Remove PIN** lifts the protection again.

## SPL Cloud

Under **Settings** › **Cloud** you connect SPL Sense with SPL Cloud. A registered installation is called an
**instance** in the cloud.

### Registering

1. **Register instance**. SPL Sense needs internet for this.
2. Open the link shown or scan the QR code with another device. The code is only valid for a short time; **Get new code**
   gives you a new one.
3. Log in to SPL Cloud and confirm the registration. Choose the **Owner**: you personally or an organization you are a
   member of. See [Organizations]({{< relref "/docs/spl-cloud/organizations" >}}).

The page then shows **Instance is registred** with instance ID, host, owner and the connection status (**Online**,
**Connecting...**, **Offline**).

Which measurements go to the cloud is set per measurement with the **Cloud Uplink**, see
[Measurements]({{< relref "measurements#edit" >}}).

### Unregistering

**Unregister Instance** disconnects SPL Sense from the cloud. The cloud uplink is switched off for all measurements;
what is already in the cloud stays there. After registering again, you switch the uplink back on per measurement.

If the page shows **Authentication failed!**, unregister the instance and register it again.

### Allowing remote control

With **Allow remote control**, people with access to this instance in SPL Cloud may start and stop, switch and create
measurements and change offsets, leveler and value profile, as long as SPL Sense is online. Calibration and updates are
never possible remotely.

Remote control is off by default. When it is on, the status bar shows this, and every command from the cloud appears as
a message and in the measurement's events, with the name of the person.

In the cloud, remote control requires [SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/remote-control" >}}) on the
measurement.

## API

The SPL Sense API lets you monitor and control SPL Sense and connect external audio processors as levelers. It is off by
default. Details under [SPL Sense API]({{< relref "/docs/developers/sense-api" >}}).

## Language

German, English, French or **System Default**.

## About

Version, release notes (English), contact, privacy policy and the open source licenses used.
