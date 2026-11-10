---
title: Measurement data
linkTitle: Measurement data
weight: 25
description: >-
  Days, chart, interval details, deviations, events, comments, excluded time ranges and reports.
---

The measurement page looks the same in SPL Sense and in SPL Cloud. What is described here applies to both; differences
in the reports are listed at the end.

## Measurement days and chart

The data is organized by measurement days; a measurement day ends at the measurement's day boundary. Each day shows the
values of the value profile, coloured according to the thresholds: yellow for **Notification**, orange for **Warning**,
red for **Limit**. **Show all days** displays older days.

The chart shows the course of the selected day:

- the values of the value profile as lines, the rating as a coloured band
- comments and events as markers
- excluded time ranges greyed out
- with an active leveler, also the signal level (line), the gain reduction and the correlation

The first values appear after the first full minute of recording.

## Interval details

A click into the chart opens the details of the minute at that point (an **interval**): all values, the spectrum in
third-octave bands and the check results. Use the arrows to move to the previous or next minute.

| Indication | Meaning |
|---|---|
| **Signature valid** | The data is unchanged since the sensor signed it. |
| **Signature invalid** / **Validation block missing** | The data cannot be proven to be unchanged. |
| **Calibration expired** | The data was recorded with an expired calibration. |
| **Clip** | The level was too high for the sensor (overload). The values of this minute are not reliable. |
| **Low Values** | The level was below the sensor's measuring range. |
| **Temperature** | The sensor was too hot. |
| **Voltage** | The sensor's supply voltage was too low. |
| **Weather Protection** | The compensation filter for the weather protection was switched on. |
| **Multiple Sensors Used** | The sensor was changed in this minute. |

## Deviations

The **Deviations** section lists, per value of the value profile, when the selected day exceeded a threshold, with the
highest value. A click on an entry draws the thresholds into the chart.

## Events

The **Events** section lists everything that happened with the measurement, newest first:

- recording started and stopped, with reason (for example manually, autonomous mode, microphone disconnected, sleep
  mode, sensor reconnected)
- measurement created, activated, completed, re-opened
- offsets, value profile and leveler settings changed, each with the old and new values
- leveler bypassed and re-enabled
- comments and changed excluded time ranges

If a change came via SPL Cloud or the API, this is indicated; for the cloud, also by whom.

## Comments

With **Add** › **Add comment** in the Events section you record something at a point in time, for example "Encore" or
"Offset checked with handheld meter". Comments appear in the chart and can be edited later. For a completed
measurement, comments are only possible up to the time of completion.

## Excluding time ranges

Some periods should not be included in the rating, for example tuning the system with pink noise before doors open.
With **Add** › **Exclude a time range** you define such a range with **From**, **To** and a comment.

An excluded range:

- is greyed out in the chart and marked **Not counted**
- does not count for maxima, the rating according to the value profile and the deviations
- is kept with all measurement data

**Count again?** removes the exclusion. Every change appears in the events.

## Reports and exports

| What | Where |
|---|---|
| Day report (PDF) of the selected day | **PDF** button next to the day |
| CSV of the selected day | **CSV** button next to the day |
| CSV of the whole measurement | **Measurement** menu › **Export all measurement days to CSV** |
| whole measurement as a backup | **Export measurement**, see [Measurements]({{< relref "measurements#import-and-export" >}}) |

In SPL Cloud, the day report (also with deviations) and a pictures report are available with
[Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}).

## Cloud uplink

If the cloud uplink is switched on, the measurement page shows the upload status: **Online**, **Offline** and how many
intervals, events and leveler statistics are still waiting for upload. Without internet, SPL Sense keeps measuring
normally and catches up with the upload.
