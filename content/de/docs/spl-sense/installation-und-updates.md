---
title: Installation und Updates
linkTitle: Installation und Updates
weight: 10
description: >-
  Windows, macOS und Linux, Updates und wo SPL Sense seine Daten ablegt.
---

## Plattformen

| Plattform | Betrieb |
|---|---|
| Windows | Desktop-App |
| macOS (Apple Silicon und Intel) | Desktop-App |
| Linux auf ARM und ARM64, z.B. Raspberry Pi | Webserver: Bedienung im Browser, auch von Tablet oder Handy im selben Netzwerk |

Die Funktionen sind überall gleich. Einzige Ausnahme: Den Sensor [kalibrieren]({{< relref "sensor-und-kalibrierung" >}})
kannst du nur in der Desktop-App.

## Installation

| Plattform | Download |
|---|---|
| Windows (64 Bit) | [SPLSenseSetup.exe](https://r.spl.swiss/dl/splsense/win-x64/SPLSenseSetup.exe) |
| macOS mit Apple-Chip (M1 und neuer) | [SPLSense-osx-arm64-Setup.pkg](https://r.spl.swiss/dl/splsense/osx-arm64/SPLSense-osx-arm64-Setup.pkg) |
| macOS mit Intel-Prozessor | [SPLSense-osx-x64-Setup.pkg](https://r.spl.swiss/dl/splsense/osx-x64/SPLSense-osx-x64-Setup.pkg) |
| Linux | siehe [Betrieb unter Linux]({{< relref "/docs/entwickler/betrieb" >}}) |

Öffne die heruntergeladene Datei und folge dem Installationsprogramm. Welchen Mac du hast, siehst du unter
Apple-Menü › **Über diesen Mac**: «Chip» bedeutet Apple-Chip, «Prozessor» Intel.

## Erster Start

Beim ersten Start zeigt SPL Sense einen Hinweis zum Datenschutz. Mit **Akzeptieren und Fortfahren** geht es weiter,
mit **Applikation beenden** wird SPL Sense geschlossen.

## Updates

SPL Sense prüft selbst, ob eine neue Version verfügbar ist. Ist das der Fall, erscheint auf der Übersicht der Hinweis
**Update verfügbar** mit den Buttons **Update** und **Später erinnern**.

1. Stoppe eine laufende Messung. Während einer Messung lässt sich kein Update installieren.
2. Klicke auf **Update** und danach auf **Aktualisieren und neu starten**.
3. SPL Sense lädt die neue Version, installiert sie und startet neu.

Startet SPL Sense nach dem Update nicht von selbst, starte es von Hand. Nach einem Neustart ist keine Messung aktiv,
ausser der [autonome Modus]({{< relref "autonomer-modus" >}}) ist eingeschaltet.

Die aktuelle Version und die Versionsgeschichte findest du unter **Einstellungen** › **Über**.

## Wo die Daten liegen

SPL Sense speichert alle Messungen lokal auf dem Computer:

| Plattform | Ordner |
|---|---|
| Windows | `%AppData%\SPLSense` |
| macOS | `~/Library/SPLSense` |
| Linux | `~/.SPLSense` |

Sichere diesen Ordner regelmässig oder schalte für deine Messungen die
[Cloud Synchronisierung]({{< relref "einstellungen#spl-cloud" >}}) ein. Einzelne Messungen sicherst du als
`.splsense`-Datei, siehe [Import und Export]({{< relref "messungen#import-und-export" >}}).
