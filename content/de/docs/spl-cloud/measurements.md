---
title: Messungen in der Cloud
linkTitle: Messungen
weight: 50
description: >-
  Messdaten in der Cloud ansehen, exportieren, abschliessen und löschen.
---

Eine Messung erscheint in der SPL Cloud, sobald in SPL Sense ihre **Cloud Synchronisierung** eingeschaltet ist und die
Instanz Internet hat. Neue Messungen stehen zuerst unter den eigenständigen Messungen auf der Übersicht.

## Die Messungsseite

Unter dem Titel steht eine Zeile mit dem Wichtigsten: Messauftrag, Besitzer, die Instanz, die gerade misst (mit
Zustand), und ob Pro aktiv ist.

- **Live:** Läuft die Messung, siehst du die aktuellen 1-Sekunden-Werte, bei aktivem Leveler auch Gain-Reduktion und
  Korrelation. Meldet sich die Instanz nicht mehr, steht **Verbindung verloren** mit dem letzten Kontakt.
- **Tage, Grafik, Abweichungen und Ereignisse:** gleich wie in SPL Sense, siehe
  [Messdaten auswerten]({{< relref "/docs/spl-sense/measurement-data" >}}).
- **Seitlich:** Zugriff (wer die Messung sieht), Pro, Bilder und die anderen Messungen desselben Messauftrags.

Ändert sich in SPL Sense etwas an der Messung, zum Beispiel der Offset, aktualisiert sich die Seite von selbst.

## Berichte und Exporte

| Was | Wo | |
|---|---|---|
| CSV des Tages | Button **CSV** beim Tag | kostenlos |
| Tagesbericht (PDF) | Button **PDF** beim Tag | [Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}) |
| CSV aller Tage (ZIP) | Menü **Messung** › **Gesamte Messung als CSV exportieren** | kostenlos |
| Tagesbericht mit Abweichungen | Menü **Messung** › **Tagesbericht mit Abweichungen öffnen** | [Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}) |
| Bilderbericht | Menü **Messung** › **Bilderbericht öffnen** | [Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}) |

Die Berichte tragen das Logo der Organisation, der die Messung gehört.

## Abschliessen

Menü **Messung** › **Messung abschliessen**. Die Cloud nimmt danach keine neuen Daten mehr an, auch wenn SPL Sense
weiter misst. Daten bis zum Zeitpunkt des Abschlusses, die noch unterwegs sind, kommen noch an.

Schliesst du die Messung in SPL Sense ab, wird sie auch in der Cloud abgeschlossen. Wieder geöffnet wird sie in SPL Sense
oder mit der [Fernsteuerung]({{< relref "/docs/spl-cloud-pro/remote-control" >}}).

## Löschen

Eine abgeschlossene Messung löschst du im Menü **Messung** › **Messung löschen**. Sie wird in der Cloud endgültig
entfernt. In SPL Sense bleibt die Messung erhalten.

## Wer die Messung sieht

| Wer | Darf |
|---|---|
| Besitzer der Messung (Person oder alle Mitglieder der Organisation) | alles: ansehen, Zugriff vergeben, abschliessen, löschen |
| Besitzer des Messauftrags, falls ein anderer | ansehen, siehe [Unterschiedliche Besitzer]({{< relref "jobs#unterschiedliche-besitzer" >}}) |
| Personen mit [Lesezugriff]({{< relref "read-access" >}}) | ansehen |
| Empfänger eines [teilbaren Links]({{< relref "/docs/spl-cloud-pro/shared-links" >}}) | ansehen, ohne Konto |
