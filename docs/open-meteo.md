# Open-Meteo — la météo du brief

> **À quoi sert ce fichier :** autoriser la météo dans les tâches planifiées (un réglage, une seule fois), et comprendre le secours quand Open-Meteo ne répond pas.
> **Mis à jour par :** contenu du projet.

## Pourquoi Open-Meteo

- **Sans clé ni compte** : il n'y a rien à recopier, donc aucun secret à protéger.
- Une prévision **heure par heure** : température, température ressentie, pluie, vent, UV.
- **Gratuit pour un usage personnel et non commercial**, données sous licence CC BY 4.0. Si tu utilises ce projet pour une activité payante (coaching de clients), regarde les [conditions d'Open-Meteo](https://open-meteo.com/en/terms) et son offre commerciale.

## Autoriser la météo dans les tâches planifiées (5 min, une fois)

Les tâches planifiées tournent dans un environnement cloud qui, par défaut, n'autorise qu'une liste de sites (GitHub, registres de logiciels…). La météo n'en fait pas partie. Les connecteurs (Nolio, Agenda) ne sont pas concernés : ils passent par les serveurs d'Anthropic.

1. Ouvre une de tes tâches planifiées, puis **Modifier**.
2. **Paramètres avancés → Général → Environnement cloud** : clique sur l'environnement (par exemple « Default »).
3. Survole-le et clique sur l'icône de réglages.
4. **Accès réseau** : choisis **Personnalisé**, et ajoute dans les domaines autorisés :
   ```
   api.open-meteo.com
   geocoding-api.open-meteo.com
   api.met.no
   ```
5. Coche **inclure aussi la liste par défaut** : GitHub en a besoin pour que le coach puisse pousser son journal.
6. Enregistre. Toutes les tâches qui utilisent cet environnement en profitent dès leur prochaine exécution.

Les libellés exacts peuvent varier selon la version de l'interface. La référence est la [documentation des environnements cloud](https://code.claude.com/docs/en/cloud-environments).

## Les requêtes

**Prévision du jour** (brief du matin) :

```
https://api.open-meteo.com/v1/forecast?latitude=45.19&longitude=5.72&hourly=temperature_2m,apparent_temperature,precipitation_probability,wind_speed_10m,uv_index&daily=sunrise,sunset&timezone=Europe%2FParis&forecast_days=1
```

**Trouver les coordonnées d'une ville** (onboarding, mode voyage) :

```
https://geocoding-api.open-meteo.com/v1/search?name=Grenoble&count=1&language=fr&format=json
```

Les coordonnées de chez toi sont dans `reglages.md` (`latitude`, `longitude`).

## Le secours : MET Norway

Il arrive qu'Open-Meteo réponde « quota dépassé » (429). Les serveurs cloud partagent des adresses : le quota gratuit peut avoir été consommé par d'autres. Le brief passe alors à l'institut météo norvégien, sans clé lui non plus :

```
curl -sS -A "coach-running/1.0 (github.com/<compte>/<repo>)" "https://api.met.no/weatherapi/locationforecast/2.0/compact?lat=45.19&lon=5.72"
```

- Le **User-Agent** (`-A`) est obligatoire : MET Norway demande qu'on identifie l'application.
- Les heures sont en **UTC**, la température est `air_temperature` et la pluie `precipitation_amount`.
- Le lever et le coucher du soleil ne sont pas fournis : le brief les omet.

Le brief note « météo : secours met.no » dans `automations/runs.md`, ce qui permet de voir si c'est fréquent.

## Vérifier que ça marche

Dans une session sur ton repo : « Quelle météo pour courir à 18 h aujourd'hui ? ». Si la réponse parle de `host_not_allowed` ou de `403`, le domaine n'est pas encore autorisé (étape 4).
