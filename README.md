# Diabetes Progression Prediction — Linear Regression Mini Project

A beginner/intermediate machine learning project that predicts diabetes disease progression using **simple** and **multiple linear regression**, built entirely on a dataset that ships with scikit-learn (no downloads required).

## 📌 Project Overview

- **Task:** Regression — predict a quantitative measure of diabetes progression one year after baseline
- **Dataset:** [`sklearn.datasets.load_diabetes`](https://scikit-learn.org/stable/datasets/toy_dataset.html#diabetes-dataset) — 442 patients, 10 baseline physiological features
- **Models used:** Simple Linear Regression (1 feature) → Multiple Linear Regression (all 10 features)
- **Why this dataset:** It's built into scikit-learn (no internet download needed to run this project), it's small and clean, but has enough features to make the problem more interesting than a single scatter-plot line fit.

## 🗂️ Features in the Dataset

| Feature | Description |
|---|---|
| age | Age of patient |
| sex | Sex of patient |
| bmi | Body mass index |
| bp | Average blood pressure |
| s1–s6 | Six blood serum measurements |
| target | Disease progression score (1 year after baseline) |

All features come pre-scaled (mean-centered, unit variance) by scikit-learn.

## 📊 Results

| Model | MSE | RMSE | MAE | R² |
|---|---|---|---|---|
| Simple Linear Regression (`bmi` only) | 4061.83 | 63.73 | 52.26 | 0.233 |
| Multiple Linear Regression (all features) | 2900.19 | 53.85 | 42.79 | 0.453 |

**Takeaway:** Using BMI alone explains about 23% of the variance in disease progression. Adding all 10 features nearly doubles that to 45%, confirming that blood pressure and serum measurements carry real predictive signal beyond BMI.

The strongest predictors (by regression coefficient) were `bmi`, `s5`, and `bp` — which lines up with known diabetes risk factors.

## 🚀 How to Run

1. Clone this repo:
   ```bash
   git clone https://github.com/<your-username>/diabetes-regression-project.git
   cd diabetes-regression-project
   ```
2. (Recommended) Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate   # on Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook regression_analysis.ipynb
   ```

No data files or API keys needed — the dataset loads directly from scikit-learn.

## 🛠️ Tech Stack

- Python 3
- pandas, numpy
- matplotlib, seaborn
- scikit-learn

## 📁 Project Structure

```
diabetes-regression-project/
├── regression_analysis.ipynb   # main notebook: EDA + modeling + evaluation
├── requirements.txt
├── README.md
└── .gitignore
```

## 🔭 Possible Extensions

- Add Ridge/Lasso regression and compare against plain linear regression
- Try non-linear models (Random Forest, Gradient Boosting)
- Use k-fold cross-validation instead of a single train/test split
- Engineer interaction features (e.g. `bmi × bp`)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
