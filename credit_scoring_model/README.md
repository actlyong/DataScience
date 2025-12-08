# Credit Scoring Model

Predicting credit card default probability using machine learning to support lending decisions.

## 📊 Project Status: 90-95% Complete

**Current Performance:**
- ✅ 2 models trained (Logistic Regression, Random Forest)
- ✅ Accuracy: ~77%
- ⚠️ ROC-AUC: ~0.60 (needs improvement to 0.75+)
- ⚠️ Default Recall: 0.24 (needs improvement to 0.60+)

## 🎯 Project Overview

This project builds a binary classification model to predict whether a credit card holder will default on their next payment. The model analyzes payment history, bill amounts, and demographic information to assess credit risk.

**Dataset:** 30,000 credit card clients from UCI Machine Learning Repository

## 🔧 Technical Implementation

### Data Preprocessing
- **Data Cleaning:** Removed invalid EDUCATION (0,4,5,6) and MARRIAGE (0,3) values
- **Outlier Handling:** Removed AGE outliers using IQR method
- **Feature Engineering:**
  - Created `BILL_AMT_average`: Average of 6 monthly bills
  - Created `BILL_AMT_trend`: Trend in billing amounts
  - Consolidated payment status (PAY < 1 → 0)
- **Normalization:** MinMaxScaler for numerical features
- **Encoding:** One-hot encoding for SEX, EDUCATION, MARRIAGE
- **Feature Selection:** 20 features selected based on correlation analysis

### Models Trained

#### 1. Logistic Regression (Baseline)
- **Accuracy:** 76.96%
- **ROC-AUC:** 0.597
- **Precision (Default):** 0.63
- **Recall (Default):** 0.24
- **F1-Score (Default):** 0.35

**Confusion Matrix:**
```
[[3919  204]
 [1073  346]]
```

#### 2. Random Forest
- **Accuracy:** ~77%
- **ROC-AUC:** ~0.60
- Similar performance to Logistic Regression
- Full evaluation metrics in notebook

### Key Findings

**Strengths:**
- High accuracy for non-default class (95% recall)
- Solid preprocessing pipeline
- Multiple models compared

**Critical Issue:**
- **Low recall for default class (24%)** - Missing 76% of actual defaults
- **Root cause:** Class imbalance (4,123 non-defaults vs 1,419 defaults)
- **Business impact:** High cost of missing defaults in credit scoring

## 📁 Project Structure

```
credit_scoring_model/
├── credit_scoring_model.ipynb    # Main analysis notebook
├── data/
│   └── UCI_Credit_Card.csv       # Dataset
├── README.md                      # This file
├── requirements.txt               # Dependencies
└── todo.md                        # Development roadmap
```

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.8+
pandas
numpy
scikit-learn
matplotlib
seaborn
```

### Installation
```bash
# Clone repository
git clone <repo-url>
cd credit_scoring_model

# Install dependencies
pip install -r requirements.txt

# Run Jupyter notebook
jupyter notebook credit_scoring_model.ipynb
```

## 📈 Next Steps (To Hire-Ready)

### Priority 1: Improve Model Performance (2-3 hours)
1. **Address class imbalance** using SMOTE or class weights
2. **Retrain models** with balanced data
3. **Target metrics:** ROC-AUC > 0.75, Recall > 0.60

### Priority 2: Model Comparison
- Create side-by-side comparison table
- Select best model with justification
- Document business recommendations

### Priority 3: Optional Enhancements
- Try XGBoost
- Hyperparameter tuning
- Feature importance analysis
- Cross-validation

## 🎓 Key Learnings

**Technical:**
- Feature engineering reduces multicollinearity
- Class imbalance significantly impacts model performance
- Multiple models needed for comparison

**Business:**
- In credit scoring, recall for default class is critical
- Missing defaults is more costly than false positives
- Model performance must align with business objectives

## 📊 Technologies Used

- **Python 3.12**
- **pandas** - Data manipulation
- **scikit-learn** - Machine learning models
- **matplotlib/seaborn** - Visualization
- **Jupyter Notebook** - Development environment

## 📝 Dataset Information

**Source:** UCI Machine Learning Repository  
**Size:** 30,000 samples  
**Features:** 23 features + 1 target  
**Target:** default.payment.next.month (0 = No default, 1 = Default)

**Key Features:**
- LIMIT_BAL: Credit limit
- PAY_0 to PAY_6: Payment status history
- BILL_AMT1 to BILL_AMT6: Monthly bill amounts
- PAY_AMT1 to PAY_AMT6: Monthly payment amounts
- Demographics: SEX, EDUCATION, MARRIAGE, AGE

## 🤝 Contributing

This is a portfolio project. Feedback and suggestions are welcome!

## 📧 Contact

[Your Name]  
[Your Email]  
[LinkedIn Profile]

---

**Status:** Active Development | **Last Updated:** December 7, 2025
