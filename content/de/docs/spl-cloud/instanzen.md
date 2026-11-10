---
title: SPL Sense Instanzen
linkTitle: SPL Sense Instanzen
weight: 30
description: >-
  Angemeldete SPL Sense Installationen überwachen und verwalten.
---

Jede Installation von SPL Sense, die bei der SPL Cloud angemeldet ist, heisst **Instanz**: ein Laptop, ein Desktop-PC
oder ein Raspberry Pi. Wie du eine Instanz anmeldest, steht unter
[SPL Sense › Einstellungen]({{< relref "/docs/spl-sense/einstellungen#spl-cloud" >}}).

## Zustände

| Zustand | Bedeutung |
|---|---|
| **Misst** | SPL Sense ist online und zeichnet auf. |
| **Verbindung verloren** | Die Instanz hat sich während einer Messung nicht mehr gemeldet. SPL Sense misst in der Regel weiter und lädt die Daten nach, sobald wieder Internet da ist. |
| **Online** | SPL Sense läuft und ist verbunden, misst aber nicht. |
| **Offline** | SPL Sense läuft nicht oder hat kein Internet. Angezeigt wird der letzte Kontakt. |

## Wo du Instanzen findest

- **Statusleiste**: «SPL Sense 3 von 5 online», mit Liste aller deiner Instanzen
- **Übersicht**, ganz unten: alle Instanzen mit Zustand, Tätigkeit, Besitzer und aktuellem Pegel
- **Einstellungen** › **Persönliche SPL Sense Instanzen** und auf der Seite jeder Organisation

Jede Instanz zeigt das Symbol ihres Betriebssystems (Apple, Windows, Linux).

## Seite einer Instanz

Ein Klick auf eine Instanz zeigt:

- was sie gerade tut: während der Messung die laufende Messung mit den aktuellen 1-Sekunden-Werten, bei aktivem
  Leveler mit Gain-Reduktion und Korrelation; offline den letzten Kontakt
- die **Details**: Instanz ID, Host, Betriebssystem, Besitzer, Datum der Registrierung
- mit [Pro]({{< relref "/docs/spl-cloud-pro/fernsteuerung" >}}) die Fernsteuerung

## Wem die Daten gehören

Eine neue Messung, die eine Instanz hochlädt, gehört dem Besitzer der Instanz. In eine bestehende Messung dürfen nur
Instanzen desselben Besitzers hochladen.

## Besitzer wechseln

Den Besitzer einer Instanz wechselst du, indem du sie neu anmeldest:

1. In SPL Sense: **Einstellungen** › **Cloud** › **Instanz abmelden**.
2. **Instanz anmelden** und bei der Bestätigung in der Cloud den neuen **Besitzer** wählen.
3. In SPL Sense die **Cloud Synchronisierung** der gewünschten Messungen wieder einschalten.

Die Instanz behält ihre ID. Bereits hochgeladene Messungen behalten ihren bisherigen Besitzer.

## Instanz entfernen

Auf der Seite der Instanz im Menü: **Instanz entfernen**. Die Instanz kann danach nichts mehr hochladen. Die Messungen
in der Cloud bleiben erhalten. Melde die Instanz auch in SPL Sense ab, damit sie nicht weiter versucht, sich zu
verbinden.
