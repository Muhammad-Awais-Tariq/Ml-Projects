# ML-Projects

A collection of baseline Machine Learning projects built right after completing **Course 1 of Andrew Ng's Machine Learning Specialization**. These are intentional baselines — clean, end-to-end pipelines using core concepts from the course. They will be improved progressively as I complete more of the specialization and learn feature engineering.

---

## Project Structure

```
ML-Projects/
│
├── Data/
│   ├── diabetes/
│   │   └── diabetes_data.csv
│   ├── house_price/
│   └── Titanic/
│
├── Diabetes/
│   ├── data_cleaning/
│   │   └── data_cleaning.ipynb
│   └── ml_training/
│       └── ml_training.ipynb
│
├── House_Price/
│   ├── Data_cleaning/
│   │   ├── report/
│   │   │   └── report.html
│   │   ├── data_cleaning_test.ipynb
│   │   └── data_cleaning.ipynb
│   └── Ml_prediction/
│       ├── finalprediction.csv
│       └── ml_prediction.ipynb
│
├── Titanic/
│   ├── Data_cleaning/
│   │   ├── Reports/
│   │   │   ├── cleaned_report.html
│   │   │   └── report.html
│   │   ├── data_cleaning.ipynb
│   │   └── test_data_cleaning.ipynb
│   └── Ml_training/
│       ├── final_prediction.csv
│       └── ml_training.ipynb
│
├── .gitignore
├── .python-version
├── pyproject.toml
├── uv.lock
└── README.md
```

> **Note:** The `Data/` folder is not pushed to GitHub. Download links for each dataset are provided under each project below.

---

## Projects

### 1. Titanic Survival Prediction

**Type:** Binary Classification  
**Dataset:** [Kaggle — Titanic: Machine Learning from Disaster](https://www.kaggle.com/competitions/titanic/data)

**What I did:**
- Full data cleaning: median imputation for `Age`, mode imputation for `Embarked`, binary `has_cabin` feature, one-hot encoding
- Built a scikit-learn `Pipeline` with `StandardScaler` + `LogisticRegression`
- Evaluated on train/test split and submitted predictions to Kaggle

**Results (Baseline):**

| Split | Accuracy |
|-------|----------|
| Train | 82.84%   |
| Test  | 80.60%   |

> This is a baseline. No advanced feature engineering applied yet 

---

### 2. House Price Prediction

**Type:** Regression  
**Dataset:** [Kaggle — House Prices: Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data)

**What I did:**
- Data cleaning and preprocessing on both train and test sets
- Built a scikit-learn `Pipeline` with `StandardScaler` + `Ridge Regression` (no polynomial features — intentional baseline)
- Generated final predictions submitted to Kaggle

**Results (Baseline):**

| Split | RMSE       | R²   |
|-------|------------|------|
| Train | $19,828    | 0.94 |
| Test  | $24,716    | —    |

> The gap between train and test RMSE indicates some overfitting. Will be addressed with better feature engineering and regularization tuning later.

---

### 3. Diabetes Progression Prediction

**Type:** Regression  
**Dataset:** [scikit-learn built-in diabetes dataset](https://scikit-learn.org/stable/datasets/toy_dataset.html#diabetes-dataset) — also available on [Kaggle](https://www.kaggle.com/datasets/mathchi/diabetes-data-set)

**What I did:**
- Used the sklearn built-in diabetes dataset (442 samples, 10 features)
- Built a `Pipeline` with `StandardScaler` + `PolynomialFeatures(degree=2)` + `Ridge Regression`
- Evaluated on train/validation/test splits

**Results (Baseline):**

| Split      | RMSE   |
|------------|--------|
| Train      | 51.94  |
| Validation | 49.52  |
| Test       | 55.61  |

> Polynomial degree=2 with Ridge is a deliberate choice to practice regularization concepts from Ng's course. Will experiment with higher degrees and better hyperparameter tuning later.

---

## What I Learned Across All Three Projects

- How scikit-learn `Pipeline` prevents data leakage between train and test splits
- When to use `StandardScaler` vs `MinMaxScaler`
- The difference between classification metrics (accuracy) and regression metrics (RMSE, R²)
- How regularization in Ridge helps control overfitting
- Why establishing a clean baseline matters before any feature engineering

---

## Tech Stack

- **Python 3.12**
- **scikit-learn** — Pipelines, LogisticRegression, Ridge, PolynomialFeatures, StandardScaler
- **Pandas & NumPy** — Data cleaning and manipulation
- **Sweetviz** — EDA reports (see `report.html` files in each project)
- **uv** — Package manager

---

## Author

Muhammad Awais Tariq

---
If you like this project, consider giving it a star ⭐
