---
title: Démarrage rapide
linkTitle: Démarrage rapide
weight: 10
description: >-
  Votre première mesure en quelques étapes : installer SPL Sense, créer une mesure, régler le décalage, mesurer,
  archiver dans SPL Cloud et télécharger un rapport PDF.
aliases:
  - /fr/docs/quickstartsense/
  - /fr/docs/quickstartcloud/
---

Ce guide vous mène pas à pas à votre première mesure. Aucune connaissance préalable n'est nécessaire.

**Ce dont vous avez besoin :**

- un ordinateur sous Windows ou macOS
- un capteur SPL Tools avec câble USB
- pour SPL Cloud (étape 8) : Internet et une adresse e-mail

## 1. Installer SPL Sense

1. Téléchargez SPL Sense pour votre système d'exploitation :
   - [Windows](https://r.spl.swiss/dl/splsense/win-x64/SPLSenseSetup.exe)
   - [macOS avec puce Apple (M1 et plus récent)](https://r.spl.swiss/dl/splsense/osx-arm64/SPLSense-osx-arm64-Setup.pkg)
   - [macOS avec processeur Intel](https://r.spl.swiss/dl/splsense/osx-x64/SPLSense-osx-x64-Setup.pkg)
2. Ouvrez le fichier téléchargé et suivez le programme d'installation.
3. Lancez SPL Sense. Au premier démarrage, un avis s'affiche. Lisez-le et cliquez sur **Accepter et continuer**.

SPL Sense se met à jour tout seul : lorsqu'une nouvelle version est disponible, un avis s'affiche.

## 2. Brancher le capteur

Branchez le capteur en USB. Un seul capteur peut être branché par ordinateur. La barre d'état en haut à droite indique
si SPL Sense reconnaît le capteur.

Si la barre d'état affiche **Capteur déconnecté**, débranchez le câble et rebranchez-le.

{{% alert title="Calibration" color="info" %}}
Si la calibration du capteur a expiré, SPL Sense vous avertit au démarrage de la mesure. Vous pouvez quand même
mesurer, mais les valeurs mesurées seront marquées. Plus d'informations sous
[Capteur et calibration]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}).
{{% /alert %}}

## 3. Créer une mesure

Une **mesure** correspond à un point de mesure, par exemple « Scène principale Openair 2026 ». Elle peut durer plusieurs
jours.

1. Dans la vue d'ensemble, cliquez sur **Nouvelle mesure**.
2. Remplissez les champs :
   - **Nom** : c'est ainsi que la mesure apparaît dans la vue d'ensemble et dans le rapport.
   - **Profil de valeur** : définit quelles valeurs sont calculées et quelles limites s'appliquent. Pour les
     manifestations en Suisse, choisissez le modèle correspondant à la catégorie annoncée : **VNISSG 93dBA**,
     **VNISSG 96dBA** ou **VNISSG 100dBA**. En Allemagne, choisissez **DIN 15905-5**. Contenu des modèles :
     [Modèles pour l'O-LRNIS et la DIN 15905-5]({{< relref "/docs/basics/templates-vnissg-din" >}}).
   - **Limite journalière** : l'heure à laquelle un jour de mesure se termine. Choisissez une heure environ deux heures
     après la fin de la manifestation, au plus tard 06:00. Ainsi, une soirée qui dure jusqu'à 03:00 tombe dans *un*
     seul jour et non dans deux.
   - **transmission au Cloud (Cloud Uplink)** : laissez désactivé pour l'instant. Vous l'activerez dès que SPL Sense
     sera connecté au cloud (étape 8).
3. Cliquez sur **Créer une mesure**.

## 4. Activer la mesure

Une seule mesure peut être active à la fois. La mesure active est celle dans laquelle SPL Sense enregistre.

Ouvrez la mesure et cliquez sur **Activer la mesure**.

## 5. Régler le décalage

La valeur limite s'applique à l'**endroit le plus bruyant du public**, à hauteur d'oreille. En général, vous ne pouvez
pas y placer le capteur. Vous mesurez donc à un autre endroit et compensez la différence avec le **décalage** (offset).
Contexte : [Point de mesure et décalage]({{< relref "/docs/basics/measuring-point-and-offset" >}}).

Pour régler le décalage (la mesure doit être active et arrêtée, le capteur branché) :

1. Dans le menu **Mesure**, ouvrez **Réglages des décalages (Offset)**.
2. Diffusez du bruit rose (pink noise) sur la sonorisation, aussi fort que pendant la manifestation.
3. Cliquez sur **Réinitialisation des valeurs maximales**.
4. Parcourez la zone du public avec le capteur, y compris l'avant et les côtés. SPL Sense retient la valeur la plus
   élevée.
5. Placez le capteur à son point de mesure, par exemple à la table de mixage.
6. Réglez le **Décalage (Offset)** de sorte que **Niveau avec décalage (Offset) appliqué** soit aussi élevé que la valeur
   **Max** retenue.
7. Cliquez sur **Sauvegarder**.

Rien n'est enregistré pendant le réglage des décalages. Si vous connaissez déjà le décalage, par exemple grâce à un
sonomètre portable, saisissez-le directement sous **Modifier la mesure**.

## 6. Mesurer

1. Cliquez sur **Démarrage**. SPL Sense enregistre maintenant. Les premières valeurs apparaissent après la première
   minute complète.
2. Sous le titre de la page, vous voyez les niveaux actuels. Le graphique montre l'évolution de la journée.
3. Pour un affichage grand et bien lisible, par exemple pour le DJ ou les techniciens, cliquez sur **Écran en direct**.
4. Une fois la manifestation terminée, cliquez sur **Arrêter** et confirmez.

{{< bild id="sense-messung-laeuft" >}}

Si le capteur est débranché pendant la mesure, SPL Sense affiche **Interrompu**. Dès que vous le rebranchez, la mesure
reprend d'elle-même.

## 7. Modifier la mesure

Vous pouvez modifier ultérieurement le nom, la limite journalière, les décalages et le profil de valeur, tant que la
mesure est arrêtée : menu **Mesure** › **Modifier la mesure**, modifiez et **Sauvegarder**.

Si vous modifiez le profil de valeur ou la limite journalière, SPL Sense recalcule les limites et les jours de mesure.

## 8. Se connecter à SPL Cloud

Dans SPL Cloud, vos mesures sont archivées en toute sécurité. Vous les consultez aussi en déplacement et pouvez les
partager. Les fonctions de base sont gratuites.

**Créer un compte** (une seule fois) :

1. Ouvrez [spl.cloud](https://spl.cloud) dans le navigateur. La page de connexion est toujours en anglais.
2. Cliquez sur **Sign up now**, saisissez votre adresse e-mail et cliquez sur **Send verification code**.
3. Saisissez le code reçu par e-mail et confirmez.
4. Complétez le mot de passe et le nom, puis terminez avec **Create**.

**Enregistrer SPL Sense** (une fois par ordinateur) :

1. Dans SPL Sense : **Paramètres** › **Cloud** › **Instance de registre**.
2. Cliquez sur le lien affiché ou scannez le code QR avec votre téléphone. Le code n'est valable que peu de temps ;
   s'il a expiré, demandez-en un nouveau avec **Obtenir un nouveau code**.
3. Dans SPL Cloud : sous **Propriétaire**, choisissez à qui appartient cet ordinateur : à vous personnellement ou à une
   organisation dont vous êtes membre. Cliquez sur **Sauvegarder**.
4. SPL Sense affiche maintenant **L'instance est enregistrée**.

**Transférer la mesure dans le cloud :**

1. Ouvrez la mesure dans SPL Sense, menu **Mesure** › **Modifier la mesure**.
2. Activez **transmission au Cloud (Cloud Uplink)** et sauvegardez.

SPL Sense téléverse maintenant toutes les données de la mesure, y compris celles déjà enregistrées. Si la connexion
Internet est interrompue, SPL Sense continue de mesurer et rattrape le téléversement plus tard. Dans SPL Cloud, la
mesure apparaît dans la vue d'ensemble sous les mesures indépendantes.

## 9. Télécharger un rapport PDF

Pour chaque jour de mesure, SPL Sense propose un rapport journalier en PDF.

1. Ouvrez la mesure dans SPL Sense.
2. Sélectionnez le jour souhaité.
3. Cliquez sur **PDF** à côté du jour.

Avec **CSV** juste à côté, vous exportez les valeurs du jour, par exemple pour Excel.

Dans SPL Cloud, le rapport journalier est disponible avec [SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}).

## Et ensuite ?

- Quand la manifestation est entièrement terminée, clôturez la mesure : menu **Mesure** › **Mesure complète**. Elle ne
  peut ensuite plus être modifiée. Vous pouvez la rouvrir si nécessaire.
- [Point de mesure et décalage]({{< relref "/docs/basics/measuring-point-and-offset" >}}) : bien mesurer selon l'O-LRNIS et la DIN 15905-5
- [Accès en lecture]({{< relref "/docs/spl-cloud/read-access" >}}) : donner un aperçu à l'organisateur ou à l'autorité
- [Leveler]({{< relref "/docs/spl-sense/leveler" >}}) : maintenir automatiquement le niveau sous la limite
