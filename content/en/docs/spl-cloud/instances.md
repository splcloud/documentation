---
title: SPL Sense instances
linkTitle: SPL Sense instances
weight: 30
description: >-
  Monitor and manage registered SPL Sense installations.
---

Every installation of SPL Sense that is registered with SPL Cloud is called an **instance**: a laptop, a desktop PC or a
Raspberry Pi. How to register an instance is described under
[SPL Sense › Settings]({{< relref "/docs/spl-sense/settings#spl-cloud" >}}).

## States

| State | Meaning |
|---|---|
| **Measuring** | SPL Sense is online and recording. |
| **Connection lost** | The instance stopped reporting during a measurement. SPL Sense usually keeps measuring and uploads the data as soon as internet is back. |
| **Online** | SPL Sense is running and connected, but not measuring. |
| **Offline** | SPL Sense is not running or has no internet. The last contact is shown. |

## Where to find instances

- **Status bar**: "SPL Sense 3 of 5 online", with a list of all your instances
- **Overview**, at the very bottom: all instances with state, activity, owner and current level
- **Settings** › **Personal Sense Instances** and on the page of each organization

Each instance shows the icon of its operating system (Apple, Windows, Linux).

## Instance page

Clicking an instance shows:

- what it is doing: during a measurement, the running measurement with the current 1-second values, with an active
  leveler also gain reduction and correlation; when offline, the last contact
- the **Details**: Instance ID, host, operating system, owner, registration date
- with [Pro]({{< relref "/docs/spl-cloud-pro/remote-control" >}}), remote control

## Who owns the data

A new measurement uploaded by an instance belongs to the owner of the instance. Only instances of the same owner may
upload into an existing measurement.

## Changing the owner

You change the owner of an instance by registering it again:

1. In SPL Sense: **Settings** › **Cloud** › **Unregister Instance**.
2. **Register instance** and, when confirming in the cloud, choose the new **Owner**.
3. In SPL Sense, switch on the **Cloud Uplink** for new measurements.

The instance keeps its ID. Measurements that have already been uploaded keep their previous owner. The instance can no
longer upload into them, because only instances of a measurement's owner may upload into it. So change the owner
between two assignments, not during a running measurement.

## Removing an instance

On the instance page, in the menu: **Unregister Instance**. The instance can then no longer upload anything. The
measurements in the cloud are kept. Also unregister the instance in SPL Sense so that it stops trying to connect.
