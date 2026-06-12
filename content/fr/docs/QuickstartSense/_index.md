---
title: "Guide de démarrage rapide SPL Sense"
linkTitle: "Guide de démarrage rapide SPL Sense"
weight: 100
description: >-
  Guide de démarrage rapide SPL Sense
---

## Vue d'ensemble du tableau de bord

![Dashboard](https://docs.spl.swiss/docs/quickstartsense/Dashboard.png)  
• **Logo en haut à gauche :** Un clic sur le logo ramène au tableau de bord.  
• **Indicateur de statut (en haut à droite) :** Affiche le statut actuel (aucune mesure chargée / mesure arrêtée / mesure en cours).  
• **Paramètres (icône d'engrenage en haut à droite) :** Ouvre les paramètres.  
• **Créer une nouvelle mesure :** Clique sur le bouton «+» à côté de «Mesures sauvegardées» pour créer une nouvelle mesure.  
• **Afficher le capteur connecté :** Le capteur de mesure connecté est affiché sur le côté droit. Un clic dessus affiche le statut détaillé du capteur.  


## Statut du capteur / Paramètres

![Vue d'ensemble du capteur](https://docs.spl.swiss/docs/quickstartsense/Sensor.png)  
Dans l'écran de détail du capteur, tu peux activer la compensation pour la protection contre les intempéries. Lorsque cette option est active, la protection contre les intempéries est compensée par un filtre FIR dans le capteur.  


## Connexion à SPL Cloud (optionnel)

Chaque SPL Sense peut être connecté à la SPL Cloud pour consulter et enregistrer des données en temps réel.  

1. **Ouvrir les paramètres :** Clique sur l'icône d'engrenage en haut à droite.  
![Vue d'ensemble des paramètres](https://docs.spl.swiss/docs/quickstartsense/Einstellungen.png)  
2. **Sélectionner Cloud :** Choisis l'option «Cloud».  
![Connexion Cloud](https://docs.spl.swiss/docs/quickstartsense/ConnectCloud.png)  
3. **Établir la connexion :** Clique sur le lien ou scanne le QR code. (SPL Sense doit être connecté à Internet et un accès personnel à la SPL Cloud doit être créé.)  
Une fois ces étapes effectuées, SPL Sense est connecté à la SPL Cloud.  
![Cloud connecté](https://docs.spl.swiss/docs/quickstartsense/ConnectCloudCloudstatus.png)  


## Créer une mesure

1. **Créer une nouvelle mesure :** Clique sur le bouton «+» à côté de «Mesures sauvegardées».  
2. **Saisir un nom :** Entre un nom pour la mesure. Ce nom sera affiché comme titre de la mesure.  
3. **Définir la limite journalière :** Règle la limite journalière. Elle peut être décalée de minuit jusqu'à 06h00 du matin. Ainsi, un concert ou une fête est affiché dans une vue journalière unique et non réparti sur deux jours lors du passage à minuit. Nous recommandons de fixer la limite environ 2 heures après la fin prévue de l'événement.  
4. **Activer la liaison cloud :** Active la liaison cloud pour transférer cette mesure vers le cloud. Cette option n'est disponible que si SPL Sense est connecté à la SPL Cloud. Si aucune connexion n'existe, cela sera indiqué en conséquence.  
![Liaison cloud](https://docs.spl.swiss/docs/quickstartsense/CloudUplink.png)  
5. **Sélectionner un profil de valeurs :** Choisis un profil de valeurs qui définit quelles valeurs sont enregistrées avec quels filtres (A/C/Z) et quels temps d'intégration. Des valeurs limites pour trois niveaux différents (notification, avertissement, limite) peuvent également être configurées. Le journal d'événements est trié selon ces niveaux. En plus des profils préenregistrés basés sur l'O-LRNIS (V-NISSG), tu peux également créer tes propres profils.  
![Sélectionner un profil de valeurs](https://docs.spl.swiss/docs/quickstartsense/NeueMessungWerteprofil.png)  
6. **Sauvegarder la mesure :** Sauvegarde la mesure.  
![Mesure dans le tableau de bord avec cloud](https://docs.spl.swiss/docs/quickstartsense/MessungAngelegtMitCloud.png)  
Après la sauvegarde, la mesure apparaît dans le tableau de bord. Une icône de nuage à côté du titre de la mesure indique si la mesure est transmise à la SPL Cloud.  


## Ouvrir et modifier une mesure

1. **Ouvrir une mesure :** Clique sur la mesure souhaitée dans le tableau de bord pour l'ouvrir.  
![Vue d'ensemble de la mesure](https://docs.spl.swiss/docs/quickstartsense/MessungDetailsOhneDaten.png)  
2. **Activer la mesure :** Active la mesure avec le bouton sur le côté droit. Note qu'une seule mesure peut être active à la fois.  
![Mesure activée](https://docs.spl.swiss/docs/quickstartsense/MessungAktiviert.png)  
3. **Ajuster les paramètres de base :** Sous «Modifier la mesure» sur le côté droit, les paramètres de base de la mesure peuvent être ajustés. En plus des paramètres déjà mentionnés, des offsets peuvent être configurés et un code PIN pour quitter l'écran live peut être défini. Il est également possible de supprimer définitivement la mesure avec toutes ses données de l'ordinateur.  
![Modifier la mesure](https://docs.spl.swiss/docs/quickstartsense/MessungBearbeiten.png)  


## Offset tune

L'offset peut être réglé à l'aide de la fonction «Offset tune» sur le côté droit. Toutes les valeurs mesurées pendant ce processus ne sont pas enregistrées dans la mesure. Nous recommandons de régler l'offset (la différence de niveau entre le point le plus fort et l'emplacement du capteur pendant la mesure) avec un signal de test, par ex. du bruit rose, comme suit :  
![Offset tune](https://docs.spl.swiss/docs/quickstartsense/Offsettune.png)  

1. **Diffuser du bruit rose :** Utilise un niveau sonore correspondant à celui attendu pendant le concert ou l'événement.  
2. **Réinitialiser la valeur maximale :** Appuie sur le bouton «Réinitialiser max».  
3. **Parcourir la zone du public :** Déplace-toi avec l'ordinateur et le capteur à travers la zone du public.  
4. **Placer le capteur :** Installe le capteur à la position de mesure prévue.  
5. **Ajuster l'offset :** Règle la valeur d'offset de sorte que le «Niveau incl. offset» corresponde au «Max LEQ1».  
6. **Sauvegarder les paramètres :** Sauvegarde les ajustements effectués.  
La différence de niveau peut également être déterminée à l'aide d'un appareil de mesure portable supplémentaire. Plus d'informations sur l'emplacement du capteur et l'offset : [Recommandation de la branche pour le procédé de mesure](https://www.bag.admin.ch/dam/fr/sd-web/KAIxMQtpqM6k/vnissg_vollzugshilfe_schall.pdfhttps://www.bag.admin.ch/dam/fr/sd-web/KAIxMQtpqM6k/vnissg_vollzugshilfe_schall.pdf)  


## Plugin Leveler pour le processeur audio

Le plugin pour le processeur audio peut être téléchargé sur le site web sous «SPL Sense Leveler». Après l'avoir inséré dans le design du processeur audio, l'adresse IP de l'ordinateur sur lequel SPL Sense fonctionne, ainsi que le port et la clé API, doivent être saisis dans le plugin. Si les saisies sont correctes, le plugin affiche l'état actuel et les valeurs mesurées de SPL Sense. Dans SPL Sense, le mode «Leveler externe uniquement» ou «Accès complet» doit être activé sous «Paramètres» - «API». La clé API peut également y être configurée.  
**Important :** Pour un leveler fonctionnel avec détection du public, aucun ajustement de niveau de ligne ne doit être effectué entre le plugin et le haut-parleur après l'étalonnage. Les compresseurs audio ou composants similaires ne doivent pas être utilisés dans ce segment du signal.  


## Paramètres du Leveler

Une bonne position du capteur et des offsets correctement réglés pour les valeurs A, C et Z sont déterminants pour de bons résultats du leveler. Une bonne position du capteur signifie que le niveau de pression acoustique du haut-parleur médium/aigu et du caisson de basse sont dans un rapport naturel. Les offsets réglés doivent généralement se situer entre -10 dB et +2 dB.  
![Paramètres du Leveler](https://docs.spl.swiss/docs/quickstartsense/LevelerEinstellungen.png)  

1. **Ouvrir les paramètres du leveler :** Ouvre le panneau de paramètres du leveler. Cela est possible pendant une mesure en cours ou arrêtée. Pour effectuer les réglages de base, la mesure doit être arrêtée.  
2. **Sélectionner le mode leveler :** Choisis entre «Désactivé» (leveler inactif), «Leveler simple» (le leveler régule toujours lentement – le public n'est pas pris en compte), «Leveler avec fonction panique» (en cas de hausse rapide du niveau de pression acoustique entraînant un dépassement, le leveler réduit rapidement le niveau – le public n'est pas pris en compte), et «Leveler avec fonction panique et compensation du public» (en cas de hausse rapide du niveau de pression acoustique entraînant un dépassement, le leveler réduit rapidement le niveau – le public ou d'autres sources de bruit externes sont pris en compte et filtrés).  
3. **Définir les valeurs limites :** Entre les limites souhaitées. Le leveler peut simultanément prendre en compte une limite pour les pondérations A, C et Z. Les limites peuvent être ajustées à tout moment, même pendant une mesure en cours.  
**Les étapes 4 et 5 ne sont nécessaires que pour le mode avec compensation du public.**  
![Paramètres du Leveler – étalonnage](https://docs.spl.swiss/docs/quickstartsense/LevelerEinstellungenEinmessvorgang.png)  
4. **Injecter du bruit rose :** Injecte du bruit rose comme source audio au niveau attendu. Utilise la chaîne de signal effective — si une table de mixage DJ est la source, alimente un générateur de bruit rose via le DJ. Si la limite pendant l'événement est de 96 dB, mesure également à 96 dB.  
5. **Mesurer le décalage de ligne (Line Offset) :** Appuie sur le bouton «Mesurer le décalage de ligne». Le système détermine pendant 3 secondes le décalage de ligne en mesurant le rapport entre le niveau de ligne et le niveau de pression acoustique. Pendant ce court laps de temps, il ne doit y avoir aucun bruit parasite. La procédure peut être répétée autant de fois que nécessaire. Une fois la mesure effectuée, la valeur de corrélation pour les pondérations A, C et Z doit être aussi proche que possible de 1.000.  
6. **Sauvegarder :** Confirme les paramètres avec «Sauvegarder».  
Pendant une mesure en cours, les limites et le décalage de ligne peuvent être ajustés manuellement. L'étalonnage automatique n'est possible que lorsque la mesure est arrêtée. La corrélation indique si le réglage est correct. En l'absence de bruit extérieur, la valeur doit être aussi proche que possible de 1. Lors d'une correction manuelle, une extrême prudence est de mise. Même un léger mauvais réglage peut faire en sorte que le leveler ignore le bruit extérieur ou intervienne trop fortement.  
Avec des décalages de ligne correctement réglés, des valeurs de corrélation inférieures à 1 indiquent un capteur atténué ou une manipulation du système de haut-parleurs. Des valeurs de corrélation supérieures à 1 indiquent un bruit extérieur.  


## Démarrer une mesure

1. **Démarrer la mesure :** Lance la mesure via le bouton sur le côté droit.  
![Vue d'ensemble de la mesure en cours](https://docs.spl.swiss/docs/quickstartsense/Messunglaeuft.png)  
2. **Afficher le niveau sonore actuel :** Le niveau sonore actuel est également affiché sur le côté droit.  
3. **Affichage actuel du leveler :** Lorsque le leveler est actif, la réduction de niveau actuelle et les corrélations SPL de ligne sont affichées pendant une mesure en cours. La valeur écrite en gras et marquée d'un «>» indique la pondération actuellement pertinente pour le leveler. Par exemple, si la valeur de corrélation A est marquée, c'est la limite de pondération A qui est actuellement dominante pour la réduction de niveau.  
4. **Contourner le leveler :** Le leveler peut être contourné à tout moment avec «Contourner le leveler». Il faut tenir compte de la réduction de niveau actuelle. Si, par exemple, une réduction de niveau de 15 dB est actuellement active, activer la fonction de contournement augmentera le volume de 15 dB.  
5. **Suivre l'historique du niveau sonore :** Un graphique documente l'évolution du niveau sonore dans le temps. En cliquant sur le graphique, des détails supplémentaires tels que les données spectrales et les lectures en dessous ou au-dessus de la plage de mesure sont affichés.  
6. **Suivre l'historique du leveler :** Dans la vue de mesure en cours, en plus du niveau de pression acoustique, l'évolution du niveau du signal de ligne (brun clair) et la réduction de niveau (rouge) sont également affichées. La corrélation est également visible. En plus de la moyenne par minute de la réduction de niveau et de la corrélation, les valeurs minimales et maximales ainsi que la dispersion sont visualisées.  
7. **Statut de connexion cloud :** Le statut de connexion au cloud est affiché sur le côté droit.  
8. **Afficher les dépassements :** Sous «Dépassements», les dépassements de niveau sont listés selon les pondérations et temps d'intégration définis dans le profil de valeurs. En cliquant sur les différentes catégories, les valeurs seuils définies apparaissent dans le graphique sous forme de lignes jaunes, oranges et rouges.  
9. **Journal d'événements :** Dans la section «Événements» sur le côté droit, les actions telles que le démarrage et l'arrêt de la mesure, les ajustements d'offset et les événements du leveler sont listés avec leur horodatage respectif.  
10. **Ouvrir la vue live :** En cliquant sur «Vue live» sur le côté droit, la vue live est affichée.  
![Vue live](https://docs.spl.swiss/docs/quickstartsense/LiveScreen.png)  
11. **Changer de vue live :** En haut à droite, tu peux basculer entre différentes vues live. Des vues live personnalisées peuvent également être créées. La vue live offre un affichage clair des valeurs mesurées souhaitées pendant l'événement et est particulièrement utile pour les techniciens ou les DJs.  
12. **Retour à la vue d'ensemble de la mesure :** Pour revenir à la vue d'ensemble de la mesure, clique sur «Retour à la mesure». Si un code PIN pour quitter la vue live a été défini sous «Modifier la mesure», il sera demandé ici pour s'assurer que seules les personnes autorisées peuvent modifier les paramètres de la mesure.  
