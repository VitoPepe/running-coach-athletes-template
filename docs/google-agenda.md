# Google Agenda — optionnel

> **À quoi sert ce fichier :** brancher ton agenda pour que le coach trouve le bon créneau et repère tes déplacements. C'est optionnel : sans lui, le coach marche très bien.
> **Mis à jour par :** contenu du projet.

## Ce que ça apporte

- **Le meilleur créneau** : le brief croise ta journée et la météo (« entre 12 h et 13 h, avant la pluie »).
- **Les déplacements** : un train, un hôtel ou une adresse dans une autre ville déclenche le mode voyage (`automations/modules/voyage.md`).
- **Le lendemain** : le débrief voit si demain est chargé.

## Ce que le coach ne fait pas

- **Il ne crée, ne modifie et ne supprime aucun événement** sans ta confirmation explicite dans la conversation.
- **Il ne recopie pas tes événements dans le repo.** Seul un déplacement peut apparaître, en une ligne, dans `etat.md` › Situation particulière (« Lyon du 2026-11-03 au 2026-11-05 »).

## Brancher (3 min)

1. Dans Claude : **Réglages → Connecteurs → Google Calendar**. Connecte ton compte Google.
2. Dans `reglages.md` : `agenda: oui`.
3. Dans les tâches **brief du matin** et **débrief du soir**, coche le connecteur Google Calendar. Laisse-le décoché pour les bilans : ils n'en ont pas besoin.
4. Vérifie dans une session : « Quel est mon meilleur créneau pour courir demain ? ».

## Débrancher

Remets `agenda: non` dans `reglages.md`, décoche le connecteur dans les tâches, et retire-le dans **Réglages → Connecteurs** si tu ne t'en sers nulle part ailleurs.
