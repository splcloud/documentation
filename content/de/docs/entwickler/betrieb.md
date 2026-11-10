---
title: Betrieb unter Linux
linkTitle: Betrieb unter Linux
weight: 20
description: >-
  SPL Sense auf einem Raspberry Pi oder anderen Linux-Geräten: Webserver-Betrieb, Kiosk und unbeaufsichtigter Betrieb.
---

Unter Linux (ARM und ARM64, zum Beispiel Raspberry Pi) läuft SPL Sense als Webserver ohne eigenes Fenster. Bedient wird
es im Browser, auf dem Gerät selbst oder von einem anderen Gerät im selben Netzwerk.

## Installation

Die Installation beschreibt die [Linux-Installationsanleitung](https://r.spl.swiss/sense/linux-installation) (PDF).

{{< offen >}}Inhalt der Linux-Installationsanleitung hier übernehmen (PDF folgt).{{< /offen >}}

## Zugriff

| | Adresse |
|---|---|
| Weboberfläche | `http://<gerät>:5980` |
| Live Ansicht | `http://<gerät>:5980/measurement/live` |
| Live Ansicht im Kiosk-Modus | `http://<gerät>:5980/measurement/live?kiosk` |
| [SPL Sense API]({{< relref "sense-api" >}}) | `http://<gerät>:5980/api` |

SPL Sense läuft als Systemdienst (`splsense`) und startet mit dem Gerät. Updates installiert SPL Sense selbst, wie auf
den anderen Plattformen; der Dienst wird danach neu gestartet.

## Kiosk-Anzeige

Für eine feste Anzeige, zum Beispiel ein Bildschirm am DJ-Pult, startet der Browser des Geräts direkt in die Live Ansicht
im Kiosk-Modus, zum Beispiel mit Chromium:

```bash
chromium-browser --kiosk "http://localhost:5980/measurement/live?kiosk"
```

Der Kiosk-Modus zeigt nur die Widgets und eine schmale Statusleiste, skaliert auf die Bildschirmgrösse. Siehe
[Live-Anzeige und Kiosk]({{< relref "/docs/spl-sense/live-anzeige#vollbild-und-kiosk" >}}).

## Unbeaufsichtigter Betrieb

Für ein Gerät, das ohne Bedienung misst:

1. [Autonomer Modus]({{< relref "/docs/spl-sense/autonomer-modus" >}}) einschalten: Die Messung startet nach jedem
   Neustart von selbst.
2. [Operator-PIN]({{< relref "/docs/spl-sense/einstellungen#operator-pin" >}}) setzen: Ohne PIN ist nur die Live Ansicht
   zugänglich, auch im Browser.
3. Mit der [SPL Cloud]({{< relref "/docs/spl-sense/einstellungen#spl-cloud" >}}) verbinden und die Cloud
   Synchronisierung einschalten.
4. Optional [Alarme]({{< relref "/docs/spl-cloud-pro/alarme" >}}) bei Ausfall und
   [Fernsteuerung]({{< relref "/docs/spl-cloud-pro/fernsteuerung" >}}) (beides Pro).

Den Sensor im Webserver-Betrieb zu kalibrieren ist nicht möglich; dafür braucht es SPL Sense für Windows oder macOS.
