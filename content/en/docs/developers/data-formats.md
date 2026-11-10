---
title: Data formats
linkTitle: Data formats
weight: 30
description: >-
  CSV export and .splsense files.
---

## CSV

The CSV export is available per day and for the whole measurement, in SPL Sense and in SPL Cloud (there for the whole
measurement as ZIP).

- Separator: semicolon `;`
- one row per minute (interval)
- first column `Timestamp`: end of the interval in ISO 8601 format with time zone, for example
  `2026-07-12T22:15:00.0000000+02:00`
- then one column per value of the value profile, in its order, with name and unit in the header
- values in dB with one decimal place, including offset
- decimal separator according to the user interface language

Excluded time ranges, comments and events are not included in the CSV.

## `.splsense`

A `.splsense` file contains a whole measurement from SPL Sense with all recordings, signed intervals, events and
settings. It is used for backup and for transfer to another computer
([Import and export]({{< relref "/docs/spl-sense/measurements#import-and-export" >}})).

The format is internal and may change with new versions. For evaluation in your own software, use the CSV export and
the [SPL Sense API]({{< relref "sense-api" >}}).
