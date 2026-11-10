---
title: Mesures
linkTitle: Mesures
weight: 20
description: >-
  Cycle de vie d'une mesure : créer, activer, mesurer, modifier, clôturer, importer et exporter.
---

Une mesure correspond à un point de mesure. Elle contient ses paramètres (profil de valeur, limite journalière,
décalages, leveler) et toutes les données enregistrées. Une mesure peut durer plusieurs jours et être démarrée et
arrêtée aussi souvent que nécessaire.

## Déroulement

```text
créer / importer
        │
        ▼
   ouverte ──activer──▶ active ──Démarrage──▶ en cours ──Arrêter──▶ active (arrêtée)
        ▲                  │                    │ capteur absent  ▲
        │             désactiver                ▼                 │ capteur revenu
        └──────────────────┘               interrompue ───────────┘
        │
    clôturer ──▶ clôturée ──rouvrir──▶ ouverte
```

- **Activer :** une seule mesure au plus est active à la fois ; SPL Sense n'enregistre que dans celle-ci. Vous ne pouvez
  changer que si la mesure active est arrêtée.
- **Démarrer et arrêter :** **Démarrage** nécessite un capteur connecté. **Arrêter** demande une confirmation. Si le
  leveler est actif, SPL Sense signale qu'il sera désactivé à l'arrêt.
- **Interrompue :** si le capteur est débranché ou ne fournit aucune valeur pendant 20 secondes (par exemple parce que
  l'ordinateur était en veille), la mesure est interrompue. Dès que le capteur fournit à nouveau des données, elle
  reprend d'elle-même. Vous terminez une mesure interrompue avec **Arrêter**.
- **Désactiver :** menu **Mesure** › **Désactiver**. La mesure reste ouverte mais n'est plus active.
- **Redémarrage de SPL Sense :** après un redémarrage, aucune mesure n'est active. Si une mesure doit reprendre
  automatiquement, utilisez le [mode autonome]({{< relref "autonomous-mode" >}}).

## Créer

Dans la vue d'ensemble, **Nouvelle mesure** :

| Champ | Signification |
|---|---|
| **Nom** | Obligatoire. Apparaît dans la vue d'ensemble, dans les rapports et dans SPL Cloud. |
| **Profil de valeur** | Un modèle (copié), **Sur mesure** (l'éditeur s'ouvre ensuite) ou **Aucun**. Voir [Profils de valeur]({{< relref "value-profiles" >}}). |
| **Limite journalière** | Heure entre 00:00 et 06:00 à laquelle un jour de mesure se termine. |
| **transmission au Cloud (Cloud Uplink)** | Transfère la mesure dans SPL Cloud. Possible uniquement si SPL Sense est enregistré dans le cloud. |

Une nouvelle mesure n'est pas encore active. Son leveler est réglé sur **SPL Tools L1 (USB)** et le mode **Arrêt**.

## Modifier

Menu **Mesure** › **Modifier la mesure**. Possible tant que la mesure n'est pas en cours, pas interrompue et pas
clôturée. Vous pouvez aussi modifier une mesure non active pendant qu'une autre enregistre.

- **Nom**, **Limite journalière**
- **transmission au Cloud (Cloud Uplink) :** l'activer téléverse toutes les données de la mesure, y compris celles déjà
  enregistrées. La désactiver arrête le téléversement ; ce qui est déjà dans le cloud y reste.
- **Décalages** pour A, C et Z, voir ci-dessous
- **Profil de valeur :** à adapter avec **Modifier le profil de valeur**

Si vous modifiez la limite journalière ou le profil de valeur, SPL Sense recalcule les limites et les jours de mesure.
Chaque modification des décalages et du profil de valeur apparaît dans les événements.

Les [paramètres du leveler]({{< relref "leveler" >}}) se modifient séparément ; ils peuvent aussi être changés pendant la
mesure.

## Décalages

Le décalage convertit les valeurs du point de mesure en valeurs à l'endroit le plus bruyant du public. La façon de le
déterminer est décrite sous [Point de mesure et décalage]({{< relref "/docs/basics/measuring-point-and-offset" >}}).

Deux possibilités :

- **Réglages des décalages (Offset)** (menu **Mesure**) : avec des valeurs en direct. Uniquement pour la mesure active
  et arrêtée avec un capteur connecté. Le tableau montre, par pondération, le niveau actuel, le niveau le plus élevé
  depuis **Réinitialisation des valeurs maximales**, le décalage et les deux valeurs avec décalage. Rien de ce que vous
  mesurez ici n'est enregistré.
- **Modifier la mesure :** saisir directement les décalages en chiffres, par exemple à partir d'une mesure avec un
  sonomètre portable.

Un décalage modifié s'applique à partir du prochain démarrage. Les données déjà enregistrées conservent le décalage avec
lequel elles ont été enregistrées.

## Clôturer et rouvrir

Une fois la manifestation terminée, clôturez la mesure : menu **Mesure** › **Mesure complète**. La mesure doit être
arrêtée. Elle est ensuite verrouillée : elle ne peut plus être activée, modifiée ou démarrée, mais elle peut être
consultée et exportée. Si le mode autonome est réglé sur cette mesure, il est désactivé.

Vous rouvrez une mesure clôturée dans le menu avec **Rouvrir la mesure**.

## Suppression

Vous supprimez une mesure ouverte sous **Modifier la mesure** › **Supprimer la mesure**, une mesure clôturée dans le menu
**Mesure**. La suppression ne concerne que cet ordinateur ; ce qui est dans SPL Cloud y reste. La façon de supprimer
aussi la mesure dans le cloud est décrite sous [Mesures dans le cloud]({{< relref "/docs/spl-cloud/measurements#supprimer" >}}).

## Importation et exportation

Une mesure peut être sauvegardée sous forme de fichier `.splsense` et relue sur un autre ordinateur, avec toutes ses
données et paramètres.

- **Exporter :** clôturez la mesure et cliquez sur **Exporter la Mesure**.
- **Importer :** dans la vue d'ensemble, **Importer**, puis faites glisser le fichier dans le champ. Si la mesure existe
  déjà, vous pouvez la remplacer avec **Remplacer une mesure existante**.

Pour exporter les valeurs sous forme de tableau CSV, voir [Données de mesure]({{< relref "measurement-data#rapports-et-exports" >}}).
