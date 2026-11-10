---
title: Quick start
linkTitle: Quick start
weight: 10
description: >-
  Your first measurement in a few steps: install SPL Sense, create a measurement, set the offset, measure, archive in
  SPL Cloud and download a PDF report.
aliases:
  - /en/docs/quickstartsense/
  - /en/docs/quickstartcloud/
---

This guide takes you step by step to your first measurement. No prior knowledge needed.

**What you need:**

- a computer running Windows or macOS
- an SPL Tools sensor with USB cable
- for SPL Cloud (step 8): internet and an email address

## 1. Install SPL Sense

1. Download SPL Sense for your operating system:
   - [Windows](https://r.spl.swiss/dl/splsense/win-x64/SPLSenseSetup.exe)
   - [macOS with Apple chip (M1 and newer)](https://r.spl.swiss/dl/splsense/osx-arm64/SPLSense-osx-arm64-Setup.pkg)
   - [macOS with Intel processor](https://r.spl.swiss/dl/splsense/osx-x64/SPLSense-osx-x64-Setup.pkg)
2. Open the downloaded file and follow the installer.
3. Start SPL Sense. On first start, a notice appears. Read it and click **Accept and Continue**.

SPL Sense updates itself: when a new version is available, a notice appears.

## 2. Connect the sensor

Connect the sensor via USB. Only one sensor may be connected per computer. The status bar at the top right shows
whether SPL Sense detects the sensor.

If the status bar shows **Sensor disconnected**, unplug the cable and plug it in again.

{{% alert title="Calibration" color="info" %}}
If the sensor's calibration has expired, SPL Sense warns you when you start the measurement. You can still measure,
but the measured values will be marked. More under [Sensor and calibration]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}).
{{% /alert %}}

## 3. Create a measurement

A **measurement** stands for one measuring point, for example "Main stage Openair 2026". It can run over many days.

1. On the overview, click **New measurement**.
2. Fill in the fields:
   - **Name**: how the measurement appears in the overview and in the report.
   - **Value Profile**: defines which values are calculated and which limits apply. For events in Switzerland, choose
     the template that matches your reported category: **VNISSG 93dBA**, **VNISSG 96dBA** or **VNISSG 100dBA**. In
     Germany, choose **DIN 15905-5**. What the templates contain:
     [Templates for V-NISSG and DIN 15905-5]({{< relref "/docs/basics/templates-vnissg-din" >}}).
   - **Day Boundary**: when a measurement day ends. Choose a time about two hours after the end of the event, at the
     latest 06:00. This way a party lasting until 03:00 ends up in *one* day instead of two.
   - **Cloud Uplink**: leave it off for now. You switch it on once SPL Sense is connected to the cloud (step 8).
3. Click **Create Measurement**.

## 4. Activate the measurement

Only one measurement can be active at a time. The active measurement is the one SPL Sense records into.

Open the measurement and click **Activate measurement**.

## 5. Set the offset

The limit applies at the **loudest place in the audience**, at ear height. You usually can't put the sensor there.
That's why you measure at a different place and compensate for the difference with the **offset**.
Background: [Measuring point and offset]({{< relref "/docs/basics/measuring-point-and-offset" >}}).

How to set the offset (the measurement must be active and stopped, the sensor connected):

1. In the **Measurement** menu, open **Tune offsets**.
2. Play pink noise through the sound system, as loud as during the event.
3. Click **Reset max values**.
4. Walk through the audience area with the sensor, including the front and the sides. SPL Sense remembers the highest
   value.
5. Place the sensor at its measuring position, for example at the mixing desk.
6. Set the **Offset** so that **Level with applied offset** is as high as the stored **Max** value.
7. Click **Save**.

Nothing is recorded while tuning offsets. If you already know the offset, for example from a handheld meter, enter it
directly under **Edit Measurement**.

## 6. Measure

1. Click **Start**. SPL Sense is now recording. The first values appear after the first full minute.
2. Below the page title you see the current levels. The chart shows the course of the day.
3. For a large, easy-to-read display, for example for the DJ or the technicians, click **Live Screen**.
4. When the event is over, click **Stop** and confirm.

{{< bild id="sense-messung-laeuft" >}}

If the sensor is unplugged during the measurement, SPL Sense shows **Interrupted**. When you plug it in again, the
measurement continues by itself.

## 7. Edit the measurement

You can change name, day boundary, offsets and value profile later, as long as the measurement is stopped:
**Measurement** menu › **Edit Measurement**, make the changes and **Save**.

If you change the value profile or the day boundary, SPL Sense recalculates the limits and measurement days.

## 8. Connect to SPL Cloud

In SPL Cloud your measurements are safely archived. You can see them on the go and share them with others. The basic
features are free.

**Create an account** (once):

1. Open [spl.cloud](https://spl.cloud) in your browser.
2. Click **Sign up now**, enter your email address and click **Send verification code**.
3. Enter the code you receive by email and confirm.
4. Add your password and name and finish with **Create**.

**Register SPL Sense** (once per computer):

1. In SPL Sense: **Settings** › **Cloud** › **Register instance**.
2. Click the link shown or scan the QR code with your phone. The code is only valid for a short time; if it has
   expired, request a new one with **Get new code**.
3. In SPL Cloud: under **Owner**, choose who this computer belongs to: you personally or an organization you are a
   member of. Click **Save**.
4. SPL Sense now shows **Instance is registred**.

**Upload the measurement to the cloud:**

1. Open the measurement in SPL Sense, **Measurement** menu › **Edit Measurement**.
2. Switch on **Cloud Uplink** and save.

SPL Sense now uploads all data of the measurement, including what was already recorded. If the internet connection
drops, SPL Sense keeps measuring and catches up with the upload later. In SPL Cloud, the measurement appears on the
overview under the independent measurements.

## 9. Download a PDF report

For every measurement day, SPL Sense offers a day report as PDF.

1. Open the measurement in SPL Sense.
2. Select the day.
3. Click **PDF** next to the day.

With **CSV** next to it, you export the values of the day, for example for Excel.

In SPL Cloud, the day report is available with [SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}).

## What next?

- When the event is completely over, complete the measurement: **Measurement** menu › **Complete measurement**.
  After that it can no longer be changed. You can re-open it if needed.
- [Measuring point and offset]({{< relref "/docs/basics/measuring-point-and-offset" >}}): measuring correctly according to V-NISSG and DIN 15905-5
- [Read access]({{< relref "/docs/spl-cloud/read-access" >}}): give the organizer or the authority insight
- [Leveler]({{< relref "/docs/spl-sense/leveler" >}}): keep the level below the limit automatically
