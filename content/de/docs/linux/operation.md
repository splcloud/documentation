---
title: Betrieb
linkTitle: Betrieb
weight: 40
description: >-
  Zugriff im Netzwerk, Kiosk-Anzeige und Betrieb als feste Messstation ohne Bedienung.
---

## Adressen

Mit dem Port `8080` aus der [Installation]({{< relref "installation" >}}):

| | Adresse |
|---|---|
| Weboberfläche | `http://<ip-adresse>:8080` |
| Live Ansicht | `http://<ip-adresse>:8080/measurement/live` |
| Live Ansicht im Kiosk-Modus | `http://<ip-adresse>:8080/measurement/live?kiosk` |
| [SPL Sense API]({{< relref "/docs/developers/sense-api" >}}) | `http://<ip-adresse>:8080/api` |

Am Raspberry Pi selbst geht statt der IP-Adresse auch `localhost`.

## Kiosk-Anzeige

Für eine feste Anzeige, zum Beispiel ein Bildschirm am DJ-Pult, öffnet der Browser die Live Ansicht direkt im
Kiosk-Modus, zum Beispiel mit Chromium:

```bash
chromium-browser --kiosk "http://localhost:8080/measurement/live?kiosk"
```

Der Kiosk-Modus zeigt nur die Widgets und eine schmale Statusleiste und passt sich der Bildschirmgrösse an. Siehe
[Live-Anzeige und Kiosk]({{< relref "/docs/spl-sense/live-screen#vollbild-und-kiosk" >}}).

## Feste Messstation ohne Bedienung

1. [Autonomer Modus]({{< relref "/docs/spl-sense/autonomous-mode" >}}) einschalten: Die Messung startet nach jedem
   Neustart von selbst, zum Beispiel nach einem Stromausfall.
2. [Operator-PIN]({{< relref "/docs/spl-sense/settings#operator-pin" >}}) setzen: Ohne PIN ist nur die Live Ansicht
   zugänglich, auch im Browser anderer Geräte.
3. Mit der [SPL Cloud]({{< relref "/docs/spl-sense/settings#spl-cloud" >}}) verbinden und die Cloud
   Synchronisierung einschalten.
4. Optional mit Pro: [Alarme]({{< relref "/docs/spl-cloud-pro/alarms" >}}) bei Ausfall und
   [Fernsteuerung]({{< relref "/docs/spl-cloud-pro/remote-control" >}}).

## Einschränkung

Den Sensor kalibrieren kannst du unter Linux nicht. Dafür brauchst du SPL Sense für Windows oder macOS.
