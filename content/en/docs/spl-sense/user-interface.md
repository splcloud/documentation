---
title: User interface and search
linkTitle: User interface and search
weight: 15
description: >-
  Status bar, device status, overview, menus and search.
---

## Status bar

The status bar is at the top of every page:

- **Logo and path:** the logo leads to the overview, the path next to it back to higher-level pages.
- **Device status:** shows at a glance what is happening:
  - **Measurement running** (green, with the current LAeq 1 s): a click opens the live screen.
  - **Measurement stopped** or **Sensor disconnected** (red): a click opens the active measurement.
  - **No measurement loaded**
- **Connected devices:** sensor, leveler and cloud connection, each with its state. If remote control from SPL Cloud is
  allowed, this is shown here too.
- **Search** (magnifying glass), **Help** (question mark, opens this documentation) and **Settings** (gear).

## Overview

The overview lists all open measurements as cards. Each card shows the state of the measurement and the values of the
last four measurement days, coloured according to the thresholds of the value profile. Below are the completed
measurements as a short list.

At the top right, **New measurement** creates a measurement and **Import** restores a backed-up measurement.

At the bottom of the overview you find the connected sensor, a connected leveler and, if available, a notice about an
update.

## Measurement page

- **Page header:** name, state and the most important actions as buttons, for example **Start** or **Stop**. All other
  actions are in the **Measurement** menu. Actions that change the measurement permanently (Deactivate, Complete) are at
  the end of the menu.
- **Live strip:** while measuring, you see the 1-second values and, if active, the leveler below the page header.
- **Days and chart:** select a measurement day; the chart shows its course. Next to the day you find the buttons
  **PDF** (day report) and **CSV**.
- **Below:** deviations, events, sensor and cloud uplink.

What the values and markers mean is described under [Measurement data]({{< relref "measurement-data" >}}).

## States of a measurement

| State | Meaning |
|---|---|
| **Active** | The measurement is loaded and ready. SPL Sense records as soon as you start. At most one measurement is active at any time. |
| **Measurement running** | SPL Sense is recording. |
| **Interrupted** | The sensor no longer delivers data, for example because it was unplugged or the computer was asleep. The measurement continues by itself as soon as the sensor delivers data again. |
| **Stopped** | Recording is paused. |
| **Completed** | The measurement is locked and can only be viewed, exported or re-opened. |

More under [Measurements]({{< relref "measurements" >}}).

## Search

Open the search with the magnifying glass or with <kbd>Ctrl</kbd>+<kbd>K</kbd> (Mac: <kbd>⌘</kbd>+<kbd>K</kbd>). It
finds measurements (open and completed), settings pages, value profiles and live screens. Use the arrow keys to select a
result and <kbd>Enter</kbd> to open it.

You can also find settings by keywords, for example "password" for the operator PIN or "limiter" for the leveler.

## Use on tablet and phone

In web server mode (Linux) you operate SPL Sense in the browser, also from a tablet or phone. The interface adapts to
small screens: the path in the status bar becomes a back link, lists are shown one below the other.
