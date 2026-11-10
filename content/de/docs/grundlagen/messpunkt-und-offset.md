---
title: Messpunkt und Offset
linkTitle: Messpunkt und Offset
weight: 20
description: >-
  Wo der Sensor hingehört, wie du den Offset bestimmst und was du dokumentieren solltest.
---

## Ermittlungsort und Messort

Die Grenzwerte der V-NISSG gelten am **Ermittlungsort**: dem lautesten Ort im Publikumsbereich, auf Ohrenhöhe. Dort kann
der Sensor während einer Veranstaltung selten stehen, mitten im Publikum wäre er gefährdet und würde durch Zurufe und
Applaus verfälscht.

Gemessen wird deshalb meist an einem anderen Ort, dem **Messort**, oft beim Mischpult. Der Unterschied zwischen den
beiden Orten ist der **Offset**. SPL Sense addiert ihn zu jedem Messwert, damit die angezeigten und gespeicherten Werte
dem Pegel am Ermittlungsort entsprechen.

## Den Messort wählen

- Der Sensor soll den **Direktschall** der Beschallung abbekommen: freie Sicht auf die Lautsprecher, nicht hinter Säulen,
  Zelten oder dem Mischpult-Dach.
- Nicht nahe an Hochtönern, Wänden oder in Raumecken.
- Möglichst wenig Publikumseinfluss: über Kopfhöhe oder etwas abseits der Menge.
- Draussen mit Wetterschutz, und den passenden [Wetterschutzfilter]({{< relref "/docs/spl-sense/sensor-und-kalibrierung" >}})
  einschalten.
- Während der Veranstaltung nicht mehr verschieben. Musst du ihn doch verschieben, bestimme den Offset neu.

## Den Offset bestimmen

Der Offset wird **vor der Veranstaltung mit rosa Rauschen** bestimmt, so laut wie im Betrieb und über dieselbe
Beschallung. In SPL Sense geht das mit **Offsets tunen**, Schritt für Schritt im
[Schnellstart]({{< relref "/docs/schnellstart#5-offset-einstellen" >}}) beschrieben. Kurz:

1. Rosa Rauschen in Betriebslautstärke abspielen.
2. Mit dem Sensor den Publikumsbereich ablaufen. SPL Sense merkt sich den höchsten Pegel, das ist dein Ermittlungsort.
3. Sensor an den Messort stellen und den Offset so einstellen, dass der Pegel am Messort plus Offset dem höchsten Pegel
   entspricht.

Statt den Bereich mit dem Sensor abzulaufen, kannst du den Pegel am Ermittlungsort auch mit einem Handmessgerät
bestimmen und die Differenz direkt unter **Messung bearbeiten** eintragen.

Der Offset gilt pro Bewertung: Für A, C und Z gibt es je einen eigenen Wert. Ist der Ermittlungsort lauter als der
Messort, ist der Offset positiv.

{{% alert title="Tipps" color="info" %}}
- Prüfe den Offset danach mit typischer Musik. Weicht er stark ab, wiederhole die Messung.
- Rechne den Offset nicht mit Faustformeln aus (z.B. «−6 dB pro Abstandsverdopplung»); miss ihn.
- Prüfe während der Veranstaltung kurz, ob die Werte plausibel sind.
{{% /alert %}}

## Dokumentieren

Halte schriftlich fest, wie du gemessen hast. Das BAG empfiehlt mindestens:

- Ermittlungsort und Messort, mit Abständen
- den Offset und wie du ihn bestimmt hast (Signal, Pegel)
- die verwendeten Messgeräte

In der SPL Cloud kannst du dafür Bilder vom Messort an die Messung hängen ([SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/berichte-und-bilder" >}}))
und Notizen als Kommentare in der Messung festhalten. Jede Änderung des Offsets erscheint automatisch in den Ereignissen.

## Weiterlesen

- [Vollzugshilfe V-NISSG, Schall](https://www.bag.admin.ch/dam/de/sd-web/YE91ECm2uBte/V-NISSG_Vollzugshilfe%20Schall_%20DE.pdf),
  Kapitel 4.3 (Ermittlungsort) und 8
- [Messverfahren zur Ermittlung von Schallpegeln an Veranstaltungen](https://www.bag.admin.ch/dam/de/sd-web/MiPiTdLBjxC8/emfehlungen_messverfahren.pdf)
