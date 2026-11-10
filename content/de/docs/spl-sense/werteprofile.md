---
title: Werteprofile
linkTitle: Werteprofile
weight: 30
description: >-
  Welche Werte berechnet werden, mit welchen Schwellen, und die eingebauten Vorlagen.
---

Ein Werteprofil legt fest, welche Werte eine Messung berechnet und ab wann sie als zu laut gelten. Es bestimmt die
Farben in Übersicht und Grafik, die Überschreitungen und die Alarme in der SPL Cloud.

## Aufbau

Ein Werteprofil besteht aus einem oder mehreren Werten. Jeder Wert hat:

| Teil | Möglichkeiten |
|---|---|
| **Integration** | **Leq** (Mittelungspegel) oder **MaxF** (höchster Pegel mit Zeitbewertung Fast) |
| **Gewichtung** | A, C oder Z |
| **Zeit** | 1 bis 60 Minuten |
| **Benachrichtigung**, **Warnung**, **Limit** | Schwellen in dB, jede optional |

Beispiele: Leq, A, 60 Minuten ergibt **LAeq 60′**; MaxF, C, 1 Minute ergibt **LCFmax 1′**.

Mittelwerte werden gleitend berechnet: LAeq 60′ ist zu jeder Minute der Mittelwert über die 60 Minuten davor, auch über
die Tagesgrenze und über Pausen hinweg. Ein Wert gilt als über der Schwelle, wenn er sie überschreitet; genau gleich
viel ist noch in Ordnung.

## Eingebaute Vorlagen

SPL Sense bringt Vorlagen für die Schweiz (V-NISSG) und Deutschland (DIN 15905-5) mit. Die Werte stehen unter
[Vorlagen für V-NISSG und DIN 15905-5]({{< relref "/docs/grundlagen/vorschriften" >}}). Eingebaute Vorlagen lassen sich
nicht verändern.

## Eigene Vorlagen

Unter **Einstellungen** › **Werteprofile** › **Erstellen** legst du eigene Vorlagen an:

1. Gib einen **Namen** ein.
2. Füge mit **Werte hinzufügen** die gewünschten Werte hinzu und setze die Schwellen.
3. Klicke auf **Speichern**.

Eigene Vorlagen kannst du jederzeit ändern oder löschen. Messungen, die eine Vorlage verwenden, sind davon nicht
betroffen: Beim Anlegen wird die Vorlage in die Messung kopiert.

## Werteprofil einer Messung ändern

Menü **Messung** › **Messung bearbeiten** › **Werteprofil bearbeiten**. Hier wählst du eine andere Vorlage oder passt
die Werte direkt an. Weicht das Profil von seiner Vorlage ab, zeigt SPL Sense das an; mit
**Profile auf Vorlage-Werte zurücksetzten** stellst du die Werte der Vorlage wieder her.

Beim Speichern rechnet SPL Sense alle bisherigen Messtage mit dem neuen Profil neu. Die Messdaten selbst ändern sich
dabei nicht. Die Änderung erscheint mit altem und neuem Profil in den Ereignissen.
