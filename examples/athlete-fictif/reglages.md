# Réglages

> **À quoi sert ce fichier :** les réglages de ton coach (mode, plateforme, lieu, connecteurs) et l'avancement de l'onboarding. Exemple fictif : les réglages de Nora, athlète inventée.
> **Mis à jour par :** l'onboarding, puis toi quand tu veux changer un réglage (édite directement sur GitHub). Ici : exemple fictif, figé.

## Athlète

- prenom: Nora

## Mode

- mode: autocoache <!-- avec-coach | autocoache -->
- coach: aucun <!-- prénom du coach si mode avec-coach, sinon « aucun » -->

## Plateforme

- plateforme: demo <!-- dans un vrai repo : nolio -->
- permissions_nolio: lecture+creation+suppression <!-- avec-coach : lecture. autocoache : lecture+creation+suppression (jamais « modification »). Voir docs/nolio.md -->

## Lieu et heure

- fuseau: Europe/Paris
- ville_meteo: Grenoble
- latitude: 45.19
- longitude: 5.72
- heure_reveil: 06:45

## Connecteurs

- nolio: oui
- meteo: oui <!-- Open-Meteo, sans clé. En démo : section « Météo simulée » de nolio-simule.md -->
- agenda: non

## Routines actives

| Tâche planifiée | Fichier | Active | Heure | Jour |
|---|---|---|---|---|
| Brief du matin | `automations/brief-matin.md` | oui | 07:47 | tous les jours |
| Débrief du soir | `automations/debrief-soir.md` | oui | 21:07 | tous les jours |
| Bilan hebdo | `automations/bilan-hebdo.md` | oui | 21:37 | dimanche |
| Bilan mensuel | `automations/bilan-mensuel.md` | oui | 19:07 | le 1er du mois |

<!-- Brief : environ 1 h après le réveil de Nora (06:45), le temps que sa montre synchronise sommeil et VFC. -->

## Onboarding — progression

- [x] 1. Qui tu es (et ton mode : avec coach ou autocoaché)
- [x] 2. Ton historique de coureur
- [x] 3. Tes objectifs et tes courses
- [x] 4. Tes contraintes de vie et de temps
- [x] 5. Ta santé
- [x] 6. Tes préférences
- [x] 7. Ta philosophie d'entraînement
- [x] 8. Lieu, connecteurs et premier état
