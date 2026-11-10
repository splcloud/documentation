---
title: Messdaten auswerten
linkTitle: Messdaten auswerten
weight: 25
description: >-
  Tage, Grafik, Intervall-Details, Überschreitungen, Ereignisse, Kommentare, ausgenommene Zeitbereiche und Berichte.
---

Die Messungsseite sieht in SPL Sense und in der SPL Cloud gleich aus. Was hier steht, gilt für beide; Abweichungen bei
den Berichten stehen am Schluss.

## Messtage und Grafik

Die Daten sind nach Messtagen gegliedert; ein Messtag endet an der Tagesgrenze der Messung. Jeder Tag zeigt die Werte
des Werteprofils, eingefärbt nach den Schwellen: gelb für **Benachrichtigung**, orange für **Warnung**, rot für **Limit**.
Mit **Alle Tage anzeigen** blendest du ältere Tage ein.

Die Grafik zeigt den Verlauf des gewählten Tages:

- die Werte des Werteprofils als Linien, die Bewertung als farbiges Band
- Kommentare und Ereignisse als Markierungen
- ausgenommene Zeitbereiche ausgegraut
- bei aktivem Leveler zusätzlich den Signalpegel (Line), die Gain-Reduktion und die Korrelation

Die ersten Werte erscheinen nach der ersten vollen Minute der Aufzeichnung.

## Intervall-Details

Ein Klick in die Grafik öffnet die Details der Minute an dieser Stelle (ein **Intervall**): alle Werte, das
Spektrum in Terzbändern und die Prüfergebnisse. Mit den Pfeilen blätterst du zur vorherigen oder nächsten Minute.

| Hinweis | Bedeutung |
|---|---|
| **Signatur gültig** | Die Daten sind unverändert, seit der Sensor sie signiert hat. |
| **Signatur ungültig** / **Blocksignatur fehlt** | Die Daten können nicht als unverändert nachgewiesen werden. |
| **Kalibrierung verfallen** | Die Daten wurden mit abgelaufener Kalibrierung aufgezeichnet. |
| **Clip** | Der Pegel war für den Sensor zu hoch (übersteuert). Die Werte dieser Minute sind nicht zuverlässig. |
| **Tiefe Werte** | Der Pegel lag unter dem Messbereich des Sensors. |
| **Temperatur** | Der Sensor war zu heiss. |
| **Versorgungsspannung** | Die Versorgungsspannung des Sensors war zu tief. |
| **Wetterschutz** | Der Kompensationsfilter für den Wetterschutz war eingeschaltet. |
| **Mehrere Sensoren benutzt** | In dieser Minute wurde der Sensor gewechselt. |

## Überschreitungen

Der Bereich **Überschreitungen** listet pro Wert des Werteprofils, wann der gewählte Tag eine Schwelle überschritten
hat, mit dem höchsten Wert. Ein Klick auf einen Eintrag zeichnet die Schwellen in die Grafik ein.

## Ereignisse

Der Bereich **Ereignisse** listet alles, was mit der Messung passiert ist, das Neueste zuoberst:

- Aufzeichnung gestartet und gestoppt, mit Grund (zum Beispiel manuell, autonomer Modus, Mikrofon getrennt,
  Ruhezustand, Sensor wieder verbunden)
- Messung erstellt, aktiviert, abgeschlossen, wieder geöffnet
- Offsets, Werteprofil und Leveler-Einstellungen geändert, jeweils mit den alten und neuen Werten
- Leveler bypassed und wieder aktiviert
- Kommentare und geänderte ausgenommene Zeitbereiche

Kam eine Änderung über die SPL Cloud oder die API, steht das dabei, bei der Cloud auch, von wem.

## Kommentare

Mit **Hinzufügen** › **Kommentar hinzufügen** im Bereich Ereignisse hältst du etwas zu einem Zeitpunkt fest, zum
Beispiel «Zugabe» oder «Offset mit Handmessgerät geprüft». Kommentare erscheinen in der Grafik und lassen sich später
bearbeiten. Bei einer abgeschlossenen Messung sind Kommentare nur bis zum Zeitpunkt des Abschlusses möglich.

## Zeitbereiche ausnehmen

Manche Zeiten sollen nicht in die Bewertung einfliessen, zum Beispiel das Einmessen mit rosa Rauschen vor Türöffnung.
Mit **Hinzufügen** › **Zeitbereich ausnehmen** legst du dafür einen Bereich mit **Von**, **Bis** und Kommentar fest.

Ein ausgenommener Bereich:

- wird in der Grafik ausgegraut und als **Nicht gewertet** markiert
- zählt nicht für Maxima, die Bewertung nach dem Werteprofil und die Überschreitungen
- bleibt mit allen Messdaten erhalten

Mit **Wieder werten?** hebst du die Ausnahme auf. Jede Änderung erscheint in den Ereignissen.

## Berichte und Exporte

| Was | Wo |
|---|---|
| Tagesbericht (PDF) des gewählten Tages | Button **PDF** beim Tag |
| CSV des gewählten Tages | Button **CSV** beim Tag |
| CSV der ganzen Messung | Menü **Messung** › **Gesamte Messung als CSV exportieren** |
| ganze Messung als Sicherung | **Messung exportieren**, siehe [Messungen]({{< relref "messungen#import-und-export" >}}) |

In der SPL Cloud gibt es den Tagesbericht, auch mit Abweichungen, sowie einen Bilderbericht mit
[Pro]({{< relref "/docs/spl-cloud-pro/berichte-und-bilder" >}}).

## Cloud-Synchronisierung

Ist die Cloud Synchronisierung eingeschaltet, zeigt die Messungsseite den Stand des Uploads: **Online**, **Offline**
und wie viele Intervalle, Ereignisse und Leveler-Statistiken noch auf den Upload warten. Ohne Internet misst
SPL Sense normal weiter und holt den Upload nach.
