---
title: Glossar
linkTitle: Glossar
weight: 10
description: >-
  Die wichtigsten Begriffe und Abkürzungen in SPL Sense und SPL Cloud, alphabetisch.
---

## Messwerte und Schreibweise

SPL Sense und SPL Cloud schreiben Messwerte so, wie es in der Akustik üblich ist:

| Anzeige | Bedeutung |
|---|---|
| **LAeq 60′** | Mittelungspegel (Leq) mit A-Bewertung über 60 Minuten. Der «Stundenpegel» der V-NISSG. |
| **LAeq 5′** | dasselbe über 5 Minuten |
| **LCeq 1 s** | Mittelungspegel mit C-Bewertung über 1 Sekunde (Live-Wert) |
| **LAFmax 1′** | höchster Pegel mit A-Bewertung und Zeitbewertung *Fast* innerhalb einer Minute |

Der Buchstabe nach dem L ist die Frequenzbewertung (A, C oder Z), danach folgt die Art (eq oder Fmax), dann die Zeit.
Ein Strich ′ steht für Minuten. Die Einheit ist immer dB.

In CSV-Exporten und PDF-Berichten stehen dieselben Werte teilweise noch in einer älteren Schreibweise.

## Begriffe A–Z

**A-, C- und Z-Bewertung**
: Filter, die das Frequenzspektrum gewichten. **A** entspricht ungefähr dem menschlichen Gehör bei leisen Pegeln und
  dämpft Bässe stark; die Mittelungspegel der V-NISSG und der DIN 15905-5 gelten in dB(A). **C** dämpft Bässe nur wenig
  und zeigt, wie viel Tieftonenergie im Spiel ist; die DIN 15905-5 begrenzt damit den Spitzenpegel. **Z** ist ungefiltert (*zero*). SPL Sense misst immer alle drei.

**Abweichung, Überschreitung**
: Ein Wert hat eine Schwelle des Werteprofils überschritten. Die Messdetails zeigen sie pro Tag.

**Ausgenommener Zeitbereich**
: Ein Zeitraum, der nicht für Maxima, Bewertung und Überschreitungen zählt, zum Beispiel das Einmessen. Die Daten bleiben
  erhalten und werden ausgegraut angezeigt.

**Ausgleichszone**
: Bereich, in dem sich das Publikum vom Lärm erholen kann. Die V-NISSG verlangt sie bei Veranstaltungen mit einem
  Stundenpegel über 96 dB(A), die länger als drei Stunden dauern.

**Beurteilungspegel (Lr)**
: Begriff der DIN 15905-5: der LAeq über 30 Minuten am Immissionsort, in Blöcken ab jeder vollen und halben Stunde.
  Zulässig sind 99 dB.

**Ermittlungsort, Immissionsort**
: Der lauteste Ort im Publikumsbereich, auf Ohrenhöhe. Dort gilt der Grenzwert. Die DIN 15905-5 nennt ihn
  *maßgeblichen Immissionsort* und unterscheidet einen für LAeq (bestimmt von Mittel- und Hochton) und einen für den
  Spitzenpegel (bestimmt von den Bässen).
  Siehe [Messpunkt und Offset]({{< relref "measuring-point-and-offset" >}}).

**Fast (F)**
: Zeitbewertung mit 125 ms. Reagiert schnell auf Spitzen. Grundlage für LAFmax.

**Gain-Reduktion (GR)**
: Um wie viele dB der [Leveler]({{< relref "/docs/spl-sense/leveler" >}}) die Lautstärke gerade senkt. Immer 0 oder negativ.

**Instanz**
: Eine Installation von SPL Sense, die bei der SPL Cloud angemeldet ist, zum Beispiel ein Laptop oder ein Raspberry Pi.

**Intervall**
: Ein aufgezeichneter Abschnitt von einer Minute. Er enthält alle Werte dieser Minute und ist digital signiert.

**Kalibrierung**
: Abgleich des Sensors mit einem Referenz-Schallpegel. Sie hat ein Ablaufdatum.
  Siehe [Sensor und Kalibrierung]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}).

**Korrelation**
: Beim Leveler das Verhältnis zwischen gemessenem und erwartetem Pegel. 1.000 heisst: Es ist nur die Beschallung zu hören.
  Werte über 1 zeigen zusätzlichen Lärm, zum Beispiel vom Publikum.

