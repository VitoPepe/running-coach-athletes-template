# Article Medium « complet » côté coureur — le plan

> **À quoi sert ce fichier :** le plan de l'article long et des posts LinkedIn : le système complet, ses 6 niveaux et ses garde-fous. La version courte, pour les non-techniques, est dans `docs/article-medium-facile.md`. La matière vient de `docs/journal-de-construction.md` ; les schémas, de `docs/architecture.md` et `AUTOMATISATION.md`.
> **Mis à jour par :** le mainteneur du projet.

## L'angle

Un coureur et ingénieur data a construit un coach de course à pied avec Claude et Nolio, **sans écrire une ligne de code** : un dossier de fichiers texte, des prompts et des tâches planifiées. L'article montre comment monter, marche par marche, du simple carnet au coach qui écrit ton plan, et pourquoi chaque garde-fou est là.

## Titres possibles

1. « J'ai construit mon coach de trail avec Claude et Nolio. Voici les 6 niveaux d'automatisation. »
2. « Un coach de course à pied en fichiers Markdown : zéro code, six niveaux, trois verrous. »
3. « De ChatGPT à l'entraîneur : comment j'ai appris à mon IA à ne jamais toucher au plan de mon coach. »
4. « Le brief du matin qui lit ma VFC, la météo et mon plan, en 30 secondes sur mon téléphone. »

## Structure de l'article (≈ 8 min de lecture)

1. **L'accroche** (≈ 150 mots) : un matin de semaine, le brief arrive sur le téléphone. Montrer le vrai format (exemple fictif de `examples/athlete-fictif/sorties/brief.md`), feu orange compris. « Ce message, personne ne l'a écrit. »
2. **Le problème** : les données sont là (montre, Nolio), le plan aussi (coach ou soi-même). Ce qui manque, c'est quelqu'un qui relie les deux chaque jour, explique, et se souvient.
3. **L'idée : un repo-mémoire** : des fichiers texte que Claude lit et écrit. Schéma 1 de `docs/architecture.md`. Pourquoi Markdown et Git (lisible, historique gratuit, zéro serveur).
4. **Les 6 niveaux**, un paragraphe et une capture chacun (schéma de `AUTOMATISATION.md`) :
   - 0, la démo ; 1, le carnet ; 2, le coach branché ; 3, le coach qui vient à toi ; 4, le coach surveillé ; 5, l'entraîneur.
   - Pour chaque niveau : ce qu'on ajoute, ce qu'on gagne, le temps d'installation.
5. **Les trois verrous** (le cœur technique) : permissions Nolio, règle « une tâche planifiée ne vaut pas accord », registre des écritures. Schéma 4.
6. **Rester léger** : `etat.md`, les prompts talons, les lectures ciblées, les modules conditionnels. Le coût ne grossit pas avec les mois. Schéma 3.
7. **Ce que j'ai appris** : 4 ou 5 entrées du journal de construction (sélection ci-dessous).
8. **Les limites** : pas un médecin, pas un coach humain, dépend de la qualité des données, abonnement payant (Claude, Nolio Premium).
9. **L'appel** : le template sur GitHub, la checklist de test, les contributions bienvenues (d'autres plateformes, une version anglaise).

## Entrées du journal à mettre en avant

- 🔍 « Une tâche planifiée ne vaut pas consentement » : quand la contrainte technique et la règle métier vont dans le même sens.
- 🔍 Les permissions Nolio et la défense en profondeur.
- ✅ `etat.md` : une mémoire courte pour un coût constant.
- ✅ Les messages de sécurité écrits mot pour mot.
- 🧱 Le débrief du soir qui pose des questions à personne.
- 🧱 La météo bloquée par l'environnement cloud, puis le quota, puis le secours.

## Visuels

- Capture du brief sur téléphone (exemple fictif).
- Schéma « vue d'ensemble » (`docs/architecture.md`, section 1).
- Schéma des niveaux (`AUTOMATISATION.md`).
- Schéma des deux modes (`docs/architecture.md`, section 4).
- Capture de `automations/runs.md` et du mail de la GitHub Action.

## Chiffres à mesurer avant de publier

- [ ] Nombre de jours de fonctionnement réel.
- [ ] Exécutions réussies / partielles / en échec (`automations/runs.md`).
- [ ] Consommation mensuelle observée (Claude, Réglages → Utilisation).
- [ ] Temps d'installation réel des niveaux 1 à 3, mesuré sur un testeur.
- [ ] Un retour de testeur (coureur ou coach), avec son accord.

## Post LinkedIn — trois pistes (format court)

**Piste 1, le résultat**
> Chaque matin à 7 h 37, mon téléphone me dit : ta séance, pourquoi elle compte, ta forme du jour (🟢🟠🔴), la météo et la tenue.
> Personne ne l'écrit. C'est Claude, branché sur Nolio, avec un dossier de fichiers texte comme mémoire.
> J'en ai fait un template open source, en 6 niveaux : du carnet au coach qui écrit ton plan (après ton « je valide »).
> Lien en commentaire.

**Piste 2, le garde-fou**
> La question qu'on m'a posée en premier : « et si l'IA modifie le plan de mon coach ? »
> Réponse : elle ne peut pas. Trois verrous : les permissions Nolio, une règle (une tâche automatique ne vaut jamais accord), et un registre de tout ce qu'elle écrit.
> Le reste est dans l'article.

**Piste 3, l'ingénieur data**
> J'ai appliqué au running ce que je fais au travail : des données propres, une mémoire courte, un contrôle nocturne qui m'envoie un mail si un traitement n'a pas tourné.
> Sauf que là, le « pipeline » me dit quoi courir demain.
