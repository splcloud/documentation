---
title: Compte et interface
linkTitle: Compte et interface
weight: 10
description: >-
  Compte, profil, vue d'ensemble, archives et recherche.
---

## Compte

Vous créez un compte sur [spl.cloud](https://spl.cloud) avec votre adresse e-mail, comme décrit dans le
[démarrage rapide]({{< relref "/docs/quick-start#8-se-connecter-à-spl-cloud" >}}). Un compte est personnel : créez-en
un pour chaque personne et travaillez en équipe avec des [organisations]({{< relref "organizations" >}}) plutôt que de
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

- **Instances SPL Sense** : par exemple « SPL Sense 3 sur 5 en ligne ». Un clic affiche toutes vos instances avec leur
  état, leur activité actuelle et, pendant la mesure, le LAeq 1 s. Les instances qui ont perdu la connexion pendant une
  mesure sont marquées en rouge. Voir [Instances SPL Sense]({{< relref "instances" >}}).
- **Recherche** (loupe), **Aide** (point d'interrogation) et **Paramètres** (roue dentée)

## Vue d'ensemble

La vue d'ensemble affiche **Événements et mesures** :

- les **Événements** avec leurs mesures
- les **Mesures indépendantes** : mesures qui ne sont attribuées à aucun événement. Une nouvelle mesure de SPL Sense
  apparaît d'abord ici.
- en bas, la liste de vos **Instances SPL Sense**

Chaque mesure affiche son état et les valeurs des derniers jours, colorées selon les seuils du profil de valeur. Si une
mesure est activée avec Pro, c'est indiqué.

**Créer un nouvel événement** crée un [événement]({{< relref "jobs" >}}).

## Archives

Dix jours après sa date de fin, un événement passe aux **Archives** ; auparavant, la vue d'ensemble indique dans
combien de jours cela se produira. Vous accédez aux archives via **événements précédents et mesures** en bas de la vue
d'ensemble. Les événements et mesures archivés sont conservés intégralement.

## Recherche

Avec la loupe ou <kbd>Ctrl</kbd>+<kbd>K</kbd> (Mac : <kbd>⌘</kbd>+<kbd>K</kbd>), vous recherchez des mesures, des
événements, des instances, des organisations et des paramètres. Les entrées archivées apparaissent en dernier et sont
marquées. Vous trouvez aussi les instances par leur système d'exploitation, par exemple « mac » ou « linux ». La
recherche n'affiche que ce que vous avez le droit d'ouvrir.

## Données en direct

Les pages avec des mesures en cours se mettent à jour d'elles-mêmes. Si la connexion est interrompue, le cloud affiche
**Connexion à SPL Cloud perdue** et se reconnecte ; **Reconnecter maintenant** le fait immédiatement.
