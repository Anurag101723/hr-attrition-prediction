# 👥 HR Attrition Prediction & Retention Simulator

> Predicting employee attrition using XGBoost and SHAP explainability — includes a What-If simulator to quantify the impact of HR interventions on individual attrition risk.

![Python](https://img.shields.io/badge/Python-3.12-blue?style=flat&logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0-red?style=flat)
![SHAP](https://img.shields.io/badge/SHAP-Explainability-orange?style=flat)
![SMOTE](https://img.shields.io/badge/SMOTE-Balanced-green?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)

---

## 📌 Overview

Employee attrition costs companies an average of **€15,000 per replacement hire**. This project builds a complete data-driven attrition prediction system that helps HR teams:

- **Identify** which employees are at high risk of leaving
- **Understand** why they are likely to leave (SHAP explainability)
- **Simulate** the impact of interventions before implementing them (What-If Simulator)
- **Prioritise** retention efforts where they matter most

Built on the IBM HR Analytics dataset with 1,470 employee records and 31 features.

---

## 🎯 Key Results

| Metric | Score |
|---|---|
| Best Model | XGBoost Classifier |
| Accuracy | **82%** |
| ROC AUC | **0.746** |
| High Risk Employees Flagged | **31 out of 294** |
| Top 10 High Risk Accuracy | **80%** (8/10 correctly identified) |

---

## 💡 What-If Simulator — The Differentiator

The simulator allows HR to test retention interventions **before spending money** on them.

**Example — Highest Risk Employee (96.5% attrition risk):**

| Scenario | Risk |
|---|---|
| Current situation | 96.5% |
| Remove overtime only | 96.5% (already no overtime) |
| Stock options + environment improvement | **25.8%** |
| **Risk reduction** | **−70.7%** |

> *"Offering stock options and addressing workplace environment concerns can reduce this employee's attrition risk from 96.5% to 25.8% — a saving of ~€15,000 in replacement costs."*

---

## 🔑 Top Attrition Drivers (SHAP Analysis)

| Rank | Feature | Business Insight |
|---|---|---|
| 1 | Stock Option Level | No stock options = high flight risk |
| 2 | Job Satisfaction | Low satisfaction drives exits |
| 3 | Environment Satisfaction | Poor workplace environment |
| 4 | Job Involvement | Disengaged employees leave |
| 5 | Years with Manager | New/changing managers = instability |

---

## 📊 EDA Findings

- **Sales department** has the highest attrition rate
- **Overtime** employees are significantly more likely to leave
- **Lower income** employees under 30 show the highest attrition
- **Low job satisfaction** strongly correlates with leaving
- Employees with **more years at company** are more loyal

---

## 🛠️ Tech Stack

- **Language:** Python 3.12
- **ML Models:** XGBoost, Random Forest
- **Explainability:** SHAP (TreeExplainer)
- **Imbalance Handling:** SMOTE (imbalanced-learn)
- **Data Processing:** Pandas, NumPy, Scikit-learn
- **Visualisation:** Matplotlib, Seaborn
- **Environment:** Jupyter Notebook

---

## 🔍 Methodology

```
IBM HR Dataset (1,470 employees, 35 features)
              ↓
Data Cleaning & Preprocessing
(drop useless columns, label encoding)
              ↓
Exploratory Data Analysis
(attrition by dept, overtime, income, age, satisfaction)
              ↓
SMOTE — Fix Class Imbalance
(16% attrition → balanced 50/50 training set)
              ↓
Model Training
├── Random Forest  → Accuracy: 80%, AUC: 0.727
└── XGBoost        → Accuracy: 82%, AUC: 0.746 ✅ Best
              ↓
SHAP Explainability
(global feature importance + directional impact)
              ↓
Risk Scoring
(Low / Medium / High risk categories for all employees)
              ↓
What-If Simulator
(test HR interventions before implementing them)
              ↓
Business Recommendations
(estimated €225,000 saving if 50% of high-risk retained)
```

---

## 💰 Estimated Business Impact

| Metric | Value |
|---|---|
| Average replacement cost per employee | €15,000 |
| High risk employees identified | 31 |
| If 50% retained via interventions | 15 employees saved |
| **Estimated cost saving** | **~€225,000** |

---

## 📁 Repository Structure

```
hr-attrition-prediction/
│
├── hr_attrition.ipynb                    # Main analysis notebook
├── WA_Fn-UseC_-HR-Employee-Attrition.csv # Dataset
├── README.md                             # Project documentation
```

---

## 🚀 How to Run

1. Clone the repository
```bash
git clone https://github.com/Anurag101723/hr-attrition-prediction.git
cd hr-attrition-prediction
```

2. Install dependencies
```bash
pip install pandas numpy scikit-learn xgboost shap imbalanced-learn matplotlib seaborn
```

3. Open the notebook
```bash
jupyter notebook hr_attrition.ipynb
```

---

## 👤 Author

**Anurag Rathore**
M.Sc. Big Data & Business Analytics — FOM University of Applied Sciences
📧 anuragakrathore@gmail.com
🔗 [LinkedIn](https://linkedin.com/in/anurag1017) · [Portfolio](https://Anurag101723.github.io)
