# IT2011 — Fetal Health Classification (CTG)

**Student ID:** IT25102266  
**Name:** Ashini Sakalasooriya  
**Email:** it25102266@my.sliit.lk  
**Module:** IT2011 Artificial Intelligence and Machine Learning (Y2S1 2026)

## Problem

Classify fetal health status from cardiotocography (CTG) measurements into three classes:

| Label | Meaning        |
|-------|----------------|
| 1     | Normal         |
| 2     | Suspect        |
| 3     | Pathological   |

This is a supervised **multiclass classification** problem in the healthcare domain.

## Assigned dataset

- **File:** `data/raw/fetal_health.csv` (extracted from `data/raw/archive (1).zip`)
- **Size:** 2,126 rows × 22 columns
- **Target:** `fetal_health`
- **Features:** CTG signals such as baseline FHR, accelerations, decelerations, variability statistics, and histogram descriptors

## Repository layout

```text
README.md
data/raw/                 # assigned zip + extracted CSV
data/external/            # external data (unused)
notebooks/
  IT25102266_preprocessing_eda.ipynb
results/eda_visualizations/
results/outputs/
results/logs/
docs/                     # assignment specification PDFs
```

## How to run

1. Create a virtual environment and install dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

2. Open the notebook:

```bash
jupyter notebook notebooks/IT25102266_preprocessing_eda.ipynb
```

3. Run all cells top to bottom. Plots are saved under `results/eda_visualizations/` and the processed dataset under `results/outputs/`.

## Progress Review I scope

The notebook covers missing-value handling, categorical/ordinal encoding, outlier treatment, scaling/normalization, feature engineering with selection and PCA, exploratory visualizations with interpretation, plus a light stratified train/test baseline for the next stage.
