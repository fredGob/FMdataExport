# FM Data Export - BepInEx Plugin for Football Manager 26

BepInEx plugin that exports table data from Football Manager 26 to CSV files.

## Features

- **F10**: Export data from the active table (team, player search, etc.) to CSV
- **F9**: Dump the UI tree to BepInEx log (diagnostic)
- Progressive export with automatic scrolling for large tables (e.g., 36,000 players)
- Automatic rich text cleaning (tags like `<color>`, `<link>`, `<style>`)
- Smart data loading detection (waits for content to stabilize before reading)

## Prerequisites

### 1. Download BepInEx

Go to https://builds.bepinex.dev/projects/bepinex_be
Scroll down and click on the latest build (#753).
Download the **BepInEx-Unity.IL2CPP-win-x64** version (64-bit Windows with IL2CPP support).
Unzip the downloaded file.

### 2. Install BepInEx in FM26

Go to the FM26 installation folder.

> **Tip**: On Steam, right-click FM26 > Properties > Installed Files > Browse.

Copy/paste the unzipped files into this folder. You should get this structure:

```
.../Steam/steamapps/common/Football Manager 26/
├── BepInEx/
├── changelog.txt
├── [...]
├── fm.exe
├── fm_data/
├── [...]
├── dotnet/
├── libdoorstop.so
└── run_bepinex.sh
```

> **IMPORTANT (Linux)**: Add to Steam launch options for FM26:
> ```
> WINEDLLOVERRIDES="winhttp=n,b" %command%
> ```
> (Right-click FM26 in Steam > Properties > Launch Options)

### 3. First Launch

Launch the game **once** so BepInEx initializes and creates the `BepInEx/plugins/` folder.

Verify that the `BepInEx/plugins/` folder exists after this first launch.

## Plugin Installation

Copy `FMDataExport.dll` into the BepInEx plugins folder:

```
.../Steam/steamapps/common/Football Manager 26/BepInEx/plugins/
```

> On Linux/Proton, the actual path is:
> ```
> ~/.local/share/Steam/steamapps/compatdata/<app_id>/pfx/drive_c/users/steamuser/Documents/Sports Interactive/Football Manager 26/exports/
> ```

## Usage

### Export Data (F10)

1. Open any view with a table in FM26 (team, player search, rankings, etc.)
2. Configure the desired columns in the game
3. Press **F10**
4. For small tables: instant export
5. For large tables (player search): the table will scroll automatically. Wait for the scroll to finish.

The CSV file is saved to:
```
Documents/Sports Interactive/Football Manager 26/exports/
```

> On Linux/Proton, the actual path is:
> ```
> ~/.local/share/Steam/steamapps/compatdata/<app_id>/pfx/drive_c/users/steamuser/Documents/Sports Interactive/Football Manager 26/exports/
> ```

### Diagnose UI (F9)

Press **F9** to dump the complete UI tree to the BepInEx log. Useful for debugging and development.

---

# FM Data Export - Plugin BepInEx pour Football Manager 26

Plugin BepInEx qui permet d'exporter les données des tableaux de Football Manager 26 en fichiers CSV.

## Fonctionnalités

- **F10** : Exporte les données du tableau actif (équipe, recherche de joueurs, etc.) en CSV
- **F9** : Dump l'arbre UI dans le log BepInEx (diagnostic)
- Export progressif avec scroll automatique pour les grands tableaux (ex: 36 000 joueurs)
- Nettoyage automatique du rich text (balises `<color>`, `<link>`, `<style>`)
- Détection intelligente du chargement des données (attend que le contenu soit stable avant de lire)

## Prérequis

### 1. Télécharger BepInEx

Aller sur https://builds.bepinex.dev/projects/bepinex_be
Descendre un peu sur la page et cliquer sur le build le plus récent (#753).
Télécharger la version **BepInEx-Unity.IL2CPP-win-x64** (version 64 bits Windows avec prise en charge IL2CPP).
Dézipper le fichier téléchargé.

### 2. Installer BepInEx dans FM26

Aller dans le dossier d'installation de FM26.

> **Astuce** : Sur Steam, clic droit sur FM26 > Propriétés > Fichiers Installés > Parcourir.

Copier/coller les fichiers dézippés dans ce dossier. Vous devez obtenir cette architecture :

```
.../Steam/steamapps/common/Football Manager 26/
├── BepInEx/
├── changelog.txt
├── [...]
├── fm.exe
├── fm_data/
├── [...]
├── dotnet/
├── libdoorstop.so
└── run_bepinex.sh
```

> **IMPORTANT (Linux)** : Ajouter dans les options de lancement Steam de FM26 :
> ```
> WINEDLLOVERRIDES="winhttp=n,b" %command%
> ```
> (Clic droit sur FM26 dans Steam > Propriétés > Options de lancement)

### 3. Premier lancement

Lancer le jeu **une fois** pour que BepInEx s'initialise et crée le dossier `BepInEx/plugins/`.

Vérifier que le dossier `BepInEx/plugins/` existe après ce premier lancement.

## Installation du plugin

Copier `FMDataExport.dll` dans le dossier plugins de BepInEx :

```
.../Steam/steamapps/common/Football Manager 26/BepInEx/plugins/
```

> Sous Linux/Proton, le chemin réel est :
> ```
> ~/.local/share/Steam/steamapps/compatdata/<app_id>/pfx/drive_c/users/steamuser/Documents/Sports Interactive/Football Manager 26/exports/
> ```

## Utilisation

### Exporter des données (F10)

1. Ouvrir n'importe quelle vue avec un tableau dans FM26 (équipe, recherche de joueurs, classement, etc.)
2. Configurer les colonnes souhaitées dans le jeu
3. Appuyer sur **F10**
4. Pour les petits tableaux : export instantané
5. Pour les grands tableaux (recherche de joueurs) : le tableau défilera automatiquement. Attendre la fin du scroll.

Le fichier CSV est enregistré dans :
```
Documents/Sports Interactive/Football Manager 26/exports/
```

> Sous Linux/Proton, le chemin réel est :
> ```
> ~/.local/share/Steam/steamapps/compatdata/<app_id>/pfx/drive_c/users/steamuser/Documents/Sports Interactive/Football Manager 26/exports/
> ```

### Diagnostiquer l'UI (F9)

Appuyer sur **F9** pour dumper l'arbre UI complet dans le log BepInEx. Utile pour le debug et le développement.
