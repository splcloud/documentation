---
title: Alarmes
linkTitle: Alarmes
weight: 40
description: >-
  Notification par e-mail et SMS lorsqu'une mesure dépasse une limite ou n'envoie plus de données.
---

SPL Cloud vérifie chaque minute les mesures Pro en cours et avertit les destinataires enregistrés :

- **Dépassement** : une valeur est au-dessus d'un seuil du profil de valeur de la mesure.
- **Interruption** : une mesure en cours n'envoie plus de données, par exemple parce que le courant ou Internet est
  coupé.

Les alarmes ne fonctionnent que pour les mesures avec Pro. Les autres mesures du même périmètre sont ignorées.

## Où configurer les alarmes

- Pour tout un **événement** : menu **Événement** › **Alarmes**. Le réglage s'applique à toutes ses mesures.
- Pour une **mesure unique** : menu **Mesures** › **Configuration des alarmes**. Pour une mesure indépendante, c'est le
  seul moyen. Si la mesure appartient à un événement, ce réglage remplace celui de l'événement pour cette mesure.

En haut de la page, vous choisissez le périmètre : **Événement entier** ou **Mesure unique**. La liste en dessous
affiche les mesures concernées et signale les mesures sans Pro ou sans limites.

## Paramètres

Activez d'abord **Activer les alarmes pour ce périmètre**.

### Dépassement

- **Déclencher au niveau** : quels seuils du profil de valeur déclenchent une alarme : **Notification**,
  **Avertissement**, **Limite**. Les seuils eux-mêmes proviennent du profil de valeur de chaque mesure. Sans seuils dans
  le profil de valeur, il n'y a pas d'alarmes de dépassement.
- **Pendant au moins** : le nombre de minutes pendant lesquelles la valeur doit rester au-dessus du seuil avant qu'une
  alarme ne soit déclenchée. Cela filtre les pics courts. Par défaut : 15 minutes ; 5 à 15 minutes sont courantes.

### Interruption

- **Silence avant l'alarme** : le nombre de minutes pendant lesquelles des données peuvent manquer avant qu'une alarme
  d'interruption ne soit déclenchée. Par défaut : 30 minutes. Les appareils en réseau mobile transmettent souvent par
  à-coups ; ne choisissez alors pas un délai trop court.

### Fin d'une alarme

**Notifier aussi quand une alarme se termine** : un deuxième message dès que le niveau est redevenu normal ou que les
données arrivent à nouveau. Désactivé par défaut, car cela double environ le nombre de messages. Laissez-le désactivé
si des destinataires reçoivent des SMS.

## Destinataires

Les destinataires n'ont pas besoin de compte SPL Cloud. Avec **Ajouter un destinataire**, vous saisissez pour chaque
personne :

- **E-mail** et/ou **Téléphone**. Les SMS nécessitent un numéro de téléphone. Le format national fonctionne aussi
  (079 …) ; il est converti au format international.
- **Reçoit** : **Toutes les alarmes**, **Interruptions seulement** ou **Alarmes de limite seulement**. La personne qui
  remet un appareil en ligne a rarement besoin des dépassements, et celle qui surveille les niveaux rarement des
  interruptions.

C'est plus rapide avec **M'ajouter** et **Ajouter les membres de l'organisation** : le nom, l'e-mail et, s'il est
enregistré dans le profil, le numéro de téléphone sont repris.

## Quand une notification est envoyée

- **Dépassement** : lorsque le premier niveau est atteint et à nouveau à chaque changement de niveau (par exemple
  d'Avertissement à Limite ou inversement). Tant que le niveau reste le même, aucun autre message n'est envoyé.
- **Interruption** : une fois, lorsque l'interruption est détectée.
- Plusieurs alarmes dans la même minute sont regroupées en un seul message.
- Le message contient un lien vers la mesure ou l'événement dans SPL Cloud.
