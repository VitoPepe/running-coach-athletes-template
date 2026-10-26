# Plateformes — le contrat de données

> **À quoi sert ce fichier :** la liste de ce dont le coach a besoin, sans dépendre de Nolio. C'est le point de départ pour brancher une autre plateforme (Garmin, Strava, TrainingPeaks…).
> **Mis à jour par :** contenu du projet.

## Le principe

Les automatisations ne parlent pas de Nolio : elles parlent de **besoins** (la séance du jour, la VFC de la nuit…). La traduction vers Nolio vit à deux endroits seulement :
- `docs/nolio.md` ;
- la section « Plateforme : Nolio » à la fin de chaque fichier `automations/`.

Changer de plateforme, c'est réécrire ces deux endroits, et rien d'autre.

## Le contrat

| # | Besoin | Indispensable ? | Utilisé par | Sans lui… |
|---|---|---|---|---|
| 1 | Séances prévues : date, titre, structure, cibles, consignes | oui | brief, débrief, bilans | le coach ne sait pas ce qui était prévu : il débriefe seulement le réalisé |
| 2 | Activités réalisées : durée, distance, D+, FC, temps par zone, allure | oui | débrief, bilans, débrief de course | pas de prévu/réalisé ni de bilan chiffré |
| 3 | RPE, ressenti, commentaire de l'athlète | non | débrief | le débrief pose la question |
| 4 | VFC de la nuit (rMSSD), FC repos, sommeil | non | brief (feu), bilans | feu ⚪, ou feu sur FC repos et sommeil seulement |
| 5 | Charge et forme | non | brief, bilan hebdo | le coach s'appuie sur le volume et l'intensité |
| 6 | Records, compétitions | non | bilan mensuel, mode course | les courses viennent de `profil/objectifs.md` |
| 7 | Zones de l'athlète (FC, allure) | non | brief, planifier | zones estimées depuis la FC max de `profil/athlete.md` |
| 8 | Créer et supprimer une séance | non | planifier (autocoaché) | le coach propose, et l'athlète saisit lui-même |

## Brancher une autre plateforme

1. **Un connecteur existe-t-il ?** Cherche un connecteur (MCP) officiel ou fiable pour ta plateforme dans l'annuaire des connecteurs de Claude. Préfère un connecteur officiel : il passe par la connexion de ton compte, sans clé à recopier.
2. **Remplis le contrat** : pour chaque ligne du tableau, où se trouve la donnée et quel outil la donne. Écris-le dans `docs/<plateforme>.md`, sur le modèle de `docs/nolio.md`.
3. **Remplace la section « Plateforme »** à la fin de chaque fichier `automations/` (et dans `conversations/planifier.md` si l'écriture est possible).
4. Dans `reglages.md` : `plateforme: <nom>`.
5. **Teste** avec la checklist de `docs/checklist-de-test.md`.

## Pistes (non vérifiées dans ce projet)

| Plateforme | Ce qu'elle apporte | Ce qui risque de manquer |
|---|---|---|
| Garmin Connect | activités, VFC, sommeil, FC repos | le plan d'un coach humain, s'il est ailleurs |
| Strava | activités réalisées | séances prévues, VFC, sommeil → feu ⚪ |
| TrainingPeaks | séances prévues structurées, activités, charge | VFC et sommeil selon les appareils |

Si tu branches une de ces plateformes, propose ta page `docs/<plateforme>.md` au projet (voir « Contribuer » dans le README).
