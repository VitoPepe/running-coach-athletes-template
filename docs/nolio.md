# Nolio — brancher ta plateforme d'entraînement

> **À quoi sert ce fichier :** tout ce qui est propre à Nolio : brancher le connecteur, choisir les permissions selon ton mode, savoir ce que le coach lit et écrit. C'est le seul endroit (avec la section « Plateforme » de chaque automatisation) qui parle de Nolio.
> **Mis à jour par :** contenu du projet.

## Ce qu'il te faut

- Un compte **Nolio payant** : Premium Athlete, ou un compte coach. Le connecteur (MCP) officiel de Nolio est réservé à ces comptes.
- Un compte **Claude** (claude.ai).
- **Même avec un coach**, il te faut ton propre abonnement Premium Athlete : un compte athlète gratuit n'a pas accès au connecteur, même si ton coach a un compte payant.

## Brancher le connecteur (5 min)

1. Dans Claude : **Réglages → Connecteurs**.
2. Ajoute **Nolio** depuis l'annuaire des connecteurs, ou, s'il n'y apparaît pas, ajoute un connecteur personnalisé avec l'adresse `https://mcp.nolio.io/mcp`.
3. Connecte-toi avec ton compte Nolio et **choisis les permissions** (tableau ci-dessous).
4. Vérifie dans une session : « Quelles sont mes 3 dernières séances dans Nolio ? ».

Pour retirer l'accès : dans Nolio (**Paramètres → MCP**) ou dans Claude (**Réglages → Connecteurs**). Pour changer les permissions : déconnecte, puis reconnecte en cochant autre chose.

## Les permissions selon ton mode

| Permission | Mode `avec-coach` | Mode `autocoache` | Pourquoi |
|---|---|---|---|
| Lecture | ✅ | ✅ | séances, activités, métriques |
| Création | ❌ | ✅ (niveau 5) | créer les séances que tu as validées |
| Suppression | ❌ | ✅ (niveau 5) | changer une séance = la supprimer et la recréer |
| Modification | ❌ | ❌ | Nolio ne sait pas annuler une modification |

C'est une **défense en profondeur**. En mode `avec-coach`, même un prompt mal compris ne peut pas toucher au plan de ton coach : Nolio refuserait. En mode `autocoache`, tout ce que le coach écrit reste annulable et tracé dans `plan/registre-nolio.md`.

Note ce que tu as coché dans `reglages.md` (`permissions_nolio`).

## Ce que le coach lit et écrit

| Besoin | Utilisé par | Dans Nolio |
|---|---|---|
| Séances prévues (date, structure, cibles, consignes) | brief, débrief, bilans, planifier | le planning de l'athlète |
| Activités réalisées (durée, distance, D+, FC, zones, allure) | débrief, bilans, débrief de course | les activités synchronisées depuis la montre |
| RPE, ressenti, commentaire de l'athlète | débrief | rattachés à l'activité réalisée, s'ils ont été saisis |
| VFC, FC repos, sommeil | brief, débrief, bilan hebdo | `list_metrics` ; clés observées `RMSSD` (ms), `FCREPOS`, `SOMMEIL` |
| Charge et forme | brief, bilan hebdo | `get_training_load` |
| Records, compétitions | bilan mensuel, mode course | records personnels, séances de type compétition |
| Créer ou supprimer une séance | `conversations/planifier.md`, après « je valide » | outils de création et de suppression |

Les noms d'outils (`list_metrics`, `get_training_load`) ont été observés en octobre 2026 et peuvent évoluer. Les automatisations décrivent ce qu'il faut obtenir plutôt que l'outil exact : si un nom change, le coach cherche l'équivalent et le note dans `automations/runs.md`.

## Les règles d'écriture

- **Jamais pendant une tâche planifiée.** Une tâche propose, ta réponse dans la session valide.
- **Jamais en mode `avec-coach`.**
- **Jamais une séance absente du registre** : si le coach ne l'a pas créée, il n'y touche pas.
- Le détail est dans `CLAUDE.md` › Écrire dans Nolio, et dans `conversations/planifier.md`.

## Limites connues

- Les données de certaines sources (Zepp, Huawei) ne passent pas toutes par le connecteur : les séances arrivent avec leur durée et leur distance seulement, sans les métriques. Le feu du matin passe alors en ⚪ (« pas de mesure »).
- Le poids remonté par la montre n'est jamais lu ni affiché : c'est une règle du projet.
- Le brief tôt le matin peut tomber avant la synchronisation de la montre : décale-le d'une heure si la forme est souvent vide.

## Sources

- [Nolio — Developers (connecteur Claude, permissions)](https://www.nolio.io/en/developers/)
- [Nolio — conditions de l'API](https://www.nolio.io/en/api-terms/)
- [Documentation de l'API Nolio](https://github.com/NolioApp/NolioAPI-Documentation/)
