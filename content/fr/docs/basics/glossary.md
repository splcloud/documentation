---
title: Glossaire
linkTitle: Glossaire
weight: 10
description: >-
  Les principaux termes et abréviations de SPL Sense et SPL Cloud, par ordre alphabétique.
---

## Valeurs mesurées et notation

SPL Sense et SPL Cloud écrivent les valeurs mesurées comme il est d'usage en acoustique :

| Affichage | Signification |
|---|---|
| **LAeq 60′** | Niveau équivalent (Leq) pondéré A sur 60 minutes. Le « niveau horaire » de l'O-LRNIS. |
| **LAeq 5′** | idem sur 5 minutes |
| **LCeq 1 s** | Niveau équivalent pondéré C sur 1 seconde (valeur en direct) |
| **LAFmax 1′** | niveau le plus élevé, pondéré A avec la pondération temporelle *Fast*, sur une minute |

La lettre après le L est la pondération fréquentielle (A, C ou Z), suivie du type (eq ou Fmax), puis de la durée. Le
signe ′ signifie minutes. L'unité est toujours le dB.

Les exports CSV et les rapports PDF utilisent encore en partie une ancienne notation pour ces mêmes valeurs.

## Termes de A à Z

**Accès en lecture**
: Permet à une autre personne de consulter une mesure ou un événement dans SPL Cloud sans rien modifier.

**Bruit du public, bruit parasite**
: La DIN 15905-5 appelle *Störschall* (bruit parasite) tout ce qui ne provient pas de la sonorisation, par exemple le
  public ou la pyrotechnie. Voir [Bruit du public]({{< relref "audience-noise" >}}).

**Bruit rose (pink noise)**
: Signal de test à énergie égale par octave. Sert à déterminer le décalage et le line offset.

**Calibration**
: Ajustement du capteur par rapport à un niveau sonore de référence. Elle a une date d'expiration.
  Voir [Capteur et calibration]({{< relref "/docs/spl-sense/sensor-and-calibration" >}}).

**Code PIN opérateur**
: Protège SPL Sense contre les modifications. L'écran en direct reste accessible sans code PIN.

**Corrélation**
: Pour le leveler, le rapport entre le niveau mesuré et le niveau attendu. 1.000 signifie : seule la sonorisation est
  audible. Des valeurs supérieures à 1 indiquent un bruit supplémentaire, par exemple du public.

**Décalage (offset), valeur de correction**
: Valeur en dB ajoutée à chaque valeur mesurée pour déduire le niveau à l'endroit le plus bruyant à partir du point de
  mesure. Une valeur pour A, C et Z. Dans la DIN 15905-5, ce sont les valeurs de correction KA et KC.

**Écart, dépassement**
: Une valeur a dépassé un seuil du profil de valeur. Les détails de la mesure les affichent par jour.

**Écran en direct**
: Grand affichage des valeurs actuelles, par exemple pour le DJ ou les techniciens. Disposition librement configurable.

**Endroit le plus bruyant, lieu d'immission**
: L'endroit le plus bruyant de la zone du public, à hauteur d'oreille. C'est là que la limite s'applique. La DIN 15905-5
  l'appelle *maßgeblicher Immissionsort* et en distingue un pour LAeq (déterminé par les médiums et les aigus) et un pour
  le niveau de crête (déterminé par les basses). Voir [Point de mesure et décalage]({{< relref "measuring-point-and-offset" >}}).

**Événement (job)**
: Regroupe plusieurs mesures dans SPL Cloud, par exemple tous les points de mesure d'un festival.

**Fast (F)**
: Pondération temporelle de 125 ms. Réagit rapidement aux crêtes. Base du LAFmax.

**Filtre de protection contre les intempéries**
: Compense l'influence d'une protection contre les intempéries sur le microphone. Doit correspondre à la protection
  utilisée.

**Instance**
: Une installation de SPL Sense enregistrée dans SPL Cloud, par exemple un ordinateur portable ou un Raspberry Pi.

**Intervalle**
: Une section enregistrée d'une minute. Il contient toutes les valeurs de cette minute et est signé numériquement.

