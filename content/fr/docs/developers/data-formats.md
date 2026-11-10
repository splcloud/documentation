---
title: Formats de données
linkTitle: Formats de données
weight: 30
description: >-
  Export CSV et fichiers .splsense.
---

## CSV

L'export CSV est disponible par jour et pour toute la mesure, dans SPL Sense et dans SPL Cloud (là-bas pour toute la
mesure au format ZIP).

- Séparateur : point-virgule `;`
- une ligne par minute (intervalle)
- première colonne `Timestamp` : fin de l'intervalle au format ISO 8601 avec fuseau horaire, par exemple
  `2026-07-12T22:15:00.0000000+02:00`
- ensuite une colonne par valeur du profil de valeurs, dans son ordre, avec nom et unité dans l'en-tête
- valeurs en dB avec une décimale, offset inclus
- séparateur décimal selon la langue de l'interface

Les plages horaires exclues, les commentaires et les événements ne sont pas inclus dans le CSV.

## `.splsense`

Un fichier `.splsense` contient toute une mesure de SPL Sense avec tous les enregistrements, les intervalles signés, les
événements et les paramètres. Il sert de sauvegarde et au transfert vers un autre ordinateur
([Importation et exportation]({{< relref "/docs/spl-sense/measurements#importation-et-exportation" >}})).

Le format est interne et peut changer avec les nouvelles versions. Pour une analyse dans ton propre logiciel, utilise
l'export CSV et l'[API SPL Sense]({{< relref "sense-api" >}}).
