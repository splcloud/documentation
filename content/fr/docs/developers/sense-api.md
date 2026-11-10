---
title: API SPL Sense
linkTitle: API SPL Sense
weight: 10
description: >-
  API HTTP locale pour interroger et commander SPL Sense et comme interface de leveler pour les processeurs audio.
---

## Activer

**Paramètres** › **API** dans SPL Sense :

| Paramètre | Valeurs |
|---|---|
| **Mode** | **Arrêt** (par défaut), **Leveler externe uniquement**, **Contrôle total** |
| **Port** | Par défaut `8084` (Windows, macOS). Sous Linux, l'API tourne sur le même port que l'interface web, `8080` selon le [guide d'installation]({{< relref "/docs/linux/installation" >}}) ; le paramètre de port n'y a pas d'effet. |
| **Clé API** | au moins 6 caractères ; définie aléatoirement à l'installation |

La page affiche l'URL de base, la Swagger UI et la spécification OpenAPI :

| | Chemin |
|---|---|
| API | `/api` |
| Swagger UI | `/swagger` |
| OpenAPI | `/swagger/current/swagger.json` |

L'API écoute sur toutes les interfaces réseau, sans chiffrement (HTTP). Ne l'utilisez que dans des réseaux de confiance.

Les connexions à un SPL Tools L1 ne sont pas concernées par ce paramètre.

## Authentification

Chaque requête nécessite la clé API, comme en-tête

```http
X-Api-Key: <clé api>
```

ou en HTTP Basic Auth (nom d'utilisateur quelconque, mot de passe = clé API). Sans clé valable : `401`. Si un endpoint
n'est pas autorisé dans le mode choisi : `403`.

## Endpoints

| Méthode et chemin | But | Leveler externe uniquement | Contrôle total |
|---|---|---|---|
| `GET /api/state` | État : appareil de mesure, capteur actif (numéro de série, firmware, calibration, filtre de protection contre les intempéries), mesure actuelle | ✓ | ✓ |
| `GET /api/live` | dernière valeur en direct : LAeq/LCeq/LZeq 1 s, MaxF A/C/Z, clip, low, intégrations, spectre | ✓ | ✓ |
| `GET /api/measurements` | toutes les mesures avec profil de valeur, décalages et paramètres du leveler | ✓ | ✓ |
| `POST /api/leveler` | interface de leveler pour processeurs audio | ✓ | ✓ |
| `POST /api/control` | activer, démarrer, arrêter une mesure, bypass du leveler | | ✓ |
| `POST /api/leveler/settings` | définir le mode et les limites du leveler d'une mesure | | ✓ |

Les structures de données exactes se trouvent dans la Swagger UI.

### Commander : `POST /api/control`

```json
{ "action": "start" }
```

| `action` | Effet |
|---|---|
| `activate` | activer une mesure ; nécessite `"id": "<ID de la mesure>"` |
| `start` | démarrer la mesure active |
| `stop` | arrêter la mesure |
| `leveler-bypass` | activer le bypass du leveler |
| `leveler-disable-bypass` | désactiver le bypass du leveler |

Réponse : `{ "success": true, "errorMessage": null }`. Les mêmes règles que dans l'interface s'appliquent ; un démarrage
via l'API ne demande rien en cas de calibration expirée. Les événements de la mesure indiquent **via l'API**.

### Paramètres du leveler : `POST /api/leveler/settings`

```json
{
  "measurementId": "…",
  "mode": 30,
  "limitValueDbA": 96,
  "limitValueDbC": null,
  "limitValueDbZ": null
}
```

`mode` : `0` arrêt, `10` leveler simple, `20` avec fonction panique, `30` avec fonction panique et compensation du
public. Limites 40–140 dB ou `null` (pondération non régulée). Les line offsets restent inchangés. Impossible pour les
mesures clôturées (`409`).

## Interface de leveler : `POST /api/leveler`

Pour les processeurs audio qui fonctionnent comme leveler (par exemple avec le [plugin Q-SYS]({{< relref "/docs/spl-sense/leveler#variantes" >}})).
La mesure doit avoir la connexion **Processeur audio externe (SenseAPI)** dans ses paramètres de leveler.

Le processeur appelle l'endpoint régulièrement (typiquement une fois par seconde) et envoie son niveau de sortie
actuel :

```json
{
  "lineLevels": [ { "levelA": -18.2, "levelC": -12.5, "levelZ": -10.1 } ],
  "externalLevelerType": "MyProcessor",
  "externalLevelerVersion": "1.0"
}
```

Niveaux de ligne en dBFS (négatifs), chaque pondération facultative. Plusieurs valeurs sont moyennées énergétiquement.
Chaque appel est un cycle de régulation.

Réponse :

```json
{
  "state": 20,
  "gainReduction": -3.5,
  "headroomBeforeGainReduction": 0,
  "dominantWeighting": "A",
  "compensatedRelevantSplA": 96.2,
  "compensatedRelevantSplC": null,
  "compensatedRelevantSplZ": null,
  "lineCorrelationA": 1.012,
  "lineCorrelationC": null,
  "lineCorrelationZ": null
}
```

`gainReduction` en dB, toujours ≤ 0. Le processeur applique cette valeur comme gain.

| `state` | Signification | `gainReduction` |
|---|---|---|
| `0` | leveler désactivé ou configuré de manière incomplète | – |
| `1` | mesure arrêtée | 0 |
| `2` | mesure interrompue (capteur absent) | `null` : conserver la dernière valeur |
| `10` | pas de réduction | 0 |
| `20` | réduction | < 0 |
| `21` | réduction, panique | < 0 |
| `30` | la mesure utilise un SPL Tools L1 ; les niveaux de ligne sont ignorés | – |
| `99` | bypass | 0 |
