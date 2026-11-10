---
title: Fernsteuerung und Kommentare
linkTitle: Fernsteuerung
weight: 50
description: >-
  SPL Sense aus der SPL Cloud steuern, Kommentare und ausgenommene Zeitbereiche aus der Cloud setzen.
---

Mit der Fernsteuerung bedienst du SPL Sense aus der SPL Cloud, zum Beispiel einen Raspberry Pi im Rack oder einen
Laptop an einer anderen Bühne.

## Voraussetzungen

- **In SPL Sense erlaubt:** **Einstellungen** › **Cloud** › **Fernsteuerung erlauben**. Standardmässig aus. So
  entscheidet immer die Person vor Ort, ob ihre Instanz ferngesteuert werden darf.
- **Instanz online:** Befehle gehen nur an eine verbundene Instanz. Es gibt keine Warteschlange.
- **Pro auf der Messung:** Gesteuert werden nur Messungen mit Pro.
- **Berechtigung:** der Besitzer der Instanz, bei einer Instanz einer Organisation alle Mitglieder. Personen mit
  Lesezugriff oder teilbarem Link können nie steuern.
- **SPL Sense ab Version 2.0.**

## Was geht

Auf der Seite der Instanz oder der Messung im Bereich **Fernsteuerung**:

| Aktion | Hinweis |
|---|---|
| **Start**, **Stopp** | |
| **Leveler-Bypass**, **Bypass aufheben** | |
| Messung wechseln (**Zur aktuellen Messung machen**), deaktivieren | nur bei gestoppter Messung |
| **Neue Messung** erstellen | mit Name, Tagesgrenze und einer Werteprofilvorlage der Instanz. Die Cloud Synchronisierung ist immer an; Pro lässt sich gleich mitaktivieren. |
| Name und Tagesgrenze ändern | nicht während die Messung läuft |
| **Offsets** ändern | nicht während die Messung läuft |
| **Werteprofil** wechseln | eine der Vorlagen der Instanz; nicht während die Messung läuft |
| **Leveler Einstellungen**: Modus, Grenzwerte, Line Offsets | auch während der Messung, gilt sofort |
| **Messung abschliessen**, **Wieder öffnen** | |

Mit **Messungen auf der Instanz** siehst du alle Messungen von SPL Sense, auch solche ohne Cloud Synchronisierung.
Steuern lassen sich nur Messungen, die in der Cloud sind und Pro haben.

## Was nicht geht

- Kalibrierung und Software-Updates
- Line Offset einmessen (braucht Rauschen und Stille vor Ort)
- Leveler-Verbindung einstellen
- eigene Grenzwerte im Werteprofil bearbeiten; das geht nur auf der Instanz

## Bestätigung und Rückmeldung

Jeder Befehl, der etwas verändert, fragt vorher nach, mit Messung und Instanz im Text, zum Beispiel «Messung
'Hauptbühne' auf 'Laptop-FOH' stoppen?».

Danach meldet die Cloud das Ergebnis. Antwortet die Instanz nicht rechtzeitig, steht dort, dass der Befehl
möglicherweise trotzdem ausgeführt wurde; prüfe dann den Zustand der Instanz.

In SPL Sense erscheint jeder Befehl aus der Cloud als Meldung, und die Ereignisse der Messung zeigen, wer ihn
ausgelöst hat (**per Fernsteuerung durch …**).

Ändern Personen vor Ort und in der Cloud gleichzeitig etwas, gilt die letzte Änderung.

## Kommentare und ausgenommene Zeitbereiche

Mit Pro kannst du auch in der Cloud im Bereich **Ereignisse** **Kommentare** hinzufügen und **Zeitbereiche
ausnehmen**, genau wie in [SPL Sense]({{< relref "/docs/spl-sense/measurement-data#kommentare" >}}). Auch das läuft
über die Fernsteuerung: Die Instanz muss online sein und die Fernsteuerung erlauben.
