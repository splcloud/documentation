---
title: Messaufträge mit mehreren Messpunkten
linkTitle: Messaufträge
weight: 40
description: >-
  Mehrere Messungen zu einem Messauftrag zusammenfassen.
---

Ein **Messauftrag** fasst mehrere Messungen zusammen, die zusammengehören: alle Bühnen eines Festivals, die Messpunkte
einer Baustelle oder ein Club mit Haupt- und Nebenraum. Jeder Messpunkt bleibt eine eigene Messung mit eigenem
Sensor, eigenem Werteprofil und eigenen Daten. Der Messauftrag zeigt sie gemeinsam und lässt dich Zugriff, Pro und
Alarme für alle auf einmal einstellen.

Messaufträge gibt es nur in der SPL Cloud; SPL Sense kennt nur Messungen.

## Messauftrag erstellen

1. Auf der Übersicht **Neuer Messauftrag erstellen**.
2. **Name**, zum Beispiel «Openair 2026».
3. **Ort** (optional).
4. **Von** und **Bis**: der Zeitraum. Er bestimmt, wann der Messauftrag ins [Archiv]({{< relref "account-and-interface#archiv" >}})
   wandert, nämlich zehn Tage nach dem Enddatum.
5. **Besitzer**: du persönlich oder eine Organisation. Der Besitzer lässt sich später nicht mehr ändern.
6. **Speichern**.

## Messungen zuweisen

Auf der Seite des Messauftrags im Menü **Messauftrag** › **Messungen verwalten**:

- **Messungen zuweisen**: Wähle Messungen, die noch keinem Messauftrag angehören.
- Eine Messung entfernst du aus dem Messauftrag mit **Entfernen**. Sie wird wieder eigenständig.

Mit **Messungen verwalten beenden** schliesst du die Bearbeitung.

Jede Messung gehört höchstens zu einem Messauftrag.

## Unterschiedliche Besitzer

Messauftrag und Messungen können verschiedenen Besitzern gehören. Typisch: Der Veranstalter führt den Messauftrag
«Openair 2026» in seiner Organisation, eine Technikfirma misst eine Bühne mit ihrem eigenen Laptop. Die Messung gehört
dann der Technikfirma (dem Besitzer der Instanz, die sie hochlädt), der Messauftrag dem Veranstalter.

### Zuweisen

Eine Messung zuweisen kann nur, wer **beides** darf: den Messauftrag verwalten und die Messung verwalten. In der Praxis
ist das eine Person, die in beiden Organisationen Mitglied ist. Die Messung behält beim Zuweisen ihren Besitzer.

### Wer was darf

Im Beispiel ist **A** die Technikfirma (Besitzer der Messung) und **B** der Veranstalter (Besitzer des Messauftrags).

| | A: Besitzer der Messung | B: Besitzer des Messauftrags |
|---|---|---|
| Messung ansehen, Berichte und Exporte | ✓ | ✓ |
| Messung abschliessen, löschen, Bilder hinzufügen | ✓ | |
| Daten hochladen (nur Instanzen von A) | ✓ | |
| [Fernsteuerung]({{< relref "/docs/spl-cloud-pro/remote-control" >}}) der Instanz | ✓ | |
| [Lesezugriff]({{< relref "read-access" >}}) auf diese Messung vergeben | ✓ | |
| Lesezugriff auf den ganzen Messauftrag vergeben (gilt auch für die Messung von A) | | ✓ |
| Messung aus dem Messauftrag entfernen | | ✓ |
| Pro für die Messung aktivieren (A bezahlt) | ✓ | |
| Pro für den Messauftrag aktivieren (B bezahlt, auch für die Messung von A) | | ✓ |
| Kosten und Lizenzdetails des Messauftrags sehen | | ✓ |
| [Alarme]({{< relref "/docs/spl-cloud-pro/alarms" >}}) für den ganzen Messauftrag | | ✓ |
| Alarme nur für diese Messung (überschreibt die des Messauftrags) | ✓ | |
| [Teilbarer Link]({{< relref "/docs/spl-cloud-pro/shared-links" >}}) auf die Messung (braucht Pro auf der Messung) | ✓ | |
| Teilbarer Link auf den Messauftrag (braucht Pro auf dem Messauftrag, zeigt auch die Messung von A) | | ✓ |

«A» und «B» stehen jeweils für die Person bzw. alle Mitglieder der Organisation, der Messung oder Messauftrag gehört.

### Pro bei unterschiedlichen Besitzern

- Aktiviert **B** Pro für den Messauftrag, bezahlt **B** für alle Messungen darin, auch für die von A, in der Währung
  von B.
- Hat **A** Pro schon direkt auf der Messung aktiviert, bleibt es dabei: Diese Messung bezahlt weiterhin A.
- Deaktiviert A die direkte Aktivierung, während der Messauftrag Pro ist, bleibt die Messung über den Messauftrag Pro.

Siehe auch [Preise und Abrechnung]({{< relref "/docs/spl-cloud-pro/pricing-and-billing" >}}).

## Bearbeiten und löschen

**Bearbeiten** ändert Name, Ort und Zeitraum. **Messauftrag löschen** geht nur, wenn ihm keine Messungen mehr
zugewiesen sind.

## Beispiel: Festival mit drei Messpunkten

Eine Technikfirma betreut ein Festival mit Hauptbühne, Zelt und einem Messpunkt beim nächsten Wohnhaus.

1. Drei Laptops mit SPL Sense sind als Instanzen der Organisation der Firma angemeldet.
2. Auf jedem Laptop wird eine Messung mit Cloud Synchronisierung angelegt: «Hauptbühne», «Zelt», «Nachbarschaft».
3. In der Cloud entsteht der Messauftrag «Openair 2026» mit dem Festivalzeitraum, und die drei Messungen werden
   zugewiesen.
4. Die Behörde erhält [Lesezugriff]({{< relref "read-access" >}}) auf den ganzen Messauftrag, der Betreiber des Zelts
   nur auf seine Messung.
5. Optional: [Pro]({{< relref "/docs/spl-cloud-pro" >}}) für den ganzen Messauftrag, zum Beispiel für
   [Alarme]({{< relref "/docs/spl-cloud-pro/alarms" >}}) an die Technik oder einen teilbaren Link für den Veranstalter.
