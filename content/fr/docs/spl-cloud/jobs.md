---
title: Missions de mesure avec plusieurs points de mesure
linkTitle: Missions de mesure
weight: 40
description: >-
  Regrouper plusieurs mesures dans une mission de mesure.
---

Une **mission de mesure** regroupe plusieurs mesures qui vont ensemble : toutes les scènes d'un festival, les points de mesure
d'un chantier ou un club avec une salle principale et une salle annexe. Chaque point de mesure reste une mesure à part
entière, avec son propre capteur, son propre profil de valeurs et ses propres données. La mission de mesure les affiche ensemble
et te permet de régler l'accès, Pro et les alarmes pour toutes à la fois.

Les missions de mesure n'existent que dans SPL Cloud ; SPL Sense ne connaît que des mesures.

## Créer une mission de mesure

1. Dans le tableau de bord, **Créer une nouvelle mission de mesure**.
2. **Nom**, par exemple « Openair 2026 ».
3. **Localisation** (facultatif).
4. **De** et **Pour** (jusqu'à) : la période. Elle détermine quand la mission de mesure passe aux
   [archives]({{< relref "account-and-interface#archives" >}}), à savoir dix jours après la date de fin.
5. **Propriétaire** : toi personnellement ou une organisation. Le propriétaire ne peut plus être modifié ensuite.
6. **Sauvegarder**.

## Attribuer des mesures

Sur la page de la mission de mesure, dans le menu **Mission de mesure** › **Gérer les mesures** :

- **Attribuer des mesures** : choisis des mesures qui n'appartiennent encore à aucune mission de mesure.
- **Retirer** enlève une mesure de la mission de mesure. Elle redevient autonome.

**Terminer la gestion des mesures** clôt la modification.

Chaque mesure appartient au plus à une mission de mesure.

## Propriétaires différents

La mission de mesure et les mesures peuvent appartenir à des propriétaires différents. Cas typique : l'organisateur gère
la mission de mesure « Openair 2026 » dans son organisation, une entreprise technique mesure une scène avec son propre
ordinateur portable. La mesure appartient alors à l'entreprise technique (le propriétaire de l'instance qui la
transmet), la mission de mesure à l'organisateur.

### Attribuer

Seule une personne qui a **les deux** droits peut attribuer une mesure : gérer la mission de mesure et gérer la mesure. En
pratique, c'est une personne membre des deux organisations. La mesure conserve son propriétaire lors de l'attribution.

### Qui peut faire quoi

Dans l'exemple, **A** est l'entreprise technique (propriétaire de la mesure) et **B** l'organisateur (propriétaire de
la mission de mesure).

| | A : propriétaire de la mesure | B : propriétaire de la mission de mesure |
|---|---|---|
| Voir la mesure, les rapports et les exports | ✓ | ✓ |
| Clôturer ou supprimer la mesure, ajouter des photos | ✓ | |
| Transmettre des données (seulement les instances de A) | ✓ | |
| [Commande à distance]({{< relref "/docs/spl-cloud-pro/remote-control" >}}) de l'instance | ✓ | |
| Accorder un [accès en lecture]({{< relref "read-access" >}}) à cette mesure | ✓ | |
| Accorder un accès en lecture à toute la mission de mesure (s'applique aussi à la mesure de A) | | ✓ |
| Retirer la mesure de la mission de mesure | | ✓ |
| Activer Pro pour la mesure (A paie) | ✓ | |
| Activer Pro pour la mission de mesure (B paie, aussi pour la mesure de A) | | ✓ |
| Voir les coûts et les détails de licence de la mission de mesure | | ✓ |
| [Alarmes]({{< relref "/docs/spl-cloud-pro/alarms" >}}) pour toute la mission de mesure | | ✓ |
| Alarmes uniquement pour cette mesure (remplacent celles de la mission de mesure) | ✓ | |
| [Lien partagé]({{< relref "/docs/spl-cloud-pro/shared-links" >}}) vers la mesure (nécessite Pro sur la mesure) | ✓ | |
| Lien partagé vers la mission de mesure (nécessite Pro sur la mission de mesure, affiche aussi la mesure de A) | | ✓ |

« A » et « B » désignent chacun la personne ou tous les membres de l'organisation à qui appartient la mesure ou
la mission de mesure.

### Pro avec des propriétaires différents

- Si **B** active Pro pour la mission de mesure, **B** paie pour toutes les mesures qu'il contient, y compris celle de A, dans la
  devise de B.
- Si **A** a déjà activé Pro directement sur la mesure, cela reste ainsi : A continue de payer pour cette mesure.
- Si A désactive l'activation directe alors que la mission de mesure est Pro, la mesure reste Pro via la mission de mesure.

Voir aussi [Prix et facturation]({{< relref "/docs/spl-cloud-pro/pricing-and-billing" >}}).

## Modifier et supprimer

**Editer** modifie le nom, la localisation et la période. **Supprimer la mission de mesure** n'est possible que si plus aucune
mesure ne lui est attribuée.

## Exemple : festival avec trois points de mesure

Une entreprise technique s'occupe d'un festival avec une scène principale, une tente et un point de mesure près de
l'habitation la plus proche.

1. Trois ordinateurs portables avec SPL Sense sont enregistrés comme instances de l'organisation de l'entreprise.
2. Sur chaque ordinateur, une mesure avec liaison cloud est créée : « Scène principale », « Tente »,
   « Voisinage ».
3. Dans le cloud, la mission de mesure « Openair 2026 » est créé avec la période du festival, et les trois mesures lui sont
   attribuées.
4. L'autorité reçoit un [accès en lecture]({{< relref "read-access" >}}) à toute la mission de mesure, l'exploitant de la tente
   uniquement à sa mesure.
5. En option : [Pro]({{< relref "/docs/spl-cloud-pro" >}}) pour toute la mission de mesure, par exemple pour des
   [alarmes]({{< relref "/docs/spl-cloud-pro/alarms" >}}) à l'équipe technique ou un lien partagé pour l'organisateur.
