---
title: Mise à jour
linkTitle: Mise à jour
weight: 30
description: >-
  Mettre à jour SPL Sense sous Linux : automatiquement ou manuellement.
---

## Automatiquement

Sous Linux, SPL Sense se met à jour lui-même comme sur les autres plateformes : lorsqu'une nouvelle version est
disponible, **Mise à jour disponible** apparaît dans la vue d'ensemble. Arrêtez la mesure et cliquez sur **Mise à jour**
puis **Mise à jour et redémarrage**. Voir
[Installation et mises à jour]({{< relref "/docs/spl-sense/installation-and-updates#mises-à-jour" >}}).

Cela fonctionne si SPL Sense est configuré comme décrit dans l'[installation]({{< relref "installation" >}}).

## Manuellement

Si la mise à jour automatique échoue, mettez à jour en ligne de commande. Connectez-vous au Raspberry Pi comme lors de
l'[installation]({{< relref "installation#se-connecter-par-ssh" >}}). Les
[remarques générales]({{< relref "installation#remarques-générales" >}}) s'appliquent ici aussi.

### 1. Arrêter SPL Sense

```bash
sudo service splsense stop
```

### 2. Télécharger et décompresser la nouvelle version

32 bits :

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

64 bits :

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm64 -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

### 3. Remplacer l'ancienne version

```bash
sudo rm -rf /usr/local/splsense
sudo mv splsense /usr/local
sudo chown splsense /usr/local/splsense -R
sudo chgrp splsense /usr/local/splsense -R
```

Les données de mesure se trouvent dans `/opt/splsense-data` et sont conservées.

### 4. Démarrer et redémarrer

```bash
sudo service splsense start
sudo reboot
```
