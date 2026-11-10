---
title: Organisationen und Rollen
linkTitle: Organisationen und Rollen
weight: 20
description: >-
  Wozu Organisationen dienen und was Besitzer und Mitglieder dürfen.
---

## Wozu Organisationen?

Alles in der SPL Cloud hat einen **Besitzer**: Messungen, Messaufträge und SPL Sense Instanzen. Besitzer ist entweder
eine Person oder eine **Organisation**.

Eine Organisation ist eine Gruppe von Personen, die gemeinsam auf Messungen zugreifen: eine Firma, ein Club, ein
Festival oder eine Behörde. Alle Mitglieder sehen die Messungen der Organisation, und wenn jemand die Firma verlässt,
bleiben die Daten bei der Organisation.

Eine Person kann Mitglied in mehreren Organisationen sein, zum Beispiel als freischaffender Techniker bei mehreren
Firmen. Beim Anlegen eines Messauftrags oder beim Anmelden einer Instanz wählst du, wem sie gehören soll.

## Rollen

| | Besitzer | Mitglied |
|---|---|---|
| Messungen und Messaufträge der Organisation sehen | ✓ | ✓ |
| Messaufträge anlegen, Messungen zuordnen | ✓ | ✓ |
| SPL Sense Instanzen für die Organisation anmelden | ✓ | ✓ |
| Lesezugriff vergeben | ✓ | ✓ |
| Instanzen der Organisation fernsteuern (mit Pro) | ✓ | ✓ |
| Mitglieder hinzufügen, entfernen, Rollen ändern | ✓ | |
| Name, Adresse und Logo der Organisation ändern | ✓ | |
| Zahlungsmethode und Rechnungen verwalten | ✓ | |

Eine Organisation hat immer mindestens einen Besitzer.

Wer nur Daten ansehen soll, zum Beispiel ein Veranstalter oder eine Behörde, wird nicht Mitglied, sondern erhält
[Lesezugriff]({{< relref "read-access" >}}).

## Organisation erstellen

1. **Einstellungen** › **Organisation erstellen**.
2. Gib **Name**, Adresse und **E-Mail-Adresse** ein. Die **Rechnungssprache** bestimmt die Sprache von Rechnungen und
   Zahlungsseiten.
3. **Speichern**. Du bist jetzt Besitzer der Organisation.

## Mitglieder verwalten

Auf der Seite der Organisation:

1. **Mitglied hinzufügen**.
2. Suche die Person über ihre E-Mail-Adresse. Sie muss bereits ein Konto in der SPL Cloud haben.
3. Wähle die **Rolle**: **Besitzer** oder **Mitglied**. **Speichern**.

Ein Klick auf ein Mitglied öffnet es: Rolle ändern oder **Mitglied entfernen**.

## Logo

Das Logo der Organisation erscheint in den PDF-Berichten ihrer Messungen. **Logo hochladen** (Bilddatei bis 5 MB),
**Logo ändern** oder **Logo entfernen**.

## Typische Aufbauten

**Einzelperson:** Eine Technikerin mit eigenem Sensor und Laptop, ohne Organisation. Instanz und Messungen gehören
ihr persönlich. Dem Veranstalter gibt sie Lesezugriff auf die Messung.

**Technikfirma:** Die Firma hat eine Organisation; alle Laptops und Raspberry Pis sind als Instanzen der Organisation
angemeldet. Alle Mitarbeitenden sind Mitglieder und sehen alle Messungen. An einem Festival fasst ein Messauftrag die
Messpunkte zusammen; die Behörde erhält Lesezugriff auf den ganzen Messauftrag, der Betreiber einer Bühne auf seine
Messung.

**Gemietete Geräte:** Wird ein Gerät vermietet und soll es für die Mietdauer der mietenden Firma gehören, wechselst
du den Besitzer der Instanz, siehe [SPL Sense Instanzen]({{< relref "instances#besitzer-wechseln" >}}).
