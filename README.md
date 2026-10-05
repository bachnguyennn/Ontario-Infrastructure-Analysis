# Ontario Infrastructure Analysis

An exploratory analysis of public infrastructure projects in Ontario that are in planning or under construction. The notebook looks at:

- **Regional distribution**: which regions have the most projects, and how many are in planning versus under construction
- **Funding sources**: which levels of government (municipal, provincial, federal, other) fund each project, and whether funding correlates with project status
- **Completion timelines**: cumulative projects by target completion quarter

## Data

The *Ontario Builds: Communities* dataset from Ontario Open Data ([dataset page](https://data.ontario.ca/dataset/ontario-builds-key-infrastructure-projects/resource/36f92c5b-0c8b-4a4b-b4c5-d15a43894297)). The notebook keeps projects with a target completion date after 2024-12-01. It fills in missing area names and coordinates by geocoding postal codes and coordinates with the OpenStreetMap Nominatim API.

The CSV is not included in this repository.

## Key findings

From the notebook's Discussion section:

- The Central and Northern regions have the highest concentration of projects. Central leads in projects under construction, while the Northeast and Northwest are mostly still in the planning phase.
- Government funding is spread fairly evenly across regions, and the correlation analysis found no significant relationship between funding source and project status.
- Most projects are expected to be completed by 2028, a horizon of about four years for projects under construction or in planning.

## Running it

Requires Python 3 (the notebook was last run on Python 3.13).

```
pip install pandas numpy matplotlib seaborn folium requests jupyter
```

1. Download the CSV from the dataset page and save it as `data.csv` in the same folder as the notebook.
2. Run `jupyter notebook ontario_infrastructure_analysis.ipynb`.

The geocoding step sends requests to the public Nominatim API, so it needs an internet connection.
