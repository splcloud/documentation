---
title: Update
linkTitle: Update
weight: 30
description: >-
  SPL Sense unter Linux aktualisieren: automatisch oder von Hand.
---

## Automatisch

SPL Sense aktualisiert sich unter Linux wie auf den anderen Plattformen selbst: Ist eine neue Version verfügbar,
erscheint auf der Übersicht **Update verfügbar**. Stoppe die Messung und klicke auf **Update** und
**Aktualisieren und neu starten**. Siehe [Installation und Updates]({{< relref "/docs/spl-sense/installation-and-updates#updates" >}}).

Das funktioniert, wenn SPL Sense wie in der [Installation]({{< relref "installation" >}}) beschrieben eingerichtet ist.

## Von Hand

Schlägt das automatische Update fehl, aktualisierst du per
Kommandozeile. Verbinde dich dazu wie bei der [Installation]({{< relref "installation#per-ssh-verbinden" >}}) mit dem
Raspberry Pi. Die [allgemeinen Hinweise]({{< relref "installation#allgemeine-hinweise" >}}) gelten auch hier.

### 1. SPL Sense stoppen

```bash
sudo service splsense stop
```

### 2. Neue Version herunterladen und entpacken

32 Bit:

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

64 Bit:

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm64 -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

### 3. Alte Version ersetzen

```bash
sudo rm -rf /usr/local/splsense
sudo mv splsense /usr/local
sudo chown splsense /usr/local/splsense -R
sudo chgrp splsense /usr/local/splsense -R
```

Die Messdaten liegen in `/opt/splsense-data` und bleiben dabei erhalten.

### 4. Starten und neu starten

```bash
sudo service splsense start
sudo reboot
```
