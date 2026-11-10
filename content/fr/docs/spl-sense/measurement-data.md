---
title: Données de mesure
linkTitle: Données de mesure
weight: 25
description: >-
  Jours, graphique, détails des intervalles, dépassements, événements, commentaires, plages horaires exclues et rapports.
---

La page de la mesure est identique dans SPL Sense et dans SPL Cloud. Ce qui est décrit ici vaut pour les deux ; les
différences concernant les rapports figurent à la fin.

## Jours de mesure et graphique

Les données sont organisées par jours de mesure ; un jour de mesure se termine à la limite journalière de la mesure.
Chaque jour affiche les valeurs du profil de valeurs, colorées selon les seuils : jaune pour **Notification**, orange
pour **Avertissement**, rouge pour **Limite**. **Afficher tous les jours** fait apparaître les jours plus anciens.

Le graphique montre l'évolution du jour sélectionné :

- les valeurs du profil de valeurs sous forme de lignes, l'évaluation sous forme de bande colorée
- les commentaires et événements sous forme de marqueurs
- les plages horaires exclues en grisé
- avec un leveler actif, en plus le niveau du signal (line), la réduction de gain et la corrélation

Les premières valeurs apparaissent après la première minute complète d'enregistrement.

## Détails de l'intervalle

Un clic dans le graphique ouvre les détails de la minute à cet endroit (un **intervalle**) : toutes les valeurs, le
spectre en tiers d'octave et les résultats de contrôle. Les flèches permettent de passer à la minute précédente ou
suivante.

| Indication | Signification |
|---|---|
| **Signature valide** | Les données sont inchangées depuis que le capteur les a signées. |
| **Signature non valide** / **Bloc de validation manquant** | Il n'est pas possible de prouver que les données sont inchangées. |
| **Calibrage expiré** | Les données ont été enregistrées avec une calibration expirée. |
| **Clip** | Le niveau était trop élevé pour le capteur (saturation). Les valeurs de cette minute ne sont pas fiables. |
| **Valeurs faibles** | Le niveau était inférieur à la plage de mesure du capteur. |
| **Température** | Le capteur était trop chaud. |
| **Tension** | La tension d'alimentation du capteur était trop basse. |
| **Protection contre les intempéries** | Le filtre de compensation pour la protection contre les intempéries était activé. |
| **Utilisation de plusieurs capteurs** | Le capteur a été changé pendant cette minute. |

## Dépassements

La section **Dépassements** liste, pour chaque valeur du profil de valeurs, quand le jour sélectionné a dépassé un seuil, avec
la valeur la plus élevée. Un clic sur une entrée trace les seuils dans le graphique.

## Événements

La section **Evénements** liste tout ce qui s'est passé avec la mesure, le plus récent en haut :

- enregistrement démarré et arrêté, avec la raison (par exemple manuellement, mode autonome, microphone déconnecté,
  mise en veille, capteur reconnecté)
- mesure créée, activée, clôturée, rouverte
- offsets, profil de valeurs et paramètres du leveler modifiés, à chaque fois avec les anciennes et nouvelles valeurs
- leveler bypassé et réactivé
- commentaires et plages horaires exclues modifiées

Si une modification provient de SPL Cloud ou de l'API, cela est indiqué ; pour le cloud, aussi par qui.

## Commentaires

Avec **Ajouter** › **Ajouter un commentaire** dans la section Événements, tu consignes quelque chose à un moment
donné, par exemple « Rappel » ou « Offset vérifié au sonomètre portable ». Les commentaires apparaissent dans le
graphique et peuvent être modifiés ultérieurement. Pour une mesure clôturée, les commentaires ne sont possibles que
jusqu'au moment de la clôture.

## Exclure des plages horaires

Certaines périodes ne doivent pas être prises en compte dans l'évaluation, par exemple le réglage du système avec du
bruit rose avant l'ouverture des portes. Avec **Ajouter** › **Exclure une plage horaire**, tu définis une plage
avec **De**, **À** et un commentaire.

Une plage exclue :

- est grisée dans le graphique et marquée **Non pris en compte**
- ne compte ni pour les maxima, ni pour l'évaluation selon le profil de valeurs, ni pour les dépassements
- reste conservée avec toutes les données de mesure

**Prendre à nouveau en compte ?** annule l'exclusion. Chaque modification apparaît dans les événements.

## Rapports et exports

| Quoi | Où |
|---|---|
| Rapport journalier (PDF) du jour sélectionné | bouton **PDF** à côté du jour |
| CSV du jour sélectionné | bouton **CSV** à côté du jour |
| CSV de toute la mesure | menu **Mesure** › **Exporter tous les jours de mesure au format CSV** |
| mesure complète en sauvegarde | **Exporter la Mesure**, voir [Mesures]({{< relref "measurements#importation-et-exportation" >}}) |

Dans SPL Cloud, le rapport journalier (aussi avec dépassements) et un rapport photos sont disponibles avec
[Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}).

## Liaison cloud

Si la liaison cloud est activée, la page de la mesure affiche l'état du téléversement : **En ligne**,
**Hors ligne** et combien d'intervalles, d'événements et de statistiques du leveler attendent encore d'être téléversés.
Sans Internet, SPL Sense continue de mesurer normalement et rattrape le téléversement.
