---
title: Interface et recherche
linkTitle: Interface et recherche
weight: 15
description: >-
  Barre d'état, état de l'appareil, tableau de bord, menus et recherche.
---

## Barre d'état

La barre d'état se trouve en haut de chaque page :

- **Logo et chemin :** le logo mène au tableau de bord, le chemin à côté ramène aux pages de niveau supérieur.
- **État de l'appareil :** montre d'un coup d'œil ce qui se passe :
  - **Mesure en cours d'exécution** (vert, avec le LAeq 1 s actuel) : un clic ouvre la vue live.
  - **Arrêt de la mesure** ou **Capteur déconnecté** (rouge) : un clic ouvre la mesure active.
  - **Aucune mesure chargée**
- **Appareils connectés :** capteur, leveler et connexion au cloud, chacun avec son état. Si la commande à distance
  depuis SPL Cloud est autorisée, cela s'affiche aussi ici.
- **Recherche** (loupe), **Aide** (point d'interrogation, ouvre cette documentation) et **Paramètres** (roue dentée).

## Tableau de bord

Le tableau de bord liste toutes les mesures ouvertes sous forme de cartes. Chaque carte montre l'état de la mesure et les
valeurs des quatre derniers jours de mesure, colorées selon les seuils du profil de valeurs. En dessous, les mesures
clôturées figurent sous forme de liste courte.

En haut à droite, **Nouvelle mesure** crée une mesure et **Importer** restaure une mesure sauvegardée.

En bas du tableau de bord se trouvent le capteur connecté, un leveler connecté et, le cas échéant, un avis de mise à
jour.

## Page de la mesure

- **En-tête :** nom, état et les actions principales sous forme de boutons, par exemple **Démarrage** ou **Arrêter**.
  Toutes les autres actions se trouvent dans le menu **Mesure**. Les actions qui modifient définitivement la mesure
  (désactiver, clôturer) se trouvent à la fin du menu.
- **Bandeau en direct :** pendant la mesure, tu vois sous l'en-tête les valeurs sur 1 seconde et, s'il est actif, le
  leveler.
- **Jours et graphique :** sélectionne un jour de mesure ; le graphique montre son évolution. À côté du jour se trouvent
  les boutons **PDF** (rapport journalier) et **CSV**.
- **En dessous :** dépassements, événements, capteur et liaison cloud.

La signification des valeurs et des marquages est décrite sous [Données de mesure]({{< relref "measurement-data" >}}).

## États d'une mesure

| État | Signification |
|---|---|
| **Actif** | La mesure est chargée et prête. SPL Sense enregistre dès que tu démarres. Une seule mesure au plus est active à la fois. |
| **Mesure en cours d'exécution** | SPL Sense enregistre. |
| **Interrompu** | Le capteur ne fournit plus de données, par exemple parce qu'il a été débranché ou que l'ordinateur était en veille. La mesure reprend d'elle-même dès que le capteur fournit à nouveau des données. |
| **Arrêtée** | L'enregistrement est suspendu. |
| **Clôturée** | La mesure est verrouillée et peut seulement être consultée, exportée ou rouverte. |

Plus d'informations sous [Mesures]({{< relref "measurements" >}}).

## Recherche

Ouvre la recherche avec la loupe ou avec <kbd>Ctrl</kbd>+<kbd>K</kbd> (Mac : <kbd>⌘</kbd>+<kbd>K</kbd>). Elle trouve
les mesures (ouvertes et clôturées), les pages de paramètres, les profils de valeurs et les vues live. Les
touches fléchées sélectionnent un résultat, <kbd>Entrée</kbd> l'ouvre.

Tu trouves aussi les paramètres par mots-clés, par exemple « mot de passe » pour le code PIN opérateur ou « limiteur »
pour le leveler.

## Utilisation sur tablette et téléphone

En mode serveur web (Linux), tu utilises SPL Sense dans le navigateur, aussi depuis une tablette ou un téléphone.
L'interface s'adapte aux petits écrans : le chemin dans la barre d'état devient un lien de retour, les listes s'affichent
les unes sous les autres.
