---
title: Glossary
linkTitle: Glossary
weight: 10
description: >-
  The most important terms and abbreviations in SPL Sense and SPL Cloud, in alphabetical order.
---

## Measured values and notation

SPL Sense and SPL Cloud write measured values as is common in acoustics:

| Display | Meaning |
|---|---|
| **LAeq 60′** | Equivalent continuous level (Leq), A-weighted, over 60 minutes. The "hourly level" of the V-NISSG. |
| **LAeq 5′** | the same over 5 minutes |
| **LCeq 1 s** | Equivalent level, C-weighted, over 1 second (live value) |
| **LAFmax 1′** | highest level, A-weighted with time weighting *Fast*, within one minute |

The letter after the L is the frequency weighting (A, C or Z), followed by the type (eq or Fmax) and then the time. A
prime ′ stands for minutes. The unit is always dB.

CSV exports and PDF reports partly still use an older notation for the same values.

## Terms A–Z

**A, C and Z weighting**
: Filters that weight the frequency spectrum. **A** roughly corresponds to human hearing at low levels and strongly
  attenuates bass; the equivalent levels of the V-NISSG and of DIN 15905-5 are given in dB(A). **C** attenuates bass
  only slightly and shows how much low-frequency energy is involved; DIN 15905-5 uses it to limit the peak level.
  **Z** is unfiltered (*zero*). SPL Sense always measures all three.

**Assessment level (Lr)**
: Term from DIN 15905-5: the LAeq over 30 minutes at the immission location, in blocks starting at every full and half
  hour. The permissible value is 99 dB.

**Audience noise, extraneous noise**
: DIN 15905-5 calls everything that does not come from the sound system *Störschall* (extraneous noise), for example
  audience or pyrotechnics. See [Audience noise]({{< relref "audience-noise" >}}).

**Calibration**
: Adjustment of the sensor against a reference sound level. It has an expiry date.
  See [Sensor and calibration]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}).

**Correlation**
: For the leveler, the ratio between measured and expected level. 1.000 means: only the sound system can be heard.
  Values above 1 indicate additional noise, for example from the audience.

**Day boundary**
: Time at which a measurement day ends: between midnight and 06:00.

**Deviation, exceedance**
: A value has exceeded a threshold of the value profile. The measurement details show them per day.

**Excluded time range**
: A period that does not count for maxima, rating and deviations, for example the system tuning. The data is kept and
  shown greyed out.

**Fast (F)**
: Time weighting of 125 ms. Reacts quickly to peaks. Basis for LAFmax.

**Gain reduction (GR)**
: How many dB the [leveler]({{< relref "/docs/spl-sense/leveler" >}}) is currently reducing the volume by. Always 0 or
  negative.

**Instance**
: An installation of SPL Sense registered with SPL Cloud, for example a laptop or a Raspberry Pi.

**Interval**
: A recorded section of one minute. It contains all values of that minute and is digitally signed.

**Job**
: Groups several measurements in SPL Cloud, for example all measuring points of a festival.

**LAFmax, MaxF**
: The highest level with time weighting Fast within the chosen time. The V-NISSG limits LAFmax to 125 dB(A).

**LCpeak**
: C-weighted peak sound pressure level: the highest instantaneous value of the sound pressure, without time weighting.
  DIN 15905-5 limits it to 135 dB. Not the same as LCFmax: there, the level is first smoothed with the time weighting
  Fast (125 ms), and the highest of these values is taken. Short peaks therefore come out lower; LCpeak is always equal
  to or higher than LCFmax.

**Leq (equivalent continuous level)**
: The energy average of the level over a given time. A short, very loud moment raises the Leq considerably; a quiet
  moment lowers it only slightly.

**Leveler**
: Automatically controls the volume of the sound system so that the limit is met.

**Line offset**
: For the leveler with audience compensation: the difference between the level at the sensor and the signal level at
  the output of the audio processor, measured without audience.

**Live screen**
: Large display of the current values, for example for the DJ or the technicians. Layout freely configurable.

**Loudest place, immission location**
: The loudest place in the audience area, at ear height. This is where the limit applies. The V-NISSG calls it
  *Ermittlungsort*. DIN 15905-5 calls it *maßgeblicher Immissionsort* (relevant immission location) and distinguishes
  one for LAeq (determined by mid and high frequencies) and one for the peak level (determined by the bass).
  See [Measuring point and offset]({{< relref "measuring-point-and-offset" >}}).

**Measurement**
: A measuring point with its settings and all recorded data. Can run over many days.

**Measurement day**
: A day of a measurement, delimited by the day boundary. The Pro billing also counts measurement days.

**Measuring position, substitute immission location**
: Where the sensor actually stands, for example at the mixing desk. DIN 15905-5 calls it *Ersatzimmissionsort*
  (substitute immission location).

**Offset, correction value**
: Value in dB added to each measured value to infer the level at the loudest place from the measuring position. One
  value each for A, C and Z. In DIN 15905-5 they are called correction values KA and KC.

**Operator PIN**
: Protects SPL Sense against changes. The live screen remains accessible without PIN.

**Organization**
: A company, a venue or a festival in SPL Cloud. It owns measurements, jobs and instances; several people work
  together in it.

**Pink noise**
: Test signal with equal energy per octave. Used to determine the offset and line offset.

**Read access**
: Allows another person to view a measurement or a job in SPL Cloud without changing anything.

**Recovery zone**
: Area where the audience can recover from the noise (*Ausgleichszone*). The V-NISSG requires it for events with an
  hourly level above 96 dB(A) that last longer than three hours.

**Signature**
: Every interval is digitally signed. This makes it possible to prove that the data has not been changed.

**Spectrum, third-octave band**
: The level split by frequency, in third-octave bands. Visible in the interval details and on the live screen.

**Value profile**
: Defines which values a measurement calculates (e.g. LAeq 60′, LAFmax 1′) and which thresholds apply. Each value has
  up to three levels: **Notification**, **Warning** and **Limit**.
  See [Value profiles]({{< relref "/docs/spl-sense/value-profiles" >}}).

**Weather protection filter**
: Compensates for the effect of a weather protection on the microphone. Must match the weather protection used.
