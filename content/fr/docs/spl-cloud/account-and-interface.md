---
title: Compte et interface
linkTitle: Compte et interface
weight: 10
description: >-
  Compte, profil, tableau de bord, archives et recherche.
---

## Compte

Tu crées un compte sur [spl.cloud](https://spl.cloud) avec ton adresse e-mail, comme décrit dans le
[démarrage rapide]({{< relref "/docs/quick-start#8-se-connecter-à-spl-cloud" >}}). Un compte est personnel : crées-en
un pour chaque personne et travaille en équipe avec des [organisations]({{< relref "organizations" >}}) plutôt que de
partager un compte.

### Profil

**Paramètres** › **Mon profil** › **Modifier le profil** :

- **Prénom**, **Nom**, **Nom affiché** (ce que les autres voient)
- **Nom de l'entreprise** et adresse
- **Téléphone** : pour les alarmes SMS. Le format national fonctionne aussi (079 …) ; le cloud le convertit au format
  international.

### Langue

**Paramètres** › **Langue** : **Navigateur par défaut**, allemand, allemand (Suisse), anglais ou français.

## Barre d'état

- **Instances SPL Sense** : par exemple « SPL Sense 3 sur 5 en ligne ». Un clic affiche toutes tes instances avec leur
  état, leur activité actuelle et, pendant la mesure, le LAeq 1 s. Les instances qui ont perdu la connexion pendant une
  mesure sont marquées en rouge. Voir [Instances SPL Sense]({{< relref "instances" >}}).
- **Recherche** (loupe), **Aide** (point d'interrogation) et **Paramètres** (roue dentée)

## Tableau de bord

Le tableau de bord affiche **Missions de mesure et mesures** :

- les **Missions de mesure** avec leurs mesures
- les **Mesures autonomes** : mesures qui ne sont attribuées à aucune mission de mesure. Une nouvelle mesure de SPL Sense
  apparaît d'abord ici.
- en bas, la liste de tes **Instances SPL Sense**

Chaque mesure affiche son état et les valeurs des derniers jours, colorées selon les seuils du profil de valeurs. Si une
mesure est activée avec Pro, c'est indiqué.

**Créer une nouvelle mission de mesure** crée un [mission de mesure]({{< relref "jobs" >}}).

## Archives

Dix jours après sa date de fin, une mission de mesure passe aux **Archives** ; auparavant, le tableau de bord indique dans
combien de jours cela se produira. Tu accèdes aux archives via **Missions de mesure et mesures précédentes** en bas de la vue
d'ensemble. Les missions de mesure et mesures archivées sont conservés intégralement.

## Recherche

Avec la loupe ou <kbd>Ctrl</kbd>+<kbd>K</kbd> (Mac : <kbd>⌘</kbd>+<kbd>K</kbd>), tu recherches des mesures, des
missions de mesure, des instances, des organisations et des paramètres. Les entrées archivées apparaissent en dernier et sont
marquées. Tu trouves aussi les instances par leur système d'exploitation, par exemple « mac » ou « linux ». La
recherche n'affiche que ce que tu as le droit d'ouvrir.

## Données en direct

Les pages avec des mesures en cours se mettent à jour d'elles-mêmes. Si la connexion est interrompue, le cloud affiche
**Connexion à SPL Cloud perdue** et se reconnecte ; **Reconnecter maintenant** le fait immédiatement.
