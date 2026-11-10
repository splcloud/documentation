---
title: Einstellungen
linkTitle: Einstellungen
weight: 80
description: >-
  Operator-PIN, Verbindung zur SPL Cloud und Fernsteuerung, API, Sprache.
---

Die Einstellungen öffnest du mit dem Zahnrad oben rechts. Jede Zeile zeigt den aktuellen Stand.

| Gruppe | Einstellungen |
|---|---|
| **Messen** | [Werteprofile]({{< relref "value-profiles" >}}), [Live Anzeige Screens]({{< relref "live-screen" >}}), [Autonomer Modus]({{< relref "autonomous-mode" >}}) |
| **Gerät** | [Sensor Informationen]({{< relref "sensor-and-calibration" >}}), [Leveler]({{< relref "leveler#den-l1-selbst-einrichten" >}}), [Update]({{< relref "installation-and-updates#updates" >}}) |
| **Zugriff und Verbindungen** | Operator-PIN, Cloud, API, Sprache |
| **Über** | Version, Release Notes, Kontakt, Datenschutz, Open-Source-Lizenzen |

## Operator-PIN

Mit einer Operator-PIN schützt du SPL Sense vor Änderungen. Ohne PIN kann jede Person, die Zugriff auf SPL Sense hat,
alles ändern.

1. **Einstellungen** › **Operator-PIN**.
2. Gib eine **Neue PIN** ein (4 bis 8 Ziffern) und wiederhole sie.
3. **Speichern**.

Mit gesetzter PIN:

- sind alle Seiten ausser der Live Ansicht gesperrt. SPL Sense zeigt **SPL Sense ist gesperrt** und fragt nach der PIN.
- fragt SPL Sense die PIN auch beim Verlassen der Live Ansicht und des Vollbilds ab.
- gilt die PIN in der App und im Browser (Webserver-Betrieb).

Mit **PIN entfernen** hebst du den Schutz wieder auf.

## SPL Cloud

Unter **Einstellungen** › **Cloud** verbindest du SPL Sense mit der SPL Cloud. Eine angemeldete Installation heisst in
der Cloud **Instanz**.

### Anmelden

1. **Instanz anmelden**. SPL Sense braucht dafür Internet.
2. Öffne den angezeigten Link oder scanne den QR-Code mit einem anderen Gerät. Der Code ist nur kurze Zeit gültig;
   mit **Neuer Anmeldecode abfragen** erhältst du einen neuen.
3. Melde dich in der SPL Cloud an und bestätige die Registrierung. Wähle dabei den **Besitzer**: du persönlich oder
   eine Organisation, in der du Mitglied bist. Siehe [Organisationen]({{< relref "/docs/spl-cloud/organizations" >}}).

Danach zeigt die Seite **Instanz ist registriert** mit Instanz ID, Host, Besitzer und dem Verbindungsstatus
(**Online**, **Verbinden...**, **Offline**).

Welche Messungen in die Cloud gehen, legst du pro Messung mit der **Cloud Synchronisierung** fest, siehe
[Messungen]({{< relref "measurements#bearbeiten" >}}).

### Abmelden

**Instanz abmelden** trennt SPL Sense von der Cloud. Bei allen Messungen wird die Cloud Synchronisierung
ausgeschaltet; was schon in der Cloud ist, bleibt dort. Nach einer neuen Anmeldung schaltest du die Synchronisierung
pro Messung wieder ein.

Zeigt die Seite **Authentifizierung fehlgeschlagen!**, melde die Instanz ab und wieder an.

### Fernsteuerung erlauben

Mit **Fernsteuerung erlauben** dürfen Personen mit Zugriff auf diese Instanz in der SPL Cloud Messungen starten und
stoppen, wechseln und erstellen sowie Offsets, Leveler und Werteprofil ändern, solange SPL Sense online ist.
Kalibrierung und Updates sind aus der Ferne nie möglich.

Die Fernsteuerung ist standardmässig aus. Ist sie eingeschaltet, zeigt die Statusleiste das an, und jeder Befehl aus
der Cloud erscheint als Meldung und in den Ereignissen der Messung, mit dem Namen der Person.

In der Cloud braucht die Fernsteuerung [SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/remote-control" >}}) auf der
Messung.

## API

Über die SPL Sense API lassen sich SPL Sense überwachen und steuern und externe Audioprozessoren als Leveler anbinden.
Standardmässig ist sie aus. Details unter [SPL Sense API]({{< relref "/docs/developers/sense-api" >}}).

## Sprache

Deutsch, Englisch, Französisch oder **Betriebssystem Standard**.

## Über

Version, Release Notes (englisch), Kontakt, Datenschutzerklärung und die verwendeten Open-Source-Lizenzen.
