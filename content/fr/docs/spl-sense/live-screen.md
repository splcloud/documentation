---
title: Vue live et kiosque
linkTitle: Vue live et kiosque
weight: 40
description: >-
  Vues live intégrées et personnalisées, widgets et mode kiosque.
---

La **vue live** affiche les valeurs actuelles en grand et bien lisibles, par exemple sur un second écran pour le
DJ ou les techniciens. Tu l'ouvres sur la page de la mesure avec **Vue live** ou en cliquant sur l'état de
l'appareil dans la barre d'état.

## Choisir une vue live

Choisis la vue live en haut à droite. SPL Sense retient pour chaque mesure laquelle a été utilisée en
dernier.

Des vues live pour les cas courants sont intégrées, chacun avec et sans affichage du leveler :

| Vue live | Contenu |
|---|---|
| **VNISSG 93dBA**, **96dBA**, **100dBA** | LAeq 3 s, LAeq 5′, LAeq 60′, LAFmax, historique de la dernière heure |
| **DIN 15905-5** | LAeq 5 s, LAeq 5′, LAeq 30′, LCFmax, historique de la dernière heure |
| **DJ** | LAeq 3 s et LAeq 5′, réduit à l'essentiel |
| … **Leveler** | en plus réduction de gain et corrélation |

## Vues live personnalisées

Sous **Paramètres** › **Vues live** › **Créer** :

1. Saisis un **Nom**.
2. Ajoute des widgets avec **Ajouter**.
3. Dispose-les sur la grille : fais glisser un widget pour le déplacer et son coin pour le redimensionner. Au clavier :
   les touches fléchées déplacent, <kbd>Maj</kbd> + touches fléchées redimensionnent.
4. Sélectionne un widget pour changer son type ou définir ses **Seuils de couleur**.
5. **Sauvegarder**.

L'aperçu affiche des valeurs fictives en taille réelle, tu vois ainsi la taille des chiffres. Sur les écrans étroits,
les widgets s'affichent les uns sous les autres.

### Widgets

| Groupe | Widgets |
|---|---|
| **SPL numérique** | Leq ou MaxF, pondération A, C ou Z, sur **Actuel** ou de 3 s à 60 min |
| **Graphique** | Spectre, Historique aujourd'hui, Historique Dernière heure |
| **Leveler** | Réduction de gain, Corrélation |
| **Autres** | Dernier intervalle |

### Seuils de couleur

Les widgets numériques changent de couleur lorsqu'une valeur dépasse un seuil. Tu définis les seuils manuellement ou
les reprends de la mesure avec **De profil de valeurs**. Cela ne fonctionne que pour des durées supérieures à une minute,
car le profil de valeurs ne connaît pas de durées plus courtes.

## Plein écran et kiosque

**Plein écran** fait passer la vue live en mode kiosque : au lieu des menus, une barre étroite affiche seulement la
mesure, la vue live, l'heure de la dernière valeur et l'état de l'appareil. Les widgets remplissent tout l'écran, même sur un
grand téléviseur. **Quitter le plein écran** permet de revenir.

Si un [code PIN opérateur]({{< relref "settings#code-pin-opérateur" >}}) est défini, SPL Sense le demande en quittant
la vue live et le plein écran. Ainsi, personne ne peut modifier les paramètres depuis la cabine du DJ.

Pour les appareils qui doivent démarrer directement sur la vue live, voir
[SPL Sense pour Linux › Exploitation]({{< relref "/docs/linux/operation#affichage-kiosque" >}}).
