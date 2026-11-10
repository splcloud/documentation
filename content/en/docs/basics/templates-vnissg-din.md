---
title: Templates for V-NISSG and DIN 15905-5
linkTitle: Templates V-NISSG / DIN
weight: 5
description: >-
  Which value profiles and live screens SPL Sense provides for Switzerland and Germany.
---

SPL Sense provides value profiles and live screens for the V-NISSG (Switzerland) and DIN 15905-5 (Germany). Which
requirements apply to your event is set out in the original documents (below).

## Value profiles

| Template | Values and thresholds (Notification / Warning / Limit) |
|---|---|
| **VNISSG 93dBA** | LAeq 60′: 91 / 92 / 93 · LAeq 5′: – / 92 / 93 · LAFmax 1′: Limit 125 |
| **VNISSG 96dBA** | LAeq 60′: 94 / 95 / 96 · LAeq 5′: – / 95 / 96 · LAFmax 1′: Limit 125 |
| **VNISSG 100dBA** | LAeq 60′: 98 / 99 / 100 · LAeq 5′: – / 99 / 100 · LAFmax 1′: Limit 125 |
| **DIN 15905-5** | LAeq 30′: – / 95 / 99 · LAeq 5′: – / 95 / 99 · LCFmax 1′: Limit 135 |

The values can be adjusted per measurement, see [Value profiles]({{< relref "/docs/spl-sense/value-profiles" >}}).
The matching live screens have the same names as the templates, each also in a variant with leveler display.

SPL Sense calculates averages such as LAeq 30′ or LAeq 60′ every minute as a moving average over the last 30 or
60 minutes. The value on the full and half hour equals the average over the past half hour, i.e. the 30-minute block of
DIN 15905-5. If LAeq 30′ stays below the limit at all times, all blocks are met as well.

For the peak level, the **DIN 15905-5** template uses **LCFmax 1′**: the highest C-weighted Fast value (125 ms) within
one minute.

## Original documents

- Swiss Federal Office of Public Health (BAG/FOPH): *Vollzugshilfe zur V-NISSG, Schall* (enforcement guide) and
  *Messverfahren zur Ermittlung von Schallpegeln an Veranstaltungen* (measurement procedure), on the FOPH website
- [DIN 15905-5:2022-07](https://doi.org/10.31030/3343057), Event technology – Sound engineering – Part 5: Measures to
  prevent the risk of hearing loss of the audience by high sound exposure of electroacoustic sound systems
