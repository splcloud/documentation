---
title: Exploitation
linkTitle: Exploitation
weight: 40
description: >-
  Accès réseau, affichage kiosque et exploitation comme station de mesure fixe sans surveillance.
---

## Adresses

Avec le port `8080` de l'[installation]({{< relref "installation" >}}) :

| | Adresse |
|---|---|
| Interface web | `http://<adresse-ip>:8080` |
| Vue live | `http://<adresse-ip>:8080/measurement/live` |
| Vue live en mode kiosque | `http://<adresse-ip>:8080/measurement/live?kiosk` |
| [API SPL Sense]({{< relref "/docs/developers/sense-api" >}}) | `http://<adresse-ip>:8080/api` |

Sur le Raspberry Pi lui-même, tu peux utiliser `localhost` au lieu de l'adresse IP.

## Affichage kiosque

Pour un affichage fixe, par exemple un écran à la cabine du DJ, le navigateur ouvre la vue live directement en
mode kiosque, par exemple avec Chromium :

```bash
chromium-browser --kiosk "http://localhost:8080/measurement/live?kiosk"
```

Le mode kiosque n'affiche que les widgets et une fine barre d'état, et s'adapte à la taille de l'écran. Voir
[Vue live et kiosque]({{< relref "/docs/spl-sense/live-screen#plein-écran-et-kiosque" >}}).

## Station de mesure fixe sans surveillance

1. Active le [mode autonome]({{< relref "/docs/spl-sense/autonomous-mode" >}}) : la mesure démarre d'elle-même après
   chaque redémarrage, par exemple après une panne de courant.
2. Définis un [code PIN opérateur]({{< relref "/docs/spl-sense/settings#code-pin-opérateur" >}}) : sans le code
   PIN, seule la vue live est accessible, y compris dans le navigateur d'autres appareils.
3. Connecte-toi à [SPL Cloud]({{< relref "/docs/spl-sense/settings#spl-cloud" >}}) et active la liaison cloud.
4. En option avec Pro : [alarmes]({{< relref "/docs/spl-cloud-pro/alarms" >}}) en cas de panne et
   [commande à distance]({{< relref "/docs/spl-cloud-pro/remote-control" >}}).

## Limitation

Tu ne peux pas calibrer le capteur sous Linux. Pour cela, il te faut SPL Sense pour Windows ou macOS.
