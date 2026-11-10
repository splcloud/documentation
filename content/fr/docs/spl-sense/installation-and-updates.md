---
title: Installation et mises à jour
linkTitle: Installation et mises à jour
weight: 10
description: >-
  Windows, macOS et Linux, mises à jour et emplacement des données de SPL Sense.
---

## Plateformes

| Plateforme | Fonctionnement |
|---|---|
| Windows | Application de bureau |
| macOS (Apple silicon et Intel) | Application de bureau |
| Linux sur ARM et ARM64, p. ex. Raspberry Pi | Serveur web : utilisation dans le navigateur, aussi depuis une tablette ou un téléphone sur le même réseau |

Les fonctions sont partout identiques. Seule exception : la [calibration]({{< relref "sensor-and-calibration" >}}) du
capteur n'est possible que dans l'application de bureau.

## Installation

| Plateforme | Téléchargement |
|---|---|
| Windows (64 bits) | [SPLSenseSetup.exe](https://r.spl.swiss/dl/splsense/win-x64/SPLSenseSetup.exe) |
| macOS avec puce Apple (M1 et plus récent) | [SPLSense-osx-arm64-Setup.pkg](https://r.spl.swiss/dl/splsense/osx-arm64/SPLSense-osx-arm64-Setup.pkg) |
| macOS avec processeur Intel | [SPLSense-osx-x64-Setup.pkg](https://r.spl.swiss/dl/splsense/osx-x64/SPLSense-osx-x64-Setup.pkg) |
| Linux (Raspberry Pi) | voir [SPL Sense pour Linux]({{< relref "/docs/linux" >}}) |

Ouvre le fichier téléchargé et suis le programme d'installation. Pour savoir quel Mac tu as : menu Apple ›
**À propos de ce Mac** : « Puce » signifie puce Apple, « Processeur » signifie Intel.

## Premier démarrage

Au premier démarrage, SPL Sense affiche un avis sur la protection des données. **Accepter et continuer** permet de
poursuivre, **Fermer l'application** ferme SPL Sense.

## Mises à jour

SPL Sense vérifie lui-même si une nouvelle version est disponible. Si c'est le cas, l'avis **Mise à jour disponible**
apparaît dans le tableau de bord avec les boutons **Mise à jour** et **Rappelez-moi plus tard**.

1. Arrête une mesure en cours. Aucune mise à jour ne peut être installée pendant une mesure.
2. Clique sur **Mise à jour**, puis sur **Mise à jour et redémarrage**.
3. SPL Sense télécharge la nouvelle version, l'installe et redémarre.

Si SPL Sense ne redémarre pas tout seul après la mise à jour, lance-le manuellement. Après un redémarrage, aucune mesure
n'est active, sauf si le [mode autonome]({{< relref "autonomous-mode" >}}) est activé.

La version actuelle et l'historique des versions se trouvent sous **Paramètres** › **A propos de**.

## Emplacement des données

SPL Sense enregistre toutes les mesures localement sur l'ordinateur :

| Plateforme | Dossier |
|---|---|
| Windows | `%AppData%\SPLSense` |
| macOS | `~/Library/SPLSense` |
| Linux | `~/.SPLSense` |

Sauvegarde régulièrement ce dossier ou active la [liaison cloud]({{< relref "settings#spl-cloud" >}}) pour tes
mesures. Les mesures individuelles se sauvegardent sous forme de fichier `.splsense`, voir
[Importation et exportation]({{< relref "measurements#importation-et-exportation" >}}).
