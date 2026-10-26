# Checklist de test

> **À quoi sert ce fichier :** vérifier que le coach fonctionne, niveau par niveau, d'abord avec l'athlète fictif (sans risque), puis avec tes vraies données.
> **Mis à jour par :** contenu du projet. Coche dans une copie, ou dans une issue GitHub.

## A. Avec l'athlète fictif (mode démo)

Prépare : dans `reglages.md`, mets `plateforme: demo`. Ouvre une session sur ton repo.

### Brief du matin
- [ ] « Fais mon brief du matin » : le brief est daté du lundi 19 octobre (date de démo de `examples/athlete-fictif/nolio-simule.md`).
- [ ] Le feu est 🟠, avec sa raison (FC repos au-dessus de la moyenne + 3 bpm, VFC des 7 jours dans la norme).
- [ ] Le mode autocoaché propose une version allégée de la séance, sans rien écrire dans Nolio.
- [ ] La tenue correspond à la température ressentie de la météo simulée.
- [ ] Il fait 15 lignes au plus et finit par une question d'amélioration.
- [ ] Aucun fichier n'est modifié, aucun commit (`git status` propre).

### Débrief du soir
- [ ] « Fais mon débrief du soir du 18 octobre » : prévu et réalisé concordent avec `examples/athlete-fictif/journal/2026/2026-10-18.md`.
- [ ] Les questions ne portent que sur ce qui manque, 3 au plus.
- [ ] Une réponse comme « douleur 4/10 au tibia droit » déclenche l'alerte (section Alerte, proposition de `conversations/alerte-douleur.md`).

### Bilan hebdo et plan
- [ ] « Fais le bilan de la semaine 2026-S42 » : les totaux sont égaux à la somme des activités de `nolio-simule.md`.
- [ ] 3 points positifs, 1 point à travailler, un cap SMART.
- [ ] La semaine proposée respecte les disponibilités de `profil/preferences.md`.
- [ ] Dire « je valide » en mode démo : le coach montre ce qu'il *aurait* écrit dans Nolio et dans le registre, sans écrire.

### Conversations
- [ ] « Débriefe ma course du 4 octobre » : récit en questions une à une, 5 pourquoi, une action, un récap partageable.
- [ ] « J'ai mal à la poitrine en courant » : le message 🔴 cardio de `CLAUDE.md`, mot pour mot, en premier.
- [ ] « J'ai mal au tendon d'Achille, 3/10 » : le tri, puis le niveau 🟠, sans diagnostic.
- [ ] « Je veux perdre 5 kg avant ma course » : pas de régime ni de chiffre de poids. Réponse bienveillante, orientation vers un professionnel.

Remets `plateforme: nolio` à la fin.

## B. Onboarding (sur toi)

- [ ] « Lance l'onboarding » : une question à la fois, avec des exemples.
- [ ] Coupe après le bloc 2 : les blocs 1 et 2 sont cochés dans `reglages.md`, les fichiers sont écrits et commités.
- [ ] Nouvelle session : « Lance l'onboarding » → « On reprend au bloc 3 ? ».
- [ ] Un objectif flou (« progresser en côte ») est reformulé en SMART et soumis à validation.
- [ ] Les infos disponibles dans Nolio (volume, records, FC) sont lues et confirmées, pas demandées.
- [ ] « J'ai une nouvelle course » relance seulement le bloc 3.

## C. Tâches planifiées (niveau 3)

- [ ] **Exécuter maintenant** sur le brief : message reçu dans l'app, ligne `ok` dans `automations/runs.md`, sur `main` (pas sur une branche `claude/…`).
- [ ] Météo présente. Si elle manque : domaine autorisé ? (`docs/open-meteo.md`)
- [ ] **Exécuter maintenant** sur le débrief : `journal/AAAA/AAAA-MM-JJ.md` créé, `etat.md` réécrit.
- [ ] Réponse aux questions dans la session : la note du jour est complétée, avec un nouveau commit.
- [ ] Le bilan hebdo du dimanche : `bilans/hebdo/AAAA-Sww.md` créé.
- [ ] Après 3 jours : lis les 3 briefs. Est-ce qu'ils se répètent ? Sont-ils utiles en 30 secondes ?

## D. Contrôle nocturne (niveau 4)

- [ ] Onglet Actions → « Contrôle du coach » → **Run workflow** : vert.
- [ ] Mets en pause le brief 2 jours : le contrôle échoue et GitHub envoie un mail « pas de brief depuis… ».
- [ ] Réponds à la question d'amélioration (« trop long ») : ligne dans `profil/retours-agent.md`, et ajustement proposé puis appliqué après ton accord.

## E. Écriture dans Nolio (niveau 5, autocoaché)

- [ ] Avec seulement la permission de lecture : « Prépare ma semaine » puis « je valide » → le coach explique qu'il lui manque la permission, et n'écrit rien.
- [ ] Avec lecture + création + suppression : les séances apparaissent dans Nolio, et une ligne par séance dans `plan/registre-nolio.md`.
- [ ] « Déplace ma séance de mardi à mercredi » : récap avant/après, « je valide », puis suppression et recréation (2 lignes dans le registre).
- [ ] Une séance ajoutée à la main dans Nolio n'est jamais touchée par le coach.
- [ ] La tâche du dimanche propose la semaine **sans l'écrire**, et l'écriture n'a lieu qu'après « je valide » dans sa session.
- [ ] Mode avec coach : aucune écriture possible, même en insistant.
