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
