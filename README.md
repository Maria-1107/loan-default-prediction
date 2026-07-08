 # 🏦 Loan Default Prediction

## 📌 Introduction
Financial loan services are leveraged by companies across many 
industries, from big banks to financial institutions to government 
loans. One of the primary objectives of companies with financial 
loan services is to decrease payment defaults and ensure that 
individuals are paying back their loans as expected. In order to 
do this efficiently and systematically, many companies employ 
machine learning to predict which individuals are at the highest 
risk of defaulting on their loans, so that proper interventions 
can be effectively deployed to the right audience.

## 🎯 Business Problem
Financial institutions want to predict which loan applicants are 
at high risk of defaulting, so they can make informed lending 
decisions, reduce financial losses, and intervene early with 
at-risk borrowers.

### What happens if the model is wrong?
| Mistake Type | What Happens |
|--------------|--------------|
| Predicts "will repay" but they actually default | Bank loses money (gave loan to risky person) |
| Predicts "will default" but they would've repaid | Bank loses a good customer (rejected someone safe) |

## 🏗️ Project Architecture
Raw Data (CSV)
↓

Data Loading & EDA
↓
Data Cleaning & Preprocessing
↓
Train/Test Split
↓
Model Training (3 models)
↓
Evaluation (Confusion Matrix + Recall)
↓
Compare & Pick Best Model
↓
Final Conclusion

## 🛠️ Tech Stack
| Component | Technology |
|-----------|-----------|
| Language | Python |
| Data Handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| ML Models | Scikit-learn |
| Notebook | Jupyter (.ipynb) |

## 📊 Model Comparison Results

| Model | Accuracy | Recall |
|-------|----------|--------|
| Logistic Regression | 67% | **67%** 🏆 |
| Decision Tree | 82% | 20% |
| Random Forest | 88% | 17% |

## ⚠️ Key Finding — Class Imbalance
Dataset was heavily imbalanced:
- Non-defaulters (0): 225,694 (88.4%)
- Defaulters (1): 29,653 (11.6%)

This is why **Accuracy alone is misleading** — a model predicting 
"no default" for everyone would achieve 88% accuracy while catching 
zero actual defaulters.

## ✅ Best Model — Logistic Regression
Despite Random Forest achieving the highest accuracy (88%) and 
Decision Tree achieving 82%, both models had very low Recall 
scores (17% and 20%), meaning they missed the majority of actual 
loan defaulters.

Logistic Regression achieved the highest Recall (67%), correctly 
identifying two-thirds of all actual defaulters. Since the 
business cost of missing a defaulter (False Negative) is 
significantly higher than incorrectly flagging a safe applicant 
(False Positive), **Recall is the more important metric** for 
this business problem.

## 📁 Folder Structure

Loan_Default_Prediction/
│
├── data/
│   └── loan_default.csv
│
├── notebook/
│   └── loan_default.ipynb
│
├── outputs/
│   └── plots/
│
└── README.md