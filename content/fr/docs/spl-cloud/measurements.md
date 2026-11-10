---
title: Mesures dans le cloud
linkTitle: Mesures
weight: 50
description: >-
  Consulter, exporter, clôturer et supprimer des données de mesure dans le cloud.
---

Une mesure apparaît dans SPL Cloud dès que sa **liaison cloud** est activée dans SPL Sense et que l'instance a
Internet. Les nouvelles mesures apparaissent d'abord sous les mesures autonomes dans le tableau de bord.

## La page de mesure

Sous le titre, une ligne indique l'essentiel : mission de mesure, propriétaire, l'instance qui mesure actuellement (avec son
état), et si Pro est actif.

- **En direct :** si la mesure est en cours, tu vois les valeurs actuelles sur 1 seconde, avec un leveler actif aussi
  la réduction de gain et la corrélation. Si l'instance ne se manifeste plus, **Connexion perdue** s'affiche avec le
  dernier contact.
- **Jours, graphique, dépassements et événements :** comme dans SPL Sense, voir
  [Analyser les données de mesure]({{< relref "/docs/spl-sense/measurement-data" >}}).
- **Sur le côté :** accès (qui voit la mesure), Pro, photos et les autres mesures de la même mission de mesure.

Si quelque chose change dans SPL Sense pour la mesure, par exemple l'offset, la page se met à jour d'elle-même.

## Rapports et exports

| Quoi | Où | |
|---|---|---|
| CSV du jour | Bouton **CSV** du jour | gratuit |
| Rapport journalier (PDF) | Bouton **PDF** du jour | [Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}) |
| CSV de tous les jours (ZIP) | Menu **Mesures** › **Exporter tous les jours de mesure au format CSV** | gratuit |
| Rapport journalier avec dépassements | Menu **Mesures** › **Ouvrir le rapport journalier avec dépassements** | [Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}) |
| Rapport photos | Menu **Mesures** › **Ouvrir le rapport photos** | [Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}) |

Les rapports portent le logo de l'organisation à qui appartient la mesure.

## Clôturer

Menu **Mesures** › **Terminer la mesure**. Le cloud n'accepte ensuite plus de nouvelles données, même si SPL Sense
continue de mesurer. Les données jusqu'au moment de la clôture encore en transit arrivent quand même.

Si tu clôtures la mesure dans SPL Sense, elle est aussi clôturée dans le cloud. Elle se rouvre dans SPL Sense ou avec
la [commande à distance]({{< relref "/docs/spl-cloud-pro/remote-control" >}}).

## Supprimer

Tu supprimes une mesure clôturée dans le menu **Mesures** › **Supprimer la mesure**. Elle est définitivement retirée
du cloud. Dans SPL Sense, la mesure est conservée.

## Qui voit la mesure

| Qui | Peut |
|---|---|
| Propriétaire de la mesure (personne ou tous les membres de l'organisation) | tout : voir, accorder l'accès, clôturer, supprimer |
| Propriétaire de la mission de mesure, s'il est différent | voir, voir [Propriétaires différents]({{< relref "jobs#propriétaires-différents" >}}) |
| Personnes avec [accès en lecture]({{< relref "read-access" >}}) | voir |
| Destinataires d'un [lien partagé]({{< relref "/docs/spl-cloud-pro/shared-links" >}}) | voir, sans compte |
