---
title: Hardware und Betriebssystem
linkTitle: Hardware und Betriebssystem
weight: 10
description: >-
  Raspberry Pi beschaffen, Speicherkarte wählen, Betriebssystem installieren und zusammenbauen.
---

## Hardware

Den Raspberry Pi bekommst du im Elektronikhandel. Getestet haben wir:

- Raspberry Pi 4 oder 5, Model B (alle Arbeitsspeicher-Varianten)
- für die Stromversorgung über das Netzwerkkabel: das offizielle Power-over-Ethernet-Modul (PoE HAT) für den
  Raspberry Pi 3B+ und 4B

## Speicherkarte

Die Speicherkarte ist das Teil, das bei vielen Betriebsstunden am ehesten ausfällt. SPL Sense schreibt zwar wenig, aber
eine hochwertige Micro-SD-Karte lohnt sich trotzdem. Gute Erfahrungen haben wir mit «SanDisk Extreme Pro» gemacht.

Die Grösse ist kaum ein Thema: Raspberry Pi OS mit Desktop passt auf 8 GB, und auch viele Messdaten brauchen kaum ein
Gigabyte. Wir empfehlen mindestens 16 GB.

## Betriebssystem installieren

1. Installiere den **Raspberry Pi Imager** auf deinem Computer (erhältlich auf der Website von Raspberry Pi).
2. Schreibe damit **Raspberry Pi OS with Desktop** auf die Speicherkarte.
   - Wähle 32 oder 64 Bit. Für einen Raspberry Pi 5 empfehlen wir 64 Bit. Merke dir die Wahl: Bei der Installation
     von SPL Sense brauchst du das passende Paket.
   - Lege im Imager unter den Einstellungen Benutzername und Passwort fest, und schalte **SSH** ein, wenn du den
     Raspberry Pi von einem anderen Computer aus einrichten willst.

Hast du Erfahrung mit der Kommandozeile und brauchst keinen Bildschirm am Raspberry Pi, genügt auch
**Raspberry Pi OS Lite** ohne Desktop. Diese Anleitung geht von der Desktop-Variante aus.

## Zusammenbauen

1. Baue den Raspberry Pi mit den gewünschten Zusatzmodulen ins Gehäuse und stecke die Speicherkarte ein.
2. Schliesse Bildschirm, Tastatur und Maus an.
3. Schliesse den Strom an (oder das Netzwerkkabel bei PoE). Der Raspberry Pi startet.
4. Richte beim ersten Start eine Netzwerkverbindung ein, per Kabel oder WLAN. SPL Sense wird im nächsten Schritt aus
   dem Internet geladen.
5. Falls nicht schon im Imager eingeschaltet: SSH aktivieren unter Raspberry-Menü › **Einstellungen** ›
   **Raspberry Pi Konfiguration** › **Schnittstellen**.
6. Notiere die IP-Adresse des Raspberry Pi: Sie erscheint, wenn du mit der Maus oben rechts über das Netzwerksymbol
   fährst.
