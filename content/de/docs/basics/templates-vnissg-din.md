---
title: Vorlagen für V-NISSG und DIN 15905-5
linkTitle: Vorlagen V-NISSG / DIN
weight: 5
description: >-
  Welche Werteprofile und Live-Anzeigen SPL Sense für die Schweiz und Deutschland mitbringt.
---

SPL Sense bringt Werteprofile und Live-Anzeigen für die V-NISSG (Schweiz) und die DIN 15905-5 (Deutschland) mit.
Welche Vorgaben für deine Veranstaltung gelten, entnimmst du den Originaldokumenten (unten).

## Werteprofile

| Vorlage | Werte und Schwellen (Benachrichtigung / Warnung / Limit) |
|---|---|
| **VNISSG 93dBA** | LAeq 60′: 91 / 92 / 93 · LAeq 5′: – / 92 / 93 · LAFmax 1′: Limit 125 |
| **VNISSG 96dBA** | LAeq 60′: 94 / 95 / 96 · LAeq 5′: – / 95 / 96 · LAFmax 1′: Limit 125 |
| **VNISSG 100dBA** | LAeq 60′: 98 / 99 / 100 · LAeq 5′: – / 99 / 100 · LAFmax 1′: Limit 125 |
| **DIN 15905-5** | LAeq 30′: – / 95 / 99 · LAeq 5′: – / 95 / 99 · LCFmax 1′: Limit 135 |

Die Werte lassen sich pro Messung anpassen, siehe [Werteprofile]({{< relref "/docs/spl-sense/value-profiles" >}}).
Die passenden Live-Anzeigen heissen gleich wie die Vorlagen, jeweils auch in einer Variante mit Leveler-Anzeige.

SPL Sense rechnet Mittelwerte wie LAeq 30′ oder LAeq 60′ jede Minute gleitend über die letzten 30 bzw. 60 Minuten.
Der Wert zur vollen und zur halben Stunde entspricht dem Mittelwert über die abgelaufene halbe Stunde, also dem
30-Minuten-Block der DIN 15905-5. Bleibt LAeq 30′ jederzeit unter dem Grenzwert, sind damit auch alle Blöcke
eingehalten.

Für den Spitzenpegel verwendet die Vorlage **DIN 15905-5** den Wert **LCFmax 1′**: den höchsten C-bewerteten
Fast-Wert (125 ms) innerhalb einer Minute.

## Originaldokumente

- Bundesamt für Gesundheit (BAG): *Vollzugshilfe zur V-NISSG, Schall* und *Messverfahren zur Ermittlung von
  Schallpegeln an Veranstaltungen*, auf der Website des BAG
- [DIN 15905-5:2022-07](https://doi.org/10.31030/3343057), Veranstaltungstechnik – Tontechnik – Teil 5: Maßnahmen zum
  Vermeiden einer Gehörgefährdung des Publikums durch hohe Schallemissionen elektroakustischer Beschallungstechnik
