# Pressions maritimes et biodiversité marine en Europe

**Langue / Language :** [Français](#francais) | [English](#english)

<a id="francais"></a>

## Français

Est-ce que la biodiversité marine se répartit différemment quand on s'approche des ports et des installations offshore ? C'est la question de départ de ce projet, réalisé dans le cadre d'un travail universitaire sur données (SCDON2, UPV).

Concrètement : j'ai récupéré des occurrences biologiques sur GBIF (cnidaires, élasmobranches, malacostracés), je les ai croisées avec la position des ports maritimes et des infrastructures offshore en Europe, puis j'ai calculé pour chaque observation la distance au port et à l'infrastructure les plus proches. Ces distances ont ensuite été regroupées en classes de proximité, ce qui permet de faire tourner les requêtes SQL, les cartes et les tests statistiques.

Au final, **459 773 observations géoréférencées** entre 2010 et 2023.

### Ce que montrent les données

Il y a bien une association entre la proximité des infrastructures et la façon dont les observations se répartissent dans l'espace. Mais il faut être honnête sur ce que ça vaut :

- le jeu de données est très déséquilibré — les Arthropoda écrasent tout le reste, ce qui tire les statistiques globales ;
- la grande majorité des observations sont loin des ports, donc les classes de distance sont fortement asymétriques ;
- GBIF reflète autant l'effort d'échantillonnage que la biodiversité réelle. Beaucoup d'observations près d'une côte peuvent simplement vouloir dire que beaucoup de gens y observent.

La distance utilisée reste aussi une approximation purement spatiale (à vol d'oiseau), pas une mesure de pression écologique.

### Vidéo de présentation

[![Présentation vidéo du projet](https://img.youtube.com/vi/8GbSYteuBdM/hqdefault.jpg)](https://youtu.be/bsVa2WncufQ)

### Visualisations

Animation de la distance au port au fil du temps :

![Animation de la distance au port dans le temps](GroupReportTemplate%202-2/figures/animation_distance_temporelle.gif)

[Carte interactive (HTML)](GroupReportTemplate%202-2/figures/carte_biodiversite_marine.html) — attention, le dossier `GroupReportTemplate 2-2/figures/carte_biodiversite_marine_files/` doit rester à côté du fichier HTML, sinon la carte ne s'affiche pas.

### Le rapport

- [Version PDF](GroupReportTemplate%202-2/scdon2-UPV-report-template.pdf)
- [Version HTML](GroupReportTemplate%202-2/scdon2-UPV-report-template.html)
- [Source R Markdown](GroupReportTemplate%202-2/scdon2-UPV-report-template.Rmd)

### Comment c'est fait

Modélisation relationnelle (MCD/MOD), puis import, nettoyage et enrichissement en SQL. Les distances minimales aux ports et aux infrastructures offshore sont calculées à ce niveau, puis découpées en classes. L'exploration, les graphiques et les tests statistiques se font ensuite en R / R Markdown.

### Données

| Fichier | Contenu |
| --- | --- |
| `DataSet/cnidaria_europe_2026-04-15_13-16.csv` | Occurrences cnidaires (GBIF) |
| `DataSet/elasmobranchii_europe_2026-04-15_13-16.csv` | Occurrences élasmobranches (GBIF) |
| `DataSet/malacostraca_europe_2026-04-15_13-16.csv.zip` | Occurrences malacostracés (GBIF) |
| `DataSet/port_maritime_eur_2026-04-15_13-17.csv` | Ports maritimes européens |
| `DataSet/offshore_europe_2026-04-15_13-17.csv` | Infrastructures offshore |
| `DataSet/observation_europe_2026-04-15_13-17.csv` | Observations consolidées après traitement |

### Organisation du dépôt

```text
.
├── DataSet/                         # Données sources et données préparées
├── GroupReportTemplate 2-2/         # Rapport final, figures et rendus
│   ├── figures/                     # Graphiques, GIF et carte HTML
│   └── scdon2-UPV-report-template.Rmd
├── Query SQL/                       # Résultats des requêtes, en INSERT .sql et tableaux Markdown
├── SQL requettes/                   # Résultats des requêtes, en CSV
├── nouvelle requettes.docx          # Les requêtes SQL elles-mêmes
├── code r.Rmd                       # Code R de préparation des visualisations
└── README.md
```

---

Projet réalisé par **Alban Gerschheimer**. Mes autres travaux : [albangerschheimer.vercel.app](https://albangerschheimer.vercel.app)

<a id="english"></a>

## English

Does marine biodiversity spread out differently as you get closer to ports and offshore installations? That's the starting question of this project, done as part of a university data course (SCDON2, UPV).

The approach: pull biological occurrences from GBIF (cnidarians, elasmobranchs, malacostracans), cross them with the location of European maritime ports and offshore infrastructures, then compute for each observation the distance to the nearest port and the nearest offshore structure. Those distances get grouped into proximity classes, which is what the SQL queries, maps and statistical tests run on.

The result: **459,773 georeferenced observations** between 2010 and 2023.

### What the data shows

There is an association between proximity to infrastructures and how observations are distributed in space. But it's worth being upfront about the limits:

- the dataset is heavily unbalanced — Arthropoda dwarf everything else, which drags the global statistics along with them;
- the vast majority of observations sit far from ports, so the distance classes are strongly skewed;
- GBIF reflects sampling effort as much as actual biodiversity. Lots of observations near a coast may simply mean lots of people observing there.

The distance is also a straight-line spatial approximation, not a measure of ecological pressure.

### Video walkthrough

[![Video presentation of the project](https://img.youtube.com/vi/8GbSYteuBdM/hqdefault.jpg)](https://youtu.be/bsVa2WncufQ)

### Visualizations

Distance to port over time:

![Animation of distance to port over time](GroupReportTemplate%202-2/figures/animation_distance_temporelle.gif)

[Interactive map (HTML)](GroupReportTemplate%202-2/figures/carte_biodiversite_marine.html) — the `GroupReportTemplate 2-2/figures/carte_biodiversite_marine_files/` folder has to stay next to the HTML file, otherwise the map won't render.

### The report

- [PDF version](GroupReportTemplate%202-2/scdon2-UPV-report-template.pdf)
- [HTML version](GroupReportTemplate%202-2/scdon2-UPV-report-template.html)
- [R Markdown source](GroupReportTemplate%202-2/scdon2-UPV-report-template.Rmd)

### How it was built

Relational modeling (conceptual and logical schema), then import, cleaning and enrichment in SQL. Minimum distances to ports and offshore infrastructures are computed at that stage, then bucketed into classes. Exploration, charts and statistical tests happen afterwards in R / R Markdown.

### Data

| File | Contents |
| --- | --- |
| `DataSet/cnidaria_europe_2026-04-15_13-16.csv` | Cnidarian occurrences (GBIF) |
| `DataSet/elasmobranchii_europe_2026-04-15_13-16.csv` | Elasmobranch occurrences (GBIF) |
| `DataSet/malacostraca_europe_2026-04-15_13-16.csv.zip` | Malacostracan occurrences (GBIF) |
| `DataSet/port_maritime_eur_2026-04-15_13-17.csv` | European maritime ports |
| `DataSet/offshore_europe_2026-04-15_13-17.csv` | Offshore infrastructures |
| `DataSet/observation_europe_2026-04-15_13-17.csv` | Consolidated observations after processing |

### Repository layout

```text
.
├── DataSet/                         # Source and prepared data
├── GroupReportTemplate 2-2/         # Final report, figures and rendered outputs
│   ├── figures/                     # Charts, GIF and HTML map
│   └── scdon2-UPV-report-template.Rmd
├── Query SQL/                       # Query results, as .sql INSERTs and Markdown tables
├── SQL requettes/                   # Query results, as CSV
├── nouvelle requettes.docx          # The SQL statements themselves
├── code r.Rmd                       # R code used to prepare visualizations
└── README.md
```

---

Project by **Alban Gerschheimer**. More of my work: [albangerschheimer.vercel.app](https://albangerschheimer.vercel.app)

---

## Licence / License

**Français.** C'est un projet étudiant de groupe, et aucune licence n'a été
ajoutée pour l'instant : ce choix appartient à tous les contributeurs, pas à un
seul. En attendant, le droit d'auteur par défaut s'applique — le travail n'est
pas réutilisable librement.

De toute façon les données ont leurs propres conditions : les occurrences
biologiques viennent de [GBIF](https://www.gbif.org/), les couches ports et
offshore de leurs fournisseurs européens respectifs.

**English.** This is a group student project, and no license has been added yet:
that call belongs to every contributor, not just one of them. Until then default
copyright applies — the work isn't free to reuse.

The data comes with its own terms anyway: biological occurrences from
[GBIF](https://www.gbif.org/), port and offshore layers from their respective
European providers.
