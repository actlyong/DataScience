# Credit Scoring Model

## Problem Statement
Predict the probability of credit card default for clients based on their demographic information, credit history, and payment behavior. This helps financial institutions make informed lending decisions and manage credit risk.

## Dataset
- **Source**: [UCI Credit Card Dataset](https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset)
- **Size**: 30,000 credit card clients
- **Features**: 23 features including demographics, credit limit, payment history, and bill amounts
- **Target**: Binary classification (default vs non-default)

## Key Features
- **Demographics**: Age, Sex, Education, Marriage Status
- **Credit**: Credit Limit (LIMIT_BAL)
- **Payment History**: 6 months of repayment status (PAY_0 to PAY_6)
- **Bill Amounts**: 6 months of bill statements (BILL_AMT1 to BILL_AMT6)
- **Payment Amounts**: 6 months of previous payments (PAY_AMT1 to PAY_AMT6)

## Methodology
1. Exploratory Data Analysis (EDA)
2. Data preprocessing and feature engineering
3. Model training and evaluation
4. Performance analysis

## How to Run
```bash
# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook credit_scoring_model.ipynb
```

## Results
*To be updated after model completion*

## Next Steps
- Complete model training
- Add feature importance analysis
- Compare multiple algorithms
- Implement cross-validation