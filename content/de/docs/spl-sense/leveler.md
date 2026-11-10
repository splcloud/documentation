---
title: Leveler
linkTitle: Leveler
weight: 50
description: >-
  Automatische Pegelregelung mit dem SPL Tools L1 oder einem Audioprozessor: Varianten, Modi, Einmessen und Betrieb.
---

Der Leveler hält den Pegel automatisch unter einem Grenzwert. SPL Sense misst mit dem Sensor den Schallpegel, erhält
vom Leveler-Gerät den Pegel des Signals, das es gerade ausgibt (Line-Pegel), und berechnet daraus, um wie viel die
Lautstärke gesenkt werden muss (Gain-Reduktion). Das Leveler-Gerät setzt die Reduktion im Signalweg um.

Der Leveler gehört zur Messung: Jede Messung hat ihre eigenen Leveler-Einstellungen. Du findest sie im Menü
**Messung** › **Leveler Einstellungen**.

## Varianten

| Verbindung | Wann |
|---|---|
| **SPL Tools L1 (USB)** | Der L1 hängt per USB am Computer mit SPL Sense. Standard für neue Messungen. |
| **SPL Tools L1 (Netzwerk)** | Der L1 steht woanders, zum Beispiel im Rack bei der Endstufe, und ist per Ethernet oder WLAN erreichbar. |
| **Externer Audioprozessor (SenseAPI)** | Ein Audioprozessor mit SPL-Sense-Plugin fragt SPL Sense über die [API]({{< relref "/docs/entwickler/sense-api" >}}) ab. |

