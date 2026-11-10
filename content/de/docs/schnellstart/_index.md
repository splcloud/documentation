---
title: Schnellstart
linkTitle: Schnellstart
weight: 10
description: >-
  In wenigen Schritten zur ersten Messung: SPL Sense installieren, Messung anlegen, Offset einstellen, messen,
  in der SPL Cloud archivieren und einen PDF-Bericht herunterladen.
aliases:
  - /docs/quickstartsense/
  - /docs/quickstartcloud/
---

Diese Anleitung führt dich Schritt für Schritt zu deiner ersten Messung. Du brauchst kein Vorwissen.

**Das brauchst du:**

- einen Computer mit Windows oder macOS
- einen Sensor von SPL Tools mit USB-Kabel
- für die SPL Cloud (Schritt 8): Internet und eine E-Mail-Adresse

## 1. SPL Sense installieren

1. Lade SPL Sense für dein Betriebssystem herunter:
   - [Windows](https://r.spl.swiss/dl/splsense/win-x64/SPLSenseSetup.exe)
   - [macOS mit Apple-Chip (M1 und neuer)](https://r.spl.swiss/dl/splsense/osx-arm64/SPLSense-osx-arm64-Setup.pkg)
   - [macOS mit Intel-Prozessor](https://r.spl.swiss/dl/splsense/osx-x64/SPLSense-osx-x64-Setup.pkg)
2. Öffne die heruntergeladene Datei und folge dem Installationsprogramm.
3. Starte SPL Sense. Beim ersten Start erscheint ein Hinweis. Lies ihn und klicke auf **Akzeptieren und Fortfahren**.

SPL Sense aktualisiert sich selbst: Ist eine neue Version verfügbar, erscheint ein Hinweis.

## 2. Sensor anschliessen

Schliesse den Sensor per USB an. Pro Computer darf nur ein Sensor angeschlossen sein. Oben rechts in der Statusleiste siehst du, ob SPL Sense den Sensor erkennt.

Zeigt die Statusleiste **Kein Sensor verbunden**, steck das Kabel aus und wieder ein.

{{% alert title="Kalibrierung" color="info" %}}
Ist die Kalibrierung des Sensors abgelaufen, warnt dich SPL Sense beim Start der Messung. Du kannst trotzdem messen,
die Messwerte werden dann aber markiert. Mehr dazu unter [Sensor und Kalibrierung]({{< relref "/docs/spl-sense/sensor-und-kalibrierung" >}}).
{{% /alert %}}

## 3. Messung anlegen

Eine **Messung** steht für einen Messpunkt, zum Beispiel «Hauptbühne Openair 2026». Sie kann über viele Tage laufen.

1. Klicke in der Übersicht auf **Neue Messung**.
2. Fülle die Felder aus:
   - **Name**: So erscheint die Messung in der Übersicht und im Bericht.
   - **Werteprofil**: Legt fest, welche Werte berechnet werden und welche Grenzwerte gelten. Für Veranstaltungen in der
     Schweiz wählst du die Vorlage, die zu deiner gemeldeten Kategorie passt: **VNISSG 93dBA**, **VNISSG 96dBA** oder
     **VNISSG 100dBA**. In Deutschland wählst du **DIN 15905-5**.
     Was die Vorlagen enthalten: [Vorlagen für V-NISSG und DIN 15905-5]({{< relref "/docs/grundlagen/vorschriften" >}}).
   - **Tagesgrenze**: Wann ein Messtag endet. Wähle eine Zeit etwa zwei Stunden nach dem Ende der Veranstaltung,
     spätestens 06:00 Uhr. So landet eine Party, die bis 03:00 Uhr dauert, in *einem* Tag und nicht in zwei.
   - **Cloud Synchronisierung**: Lass das vorerst aus. Du schaltest es ein, sobald SPL Sense mit der Cloud verbunden ist
     (Schritt 8).
3. Klicke auf **Messung erstellen**.

## 4. Messung aktivieren

Es kann immer nur eine Messung aktiv sein. Die aktive Messung ist die, in die SPL Sense aufzeichnet.

Öffne die Messung und klicke auf **Messung aktivieren**.

## 5. Offset einstellen

Der Grenzwert gilt am **lautesten Ort im Publikum**, auf Ohrenhöhe. Dort kannst du den Sensor aber meistens nicht
hinstellen. Deshalb misst du an einem anderen Ort und gleichst den Unterschied mit dem **Offset** aus.
Hintergründe findest du unter [Messpunkt und Offset]({{< relref "/docs/grundlagen/messpunkt-und-offset" >}}).

So stellst du den Offset ein (die Messung muss aktiv und gestoppt sein, der Sensor angeschlossen):

1. Öffne im Menü **Messung** den Punkt **Offsets tunen**.
2. Spiele rosa Rauschen (Pink Noise) über die Beschallung ab, so laut wie während der Veranstaltung.
3. Klicke auf **Max zurücksetzen**.
4. Geh mit dem Sensor durch den Publikumsbereich, auch nach vorne und an die Seiten.
   SPL Sense merkt sich den höchsten Wert.
5. Stell den Sensor an seinen Messort, zum Beispiel ans Mischpult.
6. Stell den **Offset** so ein, dass **Level inkl. offset** gleich hoch ist wie der gespeicherte **Max**-Wert.
7. Klicke auf **Speichern**.

Während des Offset-Tunens wird nichts aufgezeichnet. Kennst du den Offset schon, zum Beispiel von einem Handmessgerät,
trägst du ihn direkt unter **Messung bearbeiten** ein.

## 6. Messen

1. Klicke auf **Start**. SPL Sense zeichnet jetzt auf. Die ersten Werte erscheinen nach der ersten vollen Minute.
2. Unter dem Seitentitel siehst du laufend die aktuellen Pegel. Die Grafik zeigt den Verlauf des Tages.
3. Für einen grossen, gut lesbaren Bildschirm, zum Beispiel für den DJ oder die Technik, klicke auf **Live Ansicht**.
4. Ist die Veranstaltung vorbei, klicke auf **Stopp** und bestätige.

{{< bild id="sense-messung-laeuft" >}}

Wird der Sensor während der Messung ausgesteckt, zeigt SPL Sense **Unterbrochen**. Steckst du ihn wieder ein, läuft die
Messung von selbst weiter.

## 7. Messung bearbeiten

Name, Tagesgrenze, Offsets und Werteprofil kannst du später ändern, solange die Messung gestoppt ist:
Menü **Messung** › **Messung bearbeiten**, ändern und **Speichern**.

Änderst du das Werteprofil oder die Tagesgrenze, rechnet SPL Sense die Grenzwerte und Messtage neu.

## 8. Mit der SPL Cloud verbinden

In der SPL Cloud sind deine Messungen sicher archiviert. Du siehst sie auch von unterwegs und kannst sie mit anderen
teilen. Die Grundfunktionen sind kostenlos.

**Konto erstellen** (einmalig):

1. Öffne [spl.cloud](https://spl.cloud) im Browser. Die Anmeldeseite ist immer auf Englisch.
2. Klicke auf **Sign up now**, gib deine E-Mail-Adresse ein und klicke auf **Send verification code**.
3. Gib den Code ein, den du per E-Mail erhältst, und bestätige.
4. Ergänze Passwort und Namen und schliesse mit **Create** ab.

**SPL Sense anmelden** (einmal pro Computer):

1. In SPL Sense: **Einstellungen** › **Cloud** › **Instanz anmelden**.
2. Klicke auf den angezeigten Link oder scanne den QR-Code mit dem Handy. Der Code ist nur kurze Zeit gültig;
   ist er abgelaufen, fordere mit **Neuer Anmeldecode abfragen** einen neuen an.
3. In der SPL Cloud: Wähle bei **Besitzer**, wem dieser Computer gehört: dir persönlich oder einer Organisation, in der du
   Mitglied bist. Klicke auf **Speichern**.
4. In SPL Sense steht jetzt **Instanz ist registriert**.

**Messung in die Cloud übertragen:**

1. Öffne die Messung in SPL Sense, Menü **Messung** › **Messung bearbeiten**.
2. Schalte **Cloud Synchronisierung** ein und speichere.

SPL Sense lädt jetzt alle Daten der Messung hoch, auch die bereits aufgezeichneten. Ist das Internet einmal weg, misst
SPL Sense weiter und holt den Upload später nach. In der SPL Cloud erscheint die Messung in der **Übersicht** unter
den eigenständigen Messungen.

## 9. PDF-Bericht herunterladen

Für jeden Messtag gibt es in SPL Sense einen Tagesbericht als PDF.

1. Öffne die Messung in SPL Sense.
2. Wähle den gewünschten Tag.
3. Klicke beim Tag auf **PDF**.

Mit **CSV** daneben exportierst du die Werte des Tages, zum Beispiel für Excel.

In der SPL Cloud gibt es den Tagesbericht mit [SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/berichte-und-bilder" >}}).

## Und jetzt?

- Ist die Veranstaltung ganz vorbei, schliesse die Messung ab: Menü **Messung** › **Messung abschliessen**.
  Danach lässt sie sich nicht mehr verändern. Bei Bedarf öffnest du sie wieder.
- [Messpunkt und Offset]({{< relref "/docs/grundlagen/messpunkt-und-offset" >}}): richtig messen nach V-NISSG und DIN 15905-5
- [Lesezugriff]({{< relref "/docs/spl-cloud/lesezugriff" >}}): Veranstalter oder Behörde Einblick geben
- [Leveler]({{< relref "/docs/spl-sense/leveler" >}}): Pegel automatisch unter dem Grenzwert halten
