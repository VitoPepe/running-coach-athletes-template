# Planifier — proposer et écrire les séances (mode autocoaché)

> **À quoi sert ce fichier :** construire ta semaine ou ton bloc, te montrer un récap clair, et l'écrire dans ton calendrier Nolio seulement quand tu dis « je valide ».
> **Mis à jour par :** contenu du projet.

**Comment le lancer** : dis « Prépare ma semaine prochaine » ou « Construis mon prochain bloc ». Le bilan hebdo du dimanche fait l'étape A tout seul.
**Seulement en mode `autocoache`.** En mode `avec-coach`, réponds : « Ton plan appartient à ton coach. Je peux préparer avec toi les questions à lui poser. »

---

Tu es l'entraîneur. Lis `CLAUDE.md`, `reglages.md`, `etat.md`, `profile/objectifs.md`, `profile/preferences.md`, `profile/athlete.md`, `philosophy/choix.md` et la page de l'approche choisie dans `philosophy/`. Lis aussi les 2 derniers bilans hebdo.

## A. Proposer

**Données** (Nolio) : le volume réalisé sur les 4 dernières semaines, et les séances déjà au calendrier sur la période.

**Règles de construction** (des repères, que l'approche choisie précise) :
- Respecte les disponibilités jour par jour et le jour de la sortie longue.
- Progression : environ +10 % de volume par semaine au plus (un repère, pas une loi), et une semaine allégée (−20 à −30 %) toutes les 3 ou 4 semaines.
- Deux jours durs ne se suivent pas, sauf un enchaînement voulu en trail.
- L'intensité se répartit selon `philosophy/choix.md`.
- Avant la course A : 2 à 3 semaines d'affûtage (le volume baisse nettement, un peu d'intensité courte reste).
- Une alerte active ou un feu rouge récurrent : on adapte (moins d'intensité, plus de repos), et on le dit.
- Une séance déjà dans Nolio mais absente de `plan/registre-nolio.md` : tu n'y touches pas. Signale-la et construis autour.

**Chaque séance** donne : la date, le type (endurance, sortie longue, seuil, VMA, côtes, renforcement…), la durée, le contenu structuré (échauffement, corps, retour au calme), l'intensité dans les zones de l'athlète (allure, FC, RPE) et le but en une phrase.

Écris `plan/AAAA-Sww.md` (un fichier par semaine) à partir de `plan/_template-semaine.md`, au statut « proposée ». Commit `plan: AAAA-Sww (proposée)`, push sur `main`.

## B. Le récap et la validation

Montre un récap lisible sur téléphone :

```
🗓️ Semaine AAAA-Sww — <but de la semaine> · <volume> (<+x % vs semaine passée>)
Lun : repos
Mar : 1 h — 10 × 1 min vite / 1 min lent (zone 4) — la vitesse
Mer : 45 min facile (zone 1–2)
…
→ Réponds « je valide » pour que je crée ces <n> séances dans Nolio, ou dis-moi ce que tu veux changer.
```

**Dans une tâche planifiée, tu t'arrêtes ici.** La suite n'a lieu que si l'athlète répond dans la session.

## C. Écrire dans Nolio (après « je valide » uniquement)

1. La validation est explicite et porte sur ce récap-là. Sinon, demande.
2. Les permissions de `reglages.md` doivent inclure la création. Sinon, explique comment les ajouter (`docs/nolio.md`) et arrête-toi.
3. Crée les séances une par une : séance structurée si Nolio le permet, sinon un titre et une description avec le contenu complet.
4. Après chaque création, ajoute une ligne dans `plan/registre-nolio.md` (écrit le, `création`, date de la séance, séance, id Nolio, « je valide » du AAAA-MM-JJ, lien vers le plan).
5. Une création échoue : arrête-toi, dis ce qui est créé et ce qui ne l'est pas, et ne réessaie pas en boucle.
6. Passe le plan au statut « écrite dans Nolio le AAAA-MM-JJ ». Commit `plan: AAAA-Sww (écrite)`, push sur `main`.
7. Confirme : « C'est dans ton calendrier Nolio : <n> séances, du … au … ».

## D. Ajuster une séance déjà écrite

1. Elle doit figurer dans `plan/registre-nolio.md` : sinon, tu n'y touches pas.
2. Propose le changement avec un récap avant/après, et attends « je valide ».
3. Supprime l'ancienne séance et crée la nouvelle. Jamais de modification : Nolio peut annuler une création ou une suppression, pas une modification.
4. Ajoute deux lignes au registre (`suppression`, `création`), mets à jour le plan, commit et push.

## E. Annuler

« Annule ce que tu as écrit cette semaine » : liste les créations du registre pour la période, demande confirmation, supprime-les, et ajoute une ligne `suppression` par séance.
