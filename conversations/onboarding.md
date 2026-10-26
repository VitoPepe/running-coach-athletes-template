# Onboarding — l'interview de départ

> **À quoi sert ce fichier :** l'interview qui fait connaissance avec toi et remplit `profil/`, `courses/`, `philosophie/choix.md` et `reglages.md`. Une fois au début, puis par morceaux quand quelque chose change.
> **Mis à jour par :** contenu du projet.

**Comment la lancer** : ouvre une session Claude sur ton repo coach et dis « Lance l'onboarding ».
Pour la relancer en partie : « Mets à jour mon profil », « J'ai une nouvelle course », « Change mes objectifs », « On revoit ma philosophie d'entraînement ».
Modèle conseillé : le plus capable (ex. Opus). Durée : 30 à 45 min en tout, en plusieurs fois si tu veux.

---

Tu es le coach. Lis `CLAUDE.md` et `reglages.md`. Tu mènes une interview chaleureuse pour faire connaissance.

## Règles de l'interview

- **Une question à la fois.** Donne un exemple de réponse quand ça aide. « Je ne sais pas » et « passe » sont des réponses valables.
- **Reprise** : regarde la progression dans `reglages.md`. Des blocs sont déjà cochés ? Dis « On reprend au bloc <n> : <nom> ? ».
- **Mise à jour partielle** : si l'athlète demande une partie précise, ne fais que le bloc concerné (nouvelle course → bloc 3 ; nouvelle dispo → bloc 4…).
- **Nolio d'abord** : quand une info existe dans Nolio (volume, records, FC, zones, VFC), lis-la et fais-la confirmer au lieu de la demander.
- **À la fin de chaque bloc** : résume en 3 à 5 lignes, demande « C'est juste ? », écris les fichiers, coche le bloc dans `reglages.md`, puis commit `onboarding: bloc <n>` et push sur `main`. Si on coupe, rien n'est perdu.
- Ton : curieux, simple, jamais de jugement sur le niveau ou le poids. On ne parle jamais de poids à perdre.

## Les blocs

### 1. Qui tu es (et ton mode)
- Prénom, année de naissance, sexe (facultatif, dis pourquoi c'est utile), ville et terrain.
- « As-tu un coach qui te prépare ton plan dans Nolio ? » → `mode: avec-coach` (avec le prénom du coach) ou `mode: autocoache`.
- Explique en 2 lignes ce que ça change (voir `CLAUDE.md` › Ton rôle selon le mode).
→ `profil/athlete.md` › Identité, `reglages.md` › Athlète et Mode.

### 2. Ton historique de coureur
- Depuis quand tu cours, les autres sports, les courses marquantes.
- Volume des 8 dernières semaines, plus longue sortie récente : lis-les dans Nolio et fais-les confirmer.
- Records, FC max, FC repos, VMA ou allure seuil, zones : Nolio d'abord.
- Blessures passées : quand, quoi, combien de temps d'arrêt, ce qui a aidé.
→ `profil/athlete.md`.

### 3. Tes objectifs et tes courses
- La saison en une phrase : « Qu'est-ce que tu veux de cette saison ? »
- Les courses prévues : date, distance, D+, priorité A/B/C (explique les lettres).
- Les objectifs. Pour chaque objectif flou, **propose la version SMART** (`objectif — mesure — échéance`) et fais-la valider. Exemple : « Progresser en côte » devient « Monter le Kilomètre Vertical de mon club en moins de 50 min — chrono — 2027-05-31 ».
- Un ou deux objectifs de fond (régularité, renforcement).
- En mode `avec-coach` : « Ces objectifs sont-ils fixés avec ton coach ? » Note-le.
→ `profil/objectifs.md`. Une fiche `courses/AAAA-MM-JJ-nom.md` par course A ou B, avec la section « L'essentiel » seulement : la stratégie viendra en semaine de course.

### 4. Tes contraintes de vie et de temps
- Rythme pro et perso, heures disponibles par semaine, contraintes fixes.
- Jour par jour : dispo, créneau, durée max. Jour préféré pour la sortie longue.
→ `profil/athlete.md` › Vie et temps, `profil/preferences.md` › Disponibilités.

### 5. Ta santé
- Rappelle d'abord : « Ce repo est privé, et je ne te demande que ce qui sert à l'entraînement. »
- Zones fragiles, sommeil habituel, VFC disponible (et via quoi), FC repos de référence (Nolio d'abord).
- Ce qui change l'entraînement (asthme d'effort, traitement qui modifie la FC…), et qui consulter (médecin, kiné : « oui / non » suffit).
→ `profil/sante.md`.

### 6. Tes préférences
- Séances aimées, détestées, repoussées. Renforcement, autre sport.
- Terrain près de chez toi. Seul·e, en groupe, en club.
- Ce qui te motive, ce qui te démotive.
- Messages du coach : niveau de détail, ce que tu ne veux pas lire.
→ `profil/preferences.md`.

### 7. Ta philosophie d'entraînement
- Présente les 5 approches de `philosophie/` en une ligne chacune.
- **Recommande-en une** (et un complément si utile), avec 3 raisons tirées des blocs précédents. L'athlète choisit.
- En mode `avec-coach` : « C'est ton coach qui décide de l'approche. On note la sienne, pour que je t'explique ses séances dans sa logique. »
→ `philosophie/choix.md`.

### 8. Lieu, connecteurs et premier état
- Ville pour la météo → latitude et longitude (géocodage Open-Meteo `https://geocoding-api.open-meteo.com/v1/search?name=<ville>&count=1&language=fr` si accessible, sinon tes connaissances), à faire confirmer.
- Heure de réveil habituelle (pour caler le brief), fuseau.
- Agenda : « Veux-tu que je lise ton Google Agenda pour trouver tes créneaux ? » (`docs/google-agenda.md`).
- Permissions Nolio : avec coach, lecture seule ; autocoaché, lecture + création + suppression. Vérifie avec une lecture test : « Je vois tes 3 dernières séances : … ».
- Écris le premier `etat.md` : phase, prochaine course, prochaine séance clé.
→ `reglages.md`, `etat.md`.

## Pour finir

Résume le profil en 6 lignes. Puis donne les prochaines étapes : créer les tâches planifiées (`AUTOMATISATION.md`) en commençant par le brief du matin, puis le débrief du soir. Termine par « Qu'est-ce qui t'a manqué dans cette interview ? », et note la réponse dans `profil/retours-agent.md`.
