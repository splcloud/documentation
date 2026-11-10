---
title: V-NISSG und DIN 15905-5
linkTitle: V-NISSG und DIN 15905-5
weight: 5
description: >-
  Die wichtigsten Vorgaben für die Schweiz und Deutschland im Vergleich, und welche Vorlage in SPL Sense dazu passt.
---

SPL Sense bringt Werteprofile und Live-Anzeigen für beide Regelwerke mit. Diese Seite fasst zusammen, was für die
Bedienung wichtig ist. Massgebend sind die Originaldokumente (Links unten).

## Im Vergleich

| | Schweiz: V-NISSG | Deutschland: DIN 15905-5:2022 |
|---|---|---|
| Art | Verordnung des Bundes | Norm (Stand der Technik) |
| Beurteilte Grösse | LAeq über 60 Minuten (Stundenpegel), für jedes beliebige 60-Minuten-Intervall | Beurteilungspegel: LAeq über 30 Minuten, Blöcke ab jeder vollen und halben Stunde |
| Grenzwerte | 93, 96 oder 100 dB(A), je nach gemeldeter Kategorie | 99 dB(A) |
| Spitzen | LAFmax höchstens 125 dB(A) | LCpeak höchstens 135 dB(C) |
| Gilt am | lautesten Ort im Publikum, auf Ohrenhöhe (Ermittlungsort) | Orten mit den höchsten Pegeln im Publikum (maßgebliche Immissionsorte) |
| Messen an anderem Ort | erlaubt, mit vorher bestimmtem Offset | erlaubt (Ersatzimmissionsort), mit Korrekturwerten KA und KC |
| Publikumslärm | zählt zum Pegel | Störschall, wird nicht beurteilt |
| Aufzeichnung | ab 100 dB(A) und mehr als 3 Stunden, LAeq 5′ lückenlos, 6 Monate aufbewahren | fortlaufende Messung ab vor Beginn, Messprotokoll |

## Passende Vorlagen in SPL Sense

| Vorlage | Werte und Schwellen (Benachrichtigung / Warnung / Limit) |
|---|---|
| **VNISSG 93dBA** | LAeq 60′: 91 / 92 / 93 · LAeq 5′: – / 92 / 93 · LAFmax 1′: Limit 125 |
| **VNISSG 96dBA** | LAeq 60′: 94 / 95 / 96 · LAeq 5′: – / 95 / 96 · LAFmax 1′: Limit 125 |
| **VNISSG 100dBA** | LAeq 60′: 98 / 99 / 100 · LAeq 5′: – / 99 / 100 · LAFmax 1′: Limit 125 |
| **DIN 15905-5** | LAeq 30′: – / 95 / 99 · LAeq 5′: – / 95 / 99 · LCFmax 1′: Limit 135 |

Die Werte lassen sich pro Messung anpassen, siehe [Werteprofile]({{< relref "/docs/spl-sense/werteprofile" >}}).

{{% alert title="Hinweise zu DIN 15905-5" color="info" %}}
- SPL Sense rechnet LAeq 30′ als gleitenden Mittelwert über die letzten 30 Minuten. Der Wert zur vollen und zur halben
  Stunde entspricht dem Beurteilungspegel des abgelaufenen Blocks.
- Die Anzeige für das Bedienpersonal soll laut Norm einen LAeq über mindestens 5 Sekunden zeigen, gelb ab 95 dB,
  rot über 99 dB. Die eingebauten Live-Anzeigen **DIN 15905-5** sind so eingestellt.
{{% /alert %}}

{{< offen >}}SPL Sense misst keinen Spitzenpegel LCpeak, die Vorlage überwacht LCFmax 1′. Wie wollen wir das in der Doku
formulieren?{{< /offen >}}

## Originaldokumente

- [Vollzugshilfe V-NISSG, Schall](https://www.bag.admin.ch/dam/de/sd-web/YE91ECm2uBte/V-NISSG_Vollzugshilfe%20Schall_%20DE.pdf),
  Bundesamt für Gesundheit (BAG)
- [Messverfahren zur Ermittlung von Schallpegeln an Veranstaltungen](https://www.bag.admin.ch/dam/de/sd-web/MiPiTdLBjxC8/emfehlungen_messverfahren.pdf),
  Arbeitsgruppe Messverfahren V-NISSG
- [DIN 15905-5:2022-07](https://www.dinmedia.de/de/norm/din-15905-5/352773526), Veranstaltungstechnik – Tontechnik –
  Teil 5: Maßnahmen zum Vermeiden einer Gehörgefährdung des Publikums (kostenpflichtig bei DIN Media)
