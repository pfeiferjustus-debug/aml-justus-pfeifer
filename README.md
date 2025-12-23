# Applied Machine Learning – Projektarbeit (Regression)

## Ziel
Vorhersage der Fahrtdauer von Fahrradaktivitäten als Regressionsproblem.  
**Target:** `moving_time` (Sekunden)

**Wichtig:** `elapsed_time` ist im Datensatz vorhanden, wird aber **nicht** als Feature verwendet.

## Repository-Struktur
- `notebooks/` – Notebooks 01–08 (08 = Final Report / Abgabe)
- `data/raw/` – Rohdaten (lokal, nicht versioniert)
- `data/processed/` – erzeugte Datensätze (`processed.csv`, `model_ready.csv`) (lokal)
- `data_derived/` – erzeugte Tabellen/Artefakte (lokal)
- `plots/` – erzeugte Abbildungen (lokal)

## Datenquelle
Datensatz: Kaggle – *Outdoor cycling metrics*  
Link: https://www.kaggle.com/datasets/dorinaferencsik/outdoor-cycling-metrics  
Lizenzangabe auf Kaggle: **License unknown**

### Download & Ablage
1. Lade die Datei von Kaggle herunter. Der Download heißt: `cycling_metrics_all.csv`
2. Benenne die Datei um in: `raw.csv`
3. Lege sie hier ab: `data/raw/raw.csv`

> Hinweis: `data/raw/` wird absichtlich nicht versioniert. Dadurch bleibt das Repository schlank und es werden keine generierten Artefakte eingecheckt.

## Setup (Conda)
Das Projekt nutzt ein Conda-Environment: `aml-justus-pfeifer`.  
Die genaue Umgebung ist in `environment.yml` dokumentiert.

Falls das Environment noch nicht existiert:

```bash
conda env create -f environment.yml
conda activate aml-justus-pfeifer
```

Falls das Environment bereits existiert:

```bash
conda activate aml-justus-pfeifer
conda env update -f environment.yml --prune
```

## Reproduzierbarer Ablauf (Run Order)
Bitte die Notebooks in dieser Reihenfolge mit **Restart Kernel → Run All** ausführen:

1. `01_data_exploration.ipynb`  
2. `02_preprocessing_to_model_ready.ipynb`  
3. `03_model_baselines_cv.ipynb`  
4. `04_train_holdout_evaluation.ipynb`  
5. `05_feature_engineering_and_model_extensions.ipynb`  
6. `06_model_interpretability.ipynb`  
7. `07_discussion_and_limitations.ipynb`  
8. `08_final_report.ipynb` (**Final Report / Abgabe**)

## Hinweise zur Laufzeit
Notebook 05 enthält optionales Mini-Tuning für HistGBR (`RUN_TUNING`). Standardmäßig ist es deaktiviert, damit „Run All“ schnell durchläuft.
