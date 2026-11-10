---
title: Point de mesure et offset
linkTitle: Point de mesure et offset
weight: 20
description: >-
  Où placer le capteur, comment déterminer l'offset et ce qu'il faut documenter.
---

## Endroit le plus bruyant et point de mesure

Les valeurs limites s'appliquent à l'**endroit le plus bruyant de la zone du public**. L'O-LRNIS l'appelle *lieu de
détermination* (à hauteur d'oreille), la DIN 15905-5 *maßgeblicher Immissionsort*. Le capteur peut rarement s'y trouver
pendant une manifestation : au milieu du public, il serait menacé, et les cris et applaudissements fausseraient la
mesure.

On mesure donc à un autre endroit, le **point de mesure** (DIN : *Ersatzimmissionsort*). L'**offset** (DIN :
*valeur de correction*) compense la différence entre les deux endroits. SPL Sense l'ajoute à chaque valeur mesurée afin
que les valeurs affichées et enregistrées correspondent au niveau à l'endroit le plus bruyant du public.

## Choisir le point de mesure

- Le capteur doit recevoir le **son direct** de la sonorisation : vue dégagée sur les haut-parleurs, pas derrière des
  piliers, des mâts de tente ou le toit de la régie.
- Le moins possible de public et d'autres sources de bruit à proximité.
- Pas dans les coins de la salle ni directement contre un mur.
- En extérieur avec protection contre les intempéries, et activer le
  [filtre de protection contre les intempéries]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}) correspondant.
- Ne plus le déplacer pendant la manifestation. Si tu dois le déplacer, détermine à nouveau l'offset.

### Distance par rapport aux haut-parleurs

Le capteur a besoin d'une **distance minimale** par rapport à la sonorisation :

- Ce n'est qu'à une certaine distance que les aigus, médiums et basses se mélangent pour former le son entendu par le
  public. Trop près d'un haut-parleur, le capteur mesure surtout ce seul haut-parleur, et l'offset n'est plus valable
  pour la musique.
- Le capteur a un niveau maximal. Trop près d'un haut-parleur, les crêtes peuvent le saturer. SPL Sense l'indique par
  **Clip** dans les données de mesure.

Dans ces limites : plus le point de mesure est éloigné du public et mieux il est placé dans le son direct de la
sonorisation, moins le public et les autres sources dérangent. Si le point de mesure est plus proche de la sonorisation
que l'endroit le plus bruyant du public, l'offset devient négatif. La DIN 15905-5 recommande un tel point de mesure.

## Déterminer l'offset

L'offset est déterminé **avant la manifestation avec du bruit rose**, aussi fort qu'en exploitation et avec exactement
la sonorisation utilisée pendant la manifestation. Dans SPL Sense, cela se fait avec **Offset tune**,
décrit pas à pas dans le [Démarrage rapide]({{< relref "/docs/quick-start#5-régler-loffset" >}}). En bref :

1. Diffuser du bruit rose au volume d'exploitation.
2. Parcourir la zone du public avec le capteur. SPL Sense retient le niveau le plus élevé : c'est ton endroit le plus
   bruyant.
3. Placer le capteur au point de mesure et régler l'offset de sorte que le niveau au point de mesure plus l'offset
   corresponde au niveau le plus élevé.

Tu peux aussi mesurer le niveau à l'endroit le plus bruyant avec un sonomètre portable et saisir la différence
directement sous **Modifier la mesure**. La DIN 15905-5 exige pour cela une durée de mesure d'au moins 15 secondes.

L'offset s'applique par pondération : il y a une valeur séparée pour A, C et Z.

- **A** (pour LAeq et LAFmax) : l'endroit le plus bruyant est déterminé par les médiums et les aigus.
- **C** (pour LCFmax et le niveau de crête) : l'endroit le plus bruyant est déterminé par les basses et peut se trouver
  ailleurs. La DIN 15905-5 permet de déterminer l'offset C à partir du LCeq ; c'est plus fiable qu'avec des valeurs de
  crête.

{{% alert title="Conseils" color="info" %}}
- Vérifie ensuite l'offset avec de la musique typique. S'il s'écarte fortement, mesure à nouveau.
- Ne calcule pas l'offset avec des règles empiriques, mesure-le.
- L'offset ne vaut que pour cette configuration de haut-parleurs et ce point de mesure. Si l'un des deux change,
  mesure à nouveau.
- Pendant la manifestation, vérifie brièvement si les valeurs sont plausibles (l'aide à l'exécution de l'O-LRNIS le
  mentionne comme possibilité).
{{% /alert %}}

## Test de fonctionnement et calibration

Pour les systèmes de mesure mobiles, la DIN 15905-5 exige un test de fonctionnement avec un calibreur avant et après
chaque manifestation. La recommandation de la branche sur la procédure de mesure pour l'O-LRNIS recommande également une
calibration avant et après chaque mesure pour les systèmes mobiles ; l'aide à l'exécution elle-même n'impose pas de
calibration aux organisateurs. SPL Sense affiche l'état de calibration du capteur et avertit avant le démarrage s'il a
expiré. Voir [Capteur et calibration]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}).

## Documentation

Consigne par écrit comment tu as mesuré.

- **O-LRNIS :** au moins l'endroit le plus bruyant, l'offset et la méthode utilisée pour le déterminer.
- **DIN 15905-5 :** un procès-verbal de mesure comprenant notamment l'organisateur, la date et le lieu, le début et la
  fin de la mesure, les niveaux d'évaluation et les niveaux de crête, les appareils de mesure et de calibration, le
  résultat du test de fonctionnement, l'emplacement des lieux d'immission et du point de mesure avec justification, ainsi
  que les valeurs de correction et la façon dont elles ont été déterminées. La liste complète figure dans la norme, au
  chapitre « Messprotokoll ».

Les valeurs mesurées te sont fournies par exemple par le rapport journalier PDF.

SPL Sense t'aide : chaque modification de l'offset apparaît automatiquement dans les événements, et les commentaires
te permettent de consigner les particularités directement dans la mesure. Dans SPL Cloud, tu peux en plus joindre
des photos du point de mesure à la mesure ([SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}})).

Documents originaux : voir [Modèles pour l'O-LRNIS et la DIN 15905-5]({{< relref "templates-vnissg-din" >}}).
