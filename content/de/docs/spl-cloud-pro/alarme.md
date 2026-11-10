---
title: Alarme
linkTitle: Alarme
weight: 40
description: >-
  Benachrichtigung per E-Mail und SMS, wenn eine Messung einen Grenzwert überschreitet oder keine Daten mehr sendet.
---

Die SPL Cloud prüft jede Minute die laufenden Pro-Messungen und benachrichtigt die eingetragenen Empfänger:

- **Überschreitung**: Ein Wert liegt über einer Schwelle des Werteprofils der Messung.
- **Ausfall**: Eine laufende Messung sendet keine Daten mehr, zum Beispiel weil Strom oder Internet weg ist.

Alarme laufen nur für Messungen mit Pro. Andere Messungen im selben Bereich werden übersprungen.

## Wo du Alarme einstellst

- Für einen ganzen **Messauftrag**: Menü **Messauftrag** › **Alarme**. Die Einstellung gilt für alle seine Messungen.
- Für eine **einzelne Messung**: Menü **Messung** › **Alarmkonfiguration**. Für eine eigenständige Messung ist das der
  einzige Weg. Gehört die Messung zu einem Messauftrag, überschreibt diese Einstellung die des Messauftrags für diese
  eine Messung.

Oben auf der Seite wählst du den Bereich: **Ganzer Messauftrag** oder **Einzelne Messung**. Die Liste darunter zeigt
die betroffenen Messungen und weist auf Messungen ohne Pro oder ohne Grenzwerte hin.

## Einstellungen

Schalte zuerst **Alarme für diesen Bereich aktivieren** ein.

### Überschreitung

- **Auslösen bei Stufe**: welche Schwellen des Werteprofils einen Alarm auslösen: **Benachrichtigung**, **Warnung**,
  **Limit**. Die Schwellen selbst kommen aus dem Werteprofil jeder Messung. Ohne Schwellen im Werteprofil gibt es keine
  Überschreitungsalarme.
- **Andauernd während**: so viele Minuten muss der Wert über der Schwelle bleiben, bevor ein Alarm ausgelöst wird.
  Das filtert kurze Spitzen heraus. Standard: 15 Minuten; üblich sind 5 bis 15 Minuten.

### Ausfall

- **Stille vor dem Alarm**: so viele Minuten dürfen Daten fehlen, bevor ein Ausfallalarm ausgelöst wird. Standard:
  30 Minuten. Geräte mit Mobilfunk laden oft schubweise hoch; wähle die Zeit dann nicht zu kurz.

### Ende eines Alarms

**Auch benachrichtigen, wenn ein Alarm endet**: Eine zweite Meldung, sobald der Pegel wieder normal ist oder wieder
Daten kommen. Standardmässig aus, weil es die Anzahl Nachrichten etwa verdoppelt. Lass es aus, wenn Empfänger SMS
bekommen.

## Empfänger

Empfänger brauchen kein Konto in der SPL Cloud. Mit **Empfänger hinzufügen** trägst du pro Person ein:

- **E-Mail** und/oder **Telefon**. Für SMS braucht es eine Telefonnummer. Die nationale Schreibweise geht auch
  (079 …); sie wird ins internationale Format umgewandelt.
- **Erhält**: **Alle Alarme**, **Nur Ausfälle** oder **Nur Grenzwertalarme**. Wer ein Gerät wieder online bringt,
  braucht selten Überschreitungen, und wer die Pegel überwacht, selten Ausfälle.

Schneller geht es mit **Mich hinzufügen** und **Organisationsmitglieder hinzufügen**: Name, E-Mail und, falls im Profil
hinterlegt, die Telefonnummer werden übernommen.

## Wann benachrichtigt wird

- **Überschreitung**: wenn die erste Stufe erreicht ist und erneut bei jedem Wechsel der Stufe (zum Beispiel von
  Warnung zu Limit oder zurück). Solange die Stufe gleich bleibt, kommt keine weitere Meldung.
- **Ausfall**: einmal, wenn der Ausfall erkannt wird.
- Mehrere Alarme in derselben Minute werden zu einer Nachricht zusammengefasst.
- Die Nachricht enthält einen Link zur Messung bzw. zum Messauftrag in der SPL Cloud.
