---
title: Remote control and comments
linkTitle: Remote control
weight: 50
description: >-
  Control SPL Sense from SPL Cloud, set comments and excluded time ranges from the cloud.
---

With remote control, you operate SPL Sense from SPL Cloud, for example a Raspberry Pi in a rack or a laptop at another
stage.

## Prerequisites

- **Allowed in SPL Sense:** **Settings** › **Cloud** › **Allow remote control**. Off by default. This way the person on
  site always decides whether their instance may be remote controlled.
- **Instance online:** commands only go to a connected instance. There is no queue.
- **Pro on the measurement:** only measurements with Pro can be controlled.
- **Permission:** the owner of the instance; for an instance of an organization, all members. People with read access or
  a shared link can never control.
- **SPL Sense version 2.0 or later.**

## What is possible

On the instance or measurement page, in the **Remote control** area:

| Action | Note |
|---|---|
| **Start**, **Stop** | |
| **Leveler bypass**, **Disable bypass** | |
| Switch measurement (**Make current**), deactivate | only when the measurement is stopped |
| Create a **New measurement** | with name, day boundary and a value profile template of the instance. The cloud uplink is always on; Pro can be activated at the same time. |
| Change name and day boundary | not while the measurement is running |
| Change **Offsets** | not while the measurement is running |
| Switch **Value profile** | one of the instance's templates; not while the measurement is running |
| **Leveler settings**: mode, limits, line offsets | also during the measurement, applies immediately |
| **Complete measurement**, **Reopen** | |

**Measurements on the instance** shows all measurements of SPL Sense, including those without cloud uplink. Only
measurements that are in the cloud and have Pro can be controlled.

## What is not possible

- Calibration and software updates
- Measuring the line offset (needs noise and silence on site)
- Setting up the leveler connection
- Editing custom limits in the value profile; this is only possible on the instance

## Confirmation and feedback

Every command that changes something asks first, with measurement and instance in the text, for example "Stop
measurement 'Main stage' on 'Laptop-FOH'?".

After that, the cloud reports the result. If the instance doesn't answer in time, the message says that the command may
have been executed anyway; check the state of the instance in that case.

In SPL Sense, every command from the cloud appears as a message, and the measurement's events show who triggered it
(**remotely by …**).

If people on site and in the cloud change something at the same time, the last change wins.

## Comments and excluded time ranges

With Pro, you can also add **comments** and **exclude time ranges** in the cloud in the **Events** area, just as in
[SPL Sense]({{< relref "/docs/spl-sense/measurement-data#comments" >}}). This also goes via remote control: the instance
must be online and allow remote control.
