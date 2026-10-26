# Nora, l'athlète fictive

> **À quoi sert ce fichier :** présenter l'athlète fictive du projet, ce que montre chaque fichier de ce dossier, et comment lancer le mode démo.
> **Mis à jour par :** contenu du projet (exemple fictif). Personne ne l'écrit pendant l'usage du coach.

**Nora est inventée de toutes pièces**, comme ses courses, ses chiffres et ses échanges avec le coach. Toute ressemblance avec une personne ou une course réelle serait fortuite. Seuls les lieux d'entraînement (Grenoble, la Bastille, la Chartreuse…) sont réels.

Ce dossier a la même arborescence qu'un vrai repo coach. Il sert à deux choses :
- **une vitrine** : à quoi ressemblent un profil rempli, une semaine de journal, un bilan, un plan écrit dans Nolio ;
- **les données du mode démo** : avec `plateforme: demo`, le coach exécute les vraies tâches (`automations/brief-matin.md`, etc.) sur ces fichiers, sans compte Nolio et sans rien écrire.

## Qui est Nora

- Née en 1990, à Grenoble. Elle court depuis 2019, après des années d'escalade.
- Environ 45 km et 1 400 m de D+ par semaine, en 4 à 5 séances. FC max 188 (mesurée en course), FC repos 49, VMA 15 km/h.
- Une périostite en 2023, soignée par une reprise progressive et du renforcement des mollets.
- Temps plein ; elle court le mardi et le jeudi soir, le mercredi midi, et le week-end le matin. Le vendredi, c'est off.
- **Autocoachée** : pas de coach humain, Claude est son entraîneur et écrit dans Nolio après « je valide ».
- Saison 2026-2027 : un semi en octobre (1 h 41 min 30 s, pour un objectif à moins de 1 h 40), un trail de nuit en décembre, et un trail de 52 km et 2 900 m de D+ en avril.
- Philosophie : polarisé 80/20, avec le trail (D+ et spécifique) en complément.

## L'histoire racontée

Le semi du 2026-10-04 est débriefé avec les 5 pourquoi : départ trop rapide, faute de plan de départ écrit. Le 2026-10-06, Nora choisit un trail de 52 km comme course A. Après une semaine de récupération commence la semaine **2026-S42** (du 12 au 18 octobre), la première du bloc :
- **mercredi 14**, une nuit de 5 h 50 met le feu à l'orange : le footing passe de 45 à 35 min. Le soir, une gêne au tendon d'Achille gauche (2/10) est triée : 🟢 « gêne », à surveiller ;
- **jeudi 15**, l'Achille descend à 1/10, la PPG saute faute de temps ;
- **samedi 17**, sortie longue de 2 h 32 avec 1 080 m de D+ et un test de carburant ; l'alerte est levée ;
- **dimanche 18**, le bilan hebdo propose la semaine S43, Nora demande de déplacer la sortie longue au dimanche, valide, et le coach crée 8 séances dans Nolio ;
- **lundi 19**, la date de démo : FC repos à 53 pour une moyenne de 49, feu orange, version allégée proposée.

## Ce que montre chaque fichier

| Fichier | Ce qu'il montre |
|---|---|
| [reglages.md](reglages.md) | un réglage complet : mode autocoaché, `plateforme: demo`, onboarding terminé |
| [etat.md](etat.md) | la mémoire courte au dimanche soir, la seule chose que lit le brief |
| [profil/](profil/) | un profil rempli : historique, objectifs SMART, préférences, santé, retours sur le coach (brief limité à 12 lignes, une idée refusée) |
| [philosophie/choix.md](philosophie/choix.md) | une approche principale et un complément, avec leurs raisons |
| [courses/](courses/) | trois fiches : une course passée (avec son résultat), une course C réduite à l'essentiel, la course A avec son profil et ses ravitos |
| [bilans/courses/2026-10-04-semi-des-berges.md](bilans/courses/2026-10-04-semi-des-berges.md) | un débrief de course complet : tronçons de 5 km, 5 pourquoi, une action datée, un récap partageable |
| [decisions/2026-10-06-objectif-trail-52-km.md](decisions/2026-10-06-objectif-trail-52-km.md) | une décision structurante : options, choix, date de revue |
| [journal/2026/](journal/2026/) | 7 notes du jour, du lundi 12 au dimanche 18 octobre : statuts « conforme », « raccourcie », « repos », RPE saisi dans Nolio ou donné le soir, alerte ouverte puis levée |
| [bilans/hebdo/2026-S42.md](bilans/hebdo/2026-S42.md) | un bilan hebdo : totaux, répartition 80/20, forme, 3 positifs, 1 point à travailler, cap SMART |
| [plan/2026-S43.md](plan/2026-S43.md) | une semaine proposée, ajustée à la demande, puis écrite dans Nolio |
| [plan/registre-nolio.md](plan/registre-nolio.md) | la trace des 8 séances de S43 créées par le coach. Celles de S42, saisies par Nora elle-même, n'y sont pas : le coach n'y touche donc jamais |
| [automations/runs.md](automations/runs.md) | une semaine de journal technique, dont un brief « partiel » (météo de secours) |
| [nolio-simule.md](nolio-simule.md) | **la source de la démo** : séances prévues, activités, VFC, FC repos, sommeil, charge, records, zones et météo, avec les calculs attendus |
| [sorties/brief.md](sorties/brief.md) | le brief exact du lundi 19 octobre (feu orange, version allégée) |
| [sorties/debrief.md](sorties/debrief.md) | le débrief exact du dimanche 18 octobre, qui ne pose que la question qui manque |
| [sorties/bilan-hebdo.md](sorties/bilan-hebdo.md) | le bilan du dimanche, puis l'échange jusqu'à « je valide » et l'écriture dans Nolio |

## Lancer la démo

1. Dans le `reglages.md` **à la racine de ton repo** (pas celui de ce dossier), remplace `plateforme: nolio` par `plateforme: demo`.
2. Ouvre une session Claude sur ton repo et dis : « Fais mon brief du matin ». Le coach lit Nora et `nolio-simule.md`, où « aujourd'hui » est le lundi 2026-10-19. Compare avec [sorties/brief.md](sorties/brief.md).
3. Essaie aussi :
   - « Fais le bilan de la semaine 2026-S42 » → compare avec [bilans/hebdo/2026-S42.md](bilans/hebdo/2026-S42.md) ;
   - « Fais le débrief du soir comme si on était le dimanche 18 octobre » → compare avec [sorties/debrief.md](sorties/debrief.md) ;
   - « Prépare ma semaine prochaine » → une proposition pour la semaine S44 ;
   - « J'ai mal au tendon d'Achille » → le tri d'une douleur ;
   - « Débriefe ma course » → le semi du 4 octobre.
4. En démo, le coach n'écrit aucun fichier, ne fait aucun commit et n'écrit rien dans Nolio : il affiche seulement ce qu'il aurait écrit.
5. Remets `plateforme: nolio` avant de lancer ton propre onboarding.

Les réponses peuvent varier un peu d'une fois à l'autre ; les chiffres, eux, doivent tomber juste. Les calculs attendus (moyenne de VFC sur 7 jours, feu du matin, moyennes de la semaine) sont détaillés dans la section « Métriques » de [nolio-simule.md](nolio-simule.md).
