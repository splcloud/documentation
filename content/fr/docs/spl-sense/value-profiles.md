---
title: Profils de valeurs
linkTitle: Profils de valeurs
weight: 30
description: >-
  Quelles valeurs sont calculées, avec quels seuils, et les modèles intégrés.
---

Un profil de valeurs définit quelles valeurs une mesure calcule et à partir de quand elles sont considérées comme trop
fortes. Il détermine les couleurs dans le tableau de bord et dans le graphique, les dépassements et les alarmes dans SPL Cloud.

## Structure

Un profil de valeurs se compose d'une ou plusieurs valeurs. Chaque valeur a :

| Élément | Possibilités |
|---|---|
| **Type d'intégration** | **Leq** (niveau équivalent) ou **MaxF** (niveau le plus élevé avec la pondération temporelle Fast) |
| **Pondération** | A, C ou Z |
| **Temps** | 1 à 60 minutes |
| **Notification**, **Avertissement**, **Limite** | seuils en dB, chacun facultatif |

Exemples : Leq, A, 60 minutes donne **LAeq 60′** ; MaxF, C, 1 minute donne **LCFmax 1′**.

Les moyennes sont calculées de manière glissante : LAeq 60′ est, à chaque minute, la moyenne sur les 60 minutes
précédentes, y compris au-delà de la limite journalière et des pauses. Une valeur est considérée comme au-dessus du seuil
si elle le dépasse ; une valeur exactement égale est encore correcte.

## Modèles intégrés

SPL Sense propose des modèles pour la Suisse (O-LRNIS) et l'Allemagne (DIN 15905-5). Les valeurs figurent sous
[Modèles pour l'O-LRNIS et la DIN 15905-5]({{< relref "/docs/basics/templates-vnissg-din" >}}). Les modèles intégrés ne
peuvent pas être modifiés.

## Tes propres modèles

Sous **Paramètres** › **Profils de valeurs** › **Créer**, tu crées tes propres modèles :

1. Saisis un **Nom**.
2. Ajoute les valeurs souhaitées avec **Ajouter une valeur** et définis les seuils.
3. Clique sur **Sauvegarder**.

Tu peux modifier ou supprimer tes propres modèles à tout moment. Les mesures qui utilisent un modèle ne sont pas
concernées : le modèle est copié dans la mesure lors de sa création.

## Modifier le profil de valeurs d'une mesure

Menu **Mesure** › **Modifier la mesure** › **Modifier le profil de valeurs**. Tu choisis ici un autre modèle ou
adapte directement les valeurs. Si le profil diffère de son modèle, SPL Sense l'indique ; **Réinitialiser le profil
aux valeurs du modèle** rétablit les valeurs du modèle.

À la sauvegarde, SPL Sense recalcule tous les jours de mesure précédents avec le nouveau profil. Les données de mesure
elles-mêmes ne changent pas. La modification apparaît dans les événements avec l'ancien et le nouveau profil.
