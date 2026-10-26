# Personnaliser ton coach

> **À quoi sert ce fichier :** changer ce que fait ton coach, du plus simple (le lui dire) au plus avancé (ajouter une automatisation).
> **Mis à jour par :** contenu du projet.

## Le plus simple : le lui dire

Chaque tâche finit par une question pour s'améliorer. Réponds-y, ou dis à tout moment dans une session :
- « Ton brief est trop long, 8 lignes max. »
- « Arrête de me proposer de la mobilité. »
- « Ajoute une citation de motivation le lundi. »

Le coach note ton retour dans `profil/retours-agent.md`, te propose l'ajustement, et modifie lui-même le fichier `automations/` concerné quand tu valides. Il ne touche jamais aux règles de sécurité ni aux règles d'écriture dans Nolio.

## Les réglages courants

| Je veux… | Où | Comment |
|---|---|---|
| changer l'heure d'une tâche | dans Claude | modifie la tâche planifiée (et le mémo de `reglages.md`) |
| mettre une tâche en pause | dans Claude | interrupteur on/off de la tâche |
| ajuster le feu vert/orange/rouge | `profil/sante.md` › Seuils personnels | ex. « FC repos : orange à +5 bpm » |
| changer de mode (avec coach ↔ autocoaché) | `reglages.md` + permissions Nolio | dis « je change de mode » : le coach t'accompagne et note une décision |
| changer d'approche d'entraînement | conversation | « On revoit ma philosophie d'entraînement » (onboarding, bloc 7) |
| ajouter une course | conversation | « J'ai une nouvelle course » (onboarding, bloc 3) |
| déclarer un voyage | conversation | « Je pars à Lyon du 3 au 5 novembre » |
| changer de ville pour la météo | `reglages.md` | ville, latitude, longitude |
| ne plus voir une information | `profil/preferences.md` › Ce que je ne veux pas lire | ex. « pas de charge d'entraînement » |

## Modifier un prompt toi-même

Tout est en Markdown, modifiable sur GitHub (icône ✏️ puis « Commit changes »).
- **Le format d'un message** : la section « Format » du fichier `automations/` concerné.
- **Une rubrique** : ajoute une ligne au format, et dis dans les étapes d'où vient l'information.
- Garde la ligne `---` : la tâche exécute tout ce qui la suit.

## Ajouter une automatisation

Par exemple, un rappel de renforcement le mercredi.
1. Copie la structure d'un fichier existant (`automations/bilan-mensuel.md` est le plus court) : titre, en-tête, tableau de réglages, ligne `---`, prompt, journal technique.
2. Donne-lui un nom de tâche pour `automations/runs.md` (ex. `renfo`).
3. Ajoute ce nom et son délai maximal dans `MAX_AGE` de `scripts/controle.py` (ex. `"renfo": 8` pour une tâche hebdomadaire).
4. Ajoute une ligne dans le mémo de `reglages.md`.
5. Crée la tâche planifiée dans Claude avec le prompt talon (`AUTOMATISATION.md`), en changeant le nom du fichier.

## Ajouter un module

Un module, c'est une consigne lue seulement quand une condition est vraie (exemples : course, voyage, reprise).
1. Crée `automations/modules/<nom>.md` avec : le déclenchement, ce qu'on ajoute, le format.
2. Dans la section « Modules » du brief ou du débrief, ajoute la condition et le chemin du fichier.

## Récupérer les améliorations du projet

Un repo créé depuis un template ne se met pas à jour tout seul. Pour récupérer une nouvelle version :
1. Regarde l'historique du projet d'origine (les commits, et `docs/journal-de-construction.md`).
2. Recopie les fichiers qui t'intéressent : `automations/`, `conversations/`, `docs/`, `CLAUDE.md`. Attention : si tu les avais personnalisés, compare avant d'écraser.
3. Ne touche pas à tes données : `profil/`, `journal/`, `bilans/`, `etat.md`, `reglages.md`.

## Aller plus loin

- **Une autre plateforme** que Nolio : `docs/plateformes.md`.
- **Des données dans des tableurs** (nutrition, matériel, courses) : un connecteur Google Drive pour lire des Google Sheets. Pour écrire dedans, une petite passerelle Google Apps Script appelée par le coach (sans secret dans le repo : l'adresse et le jeton vont dans le prompt de la tâche). C'est le niveau « expert », hors du périmètre de ce projet.
- **Une version anglaise** : la structure est prête. Il faut traduire `CLAUDE.md`, `automations/`, `conversations/` et les modèles ; les noms de fichiers peuvent rester tels quels.
