---
title: SPL Sense API
linkTitle: SPL Sense API
weight: 10
description: >-
  Lokale HTTP-API zum Abfragen und Steuern von SPL Sense und als Leveler-Schnittstelle für Audioprozessoren.
---

## Einschalten

**Einstellungen** › **API** in SPL Sense:

| Einstellung | Werte |
|---|---|
| **Modus** | **Aus** (Standard), **Nur externer Leveler**, **Vollzugriff** |
| **Port** | Standard `8084` (Windows, macOS). Unter Linux läuft die API auf dem Port der Weboberfläche, nach der [Installationsanleitung]({{< relref "/docs/linux/installation" >}}) `8080`. |
| **API Key** | mindestens 6 Zeichen; bei der Installation zufällig gesetzt |

Die Seite zeigt die Basis-URL, die Swagger UI und die OpenAPI-Spezifikation:

| | Pfad |
|---|---|
| API | `/api` |
| Swagger UI | `/swagger` |
| OpenAPI | `/swagger/current/swagger.json` |

Die API lauscht auf allen Netzwerkschnittstellen, unverschlüsselt (HTTP). Betreibe sie nur in vertrauenswürdigen
Netzwerken.

Verbindungen zu einem SPL Tools L1 sind von dieser Einstellung nicht betroffen.

## Authentifizierung

Jede Anfrage braucht den API Key, als Header

```http
X-Api-Key: <api key>
```

oder als HTTP Basic Auth (Benutzername beliebig, Passwort = API Key). Ohne gültigen Key: `401`. Ist ein Endpunkt im
gewählten Modus nicht erlaubt: `403`.

## Endpunkte

| Methode und Pfad | Zweck | Nur externer Leveler | Vollzugriff |
|---|---|---|---|
| `GET /api/state` | Zustand: Messgerät, aktiver Sensor (Seriennummer, Firmware, Kalibrierung, Wetterschutzfilter), aktuelle Messung | ✓ | ✓ |
| `GET /api/live` | letzter Live-Wert: LAeq/LCeq/LZeq 1 s, MaxF A/C/Z, Clip, Low, Integrationen, Spektrum | ✓ | ✓ |
| `GET /api/measurements` | alle Messungen mit Werteprofil, Offsets und Leveler-Einstellungen | ✓ | ✓ |
| `POST /api/leveler` | Leveler-Schnittstelle für Audioprozessoren | ✓ | ✓ |
| `POST /api/control` | Messung aktivieren, starten, stoppen, Leveler-Bypass | | ✓ |
| `POST /api/leveler/settings` | Leveler-Modus und Grenzwerte einer Messung setzen | | ✓ |


Die genauen Datenstrukturen stehen in der Swagger UI.

### Steuern: `POST /api/control`

```json
{ "action": "start" }
```

| `action` | Wirkung |
|---|---|
| `activate` | Messung aktivieren; braucht `"id": "<Messungs-ID>"` |
| `start` | aktive Messung starten |
| `stop` | Messung stoppen |
| `leveler-bypass` | Leveler-Bypass einschalten |
| `leveler-disable-bypass` | Leveler-Bypass aufheben |

Antwort: `{ "success": true, "errorMessage": null }`. Es gelten dieselben Regeln wie in der Oberfläche; ein Start
über die API fragt nicht nach einer abgelaufenen Kalibrierung. In den Ereignissen der Messung steht **über die API**.

### Leveler-Einstellungen: `POST /api/leveler/settings`

```json
{
  "measurementId": "…",
  "mode": 30,
  "limitValueDbA": 96,
  "limitValueDbC": null,
  "limitValueDbZ": null
}
```

`mode`: `0` Aus, `10` Einfacher Leveler, `20` mit Panikfunktion, `30` mit Panikfunktion und Publikumskompensation.
Grenzwerte 40–140 dB oder `null` (Gewichtung nicht geregelt). Die Line Offsets bleiben unverändert. Nicht möglich bei
abgeschlossenen Messungen (`409`).

## Leveler-Schnittstelle: `POST /api/leveler`

Für Audioprozessoren, die als Leveler arbeiten (zum Beispiel mit dem [Q-SYS-Plugin]({{< relref "/docs/spl-sense/leveler#varianten" >}})).
Die Messung muss in ihren Leveler-Einstellungen die Verbindung **Externer Audioprozessor (SenseAPI)** haben.

Der Prozessor ruft den Endpunkt regelmässig auf (typisch einmal pro Sekunde) und schickt seinen aktuellen Ausgangspegel:

```json
{
  "lineLevels": [ { "levelA": -18.2, "levelC": -12.5, "levelZ": -10.1 } ],
  "externalLevelerType": "MyProcessor",
  "externalLevelerVersion": "1.0"
}
```

Line-Pegel in dBFS (negativ), je Gewichtung optional. Mehrere Werte werden energetisch gemittelt. Jeder Aufruf ist
ein Regelzyklus.

Antwort:

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

`gainReduction` in dB, immer ≤ 0. Diesen Wert setzt der Prozessor als Gain um.

| `state` | Bedeutung | `gainReduction` |
|---|---|---|
| `0` | Leveler aus oder unvollständig konfiguriert | – |
| `1` | Messung gestoppt | 0 |
| `2` | Messung unterbrochen (Sensor weg) | `null`: letzten Wert halten |
| `10` | keine Reduktion | 0 |
| `20` | Reduktion | < 0 |
| `21` | Reduktion, Panik | < 0 |
| `30` | die Messung nutzt einen SPL Tools L1; Line-Pegel werden ignoriert | – |
| `99` | Bypass | 0 |
