---
title: Prix et facturation
linkTitle: Prix et facturation
weight: 10
description: >-
  Ce que coûte Pro, comment l'activer et comment il est facturé.
---

## Le principe

- Pro s'applique **par mesure**. Tu l'actives pour une seule mesure ou pour toutes les mesures d'une mission de mesure.
- Tu paies **par jour de mesure**. Un jour de mesure compte si la mesure a enregistré plus d'une heure de données ce
  jour-là. La limite journalière de la mesure fait foi.
- Il existe un **plafond** par mesure et par an. Une fois atteint, Pro continue gratuitement jusqu'à la fin de l'année
  de mesure.
- Pas d'abonnement, pas de frais de base. Une mesure sans données ne coûte rien.

## Prix

Tu trouves les prix actuels sur [spl.swiss](https://spl.swiss/products/cloudpro). Le modèle :

- Les premiers jours de mesure d'une mesure coûtent plus cher ; à partir du 7e jour de mesure, un prix journalier plus
  bas s'applique.
- Il existe un plafond par mesure et par **année de mesure**. Une fois atteint, Pro continue gratuitement jusqu'à la fin
  de l'année de mesure.
- L'année de mesure dure 365 jours à partir du premier jour de mesure de la mesure (si elle n'a pas encore de données :
  à partir du jour de l'activation). Ensuite, une nouvelle année de mesure commence et le décompte repart du premier
  jour.
- Les prix s'entendent hors TVA.

Avant chaque activation, SPL Cloud affiche le prix et, si des données ont déjà été enregistrées, le montant exact. Si
les prix changent, une mesure déjà activée conserve le prix en vigueur au moment de son activation.

## Condition préalable : moyen de paiement

Avant d'activer Pro, le propriétaire de la mesure a besoin d'un moyen de paiement et d'une adresse de facturation.
L'adresse de facturation est nécessaire pour la TVA.

| Propriétaire de la mesure | Où le configurer | Qui |
|---|---|---|
| toi personnellement | **Paramètres** › **Paiement** | toi |
| une organisation | page de l'organisation › **Facturation** | un propriétaire de l'organisation |

Pour Pro sur une mission de mesure, c'est le propriétaire de la mission de mesure qui a besoin du moyen de paiement.

1. Choisis la **Devise de facturation** : CHF ou EUR. Elle ne peut plus être modifiée ensuite.
2. Clique sur **Configurer le paiement**. Le paiement passe par le service de paiement Stripe ; tu y choisis le
   moyen de paiement et saisis l'adresse de facturation. Tu y vois aussi les moyens de paiement disponibles.
3. De retour dans SPL Cloud, **Moyen de paiement et adresse de facturation enregistrés.** s'affiche.

La facture est établie au nom de la personne ou de l'organisation à qui appartient le moyen de paiement. **Gérer la
facturation** ouvre tes factures chez Stripe et permet de changer le moyen de paiement. Pour une organisation, la
**Langue de facturation** dans les détails de l'organisation détermine la langue des factures.

## Activer Pro

### Pour une mesure

1. Ouvre la mesure. Sur le côté, **Passez à Pro !** présente les fonctions incluses et le prix.
2. Clique sur **Activer Pro** et confirme.

### Pour une mission de mesure

Sur la page de la mission de mesure, **Activer Pro pour le job**. Toutes les mesures de la mission de mesure sont alors Pro, y compris
celles ajoutées plus tard. Chaque mesure reste facturée individuellement selon ses jours de mesure, avec son propre
plafond.

C'est le **propriétaire de la mission de mesure** qui paie, aussi pour les mesures qui appartiennent à quelqu'un d'autre. Les
mesures pour lesquelles leur propriétaire a déjà activé Pro directement restent payées par celui-ci. Détails sous
[Propriétaires différents]({{< relref "/docs/spl-cloud/jobs#propriétaires-différents" >}}).

### Heure d'essai gratuite

La première fois que tu actives directement une mesure, tu disposes d'une heure pour essayer. Il n'y a pas d'heure
d'essai lors d'une activation via la mission de mesure. Si tu désactives Pro dans cette heure, cela ne coûte rien, pas même
pour les jours déjà enregistrés. Pendant l'heure d'essai, la mesure affiche **Heure d'essai gratuite en cours**.

### Facturation rétroactive

Pro est facturé à partir du **premier jour de mesure de la mesure**, et non à partir du moment de l'activation. Si tu
actives Pro pour une mesure qui tourne depuis trois jours, ces trois jours comptent. SPL Cloud t'indique le montant
exact avant l'activation.

## Désactiver Pro

Avec **Désactiver Pro** sur la mesure ou **Désactiver Pro pour le job** sur la mission de mesure :

- Les fonctions Pro sont immédiatement bloquées. Les liens partagés ne fonctionnent plus, les alarmes ne sont plus
  évaluées.
- Les montants déjà cumulés sont facturés avec la prochaine facture. Il n'y a pas de remboursement.
- Les jours de mesure suivants ne sont plus comptés. La mesure continue d'enregistrer normalement.
- Les mesures activées directement restent actives lorsque tu désactives Pro pour la mission de mesure.

### Réactiver

Si tu réactives Pro plus tard, l'année de mesure se poursuit sans interruption, comme s'il n'y avait pas eu de pause.
**Les jours de mesure de la pause sont comptés rétroactivement.** Il n'y a plus d'heure d'essai ; la facturation
commence immédiatement. Désactiver et réactiver à répétition ne permet donc pas d'économiser.

## Facturation

La facturation a lieu une fois par mois, le dernier jour du mois civil, pour tous les jours de mesure cumulés pendant ce
mois. Le moyen de paiement enregistré est débité automatiquement.

Si le débit échoue, le service de paiement réessaie plusieurs fois. Si le paiement échoue définitivement, les fonctions
Pro des mesures concernées sont bloquées jusqu'à ce que le paiement soit réglé.

## Garder un œil sur les coûts

- **Coûts cumulés** dans les paramètres de paiement : toutes les mesures Pro avec leurs coûts de l'année en cours.
- **Détails de la licence** d'une mesure (via **Voir les détails** sous Pro) : année de mesure, jours de mesure
  facturables, état par rapport au plafond, montants déjà facturés, historique de facturation et tous les jours de
  mesure avec leur durée enregistrée.
- **Détails de la licence** d'une mission de mesure : total de toutes ses mesures.

Seules les personnes autorisées à gérer la mission de mesure ou la mesure voient les coûts.
