---
title: Sensor and calibration
linkTitle: Sensor and calibration
weight: 60
description: >-
  Sensor status, weather protection filter and calibration of the sensor.
---

## Sensor information

Under **Settings** › **Sensor Information** (or by clicking the sensor on the overview) you see:

- **Device Information**: serial number, hardware revision, MCU ID, firmware version, quality check
- **Voltage** and **MCU Temperature**, refreshed with **Refresh measured values**
- **Calibration**: date, by whom, valid until
- **Weather Protection**: the compensation filter that is set

Always connect **only one sensor** to a computer running SPL Sense. If you change the sensor during a measurement
(unplug, plug in another), SPL Sense continues measuring with the new one; the affected minute is marked in the data.

## Calibration status

| Display | Meaning |
|---|---|
| **Calibrated** | The calibration is valid. |
| **Calibration expired** | The calibration has expired. You can measure, but the data is marked. |
| **Calibration invalid** | The sensor has no valid calibration. |

If the calibration has expired or is invalid, SPL Sense asks for confirmation when starting the measurement
(**Start anyway**). If the measurement is started via autonomous mode, the API or remote control, SPL Sense does not ask.

## Weather protection filter

A weather protection over the microphone slightly changes the frequency response. The compensation filter corrects
this. It must match the weather protection used:

- **Enable Filter for SPL Tools W1** for the SPL Tools W1 weather protection
- **Enable Filter for Weather Protection V1** for the older V1 weather protection
- **Disable Filter** without weather protection

The filter is stored in the sensor and applies until you change it, also for other measurements and on other computers.
You can only change it when no measurement is running. When it is switched on, the overview shows a notice and the
measurement data is marked.

## Calibrating the sensor

With an authorization as a calibrator, you can calibrate sensors yourself. You need:

- SPL Sense for Windows or macOS (not available in web server mode)
- internet
- a sound calibrator with 94 or 114 dB
- a confirmation as a calibrator from SPL Tools (see below)

### Applying as a calibrator

1. On the sensor page, **Calibrate** › **Apply as Calibrator**.
2. Fill in the online form. In it, you also describe your calibration equipment.
3. SPL Tools reviews your application and confirms it by email.

As soon as you have the confirmation, you can calibrate.

### Procedure

The measurement must be stopped and the sensor connected.

1. Sensor page › **Calibrate** › **Log In**. SPL Sense shows who you are logged in as and the current calibration.
2. Put the running calibrator on the sensor and wait until the level is stable.
3. Click the capture button for **94 dB** or **114 dB**, matching your calibrator.
4. Check the **Capture Result**:
   - **Capture drift**: fluctuation during the capture
   - **Previous calibration drift**: how far the sensor deviates since the last calibration

   If the values indicate that the sensor is drifting, SPL Sense warns you. Calibrate again and check the sensor for
   mechanical damage; if in doubt, send it in for inspection.
5. Choose the **Signing Organization** and the certificate, and fill in **Calibrated For** and **Calibrator Device**.
6. Click **Sign and Store Calibration**.

The calibration is digitally signed and stored in the sensor. From now on, the measurement data is signed with the new
calibration.

A sensor without a previous calibration cannot be calibrated this way. In that case, contact SPL Tools.
