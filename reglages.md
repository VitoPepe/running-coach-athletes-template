# Réglages

> **À quoi sert ce fichier :** les réglages de ton coach (mode, plateforme, lieu, connecteurs) et l'avancement de l'onboarding.
> **Mis à jour par :** l'onboarding, puis toi quand tu veux changer un réglage (édite directement sur GitHub).

<!--
Comment remplir : remplace chaque _à compléter_ par ta réponse, ou laisse l'onboarding le faire pour toi.
Les valeurs possibles sont indiquées entre parenthèses. Garde les noms de champs tels quels (avant les deux-points).
-->

## Athlète

- prenom: _à compléter_

## Mode

- mode: _à compléter_ <!-- avec-coach | autocoache -->
- coach: _à compléter_ <!-- prénom du coach si mode avec-coach, sinon « aucun » -->

## Plateforme

- plateforme: nolio <!-- nolio | demo (demo = essayer avec l'athlète fictif, sans compte Nolio) -->
- permissions_nolio: _à compléter_ <!-- avec-coach : lecture. autocoache : lecture+creation+suppression (jamais « modification »). Voir docs/nolio.md -->

## Lieu et heure

- fuseau: Europe/Paris
- ville_meteo: _à compléter_ <!-- ex. Annecy -->
- latitude: _à compléter_ <!-- ex. 45.90 — l'onboarding la trouve pour toi -->
- longitude: _à compléter_ <!-- ex. 6.13 -->
- heure_reveil: _à compléter_ <!-- ex. 06:30 — sert à caler le brief du matin -->

## Connecteurs

- nolio: oui
- meteo: oui <!-- Open-Meteo, sans clé. Voir docs/open-meteo.md -->
- agenda: non <!-- Google Agenda, en lecture. Voir docs/google-agenda.md -->

## Tâches planifiées actives

| Tâche planifiée | Fichier | Active | Heure | Jour |
|---|---|---|---|---|
| Brief du matin | `automations/brief-matin.md` | oui | 07:37 | tous les jours |
| Débrief du soir | `automations/debrief-soir.md` | oui | 21:07 | tous les jours |
| Bilan hebdo | `automations/bilan-hebdo.md` | oui | 21:37 | dimanche |
| Bilan mensuel | `automations/bilan-mensuel.md` | oui | 19:07 | le 1er du mois |

<!-- Ce tableau sert de mémo. Les vraies heures se règlent dans les tâches planifiées de Claude (voir AUTOMATISATION.md). Brief : environ 1 h après ton réveil, le temps que ta montre synchronise sommeil et VFC. -->

## Onboarding — progression

<!-- Cochée par l'onboarding au fil de l'eau. S'il reste une case vide, l'onboarding reprend là. -->

- [ ] 1. Qui tu es (et ton mode : avec coach ou autocoaché)
- [ ] 2. Ton historique de coureur
- [ ] 3. Tes objectifs et tes courses
- [ ] 4. Tes contraintes de vie et de temps
- [ ] 5. Ta santé
- [ ] 6. Tes préférences
- [ ] 7. Ta philosophie d'entraînement
- [ ] 8. Lieu, connecteurs et premier état
