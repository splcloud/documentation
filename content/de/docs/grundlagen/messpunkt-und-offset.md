---
title: Messpunkt und Offset
linkTitle: Messpunkt und Offset
weight: 20
description: >-
  Wo der Sensor hingehört, wie du den Offset bestimmst und was du dokumentieren solltest.
---

## Ermittlungsort und Messort

Die Grenzwerte gelten am **lautesten Ort im Publikumsbereich**, auf Ohrenhöhe. Die V-NISSG nennt ihn
*Ermittlungsort*, die DIN 15905-5 *maßgeblichen Immissionsort*. Dort kann der Sensor während einer Veranstaltung
selten stehen: Mitten im Publikum wäre er gefährdet, und Zurufe und Applaus würden die Messung verfälschen.

Gemessen wird deshalb an einem anderen Ort, dem **Messort** (DIN: *Ersatzimmissionsort*). Den Unterschied zwischen
den beiden Orten gleicht der **Offset** aus (DIN: *Korrekturwert*). SPL Sense addiert ihn zu jedem Messwert, damit die
angezeigten und gespeicherten Werte dem Pegel am lautesten Ort im Publikum entsprechen.

## Den Messort wählen

- Der Sensor soll den **Direktschall** der Beschallung abbekommen: freie Sicht auf die Lautsprecher, nicht hinter Säulen,
  Zeltstangen oder dem Dach des Mischpults.
- Möglichst wenig Publikum und andere Geräuschquellen in der Nähe.
- Nicht in Raumecken und nicht direkt an Wänden.
- Draussen mit Wetterschutz, und den passenden [Wetterschutzfilter]({{< relref "/docs/spl-sense/sensor-und-kalibrierung" >}})
  einschalten.
- Während der Veranstaltung nicht mehr verschieben. Musst du ihn doch verschieben, bestimme den Offset neu.

### Abstand zu den Lautsprechern

Der Sensor braucht einen **Mindestabstand** zur Beschallung:

- Erst in einigem Abstand mischen sich Hoch-, Mittel- und Tieftöner zum Klang, den auch das Publikum hört. Zu nahe an
  einem Lautsprecher misst der Sensor vor allem einen einzelnen Lautsprecher, und der Offset stimmt bei Musik nicht mehr.
- Der Sensor hat einen maximalen Pegel. Zu nahe an einem Lautsprecher können Spitzen ihn übersteuern. SPL Sense zeigt
  das als **Clip** in den Messdaten an.

Innerhalb dieser Grenzen gilt: Je weiter der Messort vom Publikum entfernt und je besser er im Direktschall der
Beschallung liegt, desto weniger stören Publikum und andere Quellen. Liegt der Messort näher an der Beschallung als der
lauteste Ort im Publikum, wird der Offset negativ. Die DIN 15905-5 empfiehlt einen solchen Messort.

## Den Offset bestimmen

Der Offset wird **vor der Veranstaltung mit rosa Rauschen** bestimmt, so laut wie im Betrieb und über genau die
Beschallung, die auch während der Veranstaltung spielt. In SPL Sense geht das mit **Offsets tunen**, Schritt für
Schritt im [Schnellstart]({{< relref "/docs/schnellstart#5-offset-einstellen" >}}) beschrieben. Kurz:

1. Rosa Rauschen in Betriebslautstärke abspielen.
2. Mit dem Sensor den Publikumsbereich ablaufen. SPL Sense merkt sich den höchsten Pegel, das ist dein lautester Ort.
3. Sensor an den Messort stellen und den Offset so einstellen, dass der Pegel am Messort plus Offset dem höchsten Pegel
   entspricht.

Alternativ misst du den Pegel am lautesten Ort mit einem Handmessgerät und trägst die Differenz direkt unter
**Messung bearbeiten** ein. Die DIN 15905-5 verlangt dafür eine Messdauer von mindestens 15 Sekunden.

Der Offset gilt pro Bewertung: Für A, C und Z gibt es je einen eigenen Wert.

- **A** (für LAeq und LAFmax): Der lauteste Ort wird von den Mittel- und Hochtönern bestimmt.
- **C** (für LCFmax und den Spitzenpegel): Der lauteste Ort wird von den Bässen bestimmt und kann woanders liegen.
  Die DIN 15905-5 erlaubt, den C-Offset aus dem LCeq zu bestimmen; das ist zuverlässiger als über Spitzenwerte.

{{% alert title="Tipps" color="info" %}}
- Prüfe den Offset danach mit typischer Musik. Weicht er stark ab, miss nochmals.
- Rechne den Offset nicht mit Faustformeln aus, miss ihn.
- Der Offset gilt nur für diesen Lautsprecheraufbau und diesen Messort. Ändert sich eines davon, miss neu.
- Prüfe während der Veranstaltung kurz, ob die Werte plausibel sind.
{{% /alert %}}

## Funktionstest und Kalibrierung

Beide Regelwerke verlangen, dass die Messkette funktioniert. Bei mobilen Systemen ist ein Test mit einem
Kalibrator vor und nach jeder Veranstaltung üblich (DIN 15905-5: vorgeschrieben). SPL Sense zeigt dir den
Kalibrierstatus des Sensors und warnt vor dem Start, wenn er abgelaufen ist.
Siehe [Sensor und Kalibrierung]({{< relref "/docs/spl-sense/sensor-und-kalibrierung" >}}).

## Dokumentieren

Halte schriftlich fest, wie du gemessen hast. Beide Regelwerke verlangen ein Protokoll, mindestens mit:

- Ort und Datum der Veranstaltung, Beginn und Ende der Messung
- lautester Ort im Publikum und Messort, mit Abständen und Begründung
- Offset (Korrekturwerte) und wie du sie bestimmt hast (Signal, Pegel)
- verwendete Messgeräte und Ergebnis des Funktionstests
- die gemessenen Werte (der PDF-Tagesbericht von SPL Sense oder SPL Cloud)

Die DIN 15905-5 nennt im Abschnitt «Messprotokoll» weitere Angaben, die das Protokoll enthalten muss oder soll.

SPL Sense hilft dabei: Jede Änderung des Offsets erscheint automatisch in den Ereignissen, und mit Kommentaren hältst du
Besonderheiten direkt in der Messung fest. In der SPL Cloud kannst du zudem Bilder vom Messort an die Messung hängen
([SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/berichte-und-bilder" >}})).

Originaldokumente: siehe [Vorlagen für V-NISSG und DIN 15905-5]({{< relref "vorschriften" >}}).
