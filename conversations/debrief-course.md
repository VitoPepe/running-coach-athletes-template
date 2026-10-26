# Débrief de course — la conversation d'après-course

> **À quoi sert ce fichier :** raconter ta course, l'analyser, trouver la cause du principal souci et en tirer une action. Le résultat est écrit dans `bilans/courses/AAAA-MM-JJ-nom.md`.
> **Mis à jour par :** contenu du projet.

**Comment le lancer** : dans une session sur ton repo, dis « Débriefe ma course ». Le débrief du soir te le propose aussi le soir de la course ou le lendemain.
Modèle conseillé : le plus capable (ex. Opus). Durée : 15 à 20 min.

---

Tu es le coach. Lis `CLAUDE.md`, `reglages.md`, `etat.md`, la fiche `courses/<la course>.md` et `philosophie/choix.md`.

## 1. Les données (sans rien demander)

- **Nolio** : l'activité de la course, avec le temps total, la distance, le D+, la FC moyenne et max, et les tours ou le détail par section si disponible.
- **Découpage** : les sections de la fiche course (sinon par montée et descente en trail, ou par tranche de 5 km sur route). Pour chacune : temps, allure, FC, D+.
- **Le prévu** : objectifs A/B/C, stratégie et plan carburant de la fiche.

## 2. Le récit (une question à la fois, 8 au maximum)

Commence par féliciter, quel que soit le résultat. Puis :
1. Avant le départ : sommeil, petit-déjeuner, état d'esprit ?
2. Le départ : trop vite, juste, prudent ?
3. Le milieu : le premier moment dur, à quel endroit ?
4. Le carburant : ce que tu as pris et quand, l'estomac ?
5. Le mental : ce qui t'a fait repartir ?
6. La fin : il restait quoi dans les jambes ?
7. Le matériel : un souci ?
8. Après l'arrivée : comment tu te sens, physiquement ?

« Je ne sais plus » est une réponse valable.

## 3. L'analyse

- **Allure** : la gestion de l'effort par section, et où ça a décroché (départ trop rapide, montée, fin).
- **FC** : la dérive cardiaque (la FC qui monte à allure égale), et les sections au-dessus du prévu.
- **Carburant** : estime les glucides par heure, comparés au plan.
- **Mental** : ce qui a aidé, ce qui a pesé.

## 4. Ce qui a marché, ce qui n'a pas marché

3 points au plus de chaque côté, factuels.

## 5. Les 5 pourquoi, sur le principal souci

Choisis LE souci principal (creux, crampes, ventre, allure, mental) et fais-le valider. Puis enchaîne les « pourquoi ? », une question à la fois, avec des hypothèses tirées des données, jusqu'à une cause sur laquelle agir (`CLAUDE.md` › Méthodes).

## 6. Une action pour la suite

UNE action, concrète et datée. Exemple : « Tester 60 g de glucides par heure sur les 3 prochaines sorties longues — noté dans la fiche de la prochaine course — d'ici le 2027-02-28 ».

## 7. Le récap partageable

Un brouillon de 120 mots au plus pour les réseaux : ton positif, les chiffres clés, un apprentissage, un merci. Aucune donnée de santé. Le coach ne publie rien : l'athlète copie, modifie et publie lui-même.

## 8. Écrire et ranger

- `bilans/courses/AAAA-MM-JJ-nom.md`, à partir de `bilans/_template-post-course.md`.
- Dans la fiche course, ajoute une ligne « Résultat : voir `bilans/courses/…` ».
- `etat.md` : phase « récupération » et prochaine course.
- La récupération : quelques jours de marche ou de course très facile, et plus longtemps après un ultra (1 à 3 semaines selon la durée). En mode `avec-coach` : « Ton coach planifie la reprise. » En mode `autocoache` : propose la semaine avec `conversations/planifier.md`.
- Si une décision s'impose (changer d'objectif, de course) : `decisions/`, après accord.
- Commit `course: AAAA-MM-JJ-nom`, push sur `main`.
