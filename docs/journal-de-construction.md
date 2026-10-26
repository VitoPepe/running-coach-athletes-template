# Journal de construction

> **À quoi sert ce fichier :** les choix, les difficultés et les bonnes pratiques notés pendant la construction du projet. C'est la matière première des deux articles Medium côté coureur (`docs/article-medium-facile.md`, `docs/article-medium-complet.md`).
> **Mis à jour par :** le mainteneur du projet, au fil de l'eau. Une entrée = une idée, datée.

Légende : 🧭 choix · 🧱 difficulté · ✅ bonne pratique · 🔍 découverte

---

## 2026-10-22 — Le squelette

### 🧭 Un repo de fichiers Markdown, zéro code

Le coach est un dossier de fichiers texte : profil, objectifs, journal, bilans. Aucune ligne de code, aucun serveur.
**Pourquoi :** la cible est un coureur qui sait utiliser claude.ai et créer un compte GitHub, rien de plus. Markdown se lit et s'édite directement sur GitHub, même depuis un téléphone. Git apporte l'historique gratuitement : on voit ce que le coach a écrit, et quand.

### 🧭 Le cerveau tient dans un seul fichier court

`CLAUDE.md` est lu à chaque session. Il dit *qui tu es, quel mode, où trouver quoi, ce qui est interdit*. Le détail de chaque tâche vit dans `automations/`, et celui de chaque conversation dans `conversations/`.
**Pourquoi :** un `CLAUDE.md` long coûte des tokens à chaque exécution et dilue les règles importantes. Les règles de sécurité sont écrites une seule fois, à un seul endroit.

### 🔍 Le MCP Nolio permet de choisir ses permissions

À la connexion du connecteur Nolio, on coche lecture, création, modification, suppression. Nolio précise qu'une création ou une suppression peut être annulée, mais pas une modification.
**Conséquence :** une défense en profondeur. En mode `avec-coach`, on ne coche que *lecture* : même un prompt mal compris ne peut pas toucher au plan du coach. En mode `autocoache`, on coche *lecture + création + suppression*, jamais *modification* : pour changer une séance, le coach la supprime et la recrée. Tout reste annulable, et chaque écriture est tracée dans `plan/registre-nolio.md`.

### 🔍 Une tâche planifiée ne vaut pas consentement

Le prompt d'une tâche planifiée a été enregistré à l'avance. Il ne peut pas tenir lieu d'accord pour une action pendant l'exécution.
**Conséquence :** en autocoaché, la tâche du dimanche *propose* une semaine, et l'écriture dans Nolio n'a lieu que lorsque l'athlète répond « je valide » dans la session. C'est exactement le comportement qu'on voulait : la contrainte technique et la règle métier vont dans le même sens.

### 🔍 Par défaut, Claude pousse sur une branche `claude/…`

Dans une tâche planifiée cloud, Claude pousse ses modifications sur une branche préfixée `claude/`, sauf si le prompt dit autre chose. Pour un repo-mémoire, on veut que le journal arrive sur `main`.
**Conséquence :** chaque prompt de tâche dit explicitement « commit et push sur `main` ».

### 🧱 Open-Meteo n'est pas joignable par défaut

L'environnement cloud par défaut n'autorise qu'une liste de domaines (registres de paquets, clouds…). `api.open-meteo.com` n'en fait pas partie.
**Solution :** un réglage unique dans l'environnement (accès réseau personnalisé + le domaine). Documenté pas à pas dans `docs/open-meteo.md`. Les connecteurs (Nolio, Agenda) passent par les serveurs d'Anthropic et ne sont pas concernés.

### 🧭 Des prompts « talons »

Le prompt collé dans la tâche planifiée fait quatre lignes : « lis `CLAUDE.md`, exécute `automations/brief-matin.md`, n'écris pas dans Nolio, push sur `main` ». Toute la logique vit dans le repo.
**Pourquoi :** on améliore une automatisation en éditant un fichier, sans retourner dans les réglages de Claude. Les améliorations sont versionnées, comparables, partageables.

### ✅ Une mémoire courte : `etat.md`

Le brief du matin ne lit qu'un fichier du repo : `etat.md`, réécrit chaque soir (40 lignes max). Il ne relit jamais le journal.
**Pourquoi :** c'est le principal levier d'économie. Une tâche quotidienne qui relit 3 mois de journal coûte de plus en plus cher chaque jour. Avec `etat.md`, le coût reste constant.

### ✅ Le brief du matin n'écrit (presque) rien

Il lit, il parle, et il n'ajoute qu'une ligne au journal technique `automations/runs.md`.
**Pourquoi :** moins de bruit dans l'historique Git, moins de tokens, et aucun risque d'écraser quelque chose à 7 h du matin. La seule ligne écrite sert à la surveillance (voir plus bas).

### 🧱 Le débrief du soir pose des questions… à personne

Une tâche planifiée tourne seule : personne n'est là pour répondre aux 3 questions (ressenti, RPE, douleur).
**Solution :** le débrief écrit la note du jour avec ce qu'il sait (« non renseigné » sinon), pose ses questions en fin de message, et complète la note quand l'athlète répond dans la session, le soir même. Et si l'athlète a déjà saisi son RPE ou un commentaire dans Nolio, la question n'est pas posée.

### ✅ Les messages de sécurité sont écrits mot pour mot

Douleur thoracique, malaise, blessure : `CLAUDE.md` contient le texte exact à afficher, sans reformulation.
**Pourquoi :** un modèle de langage nuance par réflexe. Sur ces sujets, la nuance est un défaut.

### 🧭 Plusieurs niveaux d'automatisation

