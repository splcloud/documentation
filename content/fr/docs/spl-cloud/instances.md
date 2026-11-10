---
title: Instances SPL Sense
linkTitle: Instances SPL Sense
weight: 30
description: >-
  Surveiller et gérer les installations SPL Sense enregistrées.
---

Chaque installation de SPL Sense enregistrée auprès de SPL Cloud s'appelle une **instance** : un ordinateur portable,
un PC de bureau ou un Raspberry Pi. L'enregistrement d'une instance est décrit sous
[SPL Sense › Paramètres]({{< relref "/docs/spl-sense/settings#spl-cloud" >}}).

## États

| État | Signification |
|---|---|
| **Mesure en cours** | SPL Sense est en ligne et enregistre. |
| **Connexion perdue** | L'instance ne s'est plus manifestée pendant une mesure. SPL Sense continue généralement de mesurer et transmet les données dès qu'Internet est de retour. |
| **En ligne** | SPL Sense tourne et est connecté, mais ne mesure pas. |
| **Hors ligne** | SPL Sense ne tourne pas ou n'a pas d'Internet. Le dernier contact est affiché. |

## Où trouver les instances

- **Barre d'état** : « SPL Sense 3 sur 5 en ligne », avec la liste de toutes tes instances
- **Tableau de bord**, tout en bas : toutes les instances avec état, activité, propriétaire et niveau actuel
- **Paramètres** › **Instances personnelles** et sur la page de chaque organisation

Chaque instance affiche l'icône de son système d'exploitation (Apple, Windows, Linux).

## Page d'une instance

Un clic sur une instance affiche :

- ce qu'elle fait : pendant la mesure, la mesure en cours avec les valeurs actuelles sur 1 seconde, avec un leveler
  actif aussi la réduction de gain et la corrélation ; hors ligne, le dernier contact
- les **Détails** : ID de l'instance, hôte, système d'exploitation, propriétaire, date d'enregistrement
- avec [Pro]({{< relref "/docs/spl-cloud-pro/remote-control" >}}), la commande à distance

## À qui appartiennent les données

Une nouvelle mesure transmise par une instance appartient au propriétaire de l'instance. Seules les instances du même
propriétaire peuvent transmettre des données dans une mesure existante.

## Changer de propriétaire

Tu changes le propriétaire d'une instance en l'enregistrant à nouveau :

1. Dans SPL Sense : **Paramètres** › **Cloud** › désenregistrer l'instance.
2. **Instance de registre** et, lors de la confirmation dans le cloud, choisir le nouveau **Propriétaire**.
3. Dans SPL Sense, activer la **liaison cloud** pour les nouvelles mesures.

L'instance conserve son ID. Les mesures déjà transmises gardent leur propriétaire précédent. L'instance ne peut ensuite
plus y transmettre de données, car seules les instances du propriétaire d'une mesure peuvent y transmettre. Change donc
de propriétaire entre deux interventions, pas pendant une mesure en cours.

## Supprimer une instance

Sur la page de l'instance, dans le menu : **Désenregistrement de l'instance**. L'instance ne peut ensuite plus rien
transmettre. Les mesures dans le cloud sont conservées. Désenregistre aussi l'instance dans SPL Sense pour qu'elle
cesse d'essayer de se connecter.
