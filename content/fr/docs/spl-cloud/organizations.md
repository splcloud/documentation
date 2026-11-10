---
title: Organisations et rôles
linkTitle: Organisations et rôles
weight: 20
description: >-
  À quoi servent les organisations et ce que peuvent faire propriétaires et membres.
---

## Pourquoi des organisations ?

Tout dans SPL Cloud a un **propriétaire** : les mesures, les événements et les instances SPL Sense. Le propriétaire est
soit une personne, soit une **organisation**.

Une organisation est un groupe de personnes qui accèdent ensemble aux mesures : une entreprise, un club, un festival ou
une autorité. Tous les membres voient les mesures de l'organisation, et lorsque quelqu'un quitte l'entreprise, les
données restent à l'organisation.

Une personne peut être membre de plusieurs organisations, par exemple en tant que technicien indépendant pour plusieurs
entreprises. Lors de la création d'un événement ou de l'enregistrement d'une instance, vous choisissez à qui elle doit
appartenir.

## Rôles

| | Propriétaire | Membre |
|---|---|---|
| Voir les mesures et événements de l'organisation | ✓ | ✓ |
| Créer des événements, attribuer des mesures | ✓ | ✓ |
| Enregistrer des instances SPL Sense pour l'organisation | ✓ | ✓ |
| Accorder un accès en lecture | ✓ | ✓ |
| Commander à distance les instances de l'organisation (avec Pro) | ✓ | ✓ |
| Ajouter et supprimer des membres, changer les rôles | ✓ | |
| Modifier le nom, l'adresse et le logo de l'organisation | ✓ | |
| Gérer le moyen de paiement et les factures | ✓ | |

Une organisation a toujours au moins un propriétaire.

Les personnes qui doivent seulement consulter les données, par exemple un organisateur ou une autorité, ne deviennent
pas membres mais reçoivent un [accès en lecture]({{< relref "read-access" >}}).

## Créer une organisation

1. **Paramètres** › **Créer une organisation**.
2. Saisissez le **Nom**, l'adresse et l'**Adresse e-mail**. La **Langue de facturation** détermine la langue des
   factures et des pages de paiement.
3. **Sauvegarder**. Vous êtes maintenant propriétaire de l'organisation.

## Gérer les membres

Sur la page de l'organisation :

1. **Ajouter un membre**.
2. Recherchez la personne par son adresse e-mail. Elle doit déjà avoir un compte SPL Cloud.
3. Choisissez le **Rôle** : **Propriétaire** ou **Membre**. **Sauvegarder**.

Un clic sur un membre l'ouvre : changer le rôle ou **Supprimer le membre**.

## Logo

Le logo de l'organisation apparaît dans les rapports PDF de ses mesures. **Télécharger un logo** (fichier image jusqu'à
5 Mo), **Changer le logo** ou **Supprimer le logo**.

## Configurations typiques

**Personne seule :** une technicienne avec son propre capteur et son ordinateur portable, sans organisation. L'instance
et les mesures lui appartiennent personnellement. Elle donne à l'organisateur un accès en lecture à la mesure.

**Entreprise technique :** l'entreprise a une organisation ; tous les ordinateurs portables et Raspberry Pi sont
enregistrés comme instances de l'organisation. Tous les employés sont membres et voient toutes les mesures. Lors d'un
festival, un événement regroupe les points de mesure ; l'autorité reçoit un accès en lecture à tout l'événement,
l'exploitant d'une scène à sa mesure.

**Appareils loués :** si un appareil est loué et doit appartenir à l'entreprise locataire pendant la durée de la
location, changez le propriétaire de l'instance, voir
[Instances SPL Sense]({{< relref "instances#changer-de-propriétaire" >}}).
