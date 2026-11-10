---
title: Démarrage rapide
linkTitle: Démarrage rapide
weight: 10
description: >-
  Ta première mesure en quelques étapes : installer SPL Sense, créer une mesure, régler l'offset, mesurer,
  archiver dans SPL Cloud et télécharger un rapport PDF.
aliases:
  - /fr/docs/quickstartsense/
  - /fr/docs/quickstartcloud/
---

Ce guide te mène pas à pas à ta première mesure. Aucune connaissance préalable n'est nécessaire.

**Ce dont tu as besoin :**

- un ordinateur sous Windows ou macOS
- un capteur SPL Tools avec câble USB
- pour SPL Cloud (étape 8) : Internet et une adresse e-mail

## 1. Installer SPL Sense

1. Télécharge SPL Sense pour ton système d'exploitation :
   - [Windows](https://r.spl.swiss/dl/splsense/win-x64/SPLSenseSetup.exe)
   - [macOS avec puce Apple (M1 et plus récent)](https://r.spl.swiss/dl/splsense/osx-arm64/SPLSense-osx-arm64-Setup.pkg)
   - [macOS avec processeur Intel](https://r.spl.swiss/dl/splsense/osx-x64/SPLSense-osx-x64-Setup.pkg)
2. Ouvre le fichier téléchargé et suis le programme d'installation.
3. Lance SPL Sense. Au premier démarrage, un avis s'affiche. Lis-le et clique sur **Accepter et continuer**.

SPL Sense se met à jour tout seul : lorsqu'une nouvelle version est disponible, un avis s'affiche.

## 2. Brancher le capteur

Branche le capteur en USB. Un seul capteur peut être branché par ordinateur. La barre d'état en haut à droite indique
si SPL Sense reconnaît le capteur.

Si la barre d'état affiche **Capteur déconnecté**, débranche le câble et rebranche-le.

{{% alert title="Calibration" color="info" %}}
Si la calibration du capteur a expiré, SPL Sense t'avertit au démarrage de la mesure. Tu peux quand même
mesurer, mais les valeurs mesurées seront marquées. Plus d'informations sous
[Capteur et calibration]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}).
{{% /alert %}}

## 3. Créer une mesure

Une **mesure** correspond à un point de mesure, par exemple « Scène principale Openair 2026 ». Elle peut durer plusieurs
jours.

1. Dans le tableau de bord, clique sur **Nouvelle mesure**.
2. Remplis les champs :
   - **Nom** : c'est ainsi que la mesure apparaît dans le tableau de bord et dans le rapport.
   - **Profil de valeurs** : définit quelles valeurs sont calculées et quelles limites s'appliquent. Pour les
     manifestations en Suisse, choisis le modèle correspondant à la catégorie annoncée : **VNISSG 93dBA**,
     **VNISSG 96dBA** ou **VNISSG 100dBA**. En Allemagne, choisis **DIN 15905-5**. Contenu des modèles :
     [Modèles pour l'O-LRNIS et la DIN 15905-5]({{< relref "/docs/basics/templates-vnissg-din" >}}).
   - **Limite journalière** : l'heure à laquelle un jour de mesure se termine. Choisis une heure environ deux heures
     après la fin de la manifestation, au plus tard 06:00. Ainsi, une soirée qui dure jusqu'à 03:00 tombe dans *un*
     seul jour et non dans deux.
   - **Liaison cloud** : laisse désactivée pour l'instant. Tu l'activeras dès que SPL Sense
     sera connecté au cloud (étape 8).
3. Clique sur **Créer une mesure**.

## 4. Activer la mesure

Une seule mesure peut être active à la fois. La mesure active est celle dans laquelle SPL Sense enregistre.

Ouvre la mesure et clique sur **Activer la mesure**.

## 5. Régler l'offset

La valeur limite s'applique à l'**endroit le plus bruyant du public**, à hauteur d'oreille. En général, tu ne peux
pas y placer le capteur. Tu mesures donc à un autre endroit et compenses la différence avec l'**offset**.
Contexte : [Point de mesure et offset]({{< relref "/docs/basics/measuring-point-and-offset" >}}).

Pour régler l'offset (la mesure doit être active et arrêtée, le capteur branché) :

1. Dans le menu **Mesure**, ouvre **Offset tune**.
2. Diffuse du bruit rose (pink noise) sur la sonorisation, aussi fort que pendant la manifestation.
3. Clique sur **Réinitialiser max**.
4. Parcours la zone du public avec le capteur, y compris l'avant et les côtés. SPL Sense retient la valeur la plus
   élevée.
5. Place le capteur à son point de mesure, par exemple à la table de mixage.
6. Règle l'**Offset** de sorte que **Niveau incl. offset** soit aussi élevé que la valeur
   **Max** retenue.
7. Clique sur **Sauvegarder**.

Rien n'est enregistré pendant le réglage des offsets. Si tu connais déjà l'offset, par exemple grâce à un
sonomètre portable, saisis-le directement sous **Modifier la mesure**.

## 6. Mesurer

1. Clique sur **Démarrage**. SPL Sense enregistre maintenant. Les premières valeurs apparaissent après la première
   minute complète.
2. Sous le titre de la page, tu vois les niveaux actuels. Le graphique montre l'évolution de la journée.
3. Pour un affichage grand et bien lisible, par exemple pour le DJ ou les techniciens, clique sur **Vue live**.
4. Une fois la manifestation terminée, clique sur **Arrêter** et confirme.

{{< bild id="sense-messung-laeuft" >}}

Si le capteur est débranché pendant la mesure, SPL Sense affiche **Interrompu**. Dès que tu le rebranches, la mesure
reprend d'elle-même.

## 7. Modifier la mesure

Tu peux modifier ultérieurement le nom, la limite journalière, les offsets et le profil de valeurs, tant que la
mesure est arrêtée : menu **Mesure** › **Modifier la mesure**, modifie et **Sauvegarder**.

Si tu modifies le profil de valeurs ou la limite journalière, SPL Sense recalcule les limites et les jours de mesure.

## 8. Se connecter à SPL Cloud

Dans SPL Cloud, tes mesures sont archivées en toute sécurité. Tu les consultes aussi en déplacement et peux les
partager. Les fonctions de base sont gratuites.

**Créer un compte** (une seule fois) :

1. Ouvre [spl.cloud](https://spl.cloud) dans le navigateur. La page de connexion est toujours en anglais.
2. Clique sur **Sign up now**, saisis ton adresse e-mail et clique sur **Send verification code**.
3. Saisis le code reçu par e-mail et confirme.
4. Complète le mot de passe et le nom, puis termine avec **Create**.

**Enregistrer SPL Sense** (une fois par ordinateur) :

1. Dans SPL Sense : **Paramètres** › **Cloud** › **Instance de registre**.
2. Clique sur le lien affiché ou scanne le code QR avec ton téléphone. Le code n'est valable que peu de temps ;
   s'il a expiré, demandes-en un nouveau avec **Obtenir un nouveau code**.
3. Dans SPL Cloud : sous **Propriétaire**, choisis à qui appartient cet ordinateur : à toi personnellement ou à une
   organisation dont tu es membre. Clique sur **Sauvegarder**.
4. SPL Sense affiche maintenant **L'instance est enregistrée**.

**Transférer la mesure dans le cloud :**

1. Ouvre la mesure dans SPL Sense, menu **Mesure** › **Modifier la mesure**.
2. Active la **liaison cloud** et sauvegarde.

SPL Sense téléverse maintenant toutes les données de la mesure, y compris celles déjà enregistrées. Si la connexion
Internet est interrompue, SPL Sense continue de mesurer et rattrape le téléversement plus tard. Dans SPL Cloud, la
mesure apparaît dans le tableau de bord sous les mesures autonomes.

## 9. Télécharger un rapport PDF

Pour chaque jour de mesure, SPL Sense propose un rapport journalier en PDF.

1. Ouvre la mesure dans SPL Sense.
2. Sélectionne le jour souhaité.
3. Clique sur **PDF** à côté du jour.

Avec **CSV** juste à côté, tu exportes les valeurs du jour, par exemple pour Excel.

Dans SPL Cloud, le rapport journalier est disponible avec [SPL Cloud Pro]({{< relref "/docs/spl-cloud-pro/reports-and-pictures" >}}).

## Et ensuite ?

- Quand la manifestation est entièrement terminée, clôture la mesure : menu **Mesure** › **Mesure complète**. Elle ne
  peut ensuite plus être modifiée. Tu peux la rouvrir si nécessaire.
- [Point de mesure et offset]({{< relref "/docs/basics/measuring-point-and-offset" >}}) : bien mesurer selon l'O-LRNIS et la DIN 15905-5
- [Accès en lecture]({{< relref "/docs/spl-cloud/read-access" >}}) : donner un aperçu à l'organisateur ou à l'autorité
- [Leveler]({{< relref "/docs/spl-sense/leveler" >}}) : maintenir automatiquement le niveau sous la limite
