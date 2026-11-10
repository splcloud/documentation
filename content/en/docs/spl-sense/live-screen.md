---
title: Live screen and kiosk
linkTitle: Live screen and kiosk
weight: 40
description: >-
  Live screen, built-in and custom screens, widgets and kiosk mode.
---

The **Live Screen** shows the current values large and easy to read, for example on a second display for the DJ or the
technicians. You open it on the measurement page with **Live Screen** or by clicking the device status in the status bar.

## Choosing a screen

Choose the screen at the top right of the live screen. SPL Sense remembers per measurement which one was used last.

Screens for common cases are built in, each with and without leveler display:

| Screen | Content |
|---|---|
| **VNISSG 93dBA**, **96dBA**, **100dBA** | LAeq 3 s, LAeq 5′, LAeq 60′, LAFmax, history of the last hour |
| **DIN 15905-5** | LAeq 5 s, LAeq 5′, LAeq 30′, LCFmax, history of the last hour |
| **DJ** | LAeq 3 s and LAeq 5′, reduced to the essentials |
| … **Leveler** | additionally gain reduction and correlation |

## Custom screens

Under **Settings** › **Live Screens** › **Create**:

1. Enter a **Name**.
2. Add widgets with **Add**.
3. Arrange them on the grid: drag a widget to move it and its corner to resize it. With the keyboard: arrow keys move,
   <kbd>Shift</kbd> + arrow keys resize.
4. Select a widget to change its type or set its **Color Thresholds**.
5. **Save**.

The preview shows placeholder values at real size, so you can see how large the numbers will be. On narrow screens the
widgets are stacked.

### Widgets

| Group | Widgets |
|---|---|
| **Numeric SPL** | Leq or MaxF, weighting A, C or Z, over **Current** or 3 s to 60 min |
| **Graph** | Spectrum, History Today, History Last Hour |
| **Leveler** | Gain Reduction, Correlation |
| **Other** | Last Interval |

### Color thresholds

Numeric widgets change colour when a value exceeds a threshold. You set the thresholds manually or take them from the
measurement with **From value profile**. This only works for times above one minute, because the value profile knows no
shorter times.

## Full screen and kiosk

**Full screen** switches the live screen to kiosk mode: instead of menus, a slim bar shows only measurement, screen, time
of the last value and device status. The widgets fill the whole screen, even on a large TV. **Leave full screen** returns.

If an [operator PIN]({{< relref "settings#operator-pin" >}}) is set, SPL Sense asks for it when leaving the live screen
and full screen. This way nobody at the DJ booth can change the settings.

For devices that should start directly into the live screen, see
[SPL Sense for Linux › Operation]({{< relref "/docs/linux/operation#kiosk-display" >}}).
