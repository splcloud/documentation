---
title: Account and interface
linkTitle: Account and interface
weight: 10
description: >-
  Account, profile, overview, archive and search.
---

## Account

You create an account on [spl.cloud](https://spl.cloud) with your email address, as described in the
[quick start]({{< relref "/docs/quick-start#8-connect-to-spl-cloud" >}}). An account is personal: create one for each
person and work as a team with [organizations]({{< relref "organizations" >}}) instead of sharing one account.

### Profile

**Settings** › **My Profile** › **Edit Profile**:

- **First Name**, **Last Name**, **Display Name** (how others see you)
- **Company Name** and address
- **Phone**: for SMS alarms. The national format also works (079 …); the cloud converts it to the international format.

### Language

**Settings** › **Language**: **Browser Default**, German, German (Switzerland), English or French.

## Status bar

- **SPL Sense instances**: for example "SPL Sense 3 of 5 online". A click shows all your instances with their state,
  current activity and, while measuring, the LAeq 1 s. Instances that lost their connection during a measurement are
  marked red. See [SPL Sense instances]({{< relref "instances" >}}).
- **Search** (magnifier), **Help** (question mark) and **Settings** (gear)

## Overview

The overview shows **Jobs and Measurements**:

- **Jobs** with their measurements
- **Independent Measurements**: measurements that are not assigned to a job. A new measurement from SPL Sense appears
  here first.
- at the bottom, the list of your **SPL Sense instances**

Each measurement shows its state and the values of the last days, coloured according to the thresholds of the value
profile. If a measurement is activated with Pro, this is shown.

**Create new job** creates a [job]({{< relref "jobs" >}}).

## Archive

Ten days after its end date, a job moves to the **Archive**; before that, the overview shows in how many days this will
happen. You reach the archive via **Previous jobs and measurements** at the bottom of the overview. Archived jobs and
measurements are kept in full.

## Search

With the magnifier or <kbd>Ctrl</kbd>+<kbd>K</kbd> (Mac: <kbd>⌘</kbd>+<kbd>K</kbd>) you search measurements, jobs,
instances, organizations and settings. Archived entries are listed last and marked. You can also find instances by
their operating system, for example "mac" or "linux". The search only shows what you are allowed to open.

## Live data

Pages with running measurements update themselves. If the connection drops, the cloud shows
**Connection to SPL Cloud lost** and reconnects; **Reconnect now** does it immediately.
