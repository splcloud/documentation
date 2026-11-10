---
title: Measuring point and offset
linkTitle: Measuring point and offset
weight: 20
description: >-
  Where the sensor belongs, how to determine the offset and what you should document.
---

## Loudest place and measuring position

The limits apply at the **loudest place in the audience area**. The V-NISSG calls it *Ermittlungsort* (at ear height),
DIN 15905-5 calls it *maßgeblicher Immissionsort*. The sensor can rarely stand there during an event: in the middle of
the audience it would be at risk, and shouting and applause would distort the measurement.

That's why you measure at another place, the **measuring position** (DIN: *Ersatzimmissionsort*). The **offset** (DIN:
*correction value*) compensates for the difference between the two places. SPL Sense adds it to every measured value
so that the displayed and stored values correspond to the level at the loudest place in the audience.

## Choosing the measuring position

- The sensor should receive the **direct sound** of the sound system: clear line of sight to the loudspeakers, not
  behind pillars, tent poles or the roof of the mixing desk.
- As little audience and other noise sources nearby as possible.
- Not in room corners and not directly against walls.
- Outdoors with weather protection, and switch on the matching
  [weather protection filter]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}).
- Do not move it during the event. If you have to move it, determine the offset again.

### Distance to the loudspeakers

The sensor needs a **minimum distance** to the sound system:

- Only at some distance do the high, mid and low frequency drivers combine into the sound the audience hears. Too close
  to a loudspeaker, the sensor mainly measures a single loudspeaker, and the offset no longer holds for music.
- The sensor has a maximum level. Too close to a loudspeaker, peaks can overload it. SPL Sense shows this as **Clip**
  in the measurement data.

Within these limits: the farther the measuring position is from the audience and the better it lies in the direct sound
of the sound system, the less audience and other sources interfere. If the measuring position is closer to the sound
system than the loudest place in the audience, the offset becomes negative. DIN 15905-5 recommends such a measuring
position.

## Determining the offset

The offset is determined **before the event with pink noise**, as loud as during operation and through exactly the sound
system that will play during the event. In SPL Sense this is done with **Tune Offsets**, described step by step in the
[Quick start]({{< relref "/docs/quick-start#5-set-the-offset" >}}). In short:

1. Play pink noise at operating volume.
2. Walk through the audience area with the sensor. SPL Sense remembers the highest level, this is your loudest place.
3. Place the sensor at the measuring position and set the offset so that the level at the measuring position plus the
   offset equals the highest level.

Alternatively, measure the level at the loudest place with a handheld meter and enter the difference directly under
**Edit Measurement**. DIN 15905-5 requires a measuring duration of at least 15 seconds for this.

The offset applies per weighting: there is a separate value for A, C and Z.

- **A** (for LAeq and LAFmax): the loudest place is determined by the mid and high frequency drivers.
- **C** (for LCFmax and the peak level): the loudest place is determined by the bass and may be somewhere else.
  DIN 15905-5 allows the C offset to be determined from the LCeq; this is more reliable than using peak values.

{{% alert title="Tips" color="info" %}}
- Check the offset afterwards with typical music. If it deviates strongly, measure again.
- Don't calculate the offset with rules of thumb, measure it.
- The offset only applies to this loudspeaker setup and this measuring position. If either changes, measure again.
- During the event, briefly check whether the values are plausible (the V-NISSG enforcement guide mentions this as an
  option).
{{% /alert %}}

## Function test and calibration

For mobile measuring systems, DIN 15905-5 requires a function test with a calibrator before and after each event. The
industry recommendation on the measurement procedure for the V-NISSG also recommends calibration before and after each
measurement for mobile systems; the enforcement guide itself does not require organizers to calibrate. SPL Sense shows
the calibration status of the sensor and warns before the start if it has expired.
See [Sensor and calibration]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}).

## Documentation

Record in writing how you measured.

- **V-NISSG:** at least the loudest place, the offset and the method you used to determine the offset.
- **DIN 15905-5:** a measurement report including organizer, date and place, start and end of the measurement,
  assessment levels and peak levels, measuring and calibration devices, result of the function test, location of the
  immission locations and the measuring position with justification, and the correction values and how they were
  determined. The complete list is in the standard, section "Messprotokoll".

The measured values are provided, for example, by the PDF day report.

SPL Sense helps: every change of the offset automatically appears in the events, and with comments you record special
circumstances directly in the measurement. In SPL Cloud you can also attach pictures of the measuring position to the
measurement ([SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}})).

Original documents: see [Templates for V-NISSG and DIN 15905-5]({{< relref "templates-vnissg-din" >}}).
