# Credit Scoring Model

Predicting credit card default probability using machine learning to support lending decisions.

## 📊 Project Status: 100% Complete

**Current Performance:**
  - ✅ 4 models compared (LR, RF, LR+SMOTE, RF+SMOTE)
  - ✅ Best ROC-AUC: 0.673 (Logistic Regression + SMOTE)
  - ✅ Recall improved from 32% to 55%
  - ✅ Quantified savings: 38.8M NT dollars annually

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
- **Accuracy:** 78.18%
- **ROC-AUC:** 0.631
- **Recall (Default):** 32.3%
- **Precision (Default):** 64.9%
- **Confusion Matrix:** 3875 TN, 248 FP, 961 FN, 458 TP

#### 2. Random Forest (Baseline)
- **Accuracy:** 77.75%
- **ROC-AUC:** 0.641
- **Recall (Default):** 36.2%
- **Precision (Default):** 61.1%
- **Confusion Matrix:** 3861 TN, 262 FP, 906 FN, 513 TP

#### 3. Logistic Regression + SMOTE ⭐ **Best Model**
- **Accuracy:** 73.46%
- **ROC-AUC:** 0.673 (highest)
- **Recall (Default):** 54.8% (70% improvement)
- **Precision (Default):** 48.4%
- **Confusion Matrix:** 3294 TN, 829 FP, 642 FN, 777 TP
- **Business Impact:** Saves 38.8M NT dollars annually vs baseline

#### 4. Random Forest + SMOTE
- **Accuracy:** 76.47%
- **ROC-AUC:** 0.648
- **Recall (Default):** 40.9%
- **Precision (Default):** 55.5%
- **Confusion Matrix:** 3843 TN, 280 FP, 839 FN, 580 TP

### Key Findings

**Best Model Selection:**
- **Logistic Regression + SMOTE** selected as final model
- Highest ROC-AUC (0.673) indicates best overall discrimination
- Best recall (54.8%) catches more defaults - critical for credit risk
- Quantified savings: 38.8M NT dollars annually

**SMOTE Impact:**
- Improved recall from 32% to 55% (70% improvement)
- Successfully addressed class imbalance
- Trade-off: Slightly lower precision, but acceptable for business case

**Business Justification:**
- Missing a default costs full loan amount (~167K NT)
- False positive costs opportunity cost (~25K NT interest)
- Higher recall reduces costly false negatives

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

## 📈 Future Enhancements

### Potential Improvements
1. **Hyperparameter Tuning**
   - GridSearchCV for optimal parameters
   - May improve ROC-AUC beyond 0.673

2. **Advanced Models**
   - Try XGBoost/LightGBM
   - Ensemble methods

3. **Additional Features**
   - Payment velocity metrics
   - Credit utilization rate
   - Seasonal patterns

4. **Deployment Considerations**
   - Real-time API for new applications
   - Batch scoring for monthly reviews
   - Model monitoring for drift
   - A/B testing framework

5. **Business Integration**
   - Risk-based pricing
   - Credit limit optimization
   - Collection strategy prioritization

## 🎓 Key Learnings

**Technical:**
- SMOTE effectively addresses class imbalance in credit data
- Feature engineering (bill averages, trends) improves model interpretability
- ROC-AUC is better metric than accuracy for imbalanced datasets
- Recall prioritization critical for high-cost false negatives

**Business:**
- In credit scoring, missing defaults costs 10-20x more than false positives
- Model selection must align with business objectives and cost structure
- Quantifying financial impact demonstrates business value
- Trade-offs between precision and recall require business context

**Project Management:**
- Iterative approach: baseline → identify issues → apply solutions
- Documentation and clear conclusions essential for portfolio projects
- Business impact quantification differentiates good from great projects

## 📊 Technologies Used

- **Python 3.12**
- **pandas** - Data manipulation
- **scikit-learn** - Machine learning models
- **imblearn** - SMOTE for class imbalance
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

Eduardo Yong

actlyong@gmail.com

https://www.linkedin.com/in/actlyong/

https://github.com/actlyong

---

**Status:** Complete | **Last Updated:** December 8, 2025
