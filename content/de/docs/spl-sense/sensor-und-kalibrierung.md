---
title: Sensor und Kalibrierung
linkTitle: Sensor und Kalibrierung
weight: 60
description: >-
  Sensorstatus, Wetterschutzfilter und Kalibrierung des Sensors.
---

## Sensorinformationen

Unter **Einstellungen** › **Sensor Informationen** (oder mit einem Klick auf den Sensor auf der Übersicht) siehst du:

- **Geräteinformation**: Seriennummer, Hardware Revision, MCU ID, Firmware Version, Qualitätsprüfung
- **Versorgungsspannung** und **MCU Temperatur**, mit **Messwerte aktualisieren** neu abgefragt
- **Kalibrierung**: Datum, von wem, gültig bis
- **Wetterschutz**: der eingestellte Kompensationsfilter

Es ist immer genau ein Sensor aktiv. Steckst du während einer Messung einen anderen Sensor ein, misst SPL Sense mit
diesem weiter; die betroffene Minute wird in den Daten markiert.

## Kalibrierstatus

| Anzeige | Bedeutung |
|---|---|
| **Kalibriert** | Die Kalibrierung ist gültig. |
| **Kalibrierung verfallen** | Die Kalibrierung ist abgelaufen. Du kannst messen, aber die Daten werden markiert. |
| **Kalibrierung ungültig** | Der Sensor hat keine gültige Kalibrierung. |

Ist die Kalibrierung verfallen oder ungültig, fragt SPL Sense beim Start der Messung nach (**Trotzdem starten**).
Startet die Messung über den autonomen Modus, die API oder die Fernsteuerung, fragt SPL Sense nicht.

## Wetterschutzfilter

Ein Wetterschutz über dem Mikrofon verändert den Frequenzgang ein wenig. Der Kompensationsfilter gleicht das aus. Er
muss zum verwendeten Wetterschutz passen:

- **Filter für SPL Tools W1 aktivieren** für den Wetterschutz SPL Tools W1
- **Filter für Wetterschutz V1 aktivieren** für den älteren Wetterschutz V1
- **Filter deaktivieren** ohne Wetterschutz

Der Filter wird im Sensor gespeichert und gilt, bis du ihn änderst, auch für andere Messungen und auf anderen Computern.
Ändern kannst du ihn nur, wenn keine Messung läuft. Ist er eingeschaltet, zeigt die Übersicht einen Hinweis, und die
Messdaten werden markiert.

## Sensor kalibrieren

Mit einer Berechtigung als Kalibrierer kannst du Sensoren selbst kalibrieren. Du brauchst:

- SPL Sense für Windows oder macOS (im Webserver-Betrieb nicht verfügbar)
- Internet
- einen Schallkalibrator mit 94 oder 114 dB
- ein Konto als Kalibrierer und ein Kalibrierungszertifikat deiner Organisation

### Als Kalibrierer registrieren

Auf der Sensorseite **Kalibrieren** › **Anmelden zum Kalibrieren** › **Als Kalibrierer registrieren**. Du beschreibst
deine Kalibrierausrüstung; SPL Tools prüft die Anfrage und informiert dich per E-Mail.

{{< offen >}}Ablauf der Registrierung als Kalibrierer und Bezug des Kalibrierungszertifikats beschreiben.{{< /offen >}}

### Ablauf

Die Messung muss gestoppt und der Sensor verbunden sein.

1. Sensorseite › **Kalibrieren** › **Anmelden**. SPL Sense zeigt, als wer du angemeldet bist, und die aktuelle
   Kalibrierung.
2. Setze den eingeschalteten Kalibrator auf den Sensor und warte, bis der Pegel stabil ist.
3. Klicke auf **94dB messen** bzw. **114dB messen**, passend zu deinem Kalibrator.
4. Prüfe das **Messergebnis**:
   - **Messabweichung**: Schwankung während der Messung
   - **Abweichung der vorherigen Kalibrierung**: wie weit der Sensor seit der letzten Kalibrierung abweicht

   Deuten die Werte darauf hin, dass der Sensor driftet, warnt SPL Sense. Kalibriere dann nochmals und prüfe den Sensor
   auf mechanische Schäden; im Zweifel sende ihn zur Kontrolle ein.
5. Wähle die **Signierende Organisation** und das **Zertifikat**, ergänze **Kalibriert für** und **Kalibriergerät**.
6. Klicke auf **Kalibrierung signieren und speichern**.

Die Kalibrierung wird digital signiert und im Sensor gespeichert. Ab jetzt sind die Messdaten mit der neuen Kalibrierung
signiert.

Ein Sensor ohne bisherige Kalibrierung kann nicht selbst kalibriert werden. Wende dich in diesem Fall an SPL Tools.
