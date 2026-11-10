---
title: Écran en direct et kiosque
linkTitle: Écran en direct et kiosque
weight: 40
description: >-
  Écran en direct, écrans intégrés et personnalisés, widgets et mode kiosque.
---

L'**Écran en direct** affiche les valeurs actuelles en grand et bien lisibles, par exemple sur un second écran pour le
DJ ou les techniciens. Vous l'ouvrez sur la page de la mesure avec **Écran en direct** ou en cliquant sur l'état de
l'appareil dans la barre d'état.

## Choisir un écran

Choisissez l'écran en haut à droite de l'écran en direct. SPL Sense retient pour chaque mesure lequel a été utilisé en
dernier.

Des écrans pour les cas courants sont intégrés, chacun avec et sans affichage du leveler :

| Écran | Contenu |
|---|---|
| **VNISSG 93dBA**, **96dBA**, **100dBA** | LAeq 3 s, LAeq 5′, LAeq 60′, LAFmax, historique de la dernière heure |
| **DIN 15905-5** | LAeq 5 s, LAeq 5′, LAeq 30′, LCFmax, historique de la dernière heure |
| **DJ** | LAeq 3 s et LAeq 5′, réduit à l'essentiel |
| … **Leveler** | en plus réduction de gain et corrélation |

## Écrans personnalisés

Sous **Paramètres** › **Écrans en direct** › **Créer** :

1. Saisissez un **Nom**.
2. Ajoutez des widgets avec **Ajouter**.
3. Disposez-les sur la grille : faites glisser un widget pour le déplacer et son coin pour le redimensionner. Au clavier :
   les touches fléchées déplacent, <kbd>Maj</kbd> + touches fléchées redimensionnent.
4. Sélectionnez un widget pour changer son type ou définir ses **Seuils de couleur**.
5. **Sauvegarder**.

L'aperçu affiche des valeurs fictives en taille réelle, vous voyez ainsi la taille des chiffres. Sur les écrans étroits,
les widgets s'affichent les uns sous les autres.

### Widgets

| Groupe | Widgets |
|---|---|
| **SPL numérique** | Leq ou MaxF, pondération A, C ou Z, sur **Actuel** ou de 3 s à 60 min |
| **Graphique** | Spectre, Historique aujourd'hui, Historique Dernière heure |
| **Leveler** | Réduction de gain, Corrélation |
| **Autres** | Dernier intervalle |

### Seuils de couleur

Les widgets numériques changent de couleur lorsqu'une valeur dépasse un seuil. Vous définissez les seuils manuellement ou
les reprenez de la mesure avec **De profil de valeur**. Cela ne fonctionne que pour des durées supérieures à une minute,
car le profil de valeur ne connaît pas de durées plus courtes.

## Plein écran et kiosque

**Plein écran** fait passer l'écran en direct en mode kiosque : au lieu des menus, une barre étroite affiche seulement la
mesure, l'écran, l'heure de la dernière valeur et l'état de l'appareil. Les widgets remplissent tout l'écran, même sur un
grand téléviseur. **Quitter le plein écran** permet de revenir.

Si un [code PIN opérateur]({{< relref "settings#code-pin-opérateur" >}}) est défini, SPL Sense le demande en quittant
l'écran en direct et le plein écran. Ainsi, personne ne peut modifier les paramètres depuis la cabine du DJ.

Pour les appareils qui doivent démarrer directement sur l'écran en direct, voir
[SPL Sense pour Linux › Exploitation]({{< relref "/docs/linux/operation#affichage-kiosque" >}}).