**LCpeak**
: C-bewerteter Spitzenschalldruckpegel: der höchste Momentanwert des Schalldrucks, ohne Zeitbewertung. Die
  DIN 15905-5 begrenzt ihn auf 135 dB. Nicht dasselbe wie LCFmax: Dort wird der Pegel zuerst mit der Zeitbewertung
  Fast (125 ms) geglättet, und davon wird der höchste Wert genommen. Kurze Spitzen fallen dadurch tiefer aus; LCpeak
  liegt deshalb immer gleich hoch oder höher als LCFmax.

**Leq (Mittelungspegel)**
: Der energetische Mittelwert des Pegels über eine bestimmte Zeit. Ein kurzer, sehr lauter Moment hebt den Leq deutlich
  an, ein leiser Moment senkt ihn nur wenig.

**Leveler**
: Regelt die Lautstärke der Beschallung automatisch so, dass der Grenzwert eingehalten wird.

**Lesezugriff**
: Erlaubt einer anderen Person, eine Messung oder einen Messauftrag in der SPL Cloud anzusehen, ohne etwas zu ändern.

**Line Offset**
: Beim Leveler mit Publikumskompensation: der Unterschied zwischen dem Pegel am Sensor und dem Signalpegel am Ausgang des
  Audioprozessors, gemessen ohne Publikum.

**Live Ansicht**
: Grosse Anzeige der aktuellen Werte, zum Beispiel für DJ oder Technik. Aufbau frei gestaltbar.

**LAFmax, MaxF**
: Der höchste Pegel mit Zeitbewertung Fast innerhalb der gewählten Zeit. Die V-NISSG begrenzt LAFmax auf 125 dB(A).

**Messauftrag (Job)**
: Fasst in der SPL Cloud mehrere Messungen zusammen, zum Beispiel alle Messpunkte eines Festivals.

**Messort, Ersatzimmissionsort**
: Wo der Sensor tatsächlich steht, zum Beispiel beim Mischpult. Die DIN 15905-5 nennt ihn *Ersatzimmissionsort*.

**Messtag**
: Ein Tag einer Messung, begrenzt durch die Tagesgrenze. Auch die Pro-Abrechnung zählt Messtage.

**Messung**
: Ein Messpunkt mit seinen Einstellungen und allen aufgezeichneten Daten. Kann über viele Tage laufen.

**Offset, Korrekturwert**
: Wert in dB, der zu jedem gemessenen Wert addiert wird, um vom Messort auf den Ermittlungsort zu schliessen.
  Je ein Wert für A, C und Z. In der DIN 15905-5 heissen sie Korrekturwerte KA und KC.

**Operator-PIN**
: Schützt SPL Sense vor Änderungen. Die Live Ansicht bleibt ohne PIN zugänglich.

**Organisation**
: Eine Firma, ein Lokal oder ein Festival in der SPL Cloud. Ihr gehören Messungen, Messaufträge und Instanzen; mehrere
  Personen arbeiten darin zusammen.

**Rosa Rauschen (Pink Noise)**
: Testsignal mit gleicher Energie pro Oktave. Wird zum Bestimmen von Offset und Line Offset verwendet.

**Störschall**
: Begriff der DIN 15905-5: alles, was nicht von der Beschallung kommt, zum Beispiel Publikum oder Pyrotechnik.
  Siehe [Publikumslärm]({{< relref "audience-noise" >}}).

**Signatur**
: Jedes Intervall wird digital signiert. So lässt sich nachweisen, dass die Daten nicht verändert wurden.

**Spektrum, Terzband**
: Der Pegel aufgeteilt nach Frequenzen, in Dritteloktaven (Terzen). In den Intervall-Details und der Live Ansicht sichtbar.

**Tagesgrenze**
: Uhrzeit, zu der ein Messtag endet: zwischen Mitternacht und 06:00 Uhr.

**Werteprofil**
: Legt fest, welche Werte eine Messung berechnet (z.B. LAeq 60′, LAFmax 1′) und welche Schwellen gelten. Jeder Wert hat
  bis zu drei Stufen: **Benachrichtigung**, **Warnung** und **Limit**.
  Siehe [Werteprofile]({{< relref "/docs/spl-sense/value-profiles" >}}).

**Wetterschutzfilter**
: Gleicht den Einfluss eines Wetterschutzes auf das Mikrofon aus. Muss zum verwendeten Wetterschutz passen.
