---
title: Matériel et système d'exploitation
linkTitle: Matériel et système d'exploitation
weight: 10
description: >-
  Se procurer un Raspberry Pi, choisir une carte mémoire, installer le système d'exploitation et assembler.
---

## Matériel

Vous trouvez le Raspberry Pi dans le commerce électronique. Nous avons testé :

- Raspberry Pi 4 ou 5, Model B (toutes les variantes de mémoire)
- pour l'alimentation par le câble réseau : le module Power-over-Ethernet officiel (PoE HAT) pour les Raspberry Pi 3B+
  et 4B

## Carte mémoire

La carte mémoire est la pièce la plus susceptible de tomber en panne après de nombreuses heures de fonctionnement.
SPL Sense écrit peu, mais une carte micro SD de qualité en vaut tout de même la peine. Nous avons eu de bonnes
expériences avec la « SanDisk Extreme Pro ».

La taille n'est guère un problème : Raspberry Pi OS avec bureau tient sur 8 Go, et même beaucoup de données de mesure
occupent à peine un gigaoctet. Nous recommandons au moins 16 Go.

## Installer le système d'exploitation

1. Installez **Raspberry Pi Imager** sur votre ordinateur (disponible sur le site web de Raspberry Pi).
2. Écrivez avec lui **Raspberry Pi OS with Desktop** sur la carte mémoire.
   - Choisissez 32 ou 64 bits. Pour un Raspberry Pi 5, nous recommandons 64 bits. Notez votre choix : vous aurez besoin
     du paquet correspondant lors de l'installation de SPL Sense.
   - Dans les paramètres de l'Imager, définissez un nom d'utilisateur et un mot de passe, et activez **SSH** si vous
     voulez configurer le Raspberry Pi depuis un autre ordinateur.

Si vous avez l'habitude de la ligne de commande et n'avez pas besoin d'écran sur le Raspberry Pi,
**Raspberry Pi OS Lite** sans bureau suffit. Ce guide part de la variante avec bureau.

## Assembler

1. Montez le Raspberry Pi avec les modules souhaités dans le boîtier et insérez la carte mémoire.
2. Branchez l'écran, le clavier et la souris.
3. Branchez l'alimentation (ou le câble réseau en PoE). Le Raspberry Pi démarre.
4. Au premier démarrage, configurez une connexion réseau, par câble ou Wi-Fi. SPL Sense sera téléchargé depuis Internet
   à l'étape suivante.
5. Si ce n'est pas déjà fait dans l'Imager : activez SSH sous menu Raspberry › **Préférences** ›
   **Configuration du Raspberry Pi** › **Interfaces**.
6. Notez l'adresse IP du Raspberry Pi : elle apparaît lorsque vous passez la souris sur l'icône réseau en haut à droite.
