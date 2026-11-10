---
title: SPL Sense API
linkTitle: SPL Sense API
weight: 10
description: >-
  Local HTTP API for querying and controlling SPL Sense and as a leveler interface for audio processors.
---

## Enabling

**Settings** › **API** in SPL Sense:

| Setting | Values |
|---|---|
| **Mode** | **Off** (default), **External Leveler Only**, **Full Control** |
| **Port** | Default `8084` (Windows, macOS). On Linux, the API runs on the same port as the web interface, `8080` according to the [installation guide]({{< relref "/docs/linux/installation" >}}); the port setting has no effect there. |
| **API Key** | at least 6 characters; set randomly at installation |

The page shows the base URL, the Swagger UI and the OpenAPI specification:

| | Path |
|---|---|
| API | `/api` |
| Swagger UI | `/swagger` |
| OpenAPI | `/swagger/current/swagger.json` |

The API listens on all network interfaces, unencrypted (HTTP). Only operate it in trusted networks.

Connections to an SPL Tools L1 are not affected by this setting.

## Authentication

Every request needs the API key, as the header

```http
X-Api-Key: <api key>
```

or as HTTP Basic Auth (any user name, password = API key). Without a valid key: `401`. If an endpoint is not allowed in
the selected mode: `403`.

## Endpoints

| Method and path | Purpose | External Leveler Only | Full Control |
|---|---|---|---|
| `GET /api/state` | State: measuring device, active sensor (serial number, firmware, calibration, weather protection filter), current measurement | ✓ | ✓ |
| `GET /api/live` | latest live value: LAeq/LCeq/LZeq 1 s, MaxF A/C/Z, clip, low, integrations, spectrum | ✓ | ✓ |
| `GET /api/measurements` | all measurements with value profile, offsets and leveler settings | ✓ | ✓ |
| `POST /api/leveler` | leveler interface for audio processors | ✓ | ✓ |
| `POST /api/control` | activate, start, stop a measurement, leveler bypass | | ✓ |
| `POST /api/leveler/settings` | set leveler mode and limits of a measurement | | ✓ |

The exact data structures are in the Swagger UI.

### Controlling: `POST /api/control`

```json
{ "action": "start" }
```

| `action` | Effect |
|---|---|
| `activate` | activate a measurement; needs `"id": "<measurement ID>"` |
| `start` | start the active measurement |
| `stop` | stop the measurement |
| `leveler-bypass` | switch on the leveler bypass |
| `leveler-disable-bypass` | lift the leveler bypass |

Response: `{ "success": true, "errorMessage": null }`. The same rules apply as in the user interface; a start via the
API does not ask about an expired calibration. The measurement's events show **via API**.

### Leveler settings: `POST /api/leveler/settings`

```json
{
  "measurementId": "…",
  "mode": 30,
  "limitValueDbA": 96,
  "limitValueDbC": null,
  "limitValueDbZ": null
}
```

`mode`: `0` off, `10` simple leveler, `20` with panic function, `30` with panic function and audience compensation.
Limits 40–140 dB or `null` (weighting not controlled). The line offsets remain unchanged. Not possible for completed
measurements (`409`).

## Leveler interface: `POST /api/leveler`

For audio processors that work as a leveler (for example with the [Q-SYS plugin]({{< relref "/docs/spl-sense/leveler#variants" >}})).
The measurement must have the connection **External audio processor (SenseAPI)** in its leveler settings.

The processor calls the endpoint regularly (typically once per second) and sends its current output level:

```json
{
  "lineLevels": [ { "levelA": -18.2, "levelC": -12.5, "levelZ": -10.1 } ],
  "externalLevelerType": "MyProcessor",
  "externalLevelerVersion": "1.0"
}
```

Line levels in dBFS (negative), each weighting optional. Several values are averaged energetically. Each call is one
control cycle.

Response:

```json
{
  "state": 20,
  "gainReduction": -3.5,
  "headroomBeforeGainReduction": 0,
  "dominantWeighting": "A",
  "compensatedRelevantSplA": 96.2,
  "compensatedRelevantSplC": null,
  "compensatedRelevantSplZ": null,
  "lineCorrelationA": 1.012,
  "lineCorrelationC": null,
  "lineCorrelationZ": null
}
```

`gainReduction` in dB, always ≤ 0. The processor applies this value as gain.

| `state` | Meaning | `gainReduction` |
|---|---|---|
| `0` | leveler off or incompletely configured | – |
| `1` | measurement stopped | 0 |
| `2` | measurement interrupted (sensor gone) | `null`: hold the last value |
| `10` | no reduction | 0 |
| `20` | reduction | < 0 |
| `21` | reduction, panic | < 0 |
| `30` | the measurement uses an SPL Tools L1; line levels are ignored | – |
| `99` | bypass | 0 |
