---
title: Datenformate
linkTitle: Datenformate
weight: 30
description: >-
  CSV-Export und .splsense-Dateien.
---

## CSV

Den CSV-Export gibt es pro Tag und für die ganze Messung, in SPL Sense und in der SPL Cloud (dort für die ganze
Messung als ZIP).

- Trennzeichen: Semikolon `;`
- eine Zeile pro Minute (Intervall)
- erste Spalte `Timestamp`: Ende des Intervalls im Format ISO 8601 mit Zeitzone, zum Beispiel
  `2026-07-12T22:15:00.0000000+02:00`
- danach eine Spalte pro Wert des Werteprofils, in dessen Reihenfolge, mit Bezeichnung und Einheit im Kopf
- Werte in dB mit einer Nachkommastelle, inklusive Offset
- Dezimaltrennzeichen gemäss Sprache der Oberfläche

Ausgenommene Zeitbereiche, Kommentare und Ereignisse sind nicht im CSV enthalten.

## `.splsense`

Eine `.splsense`-Datei enthält eine ganze Messung aus SPL Sense mit allen Aufzeichnungen, signierten Intervallen,
Ereignissen und Einstellungen. Sie dient zur Sicherung und zum Übertragen auf einen anderen Computer
([Import und Export]({{< relref "/docs/spl-sense/measurements#import-und-export" >}})).

Das Format ist intern und kann sich mit neuen Versionen ändern. Zum Auswerten in eigener Software eignen sich der
CSV-Export und die [SPL Sense API]({{< relref "sense-api" >}}).
