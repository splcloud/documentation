---
title: Publikumslärm
linkTitle: Publikumslärm
weight: 30
description: >-
  Wie Publikum und andere Geräuschquellen die Messung beeinflussen und wie SPL Sense damit umgeht.
---

## Was zählt zum Pegel?

Hier unterscheiden sich die Regelwerke:

- **V-NISSG (Schweiz):** Es zählt **alles, was am Ermittlungsort zu hören ist**: Beschallung, Bühne, Instrumente
  und auch das Publikum (Branchenempfehlung Messverfahren).
- **DIN 15905-5 (Deutschland):** Beurteilt wird nur der Schall der Beschallungsanlage. Publikum und andere
  Quellen sind *Störschall* und sollen das Ergebnis nicht verfälschen. Deshalb empfiehlt die Norm einen Messort, an dem
  das Publikum kaum ins Gewicht fällt.

Die Aufzeichnung von SPL Sense enthält in beiden Fällen den gesamten Pegel am Sensor. Keine Einstellung rechnet das
Publikum aus den gespeicherten Messwerten heraus. Wie stark es mitzählt, bestimmst du also mit der Wahl des Messorts.

Auf den Stundenpegel hat das Publikum bei den meisten Veranstaltungen wenig Einfluss (Vollzugshilfe zur V-NISSG). Kurzzeitig kann es aber deutlich zum
Pegel beitragen: Applaus, Sprechchöre, Mitsingen, laute Bühnenmonitore oder Regen auf einem Zeltdach.

## Was du tun kannst

- **Messort gut wählen:** Steht der Sensor über Kopfhöhe, abseits der Menge und im Direktschall der Beschallung,
  wirkt sich das Publikum weniger aus. Halte dabei genug Abstand zu den Lautsprechern. Siehe [Messpunkt und Offset]({{< relref "messpunkt-und-offset" >}}).
- **Bühnenpegel tief halten:** Laute Monitore und Backline erhöhen den Pegel, ohne dass die Technik am Mischpult viel
  dagegen tun kann.
- **Kommentare setzen:** Halte besondere Momente in der Messung fest, zum Beispiel «Zugabe, Publikum singt mit».
  Kommentare erscheinen in der Tagesgrafik und helfen später beim Erklären von Spitzen.

## Leveler mit Publikumskompensation

Der [Leveler]({{< relref "/docs/spl-sense/leveler" >}}) regelt die Beschallung automatisch herunter, wenn es zu laut wird.
Ohne weitere Information würde er das auch tun, wenn das Publikum laut ist, und so die Musik unnötig leiser machen,
obwohl die Beschallung gar nicht schuld ist.

Im Modus **Leveler mit Panikfunktion und Publikumskompensation** vergleicht SPL Sense den gemessenen Pegel mit dem
Signal, das der Audioprozessor gerade ausgibt. Ist es lauter, als die Beschallung allein erklären kann (Korrelation
über 1), berücksichtigt der Leveler nur den Anteil der Beschallung. Die Messung selbst zeichnet weiterhin den
vollen Pegel auf.

Damit das funktioniert, braucht der Leveler einen genau eingemessenen **Line Offset**. Wie das geht, steht unter
[Leveler]({{< relref "/docs/spl-sense/leveler" >}}).
