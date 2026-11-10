---
title: Modèles pour l'O-LRNIS et la DIN 15905-5
linkTitle: Modèles O-LRNIS / DIN
weight: 5
description: >-
  Les profils de valeurs et écrans en direct que SPL Sense propose pour la Suisse et l'Allemagne.
---

SPL Sense propose des profils de valeurs et des vues live pour l'O-LRNIS (Suisse, en allemand V-NISSG) et la
DIN 15905-5 (Allemagne). Les exigences applicables à ta manifestation figurent dans les documents originaux
(ci-dessous).

## Profils de valeurs

| Modèle | Valeurs et seuils (Notification / Avertissement / Limite) |
|---|---|
| **VNISSG 93dBA** | LAeq 60′ : 91 / 92 / 93 · LAeq 5′ : – / 92 / 93 · LAFmax 1′ : limite 125 |
| **VNISSG 96dBA** | LAeq 60′ : 94 / 95 / 96 · LAeq 5′ : – / 95 / 96 · LAFmax 1′ : limite 125 |
| **VNISSG 100dBA** | LAeq 60′ : 98 / 99 / 100 · LAeq 5′ : – / 99 / 100 · LAFmax 1′ : limite 125 |
| **DIN 15905-5** | LAeq 30′ : – / 95 / 99 · LAeq 5′ : – / 95 / 99 · LCFmax 1′ : limite 135 |

Les valeurs peuvent être adaptées pour chaque mesure, voir [Profils de valeurs]({{< relref "/docs/spl-sense/value-profiles" >}}).
Les vues live correspondantes portent les mêmes noms que les modèles, chacune aussi dans une variante avec
affichage du leveler.

SPL Sense calcule les moyennes comme LAeq 30′ ou LAeq 60′ chaque minute, de manière glissante sur les 30 ou 60 dernières
minutes. La valeur à l'heure pile et à la demi-heure correspond à la moyenne sur la demi-heure écoulée, c'est-à-dire au
bloc de 30 minutes de la DIN 15905-5. Si LAeq 30′ reste en tout temps sous la limite, tous les blocs sont également
respectés.

Pour le niveau de crête, le modèle **DIN 15905-5** utilise la valeur **LCFmax 1′** : la valeur Fast (125 ms) pondérée C
la plus élevée sur une minute.

## Documents originaux

- Office fédéral de la santé publique (OFSP) : *Aide à l'exécution de l'O-LRNIS, son* et *Procédure de mesure des
  niveaux sonores lors de manifestations*, sur le site de l'OFSP
- [DIN 15905-5:2022-07](https://doi.org/10.31030/3343057), Veranstaltungstechnik – Tontechnik – Teil 5 (norme allemande
  sur la protection de l'ouïe du public contre les niveaux sonores élevés des systèmes de sonorisation)
