---
title: Live-Anzeige und Kiosk
linkTitle: Live-Anzeige und Kiosk
weight: 40
description: >-
  Live Ansicht, eingebaute und eigene Screens, Widgets und Kiosk-Modus.
---

Die **Live Ansicht** zeigt die aktuellen Werte gross und gut lesbar, zum Beispiel auf einem zweiten Bildschirm beim DJ
oder bei der Technik. Du öffnest sie auf der Messungsseite mit **Live Ansicht** oder mit einem Klick auf den
Gerätestatus in der Statusleiste.

## Screens wählen

Oben rechts in der Live Ansicht wählst du den Screen. SPL Sense merkt sich pro Messung, welcher zuletzt verwendet wurde.

Eingebaut sind Screens für die gängigen Fälle, jeweils mit und ohne Leveler-Anzeige:

| Screen | Inhalt |
|---|---|
| **VNISSG 93dBA**, **96dBA**, **100dBA** | LAeq 3 s, LAeq 5′, LAeq 60′, LAFmax, Verlauf der letzten Stunde |
| **DIN 15905-5** | LAeq 5 s, LAeq 5′, LAeq 30′, LCFmax, Verlauf der letzten Stunde |
| **DJ** | LAeq 3 s und LAeq 5′, reduziert auf das Wichtigste |
| … **Leveler** | zusätzlich Gain-Reduktion und Korrelation |

## Eigene Screens

Unter **Einstellungen** › **Live Anzeige Screens** › **Erstellen**:

1. Gib einen **Namen** ein.
2. Füge mit **Hinzufügen** Widgets hinzu.
3. Ordne sie auf dem Raster an: Ziehe ein Widget, um es zu verschieben, und seine Ecke, um die Grösse zu ändern.
   Mit der Tastatur: Pfeiltasten verschieben, <kbd>Shift</kbd> + Pfeiltasten ändern die Grösse.
4. Wähle ein Widget, um seinen Typ mit **Ändern** zu wechseln oder seine **Farbschwellen** festzulegen.
5. **Speichern**.

Die Vorschau zeigt Platzhalterwerte in der echten Grösse, so siehst du, wie gross die Zahlen werden. Auf schmalen
Bildschirmen stehen die Widgets untereinander.

### Widgets

| Gruppe | Widgets |
|---|---|
| **Numerisch SPL** | Leq oder MaxF, Gewichtung A, C oder Z, über **Jetzt**, 1 s bis 60 min |
| **Diagramm** | Spektrum, Verlauf heute, Verlauf letzte Stunde |
| **Leveler** | Gain-Reduktion, Korrelation |
| **Andere** | letztes Intervall |

### Farbschwellen

Numerische Widgets färben sich ein, wenn ein Wert eine Schwelle überschreitet. Die Schwellen setzt du von Hand oder
übernimmst sie mit **Vom Werteprofil** aus der Messung. Das geht nur für Zeiten über einer Minute, weil das Werteprofil
keine kürzeren Zeiten kennt.

## Vollbild und Kiosk

Mit **Vollbild** schaltet die Live Ansicht in den Kiosk-Modus: Statt Menüs zeigt eine schmale Leiste nur Messung, Screen,
Zeit des letzten Werts und Gerätestatus. Die Widgets füllen den ganzen Bildschirm, auch auf einem grossen Fernseher.
**Vollbild verlassen** führt zurück.

Ist eine [Operator-PIN]({{< relref "einstellungen#operator-pin" >}}) gesetzt, fragt SPL Sense sie beim Verlassen
der Live Ansicht und des Vollbilds ab. So kann am DJ-Pult niemand die Einstellungen ändern.

Für Geräte, die direkt in die Live Ansicht starten sollen, siehe [Betrieb ohne Bildschirm]({{< relref "/docs/entwickler/betrieb" >}}).
