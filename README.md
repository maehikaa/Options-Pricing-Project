
# 📈 Option Pricing Prediction Using Machine Learning

## 🧠 Project Overview

This project explores how machine learning models can predict option prices using S&P 500 European call option data. We compare our model predictions against traditional financial models, notably the Black-Scholes model, to assess their effectiveness in dynamic market scenarios.

---

## 📊 Objectives

- Predict option values using regression models.
- Classify whether an option is under or overestimated vs. Black-Scholes.
- Apply hyperparameter tuning to optimize models.
- Compare ML performance with Black-Scholes benchmarks.

---

## 🗃️ Dataset & Preprocessing

- **Dataset**: European call options on the S&P 500.
- **Target Variable**: Option Value (regression) and BS_Binary (classification).
- **Preprocessing**:
  - No missing data.
  - Features normalized using `StandardScaler` for regression.
  - No scaling for classification (tree-based models handle raw values well).
  - Feature engineering: added S/K ratio, log transformations.
  - Outliers retained due to financial data’s natural variability.

---

## 🔧 Modeling Techniques

### 🔢 Regression Models
- **Linear Regression** (Baseline) → R² = 0.974
- **K-Nearest Neighbors** → R² = 0.997
- **Support Vector Regression (SVM)** → R² = 0.997
- **XGBoost** → ⭐ Best model, R² = 0.998

### ✅ Classification Models
- **Random Forest** → Error = 0.066
- **Support Vector Machine** → Error = 0.086
- **XGBoost** → Error = 0.061
- **LightGBM** → ⭐ Best model, Error = 0.056

---

## ⚙️ Hyperparameter Tuning

- Used **GridSearchCV** and **StratifiedKFold**.
- Optimized parameters like:
  - `n_neighbors`, `C`, `epsilon`, `kernel`, `learning_rate`, `max_depth`, `n_estimators`
  - `num_leaves`, `min_split_gain` for LightGBM

---

## 🧪 Results Summary

| Model         | Type         | Best Metric        |
|---------------|--------------|--------------------|
| XGBoost       | Regression   | R² = 0.998         |
| LightGBM      | Classification | Error = 0.056   |

---

## 📉 ML vs. Black-Scholes

- ML models outperform Black-Scholes by adapting to real-world, non-linear dynamics.
- Black-Scholes relies on assumptions (e.g., log-normal prices) that limit flexibility.
- Caution advised: ML models must be applied carefully due to overfitting risks and market variation.

---

## 📝 Final Takeaways

- Keep all four predictors (`S`, `K`, `tau`, `r`) — each adds value.
- ML models provide actionable insights but require careful deployment.
- Re-train and validate models on new datasets (e.g., Tesla) before making business decisions.

