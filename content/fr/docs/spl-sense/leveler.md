---
title: Leveler
linkTitle: Leveler
weight: 50
description: >-
  Régulation automatique du niveau avec le SPL Tools L1 ou un processeur audio : variantes, modes, étalonnage et
  exploitation.
---

Le leveler maintient automatiquement le niveau sous une limite. SPL Sense mesure le niveau sonore avec le capteur, reçoit
de l'appareil leveler le niveau du signal qu'il émet (niveau line) et calcule de combien le volume doit être réduit
(réduction de gain). L'appareil leveler applique la réduction dans le trajet du signal.

Le leveler fait partie de la mesure : chaque mesure a ses propres paramètres de leveler. Vous les trouvez dans le menu
**Mesure** › **Paramètres du Leveler**.

## Variantes

| Connexion | Quand |
|---|---|
| **SPL Tools L1 (USB)** | Le L1 est relié en USB à l'ordinateur sur lequel tourne SPL Sense. Par défaut pour les nouvelles mesures. |
| **SPL Tools L1 (réseau)** | Le L1 se trouve ailleurs, par exemple dans le rack près de l'amplificateur, et est accessible par Ethernet ou WiFi. |
| **Processeur audio externe (SenseAPI)** | Un processeur audio avec un plugin SPL Sense interroge SPL Sense via l'[API]({{< relref "/docs/developers/sense-api" >}}). |

