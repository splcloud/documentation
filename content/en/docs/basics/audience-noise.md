---
title: Audience noise
linkTitle: Audience noise
weight: 30
description: >-
  How the audience and other noise sources affect the measurement and how SPL Sense deals with it.
---

## What counts towards the level?

The regulations differ here:

- **V-NISSG (Switzerland):** **everything that can be heard at the loudest place** counts: sound system, stage,
  instruments and also the audience (industry recommendation on the measurement procedure).
- **DIN 15905-5 (Germany):** only the sound of the sound system is assessed. Audience and other sources are
  *Störschall* (extraneous noise) and should not distort the result. That's why the standard recommends a measuring
  position where the audience hardly matters.

In both cases, the SPL Sense recording contains the total level at the sensor. No setting removes the audience from the
stored measured values. How much it counts is therefore determined by your choice of measuring position.

The audience has little influence on the hourly level at most events (V-NISSG enforcement guide). For short periods,
however, it can contribute significantly to the level: applause, chanting, singing along, loud stage monitors or rain on
a tent roof.

## What you can do

- **Choose the measuring position well:** if the sensor is above head height, away from the crowd and in the direct
  sound of the sound system, the audience has less effect. Keep enough distance to the loudspeakers. See
  [Measuring point and offset]({{< relref "measuring-point-and-offset" >}}).
- **Keep the stage level low:** loud monitors and backline increase the level without the technicians at the mixing desk
  being able to do much about it.
- **Add comments:** record special moments in the measurement, for example "Encore, audience singing along". Comments
  appear in the day chart and help explain peaks later.

## Leveler with audience compensation

The [leveler]({{< relref "/docs/spl-sense/leveler" >}}) automatically turns the sound system down when it gets too loud.
Without further information, it would also do so when the audience is loud, making the music unnecessarily quieter
even though the sound system is not to blame.

In the mode **Leveler with panic and audience compensation**, SPL Sense compares the measured level with the signal the
audio processor is currently outputting. If it is louder than the sound system alone can explain (correlation above 1),
the leveler only takes the share of the sound system into account. The measurement itself still records the full
level.

For this to work, the leveler needs an accurately calibrated **line offset**. How to do this is described under
[Leveler]({{< relref "/docs/spl-sense/leveler" >}}).
