# Bank Customer Churn Prediction Using Random Forest Modeling
## Overview
This project builds a Random Forest classification model to predict customer churn in the banking sector. Using demographic and account‑level data, the model identifies customers at risk of leaving and provides insights that support proactive retention strategies and ROI‑driven decision‑making.
## Research Question
How well can a Random Forest model predict customer churn using structured demographic and account‑level data?
## Business Context
Customer churn directly impacts profitability. Retaining existing customers is significantly more cost‑effective than acquiring new ones, making early churn detection a strategic priority. By predicting churn risk, banks can intervene before customers leave, improving retention outcomes and protecting revenue.
## Hypothesis
- Null (H₀): The Random Forest model does not exceed 70% predictive accuracy.
- Alternative (H₁): The Random Forest model achieves accuracy greater than 70%.

A 70% threshold was selected as a meaningful benchmark for operational usefulness.
## Dataset
Source: Kaggle (Bank Customer Churn dataset)
Size: 10,000+ customer records
### Features include:
- Age
- Tenure
- Credit Score
- Account Balance
- Product Usage
- Estimated Salary
- Geography
- Gender
- Churn label (Exited)
## Data Preparation
- Removed duplicates and standardized missing values
- Capped outliers using Z‑score thresholds
- Encoded categorical variables (binary and multi‑class)
- Conducted cardinality checks
- Performed feature selection using:
  - Correlation analysis
  - SelectKBest (p < 0.05)
  - Variance Inflation Factor (VIF)

Applied stratified train‑test split to preserve class imbalance structure
## Modeling Approach
- Algorithm: Random Forest Classifier
- Estimators: 200
- Evaluation Metrics:
- Accuracy
- ROC‑AUC
- Confusion Matrix
- Dual‑threshold strategy:
  - 0.5 for general churn detection
  - 0.75 for high‑risk customer flagging

This approach balances broad detection with precision targeting.
## Model Performance
- Accuracy: 85.2%
- ROC‑AUC: 0.8511
- Confusion Matrix Highlights:
  - 1494 true negatives
  - 210 true positives
  - 98 false positives
  - 198 false negatives

The model demonstrates strong discriminatory power and exceeds the 70% benchmark, supporting rejection of the null hypothesis.
## Key Insights
- The model reliably identifies high‑risk customers
- High‑risk customers were ranked by account balance to prioritize retention ROI
- 171 customers flagged as high‑risk had an average balance of $78,715.36
- Retaining just 10% of these customers preserves ~$1.34M in account value
## Limitations
- Dataset lacks behavioral or sentiment features
- Class imbalance may reduce sensitivity to minority class
- Random Forest models are less interpretable for non‑technical stakeholders
- Label encoding reduces categorical interpretability
- Dropping missing values reduces sample size
## Recommendations
- Prioritize outreach to high‑risk, high‑value customers
- Develop stakeholder dashboards to visualize churn risk
- Build segment‑specific models (e.g., by geography or tenure)
- Enrich dataset with behavioral and sentiment data for earlier churn detection
## Expected Benefits
- Strong predictive accuracy supports operational deployment
- ROI‑driven retention planning improves financial outcomes
- Model outputs can be integrated into dashboards for real‑time decision support
- Future enhancements can improve fairness, precision, and interpretability
