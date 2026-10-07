# 02-student-performance-multiple-linear-regression
# Student Performance Prediction (Multiple Linear Regression)

Predicting a student's Performance Index from study habits using multiple linear regression with scikit-learn.

## Overview
- **Goal:** Predict `Performance Index` from features like hours studied, previous scores, sleep hours, etc.
- **Model:** Multiple Linear Regression
- **Tools:** Python, pandas, NumPy, Matplotlib/Seaborn, scikit-learn

## Dataset
- **Name:** Student Performance (Multiple Linear Regression)
- **Source:** [Kaggle](PUT-KAGGLE-LINK-HERE)
- **Size:** ~10,000 rows
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
| R² (test) | TODO |
| MAE (test) | TODO |

![Predicted vs Actual](images/predicted_vs_actual.png)

## Key Insights
> TODO: 3-4 sentences about the most important features and what the coefficients mean.

## How to Run
```bash
git clone https://github.com/AliSadeghian2007/02-student-performance-multiple-linear-regression.git
cd 02-student-performance-multiple-linear-regression
pip install -r requirements.txt
jupyter notebook notebooks/student_performance_mlr.ipynb
```

## What I Learned
> TODO: a few lines (e.g., dummy variable trap, interpreting coefficients).