---
title: Installation
linkTitle: Installation
weight: 20
description: >-
  Installer SPL Sense sur le Raspberry Pi et le configurer comme service qui démarre au boot.
---

SPL Sense s'installe en ligne de commande, soit directement sur le Raspberry Pi (programme **Terminal**), soit par SSH
depuis un autre ordinateur. Avec SSH, vous pouvez copier-coller les commandes et éviter les fautes de frappe.

## Se connecter par SSH

Votre ordinateur doit être dans le même réseau que le Raspberry Pi.

- **macOS et Linux :** dans le terminal `ssh <utilisateur>@<adresse-ip>`, par exemple `ssh pi@192.168.10.144`
- **Windows :** dans le terminal (PowerShell) également `ssh <utilisateur>@<adresse-ip>`, ou avec PuTTY : saisissez
  l'adresse IP sous **Host Name**, réglez **Connection type** sur **SSH**, puis **Open**

L'utilisateur et le mot de passe sont ceux que vous avez définis dans Raspberry Pi Imager.

## Remarques générales

- Linux distingue les majuscules et les minuscules. Reprenez les commandes exactement.
- Une commande réussie n'affiche généralement aucun message. Si un message d'erreur apparaît, lisez-le et corrigez
  l'erreur avant de continuer.
- Au premier `sudo`, le Raspberry Pi demande le mot de passe de votre utilisateur.

## 1. Créer un utilisateur pour SPL Sense

```bash
sudo useradd splsense -m -d /opt/splsense-data
```

SPL Sense s'exécute sous cet utilisateur dédié et enregistre ses données dans `/opt/splsense-data`.

## 2. Télécharger et décompresser SPL Sense

Pour un système d'exploitation **32 bits** :

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

Pour un système d'exploitation **64 bits** :

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm64 -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

## 3. Déplacer le programme à sa place

```bash
sudo mv splsense /usr/local
sudo chown splsense /usr/local/splsense -R
sudo chgrp splsense /usr/local/splsense -R
```

## 4. Configurer le service

Pour que SPL Sense démarre automatiquement au boot, configurez-le comme service système. Ouvrez un nouveau fichier dans
l'éditeur `nano` :

```bash
sudo nano /etc/systemd/system/splsense.service
```

Copiez-y ce contenu :

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

Enregistrer et fermer : <kbd>Ctrl</kbd>+<kbd>X</kbd>, puis confirmer avec <kbd>Y</kbd>.

La ligne `ASPNETCORE_URLS` définit l'adresse et le port auxquels SPL Sense est accessible : ici `8080` sur toutes les
interfaces réseau. Indiquez ici un autre port si nécessaire. Sans cette ligne, SPL Sense n'est accessible que sur le
Raspberry Pi lui-même (`http://localhost:5000`).

## 5. Activer et démarrer le service

```bash
sudo systemctl enable splsense
sudo service splsense start
```

## 6. Redémarrer

```bash
sudo reboot
```

## Terminé

SPL Sense démarre désormais automatiquement à chaque boot et tourne en arrière-plan. Dans le navigateur du Raspberry Pi
ou d'un autre appareil du réseau, ouvrez l'adresse IP avec le port, par exemple `http://192.168.10.144:8080`.

La suite se déroule comme sur toute autre plateforme, par exemple avec le
[démarrage rapide]({{< relref "/docs/quick-start#2-brancher-le-capteur" >}}). Pour l'exploitation comme station de
mesure fixe, voir [Exploitation]({{< relref "operation" >}}).
