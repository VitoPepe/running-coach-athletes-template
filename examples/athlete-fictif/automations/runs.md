# Journal technique des tâches planifiées

> **À quoi sert ce fichier :** une ligne par exécution de tâche planifiée, ajoutée par la tâche elle-même. Exemple fictif : la semaine 2026-S42 de Nora (le vrai fichier est `automations/runs.md` à la racine du repo).
> **Mis à jour par :** l'agent, à la fin de chaque tâche. Le bilan mensuel ne garde que les 2 derniers mois. Contrôlé chaque nuit par `scripts/controle.py` (GitHub Action). Ici : exemple fictif, figé, non contrôlé.

Format : `AAAA-MM-JJ HH:MM | tâche | statut | détail`
- tâche : `brief`, `debrief`, `bilan-hebdo`, `bilan-mensuel`
- statut : `ok`, `partiel` (une source a échoué mais la tâche est livrée), `échec`
- détail : les sources en échec (Nolio, météo, agenda, git push…) ou `—`

Si une tâche n'a pas tourné depuis trop longtemps, ou si sa dernière exécution est en échec, le contrôle de la nuit échoue et GitHub t'envoie un mail.

## Exécutions

2026-10-12 07:48 | brief | ok | —
2026-10-12 21:08 | debrief | ok | —
2026-10-13 07:47 | brief | ok | —
2026-10-13 21:09 | debrief | ok | —
2026-10-14 07:49 | brief | partiel | météo : secours met.no
2026-10-14 21:08 | debrief | ok | —
2026-10-15 07:47 | brief | ok | —
2026-10-15 21:07 | debrief | ok | —
2026-10-16 07:48 | brief | ok | —
2026-10-16 21:08 | debrief | ok | —
2026-10-17 07:47 | brief | ok | —
2026-10-17 21:09 | debrief | ok | —
2026-10-18 07:48 | brief | ok | —
2026-10-18 21:08 | debrief | ok | —
2026-10-18 21:40 | bilan-hebdo | ok | —
