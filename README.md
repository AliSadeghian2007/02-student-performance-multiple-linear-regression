# 02-student-performance-multiple-linear-regression
# Student Performance Prediction (Multiple Linear Regression)

Predicting a student's Performance Index from study habits using multiple linear regression with scikit-learn.

## Overview
- **Goal:** Predict `Performance Index` from features like hours studied, previous scores, sleep hours, etc.
- **Model:** Multiple Linear Regression
- **Tools:** Python, pandas, NumPy, Matplotlib/Seaborn, scikit-learn

## Dataset
- **Name:** Student Performance (Multiple Linear Regression)
- **Source:** [Kaggle](https://www.kaggle.com/code/mohammedhamzamoawad/student-performance/notebook)
- **Size:** 10,000 rows (9,873 after removing 127 duplicates)
- **Target:** `Performance Index`
- **Features:** Hours Studied, Previous Scores, Extracurricular Activities, Sleep Hours, Sample Question Papers Practiced

## Project Structure
```
├── data/        # dataset
├── notebooks/   # Jupyter notebook
├── images/      # saved plots
├── requirements.txt
└── README.md
```

## Workflow
1. Data loading and exploration
2. Correlation analysis
3. Encoding categorical feature and train/test split
4. Model training
5. Evaluation (R², MAE)
6. Coefficient interpretation

## Results
> TODO: fill in after finishing the notebook.

| Metric | Value |
|---|---|
| R² (test) | 0.9884 |
| MAE (test) | 1.647 |

[Predicted vs Actual](images/predicted_vs_actual.png)

## Key Insights

- **Previous Scores is by far the strongest predictor** (r = 0.92). Each extra point is associated with about 1.02 more points of `Performance Index`, and across its full range (40 to 99) it accounts for roughly 60 points.
- **Hours Studied is second**: each extra hour is associated with about 2.85 more points (about 23 points across its range of 1 to 9 hours).
- **Sleep Hours, Sample Question Papers Practiced and Extracurricular Activities have small effects** (about 0.47, 0.19 and 0.57 points per unit). Sleep Hours has a very weak simple correlation (r = 0.05) but still a positive coefficient when the other features are held constant.
- The features are almost uncorrelated with each other (all |r| < 0.02), so multicollinearity is not a problem. These results show associations in this dataset, not cause and effect.

## How to Run
```bash
git clone https://github.com/AliSadeghian2007/02-student-performance-multiple-linear-regression.git
cd 02-student-performance-multiple-linear-regression
pip install -r requirements.txt
jupyter notebook notebooks/student_performance_mlr.ipynb
```

## What I Learned

- **Dummy variable trap:** a Yes/No column encoded into two columns is redundant (they always sum to 1), so I used `OneHotEncoder(drop='first')`.
- **Correlation is not the same as a coefficient:** a feature with a weak simple correlation can still have a positive coefficient in a multiple regression, because coefficients are computed holding the other features constant.
- **Coefficients cannot be compared by size alone** when features have different scales. I compared the total effect (coefficient × range of the feature) instead.
- **Evaluating on unseen data:** I split the data 80/20 with a fixed `random_state` and measured R² and MAE only on the test set.
- **Duplicates:** with no ID column I could not tell real duplicates from coincidences, so I dropped them to avoid train/test leakage and wrote down why.
- **Git workflow:** one small commit per step with a clear message (`feat:`, `docs:`, `chore:`).