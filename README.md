# HR Attrition Prediction and Retention Simulator

XGBoost-based employee attrition prediction system with SHAP explainability and an interactive What-If simulator for HR intervention planning.

---

## Overview

Employee attrition costs organisations an average of 15,000 EUR per replacement hire. This project builds a complete people analytics framework that identifies which employees are at high risk of leaving, explains why using SHAP, and quantifies the impact of HR interventions before they are implemented.

The What-If simulator is the core differentiator — HR teams can adjust variables such as stock options, job satisfaction, and overtime to see the predicted risk reduction before committing resources.

---

## Results

| Metric | Score |
|---|---|
| Model | XGBoost Classifier |
| Accuracy | 82% |
| ROC AUC | 0.746 |
| Fraud Recall | 84% |
| High Risk Precision | 84.4% |
| High Risk Employees Flagged | 31 out of 294 |
| Estimated Cost Saving | 225,000 EUR |

---

## What-If Simulator — Example

Employee 9 had the highest attrition risk in the test set.

| Scenario | Attrition Risk |
|---|---|
| Baseline (current situation) | 96.5% |
| Remove overtime only | 96.5% (already no overtime) |
| Stock options + environment improvement | 25.8% |
| Risk reduction | -70.7% |

This demonstrates that targeted retention interventions, modelled before implementation, can reduce flight risk from near-certain to manageable levels.

---

## Top Attrition Drivers (SHAP Analysis)

| Rank | Feature | Business Insight |
|---|---|---|
| 1 | Stock Option Level | Employees with no stock options show highest flight risk |
| 2 | Job Satisfaction | Low satisfaction is a consistent predictor of attrition |
| 3 | Environment Satisfaction | Poor workplace environment drives exits |
| 4 | Job Involvement | Disengaged employees are significantly more likely to leave |
| 5 | Years with Manager | Frequent manager changes correlate with higher attrition |

---

## EDA Findings

| Factor | Finding |
|---|---|
| Department | Sales has the highest attrition rate |
| Overtime | Overtime employees are 3x more likely to leave |
| Age | Employees under 30 show the highest attrition |
| Income | Lower income is a consistent predictor of leaving |
| Tenure | More years at company correlates with lower attrition |

---

## Risk Distribution

| Risk Level | Count | Action |
|---|---|---|
| High Risk (>70%) | 31 | Immediate HR intervention |
| Medium Risk (30-70%) | 34 | Monitor and review |
| Low Risk (<30%) | 229 | No immediate action needed |

---

## Dataset

- Source: IBM HR Analytics Employee Attrition dataset
- Records: 1,470 employees
- Features: 31 (after preprocessing)
- Target: Attrition (Yes/No)
- Class imbalance: 16.1% attrition rate, handled with SMOTE

---

## Methodology

```
IBM HR Dataset (1,470 employees, 35 features)

Data Cleaning
Drop useless columns, label encoding

Exploratory Data Analysis
Attrition by department, overtime, income, age, satisfaction

SMOTE
Fix class imbalance: 16% attrition to balanced 50/50 training set

Model Training
Random Forest  — Accuracy: 80%, AUC: 0.727
XGBoost        — Accuracy: 82%, AUC: 0.746 (selected)

SHAP Explainability
Global feature importance and directional impact

Risk Scoring
Low, Medium, High risk categories for all employees

What-If Simulator
Test HR interventions before implementing them

Business Recommendations
Estimated 225,000 EUR saving if 50% of high-risk employees retained
```

---

## Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3.12 |
| ML Models | XGBoost, Random Forest |
| Explainability | SHAP (TreeExplainer) |
| Imbalance Handling | SMOTE (imbalanced-learn) |
| Data Processing | Pandas, NumPy, Scikit-learn |
| Visualisation | Matplotlib, Seaborn |
| Environment | Jupyter Notebook |

---

## Repository Structure

```
hr-attrition-prediction/
|
|-- hr_attrition.ipynb
|-- WA_Fn-UseC_-HR-Employee-Attrition.csv
|-- README.md
```

---

## How to Run

```bash
git clone https://github.com/Anurag101723/hr-attrition-prediction.git
cd hr-attrition-prediction
pip install pandas numpy scikit-learn xgboost shap imbalanced-learn matplotlib seaborn
jupyter notebook hr_attrition.ipynb
```

---

## Author

Anurag Rathore  
anuragakrathore@gmail.com  
linkedin.com/in/anurag1017  
anurag101723.github.io
