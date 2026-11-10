---
title: Oberfläche und Suche
linkTitle: Oberfläche und Suche
weight: 15
description: >-
  Statusleiste, Gerätestatus, Übersicht, Menüs und Suche.
---

## Statusleiste

Oben auf jeder Seite steht die Statusleiste:

- **Logo und Pfad:** Das Logo führt zur Übersicht, der Pfad daneben zurück zu übergeordneten Seiten.
- **Gerätestatus:** zeigt auf einen Blick, was gerade läuft:
  - **Messung läuft** (grün, mit dem aktuellen LAeq 1 s): Ein Klick öffnet die Live Ansicht.
  - **Messung gestoppt** oder **Kein Sensor verbunden** (rot): Ein Klick öffnet die aktive Messung.
  - **Keine Messung geladen**
- **Verbundene Geräte:** Sensor, Leveler und Cloud-Verbindung, jeweils mit ihrem Zustand. Ist die Fernsteuerung aus der
  SPL Cloud erlaubt, steht hier auch das.
- **Suche** (Lupe), **Hilfe** (Fragezeichen, öffnet diese Dokumentation) und **Einstellungen** (Zahnrad).

## Übersicht

Die Übersicht listet alle offenen Messungen als Karten. Jede Karte zeigt den Zustand der Messung und die Werte der
letzten vier Messtage, eingefärbt nach den Schwellen des Werteprofils. Darunter stehen die abgeschlossenen Messungen
als kurze Liste.

Rechts oben legst du mit **Neue Messung** eine Messung an oder holst mit **Import** eine gesicherte Messung zurück.

Unten auf der Übersicht stehen der verbundene Sensor, ein angeschlossener Leveler und, wenn verfügbar, ein Hinweis auf
ein Update.

## Messungsseite

- **Seitenkopf:** Name, Zustand und die wichtigsten Aktionen als Buttons, zum Beispiel **Start** oder **Stopp**.
  Alle weiteren Aktionen stehen im Menü **Messung**. Aktionen, die die Messung endgültig verändern
  (Deaktivieren, Abschliessen), stehen am Ende des Menüs.
- **Live-Leiste:** Während der Messung siehst du unter dem Seitenkopf laufend die 1-Sekunden-Werte und, falls aktiv,
  den Leveler.
- **Tage und Grafik:** Wähle einen Messtag; die Grafik zeigt seinen Verlauf. Beim Tag findest du die Buttons **PDF**
  (Tagesbericht) und **CSV**.
- **Darunter:** Überschreitungen, Ereignisse, Sensor und Cloud-Synchronisierung.

Was die Werte und Markierungen bedeuten, steht unter [Messdaten auswerten]({{< relref "measurement-data" >}}).

## Zustände einer Messung

| Zustand | Bedeutung |
|---|---|
| **Aktiv** | Die Messung ist geladen und bereit. SPL Sense zeichnet auf, sobald du startest. Es ist immer höchstens eine Messung aktiv. |
| **Messung läuft** | SPL Sense zeichnet auf. |
| **Unterbrochen** | Der Sensor liefert keine Daten mehr, zum Beispiel weil er ausgesteckt wurde oder der Computer im Ruhezustand war. Die Messung läuft von selbst weiter, sobald der Sensor wieder Daten liefert. |
| **Gestoppt** | Die Aufzeichnung ist angehalten. |
| **Abgeschlossen** | Die Messung ist gesperrt und kann nur noch angesehen, exportiert oder wieder geöffnet werden. |

Mehr dazu unter [Messungen]({{< relref "measurements" >}}).

## Suche

Mit der Lupe oder mit <kbd>Ctrl</kbd>+<kbd>K</kbd> (Mac: <kbd>⌘</kbd>+<kbd>K</kbd>) öffnest du die Suche.
Sie findet Messungen (offene und abgeschlossene), Einstellungsseiten, Werteprofile und Live Anzeige Screens.
Mit den Pfeiltasten wählst du einen Treffer, mit <kbd>Enter</kbd> öffnest du ihn.

Einstellungen findest du auch über Stichworte, zum Beispiel «Passwort» für die Operator-PIN oder «Limiter» für den Leveler.

## Bedienung auf Tablet und Handy

Im Webserver-Betrieb (Linux) bedienst du SPL Sense über den Browser, auch von Tablet oder Handy. Die Oberfläche passt
sich an kleine Bildschirme an: Der Pfad in der Statusleiste wird zu einem Zurück-Link, Listen werden untereinander
angezeigt.
