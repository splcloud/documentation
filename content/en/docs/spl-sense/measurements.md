---
title: Measurements
linkTitle: Measurements
weight: 20
description: >-
  Life cycle of a measurement: create, activate, measure, edit, complete, import and export.
---

A measurement stands for one measuring point. It contains its settings (value profile, day boundary, offsets, leveler)
and all recorded data. A measurement can run over many days and be started and stopped as often as you like.

## Flow

```text
create / import
        │
        ▼
     open ──activate──▶ active ──Start──▶ running ──Stop──▶ active (stopped)
        ▲                  │                │ sensor gone   ▲
        │             deactivate            ▼               │ sensor back
        └──────────────────┘           interrupted ─────────┘
        │
    complete ──▶ completed ──re-open──▶ open
```

- **Activate:** at most one measurement is active at any time; SPL Sense records only into it. You can only switch when
  the active measurement is stopped.
- **Start and stop:** **Start** needs a connected sensor. **Stop** asks for confirmation. If the leveler is active,
  SPL Sense points out that it will be switched off when stopping.
- **Interrupted:** if the sensor is unplugged or delivers no values for 20 seconds (for example because the computer was
  asleep), the measurement is interrupted. When the sensor delivers data again, it continues by itself. You end an
  interrupted measurement with **Stop**.
- **Deactivate:** **Measurement** menu › **Deactivate**. The measurement remains open but is no longer active.
- **Restart of SPL Sense:** after a restart, no measurement is active. If a measurement should continue automatically,
  use [autonomous mode]({{< relref "autonomous-mode" >}}).

## Create

On the overview, **New measurement**:

| Field | Meaning |
|---|---|
| **Name** | Required. Appears on the overview, in reports and in SPL Cloud. |
| **Value Profile** | A template (copied), **Custom** (the editor opens afterwards) or **None**. See [Value profiles]({{< relref "value-profiles" >}}). |
| **Day Boundary** | Time between 00:00 and 06:00 at which a measurement day ends. |
| **Cloud Uplink** | Uploads the measurement to SPL Cloud. Only possible if SPL Sense is registered with the cloud. |

A new measurement is not yet active. Its leveler is set to **SPL Tools L1 (USB)** and mode **Off**.

## Edit

**Measurement** menu › **Edit Measurement**. Possible as long as the measurement is not running, not interrupted and
not completed. You can also edit a measurement that is not active while another one is recording.

- **Name**, **Day Boundary**
- **Cloud Uplink:** switching it on uploads all data of the measurement, including what was already recorded.
  Switching it off stops the upload; what is already in the cloud stays there.
- **Offsets** for A, C and Z, see below
- **Value Profile:** adjust it with **Edit Value Profile**

If you change the day boundary or value profile, SPL Sense recalculates the limits and measurement days. Every change
of the offsets and of the value profile appears in the events.

You edit the [leveler settings]({{< relref "leveler" >}}) separately; they can also be changed during the measurement.

## Offsets

The offset converts the values at the measuring position to the loudest place in the audience. How to determine it is
described under [Measuring point and offset]({{< relref "/docs/basics/measuring-point-and-offset" >}}).

There are two ways:

- **Tune offsets** (**Measurement** menu): with live values. Only for the active, stopped measurement with a connected
  sensor. The table shows, per weighting, the current level, the highest level since **Reset max values**, the offset
  and both values including the offset. Nothing measured here is recorded.
- **Edit Measurement:** enter offsets directly as numbers, for example from a measurement with a handheld meter.

A changed offset applies from the next start. Data already recorded keeps the offset it was recorded with.

## Complete and re-open

When the event is over, complete the measurement: **Measurement** menu › **Complete measurement**. The measurement must
be stopped. After that it is locked: it can no longer be activated, edited or started, but it can be viewed and
exported. If autonomous mode is set to this measurement, it is switched off.

You re-open a completed measurement in the menu with **Re-open measurement**.

## Deleting

You delete an open measurement under **Edit Measurement** › **Delete measurement**, a completed one in the
**Measurement** menu. It is only deleted on this computer; what is in SPL Cloud stays there. How to delete the
measurement in the cloud as well is described under
[Measurements in the cloud]({{< relref "/docs/spl-cloud/measurements#deleting" >}}).

## Import and export

A measurement can be backed up as an `.splsense` file and read in again on another computer, with all data and
settings.

- **Export:** complete the measurement and click **Export measurement**.
- **Import:** on the overview, **Import**, then drag the file into the field. If the measurement already exists, you
  can replace it with **Overwrite existing measurement**.

You export the values as a table in CSV format, see [Measurement data]({{< relref "measurement-data#reports-and-exports" >}}).
