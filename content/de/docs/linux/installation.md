---
title: Installation
linkTitle: Installation
weight: 20
description: >-
  SPL Sense auf dem Raspberry Pi installieren und als Dienst einrichten, der beim Hochfahren startet.
---

SPL Sense wird über die Kommandozeile installiert, entweder direkt am Raspberry Pi (Programm **Terminal**) oder per SSH
von einem anderen Computer. Mit SSH kannst du die Befehle kopieren und einfügen und vermeidest Tippfehler.

## Per SSH verbinden

Dein Computer muss im selben Netzwerk sein wie der Raspberry Pi.

- **macOS und Linux:** im Terminal `ssh <benutzer>@<ip-adresse>`, zum Beispiel `ssh pi@192.168.10.144`
- **Windows:** im Terminal (PowerShell) ebenfalls `ssh <benutzer>@<ip-adresse>`, oder mit PuTTY: bei **Host Name** die
  IP-Adresse eintragen, **Connection type** auf **SSH**, dann **Open**

Benutzer und Passwort sind die, die du im Raspberry Pi Imager festgelegt hast.

## Allgemeine Hinweise

- Linux unterscheidet Gross- und Kleinschreibung. Übernimm die Befehle genau.
- Ein erfolgreicher Befehl zeigt meist keine Meldung. Erscheint eine Fehlermeldung, lies sie und behebe den Fehler,
  bevor du weitermachst.
- Beim ersten `sudo` fragt der Raspberry Pi nach dem Passwort deines Benutzers.

## 1. Benutzer für SPL Sense anlegen

```bash
sudo useradd splsense -m -d /opt/splsense-data
```

SPL Sense läuft unter diesem eigenen Benutzer und speichert seine Daten in `/opt/splsense-data`.

## 2. SPL Sense herunterladen und entpacken

Für ein **32-Bit**-Betriebssystem:

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

Für ein **64-Bit**-Betriebssystem:

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm64 -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

## 3. Programm an seinen Ort verschieben

```bash
sudo mv splsense /usr/local
sudo chown splsense /usr/local/splsense -R
sudo chgrp splsense /usr/local/splsense -R
```

## 4. Dienst einrichten

Damit SPL Sense beim Hochfahren automatisch startet, richtest du es als Systemdienst ein. Öffne eine neue Datei im
Editor `nano`:

```bash
sudo nano /etc/systemd/system/splsense.service
```

Kopiere diesen Inhalt hinein:

```ini
[Unit]
Description=SPL Sense
After=network-online.target
User=splsense
Group=splsense

[Service]
Type=simple
ExecStart=/usr/local/splsense/SplSense.App.Browser
WorkingDirectory=/usr/local/splsense
Environment="ASPNETCORE_URLS=http://0.0.0.0:8080"
Environment="SPLSENSE_DATA=/opt/splsense-data"

[Install]
WantedBy=multi-user.target
```

Speichern und schliessen: <kbd>Ctrl</kbd>+<kbd>X</kbd>, dann mit <kbd>Y</kbd> bestätigen.

Die Zeile `ASPNETCORE_URLS` legt fest, unter welcher Adresse und welchem Port SPL Sense erreichbar ist: hier `8080`
auf allen Netzwerkschnittstellen. Einen anderen Port trägst du hier ein. Fehlt die Zeile, ist SPL Sense nur auf dem
Raspberry Pi selbst erreichbar (`http://localhost:5000`).

## 5. Dienst aktivieren und starten

```bash
sudo systemctl enable splsense
sudo service splsense start
```

## 6. Neu starten

```bash
sudo reboot
```

## Fertig

SPL Sense startet jetzt bei jedem Hochfahren automatisch und läuft im Hintergrund. Öffne im Browser des Raspberry Pi
oder eines anderen Geräts im Netzwerk die IP-Adresse mit dem Port, zum Beispiel `http://192.168.10.144:8080`.

Weiter geht es wie auf jeder anderen Plattform, zum Beispiel mit dem [Schnellstart]({{< relref "/docs/schnellstart#2-sensor-anschliessen" >}}).
Für den Betrieb als feste Messstation siehe [Betrieb]({{< relref "betrieb" >}}).
