---
title: Bruit du public
linkTitle: Bruit du public
weight: 30
description: >-
  Comment le public et les autres sources de bruit influencent la mesure et comment SPL Sense les traite.
---

## Qu'est-ce qui compte dans le niveau ?

Les réglementations diffèrent ici :

- **O-LRNIS (Suisse) :** **tout ce qui est audible à l'endroit le plus bruyant** compte : sonorisation, scène,
  instruments et aussi le public (recommandation de la branche sur la procédure de mesure).
- **DIN 15905-5 (Allemagne) :** seul le son de la sonorisation est évalué. Le public et les autres sources sont du
  *Störschall* (bruit parasite) et ne doivent pas fausser le résultat. C'est pourquoi la norme recommande un point de
  mesure où le public pèse peu.

Dans les deux cas, l'enregistrement de SPL Sense contient le niveau total au capteur. Aucun paramètre ne retire le public
des valeurs mesurées enregistrées. Son poids dépend donc du choix du point de mesure.

Pour la plupart des manifestations, le public a peu d'influence sur le niveau horaire (aide à l'exécution de
l'O-LRNIS). Ponctuellement, il peut toutefois contribuer nettement au niveau : applaudissements, chants de supporters,
public qui chante, retours de scène forts ou pluie sur un toit de tente.

## Ce que tu peux faire

- **Bien choisir le point de mesure :** si le capteur est au-dessus de la hauteur des têtes, à l'écart de la foule et
  dans le son direct de la sonorisation, le public a moins d'effet. Garde une distance suffisante par rapport aux
  haut-parleurs. Voir [Point de mesure et offset]({{< relref "measuring-point-and-offset" >}}).
- **Garder un niveau de scène bas :** des retours et un backline forts augmentent le niveau sans que la régie puisse y
  faire grand-chose.
- **Ajouter des commentaires :** consigne les moments particuliers dans la mesure, par exemple « Rappel, le public
  chante ». Les commentaires apparaissent dans le graphique journalier et aident plus tard à expliquer les pics.

## Leveler avec compensation du public

Le [leveler]({{< relref "/docs/spl-sense/leveler" >}}) baisse automatiquement la sonorisation lorsque le niveau est trop
élevé. Sans autre information, il le ferait aussi lorsque le public est bruyant, rendant la musique inutilement plus
faible alors que la sonorisation n'y est pour rien.

En mode **Leveler avec fonction panique et compensation du public**, SPL Sense compare le niveau mesuré avec le signal
que le processeur audio émet. S'il est plus fort que ce que la sonorisation seule peut expliquer (corrélation supérieure
à 1), le leveler ne tient compte que de la part de la sonorisation. La mesure elle-même continue d'enregistrer le niveau
complet.

Pour cela, le leveler a besoin d'un **décalage de ligne** mesuré avec précision. La procédure est décrite sous
[Leveler]({{< relref "/docs/spl-sense/leveler" >}}).
