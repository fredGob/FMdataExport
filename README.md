# FM Data Export - BepInEx Plugin for Football Manager 26

Plugin BepInEx qui permet d'exporter les donnees des tableaux de Football Manager 26 en fichiers CSV.

## Fonctionnalites

- **F10** : Exporte les donnees du tableau actif (equipe, recherche de joueurs, etc.) en CSV
- **F9** : Dump l'arbre UI dans le log BepInEx (diagnostic)
- Export progressif avec scroll automatique pour les grands tableaux (ex: 36 000 joueurs)
- Nettoyage automatique du rich text (balises `<color>`, `<link>`, `<style>`)
- Detection intelligente du chargement des donnees (attend que le contenu soit stable avant de lire)

## Prerequis

Aller sur https://builds.bepinex.dev/projects/bepinex_be

Décendre un peu sur la page et cliquer sur le build le plus récent (#753 chez moi).

Et télécharger la version BepInEx-Unity.IL2CPP-win-x64*
Soit la version 64 bits de Windows avec prise IL2CPP.

Dézipper le fichier téléchargé.


Aller dans le dossier d'installation FM26

**Astuce** : Sur Steam, clic droit sur FM26, aller dans Propriétés, puis Fichiers Installés, puis Parcourir.
Puis copier/coller les fichier dézippé précédemment.

Vous devez avoir une architecture

'''
.../.local/share/Steam/steamapps/common/Football Manager 26/

BepInEx
changelog.txt
[...]
fm.exe
fm_data
[...]
dotnert
libdoorstop.so
run_bepinex.sh
'''

**IMPORTANT**: Sur linux, Ajouter dans les options de lancement Steam de FM26 :
   ```
   WINEDLLOVERRIDES="winhttp=n,b" %command%
   ```
   (Clic droit sur FM26 dans Steam > Proprietes > Options de lancement)


## Lancer le jeu UNE FOIS pour que BepInEx initialise et cree le dossier `BepInEx/plugins/`
Verifier que ca marche: le dossier `BepInEx/plugins/` doit exister apres le premier lancement

## Installation du plugin

Copier `FMDataExport.dll` dans le dossier plugins de BepInEx :

```
~/.local/share/Steam/steamapps/common/Football Manager 26/BepInEx/plugins/
```

## Utilisation

### Exporter des donnees (F10)

1. Ouvrir n'importe quelle vue avec un tableau dans FM26 (equipe, recherche de joueurs, classement, etc.)
2. Configurer les colonnes souhaitees dans le jeu
3. Appuyer sur **F10**
4. Pour les petits tableaux : export instantane
5. Pour les grands tableaux (recherche de joueurs) : le tableau defilera automatiquement. Attendre la fin du scroll.

Le fichier CSV est enregistre dans :
```
Documents/Sports Interactive/Football Manager 26/exports/
```

> Sous Linux/Proton, le chemin reel est :
> ```
> ~/.local/share/Steam/steamapps/compatdata/<app_id>/pfx/drive_c/users/steamuser/Documents/Sports Interactive/Football Manager 26/exports/
> ```



# Dans FM26
Récupérer le fichier STATS.fmf

coller le fichier ici :
/home/fred/.local/share/Steam/steamapps/compatdata/3551340/pfx/drive_c/users/steamuser/Documents/Sports Interactive/Football Manager 26/views



Dans le menu Recrutement -> Base de donnée joueurs
Le but ici est d'afficher TOUS les joueurs de la base.

Changer le réseau et sélectionner Monde (optionnel)
Supprimer tous les filtres, sélectionner Interêt = pas envisagé
Modifier la recherche, décocher Exclure : votre équipe
Ajouter un filtre de temps de jeu minimum à 0 minutes (Ajouter condition -> Stats (générales) -> Général -> Minutes).


Charger la vue STATS 
Clic droit sur une colonne -> Importation de l'affichage -> Importer STATS


La liste des colonnes

Nom
Age
Club
Pays du club
Division
Posisition

Salaire estimé
expiration contrat

Minutes jouées
Notes

Encaissé/90min
Arrêt/90min
xG evité/90min
% arrêt

Dégagement/90min
Bloc /90min
Interception/90min
Tacles/90min
Tacles décisifs/90min

Possession remportée/90min
Possession perdue/90min

Pressing tenté/90min
Pressing réussi/90min

Duel aérien joué/90min
Duel aérien remportés/90min

Passe tentée/90min
Passe réussie/90min
% passe réussie
Passe progressive/90min
Passe clé dans le jeu/90min
Passe décisive attendue/90min
Occasion crée/90min

Centre tenté/90min
Centre réussi/90min

Dribble/90min


Tir/90min
% tir cadré
xG hors penalty

Distance/90min
Sprint/90min


Aller chercher le fichier généré
Importer ensuite le fichier csv dans l'outil html.
