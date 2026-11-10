---
title: Publikumslärm
linkTitle: Publikumslärm
weight: 30
description: >-
  Wie Publikum und andere Geräuschquellen die Messung beeinflussen und wie SPL Sense damit umgeht.
---

## Was zählt zum Pegel?

Für den Grenzwert zählt **alles, was am Ermittlungsort zu hören ist**: Beschallung, Bühne, Instrumente und auch das
Publikum. Die Aufzeichnung von SPL Sense enthält deshalb immer den gesamten Pegel. Kein Filter und keine Einstellung
rechnet das Publikum aus den gespeicherten Messwerten heraus.

Auf den Stundenpegel LAeq 60′ hat das Publikum meist wenig Einfluss. Kurzzeitig kann es aber deutlich zum Pegel
beitragen: Applaus, Sprechchöre, Mitsingen, laute Bühnenmonitore oder Regen auf einem Zeltdach.

## Was du tun kannst

- **Messort gut wählen:** Steht der Sensor über Kopfhöhe und im Direktschall der Beschallung, wirkt sich das Publikum
  weniger aus. Siehe [Messpunkt und Offset]({{< relref "messpunkt-und-offset" >}}).
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
