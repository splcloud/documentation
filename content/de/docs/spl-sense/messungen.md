---
title: Messungen
linkTitle: Messungen
weight: 20
description: >-
  Lebenszyklus einer Messung: anlegen, aktivieren, messen, bearbeiten, abschliessen, importieren und exportieren.
---

Eine Messung steht für einen Messpunkt. Sie enthält ihre Einstellungen (Werteprofil, Tagesgrenze, Offsets, Leveler)
und alle aufgezeichneten Daten. Eine Messung kann über viele Tage laufen und beliebig oft gestartet und gestoppt
werden.

## Ablauf

```text
anlegen / importieren
        │
        ▼
     offen ──aktivieren──▶ aktiv ──Start──▶ läuft ──Stopp──▶ aktiv (gestoppt)
        ▲                   │                │ Sensor weg   ▲
        │              deaktivieren          ▼              │ Sensor wieder da
        └───────────────────┘           unterbrochen ───────┘
        │
   abschliessen ──▶ abgeschlossen ──wieder öffnen──▶ offen
```

- **Aktivieren:** Es ist immer höchstens eine Messung aktiv; nur in sie zeichnet SPL Sense auf. Wechseln kannst du nur,
  wenn die aktive Messung gestoppt ist.
- **Starten und Stoppen:** **Start** braucht einen verbundenen Sensor. **Stopp** fragt zur Sicherheit nach. Ist der
  Leveler aktiv, weist SPL Sense darauf hin, dass er beim Stoppen ausgeschaltet wird.
- **Unterbrochen:** Wird der Sensor ausgesteckt oder liefert er 20 Sekunden lang keine Werte (zum Beispiel weil der
  Computer im Ruhezustand war), wird die Messung unterbrochen. Liefert der Sensor wieder Daten, läuft sie von selbst
  weiter. Eine unterbrochene Messung beendest du mit **Stopp**.
- **Deaktivieren:** Menü **Messung** › **Deaktivieren**. Die Messung bleibt offen, ist aber nicht mehr aktiv.
- **Neustart von SPL Sense:** Nach einem Neustart ist keine Messung aktiv. Soll eine Messung automatisch weiterlaufen,
  nutze den [autonomen Modus]({{< relref "autonomer-modus" >}}).

## Anlegen

Auf der Übersicht **Neue Messung**:

| Feld | Bedeutung |
|---|---|
| **Name** | Pflichtfeld. Erscheint in der Übersicht, in Berichten und in der SPL Cloud. |
| **Werteprofil** | Eine Vorlage (wird kopiert), **Benutzerdefiniert** (danach öffnet sich der Editor) oder **Keines**. Siehe [Werteprofile]({{< relref "werteprofile" >}}). |
| **Tagesgrenze** | Uhrzeit zwischen 00:00 und 06:00, zu der ein Messtag endet. |
| **Cloud Synchronisierung** | Überträgt die Messung in die SPL Cloud. Nur möglich, wenn SPL Sense in der Cloud angemeldet ist. |

Eine neue Messung ist noch nicht aktiv. Ihr Leveler ist auf **SPL Tools L1 (USB)** und den Modus **Aus** eingestellt.

## Bearbeiten

Menü **Messung** › **Messung bearbeiten**. Möglich, solange die Messung nicht läuft, nicht unterbrochen und nicht
abgeschlossen ist. Eine Messung, die nicht aktiv ist, kannst du auch bearbeiten, während eine andere aufzeichnet.

- **Name**, **Tagesgrenze**
- **Cloud Synchronisierung:** Einschalten lädt alle Daten der Messung hoch, auch die bereits aufgezeichneten.
  Ausschalten stoppt den Upload; was schon in der Cloud ist, bleibt dort.
- **Offsets** für A, C und Z, siehe unten
- **Werteprofil:** mit **Werteprofil bearbeiten** anpassen

Änderst du Tagesgrenze oder Werteprofil, rechnet SPL Sense die Grenzwerte und Messtage neu. Jede Änderung der Offsets
und des Werteprofils erscheint in den Ereignissen.

Die [Leveler-Einstellungen]({{< relref "leveler" >}}) bearbeitest du separat, sie lassen sich auch während der
Messung ändern.

## Offsets

Der Offset rechnet die Werte am Messort auf den lautesten Ort im Publikum um. Wie du ihn bestimmst, steht unter
[Messpunkt und Offset]({{< relref "/docs/grundlagen/messpunkt-und-offset" >}}).

Du hast zwei Wege:

- **Offsets tunen** (Menü **Messung**): mit Live-Werten. Nur bei der aktiven, gestoppten Messung mit verbundenem
  Sensor. Die Tabelle zeigt pro Bewertung den aktuellen Pegel, den höchsten Pegel seit **Max zurücksetzen**, den Offset
  und beide Werte inklusive Offset. Was du hier misst, wird nicht aufgezeichnet.
- **Messung bearbeiten:** Offsets direkt als Zahl eintragen, zum Beispiel aus einer Messung mit einem Handmessgerät.

Ein geänderter Offset gilt ab dem nächsten Start. Bereits aufgezeichnete Daten behalten den Offset, mit dem sie
aufgezeichnet wurden.

## Abschliessen und wieder öffnen

Ist die Veranstaltung vorbei, schliesst du die Messung ab: Menü **Messung** › **Messung abschliessen**. Die Messung
muss gestoppt sein. Danach ist sie gesperrt: Sie lässt sich nicht mehr aktivieren, bearbeiten oder starten, aber
ansehen und exportieren. Ist der autonome Modus auf diese Messung eingestellt, wird er ausgeschaltet.

Eine abgeschlossene Messung öffnest du im Menü mit **Messung wieder öffnen** wieder.

## Löschen

Eine offene Messung löschst du unter **Messung bearbeiten** › **Messung löschen**, eine abgeschlossene im Menü
**Messung**. Gelöscht wird nur auf diesem Computer; was in der SPL Cloud ist, bleibt dort. Wie du die Messung auch in
der Cloud löschst, steht unter [Messungen in der Cloud]({{< relref "/docs/spl-cloud/messungen#löschen" >}}).

## Import und Export

Eine Messung lässt sich als `.splsense`-Datei sichern und auf einem anderen Computer wieder einlesen, mit allen Daten
und Einstellungen.

- **Exportieren:** Schliesse die Messung ab und klicke auf **Messung exportieren**.
- **Importieren:** Auf der Übersicht **Import**, dann die Datei in das Feld ziehen. Gibt es die Messung schon, kannst
  du sie mit **Existierende Messung überschreiben** ersetzen.

Die Werte als Tabelle exportierst du als CSV, siehe [Messdaten auswerten]({{< relref "messdaten-auswerten#berichte-und-exporte" >}}).