Pour Q-SYS, il existe le plugin **SPL Sense Leveler** : [télécharger](https://r.spl.swiss/sense/leveler/plugin).
Ajoutez-le à votre design Q-SYS et saisissez dans le plugin l'adresse IP de l'ordinateur sur lequel tourne SPL Sense,
le port et la clé API. Dans SPL Sense, sous **Paramètres** › **API**, le mode **Leveler externe uniquement** ou
**Contrôle total** doit être activé, voir [API SPL Sense]({{< relref "/docs/developers/sense-api" >}}). Si les données
sont correctes, le plugin affiche l'état et les valeurs mesurées de SPL Sense.

### SPL Tools L1 en USB

Branchez le L1 en USB. Dans les paramètres du leveler de la mesure, **Connexion du leveler** indique alors **Connecté**
avec le type, le numéro de série et le firmware.

### SPL Tools L1 en réseau

1. Choisissez **SPL Tools L1 (réseau)**.
2. Saisissez le nom ou l'adresse IP du L1 sous **Hôte**, ou cliquez sur **Rechercher** : SPL Sense recherche alors les
   appareils L1 sur le réseau local.
3. Saisissez la **clé API** du L1.
4. Choisissez la **Sécurité** :
   - **HTTP (TLS du L1 désactivé)** : non chiffré, uniquement dans des réseaux locaux protégés
   - **HTTPS, certificat épinglé** : chiffré avec le propre certificat du L1. Lisez l'empreinte avec
     **Lire depuis le L1** et comparez-la avec celle affichée sur le L1.
   - **HTTPS, autorité de certification de confiance** : chiffré avec le certificat d'une autorité reconnue
5. Cliquez sur **Tester la connexion**, puis sur **Sauvegarder**.

Le plus simple est **Configurer depuis le L1 en USB** : branchez une fois le L1 en USB, et SPL Sense reprend l'hôte,
la clé API, la sécurité et l'empreinte. Si le L1 n'a pas encore de clé API, SPL Sense en génère une.

Après plusieurs clés API erronées, le L1 bloque la connexion pendant 30 secondes.

### Configurer le L1 lui-même

Lorsqu'un L1 est branché en USB, vous le configurez sous **Paramètres** › **Leveler** :

- **Informations sur l'appareil** : type, numéro de série, firmware, adresses MAC
- **Configuration Ethernet** : automatique ou **statique** avec adresse IP, masque de sous-réseau et passerelle
- **Configuration WiFi** : réseau et mot de passe. Le L1 ne prend en charge que les réseaux 2,4 GHz. L'état indique la
  connexion et la force du signal.
- **API réseau** : nom d'hôte, clé API (vide : leveling via le réseau désactivé ; **Générer** en crée une), mot de passe
  admin pour l'interface web du L1 et le chiffrement (**Arrêt**, **Certificat auto-signé**, **Certificat personnalisé**)

Les limites et le mode ne se règlent pas ici, mais dans les paramètres du leveler de la mesure.

## Modes

| Mode | Comportement |
|---|---|
| **Arrêt** | Pas de leveling. |
| **leveler plat** | Régule toujours lentement et régulièrement. |
| **Leveler with panic** | Comme le leveler plat, mais réduit rapidement si le niveau dépasse soudainement nettement la limite. |
| **Leveler avec compensation de la panique et de l'audience** | En plus, SPL Sense détecte quelle part du niveau ne provient pas de la sonorisation (par exemple le public) et ne régule que la part de la sonorisation. Nécessite un line offset mesuré. |

Contexte sur la compensation du public : [Bruit du public]({{< relref "/docs/basics/audience-noise" >}}).

## Limites

Sous **Valeurs limites**, vous saisissez une limite entre 40 et 140 dB pour A, C et Z. Un champ vide signifie : cette
pondération n'est pas régulée. Si plusieurs limites sont définies, c'est la pondération qui exige la plus forte
réduction qui s'applique ; elle est dite *dominante*.

Le leveler régule sur une moyenne d'environ 10 secondes. La réduction de gain est au maximum de 40 dB.

## Mesurer le line offset

Uniquement pour le mode avec compensation du public. Le line offset est la différence entre le niveau au capteur et le
niveau line lorsque seule la sonorisation joue. Avant la mesure, la mesure doit être active et arrêtée, le capteur
connecté et le mode du leveler sauvegardé ou appliqué (**Appliquer les paramètres**).

1. Diffusez du bruit rose à travers **toute la chaîne du signal**, aussi fort que pendant la manifestation. Si la source
   est une table de mixage DJ, injectez le bruit dans la table DJ.
2. Veillez au silence : pas de public, pas de conversations, pas d'autres sources.
3. Cliquez sur **Capturer Line Offset**. SPL Sense mesure pendant trois secondes et inscrit le line offset pour A, C et Z.
4. Vérifiez la **Correlation** : elle doit être aussi proche que possible de **1.000** pour toutes les pondérations.
   Sinon, répétez la mesure.
5. **Sauvegarder**.

{{% alert title="Important" color="warning" %}}
Après la mesure, plus rien ne doit modifier le niveau entre l'appareil leveler et les haut-parleurs : pas de
modification de gain sur les amplificateurs ou processeurs, pas de compresseurs ni de limiteurs dans cette partie du
trajet du signal. Sinon, le line offset n'est plus correct et le leveler régule mal.
{{% /alert %}}

Vous pouvez aussi modifier le line offset manuellement. Soyez prudent : même un petit écart amène le leveler à ignorer
le bruit du public ou à intervenir trop fortement.

## Lire la corrélation

La corrélation compare le niveau mesuré avec le niveau que la sonorisation seule devrait produire.

| Corrélation | Signification |
|---|---|
| environ 1.000 | Seule la sonorisation est audible. |
| supérieure à 1 | Bruit supplémentaire, en général le public. |
| inférieure à 1 | Le capteur est amorti, ou quelque chose a été modifié dans la sonorisation après la mesure. |

## Pendant la mesure

Lorsque la mesure est en cours et que le leveler est actif, le bandeau en direct affiche :

- la **Réduction de gain** actuelle
- la **Correlation** par pondération ; la dominante est en gras et marquée d'un `>`, par exemple `> 0.987 @A`
- le niveau sur 1 seconde de la pondération dominante, mis en évidence

Vous pouvez aussi modifier les limites, le mode et les line offsets pendant la mesure ; ils s'appliquent immédiatement
sans que la réduction de gain ne fasse de saut. La mesure du line offset n'est possible qu'avec la mesure arrêtée.

Le graphique journalier affiche en plus le niveau line, la réduction de gain et la corrélation. Avec la transmission au
cloud, ces données vont aussi dans SPL Cloud.

### Avertissements

| Message | Que faire |
|---|---|
| **Pas encore de contact avec le processeur** / **depuis …** | Vérifier la connexion au L1 ou au processeur audio. |
| **Le leveler est désactivé car la configuration est incomplète** | Il manque au moins une limite, en mode avec compensation du public aussi le line offset correspondant. |

### Bypass

**Bypass Leveler** désactive immédiatement la régulation, par exemple en cas de problème. Attention : le volume augmente
alors de la réduction de gain actuelle. Avec 15 dB de réduction, le son devient soudainement 15 dB plus fort.

Le bypass s'applique à tout l'appareil et **reste activé jusqu'à ce que vous l'annuliez avec Réactiver Leveler**, même
après un redémarrage, un changement de mesure ou un débranchement. Tant qu'il est actif, la vue d'ensemble et la page de
la mesure affichent un avis.

### Arrêt et interruption

- **Arrêter :** le leveler remet la réduction de gain à 0 et rend le contrôle. SPL Sense avertit à l'arrêt si le leveler
  est en train de réduire.
- **Interrompu** (capteur absent) : la dernière réduction de gain est maintenue jusqu'à ce que le capteur fournisse à
  nouveau des données.

## Qui peut modifier quoi

Les paramètres du leveler peuvent être modifiés pour chaque mesure ouverte, même sans capteur et même si elle n'est pas
active. Pas pour une mesure clôturée. Depuis SPL Cloud, le mode, les limites et les line offsets peuvent être modifiés
par [commande à distance]({{< relref "/docs/spl-cloud-pro/remote-control" >}}), mais pas la connexion ni la mesure du
line offset.
