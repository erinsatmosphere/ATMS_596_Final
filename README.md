# README.md

### Tropical Cyclone Response to ENSO Flavor (EP / CP / Neutral / La Niña) - 1979–2023

This repository contains all code and analysis used to examine how ENSO “flavors” (Eastern Pacific El Niño, Central Pacific El Niño, Neutral, and La Niña) influence tropical cyclone activity in the Eastern and Central Pacific basins. The project analyzes storm energetics, intensity, spatial behavior, and SST anomaly patterns using IBTrACS storm data and ERSSTv5 sea-surface temperature anomalies.

### Data Sources
- IBTrACS NOAA/WMO global best-track archive (Knapp et al. 2010, WMO/NOAA IBTrACS v04r00 https://doi.org/10.1175/2009BAMS2755.1)
- ERSSTv5 NOAA Extended Reconstructed SST (Huang et al. 2017 https://doi.org/10.1175/JCLI-D-16-0836.1)

The project is fully reproducible and offers two workflows:
1. download and process the full SST dataset (using urlretrieve included in the initial steps in the 'ATMS_596_Final.ipynb' code), or
2. load a preprocessed ENSO dataset included in this repository and skip the initial processing steps (the ERSSTv5 data is too large to include in a Github repository; therefore, this option provides simpler way to access the data).

### Using the Preprocessed ENSO Data (Recommended)

If you do not wish to download ERSSTv5, load the included cleaned ENSO file:

```
df = pd.read_csv("data/enso_jjaso_clean.csv")
```

This file contains:
- seasonal JJASO Niño1+2 anomalies
- seasonal JJASO Niño4 anomalies
- ENSO flavor (EP, CP, La Niña, Neutral)

Users can then skip the early preprocessing blocks and immediately proceed to storm-level calculations and analysis.

### Running the Full Workflow

Users who want full reproducibility may:

- Download ERSSTv5 via urlretrieve
- Compute anomalies and Niño indices
- Classify ENSO flavor
- then proceed to load IBTrACS best-track data, and compute ACE, intensity, basin separation, and genesis classifications

The notebook clearly marks which sections correspond to downloading, preprocessing, analysis, and visualization.

### Requirements & Environment:

This project was developed and tested using **Python 3.13.5**

All required packages listed below are required and compatible with Python ≥3.10:

- os
- xarray
- numpy
- pandas
- matplotlib
- cartopy
- scipy
- seaborn
- statsmodels
- urllib.request
- shapely

### Contact & Use:

This repository is publicly available for academic, instructional, and research use. All scripts are fully open and may be adapted or extended as needed. If you have questions, find errors, or would like to discuss extensions of this work, you may contact:

Erin Welch
- erinwelchc@gmail.com
- erin7@illinois.edu
- ewelch2@my.hpu.edu
- GitHub: erinsatmosphere

Users are welcome to open GitHub issues for questions about reproducibility, code improvements, data access, and clarification on ENSO or tropical cyclone methods. Collaboration or feedback is always appreciated!
