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
4. **Von** und **Bis**: der Zeitraum. Er bestimmt, wann der Messauftrag ins [Archiv]({{< relref "konto-und-oberflaeche#archiv" >}})
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

Messauftrag und Messung können verschiedenen Besitzern gehören, zum Beispiel wenn eine gemietete Firma eine Bühne misst
und der Veranstalter den Messauftrag führt. Die Messung behält dann ihren Besitzer; der Besitzer des Messauftrags
erhält automatisch Lesezugriff auf sie.

## Bearbeiten und löschen

**Bearbeiten** ändert Name, Ort und Zeitraum. **Messauftrag löschen** geht nur, wenn ihm keine Messungen mehr
zugewiesen sind.

## Beispiel: Festival mit drei Messpunkten

Eine Technikfirma betreut ein Festival mit Hauptbühne, Zelt und einem Messpunkt beim nächsten Wohnhaus.

1. Drei Laptops mit SPL Sense sind als Instanzen der Organisation der Firma angemeldet.
2. Auf jedem Laptop wird eine Messung mit Cloud Synchronisierung angelegt: «Hauptbühne», «Zelt», «Nachbarschaft».
3. In der Cloud entsteht der Messauftrag «Openair 2026» mit dem Festivalzeitraum, und die drei Messungen werden
   zugewiesen.
4. Die Behörde erhält [Lesezugriff]({{< relref "lesezugriff" >}}) auf den ganzen Messauftrag, der Betreiber des Zelts
   nur auf seine Messung.
5. Optional: [Pro]({{< relref "/docs/spl-cloud-pro" >}}) für den ganzen Messauftrag, zum Beispiel für
   [Alarme]({{< relref "/docs/spl-cloud-pro/alarme" >}}) an die Technik oder einen teilbaren Link für den Veranstalter.
