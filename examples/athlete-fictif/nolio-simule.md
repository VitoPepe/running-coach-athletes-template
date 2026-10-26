# Nolio simulé — les données de la plateforme pour la démo

> **À quoi sert ce fichier :** remplacer le connecteur Nolio et la météo en mode démo (`plateforme: demo`) : le coach lit ici ce qu'il lirait dans Nolio et sur Open-Meteo. Exemple fictif : les données inventées de Nora.
> **Mis à jour par :** personne. Données figées, écrites à la main pour la démo ; le coach ne les modifie jamais.

Date de démo (aujourd'hui) : 2026-10-19 (lundi)

Les séances de 2026-S42 ont été saisies dans Nolio par Nora elle-même : elles ne figurent pas dans `plan/registre-nolio.md`, et le coach n'y touche pas. Celles de 2026-S43 ont été créées par le coach le 2026-10-18, après « je valide » (ids `nolio-demo-…`).

| Section de ce fichier | Équivalent dans Nolio |
|---|---|
| Séances prévues | le planning de l'athlète |
| Activités réalisées | les activités, avec le RPE et le commentaire saisis par l'athlète |
| Métriques | `list_metrics` : `RMSSD`, `FCREPOS`, `SOMMEIL` |
| Charge | `get_training_load` |
| Records, zones, compétitions | le profil de l'athlète |
| Météo simulée | Open-Meteo (pas Nolio) |

## Séances prévues

| Date | Jour | Séance | Durée | Structure | Cibles d'intensité | Créée par |
|---|---|---|---|---|---|---|
| 2026-10-12 | lundi | Renforcement (PPG) | 25 min | mollets en excentrique sur une marche 3 × 15, chaise 3 × 45 s, fentes 3 × 10, gainage 3 × 40 s | RPE 4 | Nora |
| 2026-10-13 | mardi | Seuil en côte | 1 h | échauffement 15 min + 3 lignes droites ; 4 × 6 min en montée régulière (5 à 7 %), récup 2 min au trot ; retour au calme 15 min en descente souple ; ≈ 300 m D+ | répétitions en Z3 (FC 155–164), RPE 6–7 ; le reste en Z1–Z2 | Nora |
| 2026-10-14 | mercredi | Footing d'endurance | 45 min | en continu, à midi | Z1–Z2 (FC ≤ 154), RPE 2–3 | Nora |
| 2026-10-15 | jeudi | Footing + lignes droites | 50 min | 45 min en continu + 6 lignes droites de 20 s, récup complète en marchant | Z1–Z2 (FC ≤ 154) ; lignes droites relâchées | Nora |
| 2026-10-15 | jeudi | Renforcement (PPG) | 15 min | mollets, chaise, gainage | RPE 4 | Nora |
| 2026-10-17 | samedi | Sortie longue trail | 2 h 30 | boucle sur sentiers, ≈ 1 100 m D+ ; marche active dès que la pente devient raide ; test de carburant : 2 gels + 500 ml de boisson | Z1–Z2 (FC ≤ 154), montées jusqu'à Z3 tolérées, RPE 4–5 | Nora |
| 2026-10-18 | dimanche | Footing vallonné | 1 h 10 | en continu sur chemins vallonnés, ≈ 150 m D+ | Z1–Z2 (FC ≤ 154), marcher dans les bosses si besoin, RPE 3 | Nora |
| 2026-10-19 | lundi | Footing facile + 6 lignes droites | 45 min | 40 min en continu sur le plat + 6 lignes droites de 20 s, récup complète en marchant | Z1–Z2 (FC ≤ 154), RPE 2–3 ; lignes droites relâchées | coach · `nolio-demo-4312` |
| 2026-10-20 | mardi | Côtes courtes | 55 min | 20 min en Z1–Z2 ; 8 × 1 min en côte (6 à 8 %), récup en redescendant au trot (≈ 1 min 30) ; 15 min de retour au calme | côtes en Z4 (FC 165–173), RPE 8 ; le reste en Z1–Z2 | coach · `nolio-demo-4313` |
| 2026-10-21 | mercredi | Footing d'endurance | 45 min | en continu, à midi | Z1–Z2 (FC ≤ 154), RPE 2–3 | coach · `nolio-demo-4314` |
| 2026-10-22 | jeudi | Footing d'endurance | 35 min | en continu | Z1–Z2 (FC ≤ 154), RPE 2–3 | coach · `nolio-demo-4315` |
| 2026-10-22 | jeudi | Renforcement (PPG) | 20 min | mollets en excentrique 3 × 15, chaise 3 × 45 s, fentes 3 × 10, gainage 3 × 40 s | RPE 4 | coach · `nolio-demo-4316` |
| 2026-10-24 | samedi | Footing vallonné | 1 h | chemins vallonnés, ≈ 150 m D+ | Z1–Z2, marche dans les bosses si la FC passe 154 | coach · `nolio-demo-4317` |
| 2026-10-24 | samedi | Renforcement (PPG) | 20 min | comme jeudi | RPE 4 | coach · `nolio-demo-4318` |
| 2026-10-25 | dimanche | Sortie longue trail | 2 h 40 | ≈ 1 150 m D+ ; marche active dès que la pente devient raide ; descentes souples ; test de carburant ≈ 40 g/h (3 gels + 750 ml de boisson d'effort) | Z1–Z2, montées jusqu'à Z3 tolérées, RPE 4–5 | coach · `nolio-demo-4319` |

Pas de séance les vendredis (repos).

## Activités réalisées (semaine 2026-S42)

Temps par zone en minutes, regroupé en 3 zones : basse = Z1–Z2, moyenne = Z3, haute = Z4–Z5.

| Date | Titre | Durée | Distance | D+ | FC moy | FC max | Basse | Moyenne | Haute | Allure moy. | RPE | Commentaire de l'athlète |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 2026-10-12 | Renforcement (PPG) | 25 min | — | — | — | — | — | — | — | — | non saisi | — |
| 2026-10-13 | Seuil en côte | 58 min | 9,5 km | 300 m | 148 | 167 | 33 | 23 | 2 | 6:06 /km | 7 (saisi) | « Bonnes sensations, 4e rép dure mais tenue. » |
| 2026-10-14 | Footing midi | 35 min | 5,9 km | 30 m | 134 | 143 | 35 | 0 | 0 | 5:56 /km | non saisi | « Achille gauche raide au réveil, parti après 10 min. Raccourci à 35 min comme proposé ce matin. » |
| 2026-10-15 | Footing + lignes droites | 48 min | 8,3 km | 40 m | 138 | 166 | 46 | 1 | 1 | 5:47 /km | non saisi | — |
| 2026-10-17 | Sortie longue trail | 2 h 32 | 16,4 km | 1 080 m | 143 | 168 | 124 | 26 | 2 | 9:16 /km | 6 (saisi) | « 2 gels + 500 ml de boisson, estomac OK. Achille RAS. » |
| 2026-10-18 | Footing vallonné | 1 h 11 | 11,2 km | 150 m | 137 | 157 | 67 | 4 | 0 | 6:20 /km | 3 (saisi) | « Jambes un peu lourdes de la veille, pas de douleur. » |

Total course à pied de la semaine : 5 sorties, 364 min (6 h 04), 51,3 km, 1 600 m D+ ; 305 min en basse, 54 en moyenne, 5 en haute. Plus 1 séance de PPG de 25 min.

Les RPE « non saisi » ont été donnés en réponse au débrief du soir : PPG du 12 → 4, footing du 14 → 3, footing du 15 → 4 (voir le journal).

## Métriques

Norme sur 60 jours (du 2026-08-21 au 2026-10-19) :
- `RMSSD` (VFC) : moyenne 58 ms, écart-type 6 ms → norme 52–64 ms ; « très basse » sous 58 − 2 × 6 = 46 ms.
- `FCREPOS` : moyenne 49 bpm.

| Date | RMSSD (ms) | FCREPOS (bpm) | SOMMEIL (durée · score) |
|---|---|---|---|
| 2026-10-06 | 50 | 53 | 7 h 40 · 78 |
| 2026-10-07 | 53 | 52 | 7 h 25 · 75 |
| 2026-10-08 | 56 | 50 | 7 h 50 · 82 |
| 2026-10-09 | 58 | 49 | 7 h 35 · 80 |
| 2026-10-10 | 60 | 48 | 8 h 05 · 85 |
| 2026-10-11 | 57 | 49 | 7 h 20 · 77 |
| 2026-10-12 | 59 | 48 | 7 h 45 · 83 |
| 2026-10-13 | 61 | 48 | 7 h 30 · 81 |
| 2026-10-14 | 54 | 51 | 5 h 50 · 58 |
| 2026-10-15 | 58 | 50 | 7 h 40 · 80 |
| 2026-10-16 | 62 | 48 | 8 h 10 · 86 |
| 2026-10-17 | 60 | 48 | 7 h 55 · 84 |
| 2026-10-18 | 55 | 51 | 7 h 15 · 74 |
| 2026-10-19 | 49 | 53 | 7 h 05 · 71 |

Chaque ligne correspond à la nuit qui se termine ce matin-là.

### Pour vérifier la démo

Brief du 2026-10-19 :
- VFC des 7 dernières nuits (du 13 au 19) : (61 + 54 + 58 + 62 + 60 + 55 + 49) / 7 = 399 / 7 = 57,0 ms → dans la norme (52–64).
- VFC de la nuit : 49 ms, au-dessus du seuil « très basse » (46 ms).
- FC repos : 53 bpm > 49 + 3 = 52 → décroche.
- Sommeil : 7 h 05 pour une habitude de 7 h 30 (`profil/sante.md`) : pas nettement en dessous, pas de cran en plus.
- Alerte active dans `etat.md` : aucune.
- Feu attendu : 🟠 (un seul signal décroche, la FC repos).

Débrief du 2026-10-18 (forme récente de `etat.md`, nuits du 12 au 18) :
- VFC : (59 + 61 + 54 + 58 + 62 + 60 + 55) / 7 = 409 / 7 = 58,4 ms.
- FC repos : (48 + 48 + 51 + 50 + 48 + 48 + 51) / 7 = 344 / 7 = 49,1 bpm.
- Sommeil : (465 + 450 + 350 + 460 + 490 + 475 + 435) / 7 = 3 125 / 7 = 446 min, soit 7 h 26.

## Charge

Valeurs **simulées**, en unités arbitraires : Nolio calcule sa propre charge, et ses noms et formules peuvent différer. Charge chronique = moyenne des 4 semaines précédentes ; forme = chronique − aiguë (négative : en charge ; positive : frais).

| Semaine | Du … au … | Sorties (+ PPG) | Durée de course | Distance | D+ | Basse / moyenne / haute | Charge de la semaine (aiguë) | Charge chronique | Ratio aiguë / chronique | Forme |
|---|---|---|---|---|---|---|---|---|---|---|
| 2026-S38 | 2026-09-14 → 2026-09-20 | 5 (+ 2) | 6 h 15 | 54,0 km | 1 250 m | 82 / 16 / 2 % | 410 | 385 | 1,06 | −25 |
| 2026-S39 | 2026-09-21 → 2026-09-27 | 5 (+ 1) | 5 h 30 | 48,5 km | 900 m | 85 / 12 / 3 % | 360 | 395 | 0,91 | +35 |
| 2026-S40 | 2026-09-28 → 2026-10-04 | 4 (+ 1), dont le semi | 4 h 06 | 43,3 km | 250 m | 59 / 10 / 31 % | 395 | 388 | 1,02 | −7 |
| 2026-S41 | 2026-10-05 → 2026-10-11 | 4 (+ 1) | 4 h 10 | 35,4 km | 970 m | 237 / 13 / 0 min, soit 95 / 5 / 0 % | 210 | 391 | 0,54 | +181 |
| 2026-S42 | 2026-10-12 → 2026-10-18 | 5 (+ 1) | 6 h 04 | 51,3 km | 1 600 m | 305 / 54 / 5 min, soit 84 / 15 / 1 % | 405 | 344 | 1,18 | −61 |

Charges des semaines S34 à S37, pour les moyennes : 370, 390, 380, 400. S41 : 20 min de PPG.

## Records

| Distance | Temps | Date | Course |
|---|---|---|---|
| 5 km | 21 min 58 s | 2026-06-06 | test chronométré, seule, sur piste |
| 10 km | 46 min 05 s | 2025-11-09 | 10 km des Quais (fictive) |
| Semi-marathon | 1 h 41 min 30 s | 2026-10-04 | Semi-marathon des Berges (fictive) |
| Marathon | — | | |
| Trail le plus long | 5 h 12 min, 34 km, 1 900 m D+ | 2025-06-14 | Trail des Lauzes (fictive) |

FC max mesurée : 188 (2025-11-09, sprint final des 10 km des Quais).

## Compétitions

| Date | Course | Priorité | Distance | D+ |
|---|---|---|---|---|
| 2026-12-05 | Trail de la Bastille nocturne (fictive), départ 18:00 | C | 18 km | 900 m |
| 2027-04-17 | Trail des Trois Fontaines (fictive), départ 06:30 | A | 52 km | 2 900 m |

## Zones de l'athlète

Zones de FC enregistrées dans Nolio, calées sur la FC max de 188 ; allures indicatives sur le plat, pour une VMA de 15 km/h.

| Zone | FC (bpm) | % FC max | Allure indicative | Ressenti | Modèle à 3 zones du coach |
|---|---|---|---|---|---|
| Z1 | 113–135 | 60–72 % | plus lent que 6:10 /km | très facile, récupération | basse |
| Z2 | 136–154 | 72–82 % | 6:10 à 5:15 /km | endurance fondamentale, tu parles | basse |
| Z3 | 155–164 | 82–87 % | 5:15 à 4:40 /km | tempo, seuil : quelques mots | moyenne |
| Z4 | 165–173 | 87–92 % | 4:40 à 4:10 /km | fractionné long, VMA | haute |
| Z5 | 174–188 | plus de 92 % | plus rapide que 4:10 /km | fractionné court, sprint | haute |

Repères : 1er seuil vers FC 154 (≈ 5:15 /km), 2e seuil vers FC 164 (≈ 4:40 /km).

## Météo simulée

Grenoble (45.19, 5.72), lundi 2026-10-19, heure locale (Europe/Paris), comme la réponse d'Open-Meteo. Lever du soleil 07:59, coucher 18:45.

| Heure | Température | Ressenti | Pluie (%) | Vent (km/h) | UV |
|---|---|---|---|---|---|
| 06:00 | 7 °C | 5 °C | 5 | 6 | 0 |
| 07:00 | 7 °C | 5 °C | 5 | 6 | 0 |
| 08:00 | 8 °C | 6 °C | 5 | 7 | 0 |
| 09:00 | 9 °C | 8 °C | 5 | 8 | 1 |
| 10:00 | 11 °C | 10 °C | 5 | 9 | 1 |
| 11:00 | 12 °C | 11 °C | 10 | 10 | 2 |
| 12:00 | 13 °C | 12 °C | 10 | 10 | 2 |
| 13:00 | 14 °C | 13 °C | 10 | 11 | 2 |
| 14:00 | 14 °C | 13 °C | 15 | 12 | 2 |
| 15:00 | 14 °C | 13 °C | 15 | 12 | 1 |
| 16:00 | 13 °C | 12 °C | 20 | 12 | 1 |
| 17:00 | 13 °C | 12 °C | 30 | 11 | 0 |
| 18:00 | 12 °C | 11 °C | 40 | 10 | 0 |
| 19:00 | 11 °C | 9 °C | 55 | 12 | 0 |
| 20:00 | 10 °C | 8 °C | 60 | 13 | 0 |
| 21:00 | 10 °C | 8 °C | 65 | 13 | 0 |
