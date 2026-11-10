---
title: Leveler
linkTitle: Leveler
weight: 50
description: >-
  Automatic level control with the SPL Tools L1 or an audio processor: variants, modes, calibration and operation.
---

The leveler automatically keeps the level below a limit. SPL Sense measures the sound level with the sensor, receives
from the leveler device the level of the signal it is currently outputting (line level), and calculates how much the
volume must be reduced (gain reduction). The leveler device applies the reduction in the signal path.

The leveler belongs to the measurement: each measurement has its own leveler settings. You find them in the
**Measurement** menu › **Leveler Settings**.

## Variants

| Connection | When |
|---|---|
| **SPL Tools L1 (USB)** | The L1 is connected via USB to the computer running SPL Sense. Default for new measurements. |
| **SPL Tools L1 (network)** | The L1 is located elsewhere, for example in the rack next to the amplifier, and can be reached via Ethernet or WiFi. |
| **External audio processor (SenseAPI)** | An audio processor with an SPL Sense plugin queries SPL Sense via the [API]({{< relref "/docs/developers/sense-api" >}}). |

For Q-SYS there is the plugin **SPL Sense Leveler**: [download](https://r.spl.swiss/sense/leveler/plugin). Add it to
your Q-SYS design and enter the IP address of the computer running SPL Sense, the port and the API key in the plugin. In
SPL Sense, under **Settings** › **API**, the mode **External Leveler Only** or **Full Control** must be switched on, see
[SPL Sense API]({{< relref "/docs/developers/sense-api" >}}). If the settings are correct, the plugin shows the state and
the measured values of SPL Sense.

### SPL Tools L1 via USB

Connect the L1 via USB. In the measurement's leveler settings, **Leveler Connection** then shows **Connected** with
type, serial number and firmware.

### SPL Tools L1 via network

1. Choose **SPL Tools L1 (network)**.
2. Enter the name or IP address of the L1 under **Host**, or click **Search**: SPL Sense then looks for L1 devices on
   the local network.
3. Enter the **API Key** of the L1.
4. Choose the **Security**:
   - **HTTP (L1 TLS off)**: unencrypted, only in protected local networks
   - **HTTPS, pinned certificate**: encrypted with the L1's own certificate. Read the fingerprint with
     **Read from L1** and compare it with the one shown on the L1.
   - **HTTPS, trusted CA**: encrypted with a certificate from a recognized authority
5. Click **Test connection** and then **Save**.

The easiest way is **Set up from L1 on USB**: plug the L1 in via USB once, and SPL Sense takes over host, API key,
security and fingerprint. If the L1 has no API key yet, SPL Sense generates one.

After several wrong API keys, the L1 blocks the connection for 30 seconds.

### Setting up the L1 itself

When an L1 is connected via USB, you set it up under **Settings** › **Leveler**:

- **Device Information**: type, serial number, firmware, MAC addresses
- **Ethernet Configuration**: automatic or **static** with IP address, netmask and gateway
- **WiFi Configuration**: network and password. The L1 only supports 2.4 GHz networks. The status shows the connection
  and signal strength.
- **Network API**: hostname, API key (empty: leveling over the network off; **Generate** creates one), admin password
  for the L1's web interface and the encryption (**Off**, **Self-signed certificate**, **Custom certificate**)

Limits and mode do not belong here but in the measurement's leveler settings.

## Modes

| Mode | Behaviour |
|---|---|
| **Off** | No leveling. |
| **Plain leveler** | Always controls slowly and smoothly. |
| **Leveler with panic** | Like the plain leveler, but reduces quickly if the level suddenly rises well above the limit. |
| **Leveler with panic and audience compensation** | In addition, SPL Sense detects which part of the level does not come from the sound system (for example the audience) and only controls the share of the sound system. Requires a calibrated line offset. |

Background on audience compensation: [Audience noise]({{< relref "/docs/basics/audience-noise" >}}).

## Limits

Under **Limit Values** you enter a limit between 40 and 140 dB for each of A, C and Z. An empty field means: this
weighting is not controlled. If several limits are set, the weighting that requires the greatest reduction applies; it
is called *dominant*.

The leveler controls to an average over about 10 seconds. The gain reduction is at most 40 dB.

## Calibrating the line offset

Only for the mode with audience compensation. The line offset is the difference between the level at the sensor and the
line level when only the sound system is playing. Before calibrating, the measurement must be active and stopped, the
sensor connected and the leveler mode saved or applied (**Apply settings**).

1. Play pink noise through the **entire signal chain**, as loud as during the event. If a DJ mixer is the source, feed
   the noise into the DJ mixer.
2. Make sure it is quiet: no audience, no conversations, no other sources.
3. Click **Capture Line Offset**. SPL Sense measures for three seconds and enters the line offset for A, C and Z.
4. Check the **Correlation**: it should be as close as possible to **1.000** for all weightings. Otherwise repeat the
   measurement.
5. **Save**.

{{% alert title="Important" color="warning" %}}
After calibrating, nothing may change the level between the leveler device and the loudspeakers: no gain changes on
amplifiers or processors, no compressors or limiters in this part of the signal path. Otherwise the line offset is no
longer correct and the leveler controls incorrectly.
{{% /alert %}}

You can also change the line offset manually. Be careful: even a small deviation causes the leveler to ignore audience
noise or to intervene too strongly.

## Reading the correlation

The correlation compares the measured level with the level the sound system alone should produce.

| Correlation | Meaning |
|---|---|
| about 1.000 | Only the sound system can be heard. |
| above 1 | Additional noise, usually audience. |
| below 1 | The sensor is damped, or something was changed in the sound system after calibration. |

## During the measurement

When the measurement is running and the leveler is active, the live strip shows:

- the current **Gain Reduction**
- the **Correlation** per weighting; the dominant one is bold and marked with `>`, for example `> 0.987 @A`
- the 1-second level of the dominant weighting highlighted

You can change limits, mode and line offsets during the measurement as well; they apply immediately without the gain
reduction jumping. Calibrating is only possible with the measurement stopped.

The day chart additionally shows the line level, the gain reduction and the correlation. With the cloud uplink, this
data also goes to SPL Cloud.

### Warnings

| Message | What to do |
|---|---|
| **No contact with processor yet** / **since …** | Check the connection to the L1 or the audio processor. |
| **Leveler is disabled because the configuration is incomplete** | At least one limit is missing, in the mode with audience compensation also the matching line offset. |

### Bypass

**Bypass Leveler** switches the control off immediately, for example in case of a problem. Caution: the volume then
rises by the current gain reduction. With 15 dB reduction, it suddenly gets 15 dB louder.

The bypass applies to the whole device and **stays on until you lift it with Reenable Leveler**, even across a restart,
a change of measurement or unplugging and replugging. As long as it is active, the overview and the measurement page show
a notice.

### Stop and interruption

- **Stop:** the leveler sets the gain reduction to 0 and releases control. SPL Sense warns when stopping if the leveler
  is currently reducing.
- **Interrupted** (sensor gone): the last gain reduction remains until the sensor delivers data again.

## Who can change what

The leveler settings can be changed for every open measurement, even without a sensor and even when it is not active.
Not for a completed measurement. From SPL Cloud, mode, limits and line offsets can be changed via
[remote control]({{< relref "/docs/spl-cloud-pro/remote-control" >}}), but not the connection or the calibration.
