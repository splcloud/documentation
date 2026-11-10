---
title: Commande à distance et commentaires
linkTitle: Commande à distance
weight: 50
description: >-
  Commander SPL Sense depuis SPL Cloud, ajouter des commentaires et exclure des plages horaires depuis le cloud.
---

Avec la commande à distance, vous utilisez SPL Sense depuis SPL Cloud, par exemple un Raspberry Pi dans un rack ou un
ordinateur portable sur une autre scène.

## Conditions préalables

- **Autorisé dans SPL Sense :** **Paramètres** › **Cloud** › **Autoriser la commande à distance**. Désactivé par
  défaut. Ainsi, c'est toujours la personne sur place qui décide si son instance peut être commandée à distance.
- **Instance en ligne :** les commandes ne sont envoyées qu'à une instance connectée. Il n'y a pas de file d'attente.
- **Pro sur la mesure :** seules les mesures avec Pro peuvent être commandées.
- **Autorisation :** le propriétaire de l'instance ; pour une instance d'une organisation, tous ses membres. Les
  personnes avec un accès en lecture ou un lien partagé ne peuvent jamais commander.
- **SPL Sense version 2.0 ou ultérieure.**

## Ce qui est possible

Sur la page de l'instance ou de la mesure, dans la zone **Commande à distance** :

| Action | Remarque |
|---|---|
| **Démarrer**, **Arrêter** | |
| **Bypass du Leveler**, **Désactiver le bypass** | |
| Changer de mesure (**Rendre actuelle**), désactiver | seulement si la mesure est arrêtée |
| Créer une **Nouvelle mesure** | avec nom, limite de jour et un modèle de profil de valeur de l'instance. La transmission au cloud est toujours activée ; Pro peut être activé en même temps. |
| Modifier le nom et la limite de jour | pas pendant que la mesure tourne |
| Modifier les **Décalages** | pas pendant que la mesure tourne |
| Changer de **Profil de valeur** | un des modèles de l'instance ; pas pendant que la mesure tourne |
| **Paramètres du Leveler** : mode, limites, décalages de ligne | aussi pendant la mesure, s'applique immédiatement |
| **Terminer la mesure**, **Rouvrir** | |

**Mesures sur l'instance** affiche toutes les mesures de SPL Sense, y compris celles sans transmission au cloud. Seules
les mesures qui sont dans le cloud et ont Pro peuvent être commandées.

## Ce qui n'est pas possible

- Calibration et mises à jour du logiciel
- Mesurer le décalage de ligne (nécessite bruit et silence sur place)
- Configurer la connexion du leveler
- Modifier des limites personnalisées dans le profil de valeur ; cela n'est possible que sur l'instance

## Confirmation et retour

Chaque commande qui modifie quelque chose demande d'abord une confirmation, avec la mesure et l'instance dans le texte,
par exemple « Arrêter la mesure 'Scène principale' sur 'Laptop-FOH' ? ».

Ensuite, le cloud indique le résultat. Si l'instance ne répond pas à temps, le message précise que la commande a
peut-être quand même été exécutée ; vérifiez alors l'état de l'instance.

Dans SPL Sense, chaque commande du cloud apparaît sous forme de message, et les événements de la mesure indiquent qui
l'a déclenchée (**à distance par …**).

Si des personnes sur place et dans le cloud modifient quelque chose en même temps, c'est la dernière modification qui
s'applique.

## Commentaires et plages horaires exclues

Avec Pro, vous pouvez aussi, dans le cloud, ajouter des **commentaires** et **exclure des plages horaires** dans la zone
**Evénements**, exactement comme dans [SPL Sense]({{< relref "/docs/spl-sense/measurement-data#commentaires" >}}). Cela
passe aussi par la commande à distance : l'instance doit être en ligne et autoriser la commande à distance.
