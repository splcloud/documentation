---
title: Capteur et calibration
linkTitle: Capteur et calibration
weight: 60
description: >-
  État du capteur, filtre de protection contre les intempéries et calibration du capteur.
---

## Informations du capteur

Sous **Paramètres** › **Informations du capteur** (ou en cliquant sur le capteur dans la vue d'ensemble), vous voyez :

- **Informations sur l'appareil** : numéro de série, révision du matériel, MCU ID, version du firmware, contrôle qualité
- **Tension** et **Température du MCU**, actualisées avec **Actualiser les valeurs mesurées**
- **Calibration** : date, par qui, valable jusqu'à
- **Protection contre les intempéries** : le filtre de compensation réglé

Branchez toujours **un seul capteur** à un ordinateur avec SPL Sense. Si vous changez de capteur pendant une mesure
(débrancher, en brancher un autre), SPL Sense continue de mesurer avec le nouveau ; la minute concernée est marquée dans
les données.

## État de la calibration

| Affichage | Signification |
|---|---|
| **Calibré** | La calibration est valable. |
| **Calibrage expiré** | La calibration a expiré. Vous pouvez mesurer, mais les données sont marquées. |
| **Calibration invalide** | Le capteur n'a pas de calibration valable. |

Si la calibration a expiré ou n'est pas valable, SPL Sense demande une confirmation au démarrage de la mesure
(**Démarrer quand même**). Si la mesure est démarrée par le mode autonome, l'API ou la commande à distance, SPL Sense ne
demande rien.

## Filtre de protection contre les intempéries

Une protection contre les intempéries sur le microphone modifie légèrement la réponse en fréquence. Le filtre de
compensation corrige cela. Il doit correspondre à la protection utilisée :

- **Activer le filtre pour SPL Tools W1** pour la protection SPL Tools W1
- **Activer le filtre pour protection intempéries V1** pour l'ancienne protection V1
- **Désactiver le filtre** sans protection contre les intempéries

Le filtre est enregistré dans le capteur et s'applique jusqu'à ce que vous le modifiiez, aussi pour d'autres mesures et
sur d'autres ordinateurs. Vous ne pouvez le modifier que lorsqu'aucune mesure n'est en cours. Lorsqu'il est activé, la
vue d'ensemble affiche un avis et les données de mesure sont marquées.

## Calibrer le capteur

Avec une autorisation de calibrateur, vous pouvez calibrer vous-même des capteurs. Il vous faut :

- SPL Sense pour Windows ou macOS (pas disponible en mode serveur web)
- Internet
- un calibreur acoustique de 94 ou 114 dB
- une confirmation en tant que calibrateur de SPL Tools (voir ci-dessous)

### Postuler en tant que calibrateur

1. Sur la page du capteur, **Calibrer** › **Postuler en tant que calibrateur**.
2. Remplissez le formulaire en ligne. Vous y décrivez aussi votre équipement de calibration.
3. SPL Tools examine votre demande et la confirme par e-mail.

Dès que vous avez la confirmation, vous pouvez calibrer.

### Déroulement

La mesure doit être arrêtée et le capteur connecté.

1. Page du capteur › **Calibrer** › **Connexion**. SPL Sense indique sous quel nom vous êtes connecté ainsi que la
   calibration actuelle.
2. Placez le calibreur allumé sur le capteur et attendez que le niveau soit stable.
3. Cliquez sur le bouton de mesure **94 dB** ou **114 dB**, selon votre calibreur.
4. Vérifiez le **Résultat de la capture** :
   - **Dérive de la capture** : fluctuation pendant la mesure
   - **Dérive de la calibration précédente** : l'écart du capteur depuis la dernière calibration

   Si les valeurs indiquent que le capteur dérive, SPL Sense vous avertit. Calibrez à nouveau et vérifiez que le capteur
   n'a pas de dommages mécaniques ; en cas de doute, envoyez-le pour contrôle.
5. Choisissez l'**Organisation signataire** et le certificat, complétez **Calibré pour** et **Appareil de calibration**.
6. Cliquez sur **Signer et enregistrer la calibration**.

La calibration est signée numériquement et enregistrée dans le capteur. Dès lors, les données de mesure sont signées avec
la nouvelle calibration.

Un capteur sans calibration antérieure ne peut pas être calibré de cette manière. Dans ce cas, contactez SPL Tools.
