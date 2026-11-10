---
title: Paramètres
linkTitle: Paramètres
weight: 80
description: >-
  Code PIN opérateur, connexion à SPL Cloud et commande à distance, API, langue.
---

Ouvrez les paramètres avec la roue dentée en haut à droite. Chaque ligne indique l'état actuel.

| Groupe | Paramètres |
|---|---|
| **Mesure** | [Profils de valeur]({{< relref "value-profiles" >}}), [Écrans en direct]({{< relref "live-screen" >}}), [Mode autonome]({{< relref "autonomous-mode" >}}) |
| **Appareil** | [Informations du capteur]({{< relref "sensor-and-calibration" >}}), [Leveler]({{< relref "leveler#configurer-le-l1-lui-même" >}}), [Mise à jour]({{< relref "installation-and-updates#mises-à-jour" >}}) |
| **Accès et connexions** | Code PIN opérateur, Cloud, API, Langue |
| **A propos de** | Version, notes de version, contact, protection des données, licences open source |

## Code PIN opérateur

Un code PIN opérateur protège SPL Sense contre les modifications. Sans code PIN, toute personne ayant accès à SPL Sense
peut tout modifier.

1. **Paramètres** › **Code PIN opérateur**.
2. Saisissez un **Nouveau code PIN** (4 à 8 chiffres) et répétez-le.
3. **Sauvegarder**.

Avec un code PIN défini :

- toutes les pages sauf l'écran en direct sont verrouillées. SPL Sense affiche **SPL Sense est verrouillé** et demande
  le code PIN.
- SPL Sense demande aussi le code PIN en quittant l'écran en direct et le plein écran.
- le code PIN s'applique dans l'application et dans le navigateur (mode serveur web).

**Supprimer le code PIN** lève la protection.

## SPL Cloud

Sous **Paramètres** › **Cloud**, vous connectez SPL Sense à SPL Cloud. Une installation enregistrée s'appelle une
**instance** dans le cloud.

### Enregistrer

1. **Instance de registre**. SPL Sense a besoin d'Internet pour cela.
2. Ouvrez le lien affiché ou scannez le code QR avec un autre appareil. Le code n'est valable que peu de temps ;
   **Obtenir un nouveau code** vous en fournit un nouveau.
3. Connectez-vous à SPL Cloud et confirmez l'enregistrement. Choisissez le **Propriétaire** : vous personnellement ou une
   organisation dont vous êtes membre. Voir [Organisations]({{< relref "/docs/spl-cloud/organizations" >}}).

La page affiche ensuite **L'instance est enregistrée** avec l'ID de l'instance, l'hôte, le propriétaire et l'état de la
connexion (**En ligne**, **En cours de connexion...**, **Hors ligne**).

Les mesures transmises au cloud se définissent pour chaque mesure avec la **transmission au Cloud (Cloud Uplink)**, voir
[Mesures]({{< relref "measurements#modifier" >}}).

### Désenregistrer

**Instance non enregistrée** (bouton de désenregistrement) déconnecte SPL Sense du cloud. La transmission au cloud est
désactivée pour toutes les mesures ; ce qui est déjà dans le cloud y reste. Après un nouvel enregistrement, vous
réactivez la transmission pour chaque mesure.

Si la page affiche **Échec de l'authentification !**, désenregistrez l'instance et enregistrez-la à nouveau.

### Autoriser la commande à distance

Avec **Autoriser la commande à distance**, les personnes ayant accès à cette instance dans SPL Cloud peuvent démarrer et
arrêter, changer et créer des mesures et modifier les décalages, le leveler et le profil de valeur, tant que SPL Sense
est en ligne. La calibration et les mises à jour ne sont jamais possibles à distance.

La commande à distance est désactivée par défaut. Lorsqu'elle est activée, la barre d'état l'indique, et chaque commande
du cloud apparaît sous forme de message et dans les événements de la mesure, avec le nom de la personne.

Dans le cloud, la commande à distance nécessite [SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/remote-control" >}}) sur
la mesure.

## API

L'API SPL Sense permet de surveiller et commander SPL Sense et de connecter des processeurs audio externes comme leveler.
Elle est désactivée par défaut. Détails sous [API SPL Sense]({{< relref "/docs/developers/sense-api" >}}).

## Langue

Allemand, anglais, français ou **système par défaut**.

## A propos de

Version, notes de version (en anglais), contact, déclaration de protection des données et licences open source utilisées.
