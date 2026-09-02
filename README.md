<div align="center">

# Maritime Pressures and Marine Biodiversity in Europe

**Do ports and offshore infrastructures shape where marine biodiversity is observed?**

[![R](https://img.shields.io/badge/R-R%20Markdown-276DC3.svg)](https://rmarkdown.rstudio.com/)
[![SQL](https://img.shields.io/badge/analysis-SQL%20%2B%20R-336791.svg)](#methods)
[![Data](https://img.shields.io/badge/data-459%2C773%20observations-lightgrey.svg)](#data-used)
[![Period](https://img.shields.io/badge/period-2010--2023-lightgrey.svg)](#data-used)

**Language / Langue — [English](#english) · [Français](#francais)**

</div>

---

<a id="english"></a>

## English

### Summary

This project studies the relationship between the spatial distribution of marine biodiversity observations in Europe and the proximity of two types of anthropogenic pressure: maritime ports and offshore infrastructures.

The final dataset combines biological occurrences from GBIF with geographic data on ports and offshore infrastructures. Each observation is associated with a minimum distance to the nearest port and the nearest offshore infrastructure, then grouped into proximity classes for SQL queries, visualizations and statistical analyses.

### Author Portfolio

This project is part of the work of **Alban Gerschheimer**. More projects are available on the portfolio: [albangerschheimer.vercel.app](https://albangerschheimer.vercel.app).

### Research Question

To what extent does proximity to maritime ports and offshore infrastructures influence the spatial distribution of marine biodiversity observations in Europe?

### Data Used

- Marine biological observations: `DataSet/cnidaria_europe_2026-04-15_13-16.csv`, `DataSet/elasmobranchii_europe_2026-04-15_13-16.csv`, `DataSet/malacostraca_europe_2026-04-15_13-16.csv.zip`
- Maritime ports: `DataSet/port_maritime_eur_2026-04-15_13-17.csv`
- Offshore infrastructures: `DataSet/offshore_europe_2026-04-15_13-17.csv`
- Consolidated observations: `DataSet/observation_europe_2026-04-15_13-17.csv`

### Key Findings

- The final dataset contains **459,773 georeferenced biological observations** for the 2010-2023 period.
- The observations are highly imbalanced taxonomically: Arthropoda represents almost all records.
- Most observations are located far from ports, producing a strongly asymmetric distribution of distance classes.
- The analyses show an association between proximity to infrastructures and the spatial structure of observations, but interpretation remains limited by sampling bias and the imbalance between phyla.

### Visualizations

#### Temporal Animation

![Animation of distance to port over time](GroupReportTemplate%202-2/figures/animation_distance_temporelle.gif)

#### Interactive Map

[Open the interactive HTML map](GroupReportTemplate%202-2/figures/carte_biodiversite_marine.html)

The map also depends on the `GroupReportTemplate 2-2/figures/carte_biodiversite_marine_files/` folder, which must remain next to the HTML file.

### Report

- [R Markdown report](GroupReportTemplate%202-2/scdon2-UPV-report-template.Rmd)
- [PDF report](GroupReportTemplate%202-2/scdon2-UPV-report-template.pdf)
- [HTML report](GroupReportTemplate%202-2/scdon2-UPV-report-template.html)

### Repository Structure

```text
.
├── DataSet/                         # Source and prepared data
├── GroupReportTemplate 2-2/         # Final report, figures and rendered outputs
│   ├── figures/                     # Charts, GIF and HTML map
│   └── scdon2-UPV-report-template.Rmd
├── Query SQL/                       # Query results, exported as .sql INSERTs and Markdown tables
├── SQL requettes/                   # Query results, exported as CSV
├── nouvelle requettes.docx          # The SQL statements themselves
├── code r.Rmd                       # R code used to prepare visualizations
└── README.md
```

### Methods

The project combines:

- relational modeling with MCD/MOD;
- SQL import, cleaning and enrichment;
- calculation of minimum distances to ports and offshore infrastructures;
- proximity classes;
- exploratory analyses and statistical tests in R/R Markdown.

### Limitations

The results should be interpreted with caution: the distance used is a spatial approximation, GBIF data reflect sampling effort as much as actual biodiversity, and the massive imbalance in favor of Arthropoda strongly affects the global statistics.

<a id="francais"></a>

## Français

### Résumé

Ce projet étudie la relation entre la distribution spatiale d'observations de biodiversité marine en Europe et la proximité de deux types de pressions anthropiques : les ports maritimes et les infrastructures offshore.

Le jeu de données final croise des occurrences biologiques issues de GBIF avec des données géographiques sur les ports et les infrastructures offshore. Les observations sont associées à une distance minimale au port le plus proche et à l'infrastructure offshore la plus proche, puis regroupées en classes de proximité pour produire des requêtes SQL, des visualisations et des analyses statistiques.

### Portfolio

Ce projet fait partie des travaux de **Alban Gerschheimer**. D'autres projets sont disponibles sur le portfolio : [albangerschheimer.vercel.app](https://albangerschheimer.vercel.app).

### Problématique

Dans quelle mesure la proximité des ports maritimes et des infrastructures offshore influence-t-elle la distribution spatiale des observations de biodiversité marine en Europe ?

### Données utilisées

- Observations biologiques marines : `DataSet/cnidaria_europe_2026-04-15_13-16.csv`, `DataSet/elasmobranchii_europe_2026-04-15_13-16.csv`, `DataSet/malacostraca_europe_2026-04-15_13-16.csv.zip`
- Ports maritimes : `DataSet/port_maritime_eur_2026-04-15_13-17.csv`
- Infrastructures offshore : `DataSet/offshore_europe_2026-04-15_13-17.csv`
- Observations consolidées : `DataSet/observation_europe_2026-04-15_13-17.csv`

### Résultats principaux

- Le jeu final contient **459 773 observations** biologiques géoréférencées sur la période 2010-2023.
- Les observations sont très déséquilibrées taxonomiquement : Arthropoda représente la quasi-totalité des données.
- La majorité des observations se situe loin des ports, ce qui crée une distribution très asymétrique des classes de distance.
- Les analyses montrent une association entre proximité aux infrastructures et structure spatiale des observations, mais l'interprétation reste limitée par les biais d'échantillonnage et le déséquilibre entre phylums.

### Visualisations

#### Animation temporelle

![Animation de la distance au port dans le temps](GroupReportTemplate%202-2/figures/animation_distance_temporelle.gif)

#### Carte interactive

[Ouvrir la carte interactive HTML](GroupReportTemplate%202-2/figures/carte_biodiversite_marine.html)

La carte dépend aussi du dossier `GroupReportTemplate 2-2/figures/carte_biodiversite_marine_files/`, qui doit rester à côté du fichier HTML.

### Rapport

- [Rapport R Markdown](GroupReportTemplate%202-2/scdon2-UPV-report-template.Rmd)
- [Rapport PDF](GroupReportTemplate%202-2/scdon2-UPV-report-template.pdf)
- [Version HTML du rapport](GroupReportTemplate%202-2/scdon2-UPV-report-template.html)

### Organisation du dépôt

```text
.
├── DataSet/                         # Données sources et données préparées
├── GroupReportTemplate 2-2/         # Rapport final, figures et rendus
│   ├── figures/                     # Graphiques, GIF et carte HTML
│   └── scdon2-UPV-report-template.Rmd
├── Query SQL/                       # Résultats des requêtes, exportés en INSERT .sql et en tableaux Markdown
├── SQL requettes/                   # Résultats des requêtes, exportés en CSV
├── nouvelle requettes.docx          # Les requêtes SQL elles-mêmes
├── code r.Rmd                       # Code R de préparation des visualisations
└── README.md
```

### Méthodes

Le projet combine :

- modélisation relationnelle avec MCD/MOD ;
- import, nettoyage et enrichissement SQL ;
- calcul de distances minimales aux ports et aux infrastructures offshore ;
- classes de proximité ;
- analyses exploratoires et tests statistiques dans R/R Markdown.

### Limites

Les résultats doivent être interprétés avec prudence : la distance utilisée est une approximation spatiale, les données GBIF reflètent l'effort de collecte autant que la biodiversité réelle, et le déséquilibre massif en faveur d'Arthropoda influence fortement les statistiques globales.

## Video / Vidéo

[![Video presentation of the project](https://img.youtube.com/vi/8GbSYteuBdM/hqdefault.jpg)](https://youtu.be/bsVa2WncufQ)

---

## License / Licence

**English.** This is a group student project. A license file has not been added
yet because that decision belongs to every contributor, not just one of them.
Until then, default copyright applies: the work is not licensed for reuse.

The data has its own terms in any case — the biological occurrences come from
[GBIF](https://www.gbif.org/), and the port and offshore layers from their
respective European providers.

**Français.** Ceci est un projet étudiant de groupe. Aucun fichier de licence n'a
encore été ajouté, car cette décision appartient à l'ensemble des contributeurs
et pas à un seul d'entre eux. D'ici là, le droit d'auteur par défaut s'applique :
l'œuvre n'est pas sous licence de réutilisation.

Les données ont de toute façon leurs propres conditions : les occurrences
biologiques proviennent de [GBIF](https://www.gbif.org/), et les couches ports et
offshore de leurs fournisseurs européens respectifs.
