---
title: Alarms
linkTitle: Alarms
weight: 40
description: >-
  Notification by email and SMS when a measurement exceeds a limit or stops sending data.
---

SPL Cloud checks the running Pro measurements every minute and notifies the registered recipients:

- **Exceedance**: a value is above a threshold of the measurement's value profile.
- **Downtime**: a running measurement stops sending data, for example because power or internet is gone.

Alarms only run for measurements with Pro. Other measurements in the same scope are skipped.

## Where to set up alarms

- For a whole **job**: menu **Job** › **Alarms**. The setting applies to all its measurements.
- For a **single measurement**: menu **Measurement** › **Alarm configuration**. For an independent measurement, this is
  the only way. If the measurement belongs to a job, this setting overrides the job's setting for this one measurement.

At the top of the page you choose the scope: **Full Job** or **Single Measurement**. The list below shows the affected
measurements and points out measurements without Pro or without limits.

## Settings

First switch on **Enable alarms for this scope**.

### Exceedance

- **Trigger at severity**: which thresholds of the value profile trigger an alarm: **Notification**, **Warning**,
  **Limit**. The thresholds themselves come from each measurement's value profile. Without thresholds in the value
  profile, there are no exceedance alarms.
- **Sustained for**: the number of minutes the value must stay above the threshold before an alarm is triggered. This
  filters out short peaks. Default: 15 minutes; 5 to 15 minutes are common.

### Downtime

- **Silence before alarm**: the number of minutes data may be missing before a downtime alarm is triggered. Default:
  30 minutes. Devices on mobile networks often upload in bursts; don't choose too short a time for them.

### End of an alarm

**Also notify when an alarm clears**: a second message as soon as the level is normal again or data arrives again. Off
by default, because it roughly doubles the number of messages. Leave it off if recipients get SMS.

## Recipients

Recipients don't need an SPL Cloud account. With **Add recipient** you enter per person:

- **Email** and/or **Phone**. SMS needs a phone number. The national format also works (079 …); it is converted to the
  international format.
- **Receives**: **All alarms**, **Downtime only** or **Limit alarms only**. Whoever brings a device back online rarely
  needs exceedances, and whoever monitors levels rarely needs downtime alarms.

It's quicker with **Add me** and **Add organization members**: name, email and, if stored in the profile, the phone
number are taken over.

## When notifications are sent

- **Exceedance**: when the first severity is reached and again at every change of severity (for example from Warning to
  Limit or back). As long as the severity stays the same, no further message is sent.
- **Downtime**: once, when the downtime is detected.
- Several alarms in the same minute are combined into one message.
- The message contains a link to the measurement or job in SPL Cloud.
