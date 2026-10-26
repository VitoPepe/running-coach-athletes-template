# Architecture — comment le coach fonctionne, en schémas

> **À quoi sert ce fichier :** comprendre le système d'un coup d'œil : qui parle à qui, ce qui se passe dans une journée, où vit la mémoire, et comment les deux modes protègent ton plan.
> **Mis à jour par :** contenu du projet.

## 1. Vue d'ensemble

Trois briques : **Claude** (le cerveau qui exécute), **ton repo GitHub** (la mémoire, en fichiers texte) et les **connecteurs** (Nolio pour les séances et la montre, la météo, l'agenda en option). Une GitHub Action surveille le tout chaque nuit.

```mermaid
flowchart TB
    A(["🏃 Toi · app Claude, sur téléphone ou ordinateur"])
    subgraph C["🧠 Claude, ton compte"]
        direction LR
        T["⏰ Tâches planifiées<br/>brief · débrief · bilans"]
        S["💬 Conversations<br/>onboarding · course · douleur · plan"]
    end
    subgraph R["📁 Ton repo : la mémoire"]
        direction LR
        M["profil/ · journal/ · bilans/<br/>etat.md · reglages.md"]
        P["CLAUDE.md · automations/<br/>conversations/"]
    end
    subgraph X["🔌 Sources"]
        direction LR
        N[("Nolio<br/>séances · montre · VFC")]
        W[("Météo<br/>Open-Meteo, met.no")]
        G[("Google Agenda<br/>optionnel")]
    end
    GH["🔍 GitHub Action<br/>contrôle nocturne, mail si problème"]
    A <-->|"briefs, questions, réponses"| C
    C <-->|"lit, écrit, commit"| R
    C -->|"lit ; écrit dans Nolio seulement après « je valide »"| X
    R -->|"automations/runs.md, chaque nuit"| GH
```

## 2. Une journée

Le brief du matin ne lit **qu'un fichier** du repo (`etat.md`). Le débrief du soir écrit la note du jour et réécrit `etat.md` pour le lendemain. La boucle est bouclée.

```mermaid
sequenceDiagram
    autonumber
    participant M as Montre
    participant N as Nolio
    participant B as Brief 07:37
    participant A as Toi
    participant D as Débrief 21:07
    participant R as Repo
    M->>N: nuit synchronisée (VFC, FC repos, sommeil)
    B->>R: lit etat.md
    B->>N: séance du jour et forme
    B->>A: séance expliquée, feu, météo, tenue
    B->>R: une ligne dans runs.md
    A->>M: la séance
    M->>N: activité synchronisée
    D->>N: prévu, réalisé, séance de demain
    D->>R: note du jour et nouvel etat.md
    D->>A: bilan du jour et 3 questions au plus
    A->>D: réponses en vrac, quand tu veux
    D->>R: note du jour complétée
```

## 3. La mémoire : qui lit quoi

Chaque niveau résume le précédent : le journal fait les bilans hebdo, les bilans hebdo font le bilan mensuel. Personne ne relit tout, et le coût reste constant au fil des mois.

```mermaid
flowchart TB
    BR["☀️ brief-matin"]
    DS["🌙 debrief-soir"]
    BH["📊 bilan-hebdo"]
    BM["🗓️ bilan-mensuel"]
    ET["etat.md<br/>mémoire courte, 40 lignes"]
    JO["journal/AAAA/AAAA-MM-JJ.md<br/>une note par jour, figée"]
    BHf["bilans/hebdo/AAAA-Sww.md"]
    BMf["bilans/mensuel/AAAA-MM.md"]
    PR["profil/objectifs.md"]
    DS -->|"écrit"| JO
    DS -->|"réécrit"| ET
    ET -->|"seul fichier lu"| BR
    JO -->|"les 7 notes"| BH
    BH -->|"écrit"| BHf
    BH -->|"met à jour"| ET
    BHf -->|"4 ou 5 bilans"| BM
    BM -->|"écrit"| BMf
    BM -.->|"propose, tu valides"| PR
```

## 4. Les deux modes

Le même coach, deux rôles. Avec un coach humain, il assiste et ne touche jamais au plan. En autocoaché, il entraîne, mais n'écrit qu'après ta validation, en conversation.

```mermaid
flowchart TD
    Q{"mode dans reglages.md"}
    Q -->|"avec-coach"| AC["Assistant<br/>lit Nolio, explique, prépare, débriefe"]
    AC --> AC2["Ses idées deviennent des questions pour ton coach<br/>Nolio en lecture seule"]
    Q -->|"autocoache"| AU["Entraîneur<br/>propose tes semaines et tes blocs"]
    AU --> R1["Récap clair : dates, contenu, intensité"]
    R1 --> V{"« je valide »<br/>dans une conversation ?"}
    V -->|"oui"| W["Crée les séances dans Nolio<br/>et les note dans registre-nolio.md"]
    V -->|"non, ou tâche planifiée"| P["Rien n'est écrit<br/>la semaine reste une proposition"]
```

Trois verrous empilés :
1. **Les permissions Nolio** : lecture seule en mode avec coach, et jamais « modification ».
2. **La règle de `CLAUDE.md`** : jamais d'écriture pendant une tâche planifiée, et jamais sans récap ni « je valide ».
3. **Le registre** : le coach ne touche qu'aux séances qu'il a créées lui-même.

## 5. Le feu du matin

```mermaid
flowchart TD
    D{"Mesures de la nuit ?"} -->|"non"| GR["⚪ pas de mesure : écoute tes sensations"]
    D -->|"oui"| NB{"VFC de la nuit très basse ?<br/>sous moyenne 60 j − 2 écarts-types"}
    NB -->|"oui"| RO["🔴 repos ou 30 min très facile"]
    NB -->|"non"| V{"VFC des 7 jours dans ta norme ?<br/>moyenne 60 j ± 1 écart-type"}
    V -->|"oui"| F1{"FC repos ≤ moyenne + 3 bpm ?"}
    V -->|"non"| F2{"FC repos ≤ moyenne + 3 bpm ?"}
    F1 -->|"oui"| G["🟢 la séance telle quelle"]
    F1 -->|"non"| O["🟠 écoute tes sensations, version allégée possible"]
    F2 -->|"oui"| O
    F2 -->|"non"| RO
```

Ensuite : un sommeil sous 6 h décale d'un cran vers l'orange, et une alerte active (douleur, maladie) interdit le vert. Les règles complètes sont dans `automations/brief-matin.md`.

## 6. Générique contre propre à Nolio

Tout ce qui parle de Nolio est isolé. Brancher Garmin, Strava ou TrainingPeaks demain, c'est réécrire la partie de droite, sans toucher au reste.

```mermaid
flowchart LR
    subgraph G["Générique : ne bouge pas"]
        CL["CLAUDE.md"]
        AU["automations/ : les étapes"]
        CO["conversations/"]
        DA["profil/ · journal/ · bilans/"]
    end
    subgraph S["Propre à la plateforme"]
        SP["section « Plateforme : Nolio »<br/>de chaque automatisation"]
        DN["docs/nolio.md"]
    end
    CT["docs/plateformes.md<br/>le contrat de données"]
    AU --> SP
    SP --> MCP[("connecteur Nolio")]
    DN -.- SP
    CT -.-> SP
```

## 7. Le contrôle nocturne

```mermaid
sequenceDiagram
    participant T as Chaque tâche
    participant R as automations/runs.md
    participant GA as GitHub Action 04:17 UTC
    participant A as Toi
    T->>R: AAAA-MM-JJ HH:MM | brief | ok | —
    GA->>R: lit les dernières lignes
    alt tout va bien
        GA-->>GA: ✅ « Ton coach tourne bien »
    else tâche absente, en échec, ou lien cassé
        GA->>A: mail de GitHub avec le rapport
    end
```
