---
title: Value profiles
linkTitle: Value profiles
weight: 30
description: >-
  Which values are calculated, with which thresholds, and the built-in templates.
---

A value profile defines which values a measurement calculates and from when they count as too loud. It determines the
colours on the overview and in the chart, the deviations and the alarms in SPL Cloud.

## Structure

A value profile consists of one or more values. Each value has:

| Part | Options |
|---|---|
| **Integration Type** | **Leq** (equivalent continuous level) or **MaxF** (highest level with time weighting Fast) |
| **Weighting** | A, C or Z |
| **Time** | 1 to 60 minutes |
| **Notification**, **Warning**, **Limit** | thresholds in dB, each optional |

Examples: Leq, A, 60 minutes gives **LAeq 60′**; MaxF, C, 1 minute gives **LCFmax 1′**.

Averages are calculated as moving averages: LAeq 60′ is, at every minute, the average over the preceding 60 minutes,
also across the day boundary and across pauses. A value counts as above the threshold if it exceeds it; exactly equal is
still fine.

## Built-in templates

SPL Sense provides templates for Switzerland (V-NISSG) and Germany (DIN 15905-5). The values are listed under
[Templates for V-NISSG and DIN 15905-5]({{< relref "/docs/basics/templates-vnissg-din" >}}). Built-in templates cannot be
changed.

## Your own templates

Under **Settings** › **Value Profiles** › **Create** you create your own templates:

1. Enter a **Name**.
2. Add the values you need with **Add Value** and set the thresholds.
3. Click **Save**.

You can change or delete your own templates at any time. Measurements that use a template are not affected: the template
is copied into the measurement when it is created.

## Changing the value profile of a measurement

**Measurement** menu › **Edit Measurement** › **Edit Value Profile**. Here you choose another template or adjust the
values directly. If the profile differs from its template, SPL Sense indicates this; **Reset profile to template values**
restores the template's values.

When saving, SPL Sense recalculates all previous measurement days with the new profile. The measurement data itself does
not change. The change appears in the events with the old and new profile.