**Jour de mesure**
: Un jour d'une mesure, délimité par la limite journalière. La facturation Pro compte aussi les jours de mesure.

**LAFmax, MaxF**
: Le niveau le plus élevé avec la pondération temporelle Fast pendant la durée choisie. L'O-LRNIS limite le LAFmax à
  125 dB(A).

**LCpeak**
: Niveau de pression acoustique de crête pondéré C : la valeur instantanée la plus élevée de la pression acoustique,
  sans pondération temporelle. La DIN 15905-5 le limite à 135 dB. Différent du LCFmax : pour celui-ci, le niveau est
  d'abord lissé avec la pondération temporelle Fast (125 ms), puis la valeur la plus élevée est retenue. Les crêtes
  courtes en ressortent plus basses ; le LCpeak est donc toujours égal ou supérieur au LCFmax.

**Leq (niveau équivalent)**
: La moyenne énergétique du niveau sur une durée donnée. Un court moment très fort augmente nettement le Leq ; un moment
  calme ne le diminue que peu.

**Leveler**
: Règle automatiquement le volume de la sonorisation pour que la limite soit respectée.

**Limite journalière**
: Heure à laquelle un jour de mesure se termine : entre minuit et 06:00.

**Line offset**
: Pour le leveler avec compensation du public : la différence entre le niveau au capteur et le niveau du signal à la
  sortie du processeur audio, mesurée sans public.

**Mesure**
: Un point de mesure avec ses paramètres et toutes les données enregistrées. Peut durer plusieurs jours.

**Niveau d'évaluation (Lr)**
: Terme de la DIN 15905-5 : le LAeq sur 30 minutes au lieu d'immission, par blocs commençant à chaque heure pile et
  demi-heure. La valeur admissible est de 99 dB.

**Organisation**
: Une entreprise, un établissement ou un festival dans SPL Cloud. Elle possède des mesures, des événements et des
  instances ; plusieurs personnes y travaillent ensemble.

**Plage horaire exclue**
: Une période qui ne compte pas pour les maxima, l'évaluation et les écarts, par exemple le réglage du système. Les
  données sont conservées et affichées en grisé.

**Point de mesure, lieu d'immission de substitution**
: L'endroit où se trouve réellement le capteur, par exemple à la table de mixage. La DIN 15905-5 l'appelle
  *Ersatzimmissionsort*.

**Pondération A, C et Z**
: Filtres qui pondèrent le spectre de fréquences. **A** correspond à peu près à l'ouïe humaine à faible niveau et
  atténue fortement les basses ; les niveaux équivalents de l'O-LRNIS et de la DIN 15905-5 sont exprimés en dB(A).
  **C** n'atténue que peu les basses et montre la part d'énergie dans les basses fréquences ; la DIN 15905-5 l'utilise
  pour limiter le niveau de crête. **Z** n'est pas filtré (*zero*). SPL Sense mesure toujours les trois.

**Profil de valeur**
: Définit quelles valeurs une mesure calcule (p. ex. LAeq 60′, LAFmax 1′) et quels seuils s'appliquent. Chaque valeur a
  jusqu'à trois niveaux : **Notification**, **Avertissement** et **Limite**.
  Voir [Profils de valeur]({{< relref "/docs/spl-sense/value-profiles" >}}).

**Réduction de gain (GR)**
: De combien de dB le [leveler]({{< relref "/docs/spl-sense/leveler" >}}) réduit actuellement le volume. Toujours 0 ou
  négatif.

**Signature**
: Chaque intervalle est signé numériquement. Cela permet de prouver que les données n'ont pas été modifiées.

**Spectre, bande de tiers d'octave**
: Le niveau réparti par fréquences, en tiers d'octave. Visible dans les détails de l'intervalle et sur l'écran en
  direct.

**Zone de compensation**
: Zone où le public peut se reposer du bruit (*Ausgleichszone*). L'O-LRNIS l'exige pour les manifestations avec un
  niveau horaire supérieur à 96 dB(A) qui durent plus de trois heures.
