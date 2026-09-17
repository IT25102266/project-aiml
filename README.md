# IT2011 — Fetal Health Classification (CTG)

**Module:** IT2011 Artificial Intelligence and Machine Learning (Y2S1 2026)  
**Problem:** Multiclass classification of fetal health from CTG features (Normal / Suspect / Pathological)

## Group members

| Student ID | Email | Notebook |
|------------|-------|----------|
| IT25102266 | it25102266@my.sliit.lk | `notebooks/IT25102266_preprocessing_eda.ipynb` |
| IT25102264 | it25102264@my.sliit.lk | `notebooks/IT25102264_mean_impute_zscore_minmax_corrfilter.ipynb` |
| IT24101349 | it24101349@my.sliit.lk | `notebooks/IT24101349_knn_impute_isolation_robust_mutualinfo.ipynb` |
| IT25102265 | it25102265@my.sliit.lk | `notebooks/IT25102265_median_iqr_remove_maxabs_variance.ipynb` |
| IT24101008 | it24101008@my.sliit.lk | `notebooks/IT24101008_mode_median_iqr_log_selectfrommodel.ipynb` |
| IT24102871 | it24102871@my.sliit.lk | `notebooks/IT24102871_median_zscore_remove_standard_chi2_svd.ipynb` |

> Note: `docs/MEMBERS.md` listed `IT241021008` with email `it24101008@...`. Notebooks use **IT24101008** to match the email. Rename if your official ID differs.

## How techniques are split (important)

Progress Review I marks each student on **all five technique categories**.  
Notebooks are **not** “one technique each.” Each notebook covers missing data, encoding, outliers, scaling, and feature engineering/selection/dimension reduction, but uses **different methods** so work is varied.

| Student | Missing | Outliers | Encoding | Scaling | Selection / DR |
|---------|---------|----------|----------|---------|----------------|
| IT25102266 | median | IQR winsorize | ordinal + LabelEncoder | StandardScaler | SelectKBest + PCA |
| IT25102264 | mean | Z-score cap | one-hot tendency | MinMaxScaler | correlation filter + PCA |
| IT24101349 | KNN imputer | IsolationForest + IQR cap | LabelEncoder | RobustScaler | mutual info + PCA |
| IT25102265 | median | IQR remove (protect class 3) | get_dummies | MaxAbsScaler | VarianceThreshold + PCA |
| IT24101008 | median + mode | IQR + log1p | OrdinalEncoder | StandardScaler | SelectFromModel + PCA |
| IT24102871 | median | Z-score remove | baseline bins one-hot | StandardScaler | chi2 + TruncatedSVD |

## Assigned dataset

- **File:** `data/raw/fetal_health.csv` (from `data/raw/archive (1).zip`)
- **Size:** 2,126 rows × 22 columns
- **Target:** `fetal_health`

## Repository layout

```text
README.md
data/raw/
notebooks/                      # one notebook per student
results/eda_visualizations/     # shared + per-student folders
results/outputs/                # processed CSVs per student
docs/
```

## How to run

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/
```

Run each student's notebook top to bottom. Figures go under `results/eda_visualizations/<StudentID>/` (IT25102266 figures are in `results/eda_visualizations/` root). Processed CSVs go under `results/outputs/`.