Für Q-SYS gibt es das Plugin **SPL Sense Leveler**: [herunterladen](https://r.spl.swiss/sense/leveler/plugin).
Füge es in dein Q-SYS-Design ein und trage im Plugin die IP-Adresse des Computers mit SPL Sense, den Port und den
API Key ein. In SPL Sense muss unter **Einstellungen** › **API** der Modus **Nur externer Leveler** oder
**Vollzugriff** eingeschaltet sein, siehe [SPL Sense API]({{< relref "/docs/entwickler/sense-api" >}}). Stimmen die
Angaben, zeigt das Plugin den Zustand und die Messwerte von SPL Sense an.

### SPL Tools L1 über USB

Schliesse den L1 per USB an. In den Leveler-Einstellungen der Messung steht unter **Leveler-Verbindung** dann
**Verbunden** mit Typ, Seriennummer und Firmware.

### SPL Tools L1 über Netzwerk

1. Wähle **SPL Tools L1 (Netzwerk)**.
2. Trage bei **Host** den Namen oder die IP-Adresse des L1 ein, oder klicke auf **Suchen**: SPL Sense sucht dann
   L1-Geräte im lokalen Netzwerk.
3. Trage den **API Key** des L1 ein.
4. Wähle die **Sicherheit**:
   - **HTTP (L1 TLS aus)**: unverschlüsselt, nur in geschützten lokalen Netzwerken
   - **HTTPS, fixiertes Zertifikat**: verschlüsselt mit dem eigenen Zertifikat des L1. Lies den Fingerabdruck mit
     **Vom L1 lesen** und vergleiche ihn mit dem, der auf dem L1 angezeigt wird.
   - **HTTPS, vertrauenswürdige CA**: verschlüsselt mit einem Zertifikat einer anerkannten Stelle
5. Klicke auf **Verbindung testen** und danach auf **Speichern**.

Am einfachsten geht es mit **Vom L1 an USB einrichten**: Steck den L1 einmal per USB an, und SPL Sense übernimmt Host,
API Key, Sicherheit und Fingerabdruck. Hat der L1 noch keinen API Key, erzeugt SPL Sense einen.

Nach mehreren falschen API Keys sperrt der L1 die Verbindung für 30 Sekunden.

### Den L1 selbst einrichten

Ist ein L1 per USB angeschlossen, richtest du ihn unter **Einstellungen** › **Leveler** ein:

- **Geräteinformation**: Typ, Seriennummer, Firmware, MAC-Adressen
- **Ethernet Konfiguration**: automatisch oder **statisch** mit IP-Adresse, Netzmaske und Gateway
- **WiFi Konfiguration**: Netzwerk und Passwort. Der L1 unterstützt nur 2.4-GHz-Netzwerke.
  Der Status zeigt Verbindung und Signalstärke.
- **Netzwerk-API**: Hostname, API Key (leer: Leveling über das Netzwerk aus; mit **Generieren** erzeugst du einen),
  Admin-Passwort für die Weboberfläche des L1 und die Verschlüsselung (**Aus**, **Selbstsigniertes Zertifikat**,
  **Eigenes Zertifikat**)

Grenzwerte und Modus gehören nicht hierher, sondern in die Leveler-Einstellungen der Messung.

## Modi

| Modus | Verhalten |
|---|---|
| **Aus** | Kein Leveling. |
| **Einfacher Leveler** | Regelt immer langsam und gleichmässig. |
| **Leveler mit Panikfunktion** | Wie der einfache Leveler, regelt aber schnell zurück, wenn der Pegel plötzlich deutlich über den Grenzwert steigt. |
| **Leveler mit Panikfunktion und Publikumskompensation** | Zusätzlich erkennt SPL Sense, welcher Anteil des Pegels nicht von der Beschallung kommt (zum Beispiel Publikum), und regelt nur den Anteil der Beschallung. Braucht einen eingemessenen Line Offset. |

Hintergrund zur Publikumskompensation: [Publikumslärm]({{< relref "/docs/grundlagen/publikumslaerm" >}}).

## Grenzwerte

Unter **Limit Werte** trägst du für A, C und Z je einen Grenzwert zwischen 40 und 140 dB ein. Ein leeres Feld heisst:
Diese Gewichtung wird nicht geregelt. Sind mehrere Grenzwerte gesetzt, gilt jeweils die Gewichtung, die die grösste
Reduktion verlangt; sie heisst *dominant*.

Der Leveler regelt auf einen Mittelwert über etwa 10 Sekunden. Die Gain-Reduktion beträgt höchstens 40 dB.

## Line Offset einmessen

Nur für den Modus mit Publikumskompensation. Der Line Offset ist der Unterschied zwischen dem Pegel am Sensor und dem
Line-Pegel, wenn nur die Beschallung spielt. Vor dem Einmessen muss die Messung aktiv und gestoppt sein, der Sensor
verbunden und der Leveler-Modus gespeichert oder angewendet (**Anwenden**).

1. Spiele rosa Rauschen über die **ganze Signalkette** ab, so laut wie während der Veranstaltung. Ist ein DJ-Pult die
   Quelle, speise das Rauschen am DJ-Pult ein.
2. Achte darauf, dass es still ist: kein Publikum, keine Gespräche, keine anderen Quellen.
3. Klicke auf **Line Offset messen**. SPL Sense misst drei Sekunden lang und trägt den Line Offset für A, C und Z ein.
4. Prüfe die **Korrelation**: Sie sollte bei allen Gewichtungen möglichst genau **1.000** betragen. Sonst wiederhole die
   Messung.
5. **Speichern**.

{{% alert title="Wichtig" color="warning" %}}
Nach dem Einmessen darf zwischen dem Leveler-Gerät und den Lautsprechern nichts mehr am Pegel verändert werden:
keine Gain-Änderungen an Endstufen oder Prozessoren, keine Kompressoren oder Limiter in diesem Teil des Signalwegs.
Sonst stimmt der Line Offset nicht mehr, und der Leveler regelt falsch.
{{% /alert %}}

Den Line Offset kannst du auch von Hand ändern. Sei dabei vorsichtig: Schon eine kleine Abweichung führt dazu, dass der
Leveler Publikumslärm ignoriert oder zu stark eingreift.

## Korrelation lesen

Die Korrelation vergleicht den gemessenen Pegel mit dem Pegel, den die Beschallung allein erzeugen sollte.

| Korrelation | Bedeutung |
|---|---|
| etwa 1.000 | Es ist nur die Beschallung zu hören. |
| über 1 | Zusätzliche Geräusche, meist Publikum. |
| unter 1 | Der Sensor ist abgedämpft, oder an der Beschallung wurde nach dem Einmessen etwas verändert. |

## Während der Messung

Läuft die Messung und ist der Leveler aktiv, zeigt die Live-Leiste:

- die aktuelle **Gain-Reduktion**
- die **Korrelation** pro Gewichtung; die dominante ist fett und mit `>` markiert, zum Beispiel `> 0.987 @A`
- den 1-Sekunden-Pegel der dominanten Gewichtung hervorgehoben

Grenzwerte, Modus und Line Offsets kannst du auch während der Messung ändern; sie gelten sofort, ohne dass die
Gain-Reduktion springt. Das Einmessen ist nur bei gestoppter Messung möglich.

Die Tagesgrafik zeigt zusätzlich den Line-Pegel, die Gain-Reduktion und die Korrelation. Mit der Cloud Synchronisierung
gehen diese Daten auch in die SPL Cloud.

### Warnungen

| Meldung | Was tun |
|---|---|
| **Keine Verbindung vom Prozessor bis jetzt** / **seit …** | Verbindung zum L1 oder Audioprozessor prüfen. |
| **Der Leveler ist aufgrund unvollständiger Konfiguration deaktiviert** | Mindestens ein Grenzwert fehlt, im Modus mit Publikumskompensation auch der passende Line Offset. |

### Bypass

Mit **Leveler bypassen** schaltest du die Regelung sofort aus, zum Beispiel bei einem Problem. Achtung: Die Lautstärke
steigt dann um die aktuelle Gain-Reduktion. Bei 15 dB Reduktion wird es also schlagartig 15 dB lauter.

Der Bypass gilt für das ganze Gerät und **bleibt eingeschaltet, bis du ihn mit Leveler aktivieren aufhebst**, auch über
einen Neustart, einen Messungswechsel oder ein Aus- und Einstecken hinweg. Solange er aktiv ist, zeigen Übersicht und
Messungsseite einen Hinweis.

### Stopp und Unterbruch

- **Stopp:** Der Leveler setzt die Gain-Reduktion auf 0 und gibt die Kontrolle ab. SPL Sense warnt beim Stoppen, wenn
  der Leveler gerade reduziert.
- **Unterbrochen** (Sensor weg): Die letzte Gain-Reduktion bleibt bestehen, bis der Sensor wieder Daten liefert.

## Wer was ändern kann

Die Leveler-Einstellungen lassen sich bei jeder offenen Messung ändern, auch ohne Sensor und auch, wenn sie nicht aktiv
ist. Bei einer abgeschlossenen Messung nicht. Aus der SPL Cloud lassen sich Modus, Grenzwerte und Line Offsets per
[Fernsteuerung]({{< relref "/docs/spl-cloud-pro/fernsteuerung" >}}) ändern, nicht aber die Verbindung und das Einmessen.
