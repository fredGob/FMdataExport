# FM26 Scout Dashboard

Football scouting dashboard based on CSV exports from Football Manager 2026. **100% client-side** application in a single HTML file.

## Quick Start

1. Open `FM26_dataAnalyser.html` in a browser
2. Drag and drop (or click) to load a CSV file exported from FM26
3. Explore players by profile, apply filters, click on a player for details

## Prepare Data in FM26

### Install STATS View

The `STATS.fmf` file contains the column configuration expected by the dashboard.

Copy `STATS.fmf` to the FM26 views folder:
```
Documents/Sports Interactive/Football Manager 26/views/
```

> On Linux/Proton:
> ```
> ~/.local/share/Steam/steamapps/compatdata/<app_id>/pfx/drive_c/users/steamuser/Documents/Sports Interactive/Football Manager 26/views/
> ```

### Configure Player Search

1. Go to **Scouting > Player Database**
2. Change the network and select **World** (optional, to get all players)
3. Remove all filters, select **Interest = not considered**
4. Modify search, uncheck **Exclude: your team**
5. Add a minimum playing time filter to **0 minutes** (Add condition > General Stats > General > Minutes)
6. Load the **STATS** view: right-click on a column > Import View > Import STATS

### Export

Use the [DataExport](../DataExport/) plugin (**F10**) to generate the CSV, then import it into the dashboard.

## Features

- **Filters**: name, club, division, age, minutes played, minimum rating, max salary, contract end, league level
- **8 position profiles**: GK, CB, FB, DM, CM, AM, WG, ST
- **Play styles**: each profile has specialized sub-styles (e.g., CB > Stopper / Ball-Playing)
- **Rating**: each player is rated 0-100 by an adapted rating system
- **League strength**: rating adjustment based on division level
- **Detail panel**: ratings by profile and style, interactive radar chart, complete stats
- **Settings**: modify profile weights via settings modal
- **Theme**: dark / light, persisted in localStorage

### Available Profiles and Styles

| Profile | Specialized Styles |
|---------|---------------------|
| GK | Sweeper, Ball-Playing |
| CB | Stopper, Ball-Playing |
| FB | Defensive, Offensive |
| DM | Anchor, Playmaker |
| CM | Organizer, Box-to-Box |
| AM | Creator, Attacking |
| WG | Dribbler, Playmaker |
| ST | Finisher, Target Man |

## Technical Stack

No build, no server. Just open `FM26_dataAnalyser.html`.

- **PapaParse 5.4.1** (CDN) — CSV parsing
- **Chart.js 4.4.0** (CDN) — radar charts
- **Google Fonts (Inter)** — typography
- **Font Awesome 6.5.1** (CDN) — icons

## Expected CSV Format

Export via DataExport plugin with STATS view:
- **Encoding**: UTF-8 BOM, comma delimiter, European numbers (`2,7` = 2.7)
- **44 columns** (name, age, club, division, position, salary, contract, matches, minutes, goals, stats per-90)
- **10,000+ players** typically

## Files

| File | Description |
|-------|-------------|
| `FM26_dataAnalyser.html` | Complete application (HTML + CSS + JS) |
| `STATS.fmf` | FM26 view with expected columns |
| `FM26_Example_data.csv` | Example file to test the dashboard |

---

# FM26 Scout Dashboard

Dashboard de recrutement football basé sur les exports CSV de Football Manager 2026. Application **100% client-side** dans un seul fichier HTML.

## Utilisation rapide

1. Ouvrir `FM26_dataAnalyser.html` dans un navigateur
2. Glisser-déposer (ou cliquer) pour charger un fichier CSV exporté depuis FM26
3. Explorer les joueurs par profil, appliquer des filtres, cliquer sur un joueur pour le détail

## Préparer les données dans FM26

### Installer la vue STATS

Le fichier `STATS.fmf` contient la configuration des colonnes attendues par le dashboard.

Copier `STATS.fmf` dans le dossier des vues FM26 :
```
Documents/Sports Interactive/Football Manager 26/views/
```

> Sous Linux/Proton :
> ```
> ~/.local/share/Steam/steamapps/compatdata/<app_id>/pfx/drive_c/users/steamuser/Documents/Sports Interactive/Football Manager 26/views/
> ```

### Configurer la recherche de joueurs

1. Aller dans **Recrutement > Base de données joueurs**
2. Changer le réseau et sélectionner **Monde** (optionnel, pour avoir tous les joueurs)
3. Supprimer tous les filtres, sélectionner **Intérêt = pas envisagé**
4. Modifier la recherche, décocher **Exclure : votre équipe**
5. Ajouter un filtre de temps de jeu minimum à **0 minutes** (Ajouter condition > Stats générales > Général > Minutes)
6. Charger la vue **STATS** : clic droit sur une colonne > Importation de l'affichage > Importer STATS

### Exporter

Utiliser le plugin [DataExport](../DataExport/) (**F10**) pour générer le CSV, puis l'importer dans le dashboard.

## Fonctionnalités

- **Filtres** : nom, club, division, âge, minutes jouées, note minimum, salaire max, fin de contrat, niveau de ligue
- **8 profils de poste** : GK, CB, FB, DM, CM, AM, WG, ST
- **Styles de jeu** : chaque profil dispose de sous-styles spécialisés (ex: CB > Stoppeur / Relanceur)
- **Notation** : chaque joueur est noté 0-100 par un système de note adapté
- **Force des ligues** : ajustement de la note selon le niveau de la division
- **Panneau détail** : notes par profil et par style, radar chart interactif, stats complètes
- **Paramètres** : modifier les poids de chaque profil via la modale paramètres
- **Thème** : dark / light, persisté en localStorage

### Profils et styles disponibles

| Profil | Styles spécialisés |
|--------|-------------------|
| GK | Ligne, Relanceur |
| CB | Stoppeur, Relanceur |
| FB | Défensif, Offensif |
| DM | Sentinelle, Relayeur |
| CM | Organisateur, Box-to-Box |
| AM | Créateur, Attaquant |
| WG | Dribbleur, Passeur |
| ST | Finisseur, Pivot |

## Stack technique

Aucun build, aucun serveur. Juste ouvrir `FM26_dataAnalyser.html`.

- **PapaParse 5.4.1** (CDN) — parsing CSV
- **Chart.js 4.4.0** (CDN) — radar charts
- **Google Fonts (Inter)** — typographie
- **Font Awesome 6.5.1** (CDN) — icônes

## Format du CSV attendu

Export via le plugin DataExport avec la vue STATS :
- **Encodage** : UTF-8 BOM, délimiteur virgule, nombres européens (`2,7` = 2.7)
- **44 colonnes** (nom, âge, club, division, position, salaire, contrat, matchs, minutes, buts, stats per-90)
- **10 000+ joueurs** typiquement

## Fichiers

| Fichier | Description |
|---------|-------------|
| `FM26_dataAnalyser.html` | Application complète (HTML + CSS + JS) |
| `STATS.fmf` | Vue FM26 avec les colonnes attendues |
| `FM26_Example_data.csv` | Fichier d'exemple pour tester le dashboard |
