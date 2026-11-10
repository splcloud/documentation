---
title: Mode autonome
linkTitle: Mode autonome
weight: 70
description: >-
  SPL Sense démarre automatiquement une mesure dès qu'il est lancé.
---

En mode autonome, SPL Sense active et démarre de lui-même une mesure donnée dès que SPL Sense démarre. Ce mode est prévu
pour les systèmes installés à demeure, par exemple dans un club ou sur un Raspberry Pi : après une panne de courant ou un
redémarrage, le système continue de mesurer sans intervention.

## Configuration

1. **Paramètres** › **Mode autonome**.
2. Réglez l'exécution automatique d'une mesure sur **Mise en marche**.
3. Choisissez la **Mesure**. Seules les mesures ouvertes sont proposées.
4. **Sauvegarder**. Si SPL Sense est arrêté et qu'un capteur est connecté, SPL Sense propose de démarrer la mesure
   immédiatement.

## Comportement

- **Au démarrage de SPL Sense :** la mesure choisie est activée et démarrée. Si aucun capteur n'est connecté, la mesure
  est **Interrompu** et commence à enregistrer dès que le capteur est là.
- **Arrêt :** vous pouvez arrêter la mesure à tout moment. Elle reste alors arrêtée jusqu'au prochain démarrage de
  SPL Sense.
- **Clôture :** lorsque la mesure est clôturée, le mode autonome se désactive.
- **Calibration :** lors du démarrage automatique, SPL Sense ne demande rien, même si la calibration a expiré. Les
  événements indiquent la raison **Démarrage automatique en tant que mesure autonome**.

## Pour une exploitation sans surveillance

Combinez le mode autonome avec :

- un [code PIN opérateur]({{< relref "settings#code-pin-opérateur" >}}), pour que personne ne modifie les paramètres
- l'[écran en direct en mode kiosque]({{< relref "live-screen#plein-écran-et-kiosque" >}}) comme affichage
- la [transmission au cloud]({{< relref "settings#spl-cloud" >}}), pour voir la mesure à distance, et avec Pro des
  [alarmes]({{< relref "/docs/spl-cloud-pro/alarms" >}}) en cas de panne de la mesure
