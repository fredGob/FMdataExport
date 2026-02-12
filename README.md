# FM26 Scout Tools

Outils de scouting pour Football Manager 2026 : extraction des données du jeu et analyse dans un dashboard interactif.

## Structure du projet

Le projet est composé de deux parties indépendantes :

### [DataExport](DataExport/)

Plugin BepInEx qui s'injecte dans FM26 pour exporter les données des tableaux en fichiers CSV. Appuyer sur **F10** en jeu pour lancer l'export.

- Plugin C# (.dll) pour BepInEx
- Export progressif avec scroll automatique pour les grands tableaux (36 000+ joueurs)
- Nettoyage automatique du rich text

### [DataAnalyser](DataAnalyser/)

Dashboard web 100% client-side pour analyser les joueurs exportés. Ouvrir `index.html` dans un navigateur et importer le CSV.

- 8 profils de poste (GK, CB, FB, DM, CM, AM, WG, ST) avec styles de jeu spécialisés
- Notation percentile pondérée avec prise en compte de la force des ligues
- Filtres avancés, tri, pagination, radar charts, panneau détail

## Workflow

```
FM26 (en jeu)          DataExport             DataAnalyser
+--------------+      +-------------+      +----------------+
| Tableau de   | F10  | Export CSV   | -->  | Import CSV     |
| joueurs      |----->| automatique  |      | + Analyse      |
+--------------+      +-------------+      +----------------+
```

1. Configurer la vue dans FM26 (voir [DataAnalyser/README](DataAnalyser/) pour la vue recommandée)
2. Appuyer sur **F10** pour exporter en CSV via le plugin
3. Ouvrir le dashboard et importer le fichier CSV
