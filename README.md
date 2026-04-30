# Pressions maritimes et biodiversité marine en Europe

## Résumé

Ce projet étudie la relation entre la distribution spatiale d'observations de biodiversité marine en Europe et la proximité de deux types de pressions anthropiques : les ports maritimes et les infrastructures offshore.

Le jeu de données final croise des occurrences biologiques issues de GBIF avec des données géographiques sur les ports et les infrastructures offshore. Les observations sont associées à une distance minimale au port le plus proche et à l'infrastructure offshore la plus proche, puis regroupées en classes de proximité pour produire des requêtes SQL, des visualisations et des analyses statistiques.

## Problématique

Dans quelle mesure la proximité des ports maritimes et des infrastructures offshore influence-t-elle la distribution spatiale des observations de biodiversité marine en Europe ?

## Données utilisées

- Observations biologiques marines : `DataSet/cnidaria_europe_2026-04-15_13-16.csv`, `DataSet/elasmobranchii_europe_2026-04-15_13-16.csv`, `DataSet/malacostraca_europe_2026-04-15_13-16.csv.zip`
- Ports maritimes : `DataSet/port_maritime_eur_2026-04-15_13-17.csv`
- Infrastructures offshore : `DataSet/offshore_europe_2026-04-15_13-17.csv`
- Observations consolidées : `DataSet/observation_europe_2026-04-15_13-17.csv`

## Résultats principaux

- Le jeu final contient **459 773 observations** biologiques géoréférencées sur la période 2010-2023.
- Les observations sont très déséquilibrées taxonomiquement : Arthropoda représente la quasi-totalité des données.
- La majorité des observations se situe loin des ports, ce qui crée une distribution très asymétrique des classes de distance.
- Les analyses montrent une association entre proximité aux infrastructures et structure spatiale des observations, mais l'interprétation reste limitée par les biais d'échantillonnage et le déséquilibre entre phylums.

## Visualisations

### Animation temporelle

![Animation de la distance au port dans le temps](GroupReportTemplate%202-2/figures/animation_distance_temporelle.gif)

### Carte interactive

[Ouvrir la carte interactive HTML](GroupReportTemplate%202-2/figures/carte_biodiversite_marine.html)

La carte dépend aussi du dossier `GroupReportTemplate 2-2/figures/carte_biodiversite_marine_files/`, qui doit rester à côté du fichier HTML.

## Rapport

- [Rapport R Markdown](GroupReportTemplate%202-2/scdon2-UPV-report-template.Rmd)
- [Rapport PDF](GroupReportTemplate%202-2/scdon2-UPV-report-template.pdf)
- [Version HTML du rapport](GroupReportTemplate%202-2/scdon2-UPV-report-template.html)

## Organisation du dépôt

```text
.
├── DataSet/                         # Données sources et données préparées
├── GroupReportTemplate 2-2/         # Rapport final, figures et rendus
│   ├── figures/                     # Graphiques, GIF et carte HTML
│   └── scdon2-UPV-report-template.Rmd
├── Query SQL/                       # Requêtes SQL et versions Markdown
├── SQL requettes/                   # Sorties CSV des requêtes
├── code r.Rmd                       # Code R de préparation des visualisations
└── README.md
```

## Méthodes

Le projet combine :

- modélisation relationnelle avec MCD/MOD ;
- import, nettoyage et enrichissement SQL ;
- calcul de distances minimales aux ports et aux infrastructures offshore ;
- classes de proximité ;
- analyses exploratoires et tests statistiques dans R/R Markdown.

## Limites

Les résultats doivent être interprétés avec prudence : la distance utilisée est une approximation spatiale, les données GBIF reflètent l'effort de collecte autant que la biodiversité réelle, et le déséquilibre massif en faveur d'Arthropoda influence fortement les statistiques globales.