Du « carnet que tu remplis en conversation » au « coach qui écrit ton plan dans Nolio », chaque niveau ajoute une brique et reste utile seul. Voir `AUTOMATISATION.md`.
**Pourquoi :** on peut s'arrêter à n'importe quel niveau, et l'article Medium suit cette progression.

### 🧭 Partir d'un agent qui tourne déjà

La structure ne sort pas d'un tableau blanc. Elle reprend celle d'un agent personnel en production depuis octobre 2026 : un dossier `automations/` avec un fichier par tâche planifiée (en-tête de réglages, puis le prompt après `---`), un journal technique des exécutions, une boucle de retours, et un « mode course » lu par le brief et le récap.
**Pourquoi :** chaque choix a déjà été éprouvé au quotidien. Le travail a surtout consisté à *retirer* ce qui était personnel (nutrition détaillée, recettes, proches…) pour garder un cœur générique et sûr.

### 🧭 `automations/` d'un côté, `conversations/` de l'autre

Ce qui tourne tout seul (brief, débrief, bilans) vit dans `automations/`. Ce qu'on lance en parlant (onboarding, débrief de course, douleur, planification) vit dans `conversations/`.
**Pourquoi :** pour un non-développeur, la question est simple : « est-ce que je dois faire quelque chose pour que ça se lance ? ». Le dossier répond.

### ✅ Des modules plutôt que des tâches en plus

La semaine de course, le voyage, la reprise, la veille d'une séance clé et le check matériel ne sont pas des tâches planifiées. Ce sont des consignes (`automations/modules/`) que le brief ou le débrief lisent seulement quand la condition est vraie.
**Pourquoi :** zéro tâche de plus à créer, et zéro token dépensé les jours où ça ne sert pas.

### 🧱 Un agent qui tourne seul peut tomber en panne en silence

Un connecteur expiré, un domaine bloqué, un quota dépassé : la tâche « réussit » techniquement (statut vert) mais le brief est vide. Ce sont des incidents réellement observés sur l'agent personnel.
**Solution :** chaque tâche écrit une ligne `date | tâche | ok/partiel/échec | sources en échec` dans `automations/runs.md`. Chaque nuit, une GitHub Action lance `scripts/controle.py` : une tâche absente ou en échec fait échouer le contrôle, et GitHub envoie un mail. Rien à configurer pour l'athlète.

### 🧱 Le quota Open-Meteo dépassé

Les environnements cloud partagent des adresses : le quota gratuit d'Open-Meteo a déjà été atteint, par d'autres, avant même le premier appel du jour.
**Solution :** un secours sans clé, MET Norway (`api.met.no`), qui exige seulement un User-Agent identifiant l'application. Le brief note « secours met.no » dans le journal technique.

### 🧭 Le feu de forme : ta norme, pas une norme

Le feu compare la VFC moyenne des 7 derniers jours à ta norme personnelle sur 60 jours (moyenne ± 1 écart-type), et la FC repos à ta moyenne (+3 bpm). Le rouge vient quand les deux décrochent, ou quand une nuit est très basse.
**Pourquoi :** la VFC varie énormément d'une personne à l'autre. Seule la tendance par rapport à soi a du sens. C'est aussi une règle qu'on peut expliquer en une ligne dans le brief.

### ✅ Une boucle d'amélioration intégrée

Chaque tâche finit par une question (« Trop long ce matin ? »). Les réponses vont dans `profil/retours-agent.md`, et l'agent ajuste son propre prompt quand l'athlète valide, sans jamais toucher aux règles de sécurité. Le bilan mensuel condense le fichier pour qu'il reste sous 4 Ko.
**Pourquoi :** le meilleur prompt est celui que l'athlète a façonné. Et un fichier de retours qui grossit sans fin finit par coûter cher à chaque lecture.

### 🧭 Une démo sans compte

`examples/athlete-fictif/` contient un athlète complet et un faux Nolio (`nolio-simule.md`, météo comprise). Avec `plateforme: demo`, les vrais prompts tournent sur ces données, sans rien écrire.
**Pourquoi :** on essaie en 5 minutes avant de s'engager. Et ça sert aussi de banc de test reproductible pour chaque modification de prompt.

### 🔍 Le connecteur Nolio demande un Premium Athlete, même avec un coach

Vérifié le 2026-10-23 : un athlète sur un compte gratuit n'a pas accès au connecteur, même si son coach a un compte payant.
**Conséquence :** le mode `avec-coach` suppose que l'athlète paie son propre Premium Athlete. C'est écrit dans les prérequis (README, `AUTOMATISATION.md`, `docs/nolio.md`). À garder en tête pour une offre destinée aux coachs : le coût se répercute sur chaque athlète.

---

## Ce qui reste à faire

- [ ] Fusionner `feat/squelette` dans `main`, puis passer le repo en template (Settings → Template repository).
- [ ] Tester le mode démo (`docs/checklist-de-test.md`, partie A) sur un vrai compte Claude.
- [ ] Vérifier sur un vrai compte que les outils `list_metrics` et `get_training_load` existent dans le connecteur Nolio (demander à Claude « Quels outils Nolio as-tu ? »), et corriger `docs/nolio.md` sinon.
- [ ] Faire l'onboarding sur soi, puis faire tourner les tâches planifiées une semaine.
- [ ] Mesurer les chiffres des articles : jours de fonctionnement, exécutions ok/partielles/échec, consommation, temps d'installation d'un testeur.
- [ ] Rédiger les deux articles à partir de `docs/article-medium-facile.md` et `docs/article-medium-complet.md`.
- [ ] Projet jumeau pour les coachs : `running-coach-coaches-template` (même structure).
