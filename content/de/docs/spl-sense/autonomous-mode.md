---
title: Autonomer Modus
linkTitle: Autonomer Modus
weight: 70
description: >-
  SPL Sense startet eine Messung automatisch, sobald es läuft.
---

Im autonomen Modus aktiviert und startet SPL Sense eine bestimmte Messung von selbst, sobald SPL Sense startet. Das
ist gedacht für fest installierte Systeme, zum Beispiel in einem Club oder auf einem Raspberry Pi: Nach einem
Stromausfall oder Neustart misst das System ohne Zutun weiter.

## Einrichten

1. **Einstellungen** › **Autonomer Modus**.
2. Schalte **Automatische Messung wenn eingeschaltet** auf **Ein**.
3. Wähle die **Messung**. Zur Auswahl stehen nur offene Messungen.
4. **Speichern**. Ist SPL Sense gestoppt und ein Sensor verbunden, bietet SPL Sense an, die Messung sofort zu
   starten.

## Verhalten

- **Beim Start von SPL Sense:** Die gewählte Messung wird aktiviert und gestartet. Ist kein Sensor verbunden, steht die
  Messung auf **Unterbrochen** und beginnt aufzuzeichnen, sobald der Sensor da ist.
- **Stoppen:** Du kannst die Messung jederzeit stoppen. Sie bleibt dann gestoppt, bis SPL Sense das nächste Mal startet.
- **Abschliessen:** Wird die Messung abgeschlossen, schaltet sich der autonome Modus aus.
- **Kalibrierung:** Beim automatischen Start fragt SPL Sense nicht nach, auch wenn die Kalibrierung abgelaufen ist.
  In den Ereignissen steht als Grund **Automatisch gestartet (autonome Messung)**.

## Für den unbeaufsichtigten Betrieb

Kombiniere den autonomen Modus mit:

- einer [Operator-PIN]({{< relref "settings#operator-pin" >}}), damit niemand die Einstellungen ändert
- der [Live Ansicht im Kiosk-Modus]({{< relref "live-screen#vollbild-und-kiosk" >}}) als Anzeige
- der [Cloud Synchronisierung]({{< relref "settings#spl-cloud" >}}), damit du die Messung aus der Ferne siehst,
  und mit Pro [Alarmen]({{< relref "/docs/spl-cloud-pro/alarms" >}}), falls die Messung ausfällt
