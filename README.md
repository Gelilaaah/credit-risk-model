Credit Risk Probability Model for Alternative Data

End-to-End Credit Scoring, Risk Prediction, and Model Deployment for Buy-Now-Pay-Later Services

---

PROJECT OVERVIEW

Bati Bank is partnering with an eCommerce platform to offer Buy-Now-Pay-Later (BNPL) services. Before granting credit, the bank needs a reliable way to estimate the likelihood that a customer may become a risky borrower.

The challenge is that the available dataset does not contain a direct loan default indicator. Therefore, this project focuses on transforming customer transaction behavior into a meaningful credit risk signal and using machine learning to predict risk probabilities.

The final solution will provide:

✓ A proxy credit risk indicator

✓ Risk probability predictions for new customers

✓ Credit score generation

✓ Loan recommendation support

✓ A deployable REST API

✓ Automated testing and CI/CD integration

---

BUSINESS PROBLEM

Traditional credit scoring models rely heavily on historical loan repayment data. In many emerging markets, such information may be unavailable or incomplete.

To address this challenge, Bati Bank seeks to leverage alternative transaction data from its eCommerce partner.

The objective is to identify behavioral patterns that indicate whether a customer is likely to represent a low-risk or high-risk borrower and convert those patterns into a practical credit scoring solution.

---

PROJECT OBJECTIVES

This project aims to:

• Understand the business and regulatory requirements of credit risk modeling.

• Create a proxy target variable representing customer risk.

• Engineer meaningful features from transaction data.

• Train and compare multiple machine learning models.

• Estimate customer risk probabilities.

• Generate credit scores from risk estimates.

• Build a production-ready API for real-time predictions.

• Track experiments and model versions using MLflow.

• Automate testing and deployment workflows.

---

CREDIT SCORING BUSINESS UNDERSTANDING

Why Basel II Matters

The Basel II Accord requires financial institutions to maintain transparent and well-documented risk assessment systems.

This means that every model used to support lending decisions should be:

✓ Explainable

✓ Auditable

✓ Reproducible

✓ Properly documented

As a result, model selection involves more than maximizing accuracy. Regulatory compliance and interpretability are equally important.

---

Why a Proxy Target Variable is Needed

The dataset contains transaction information but does not contain a direct "default" label.

To train a supervised learning model, a target variable must first be created.

This project uses customer behavioral patterns such as:

• Recency
• Frequency
• Monetary Value

to construct a proxy indicator of credit risk.

Customers with weaker transaction behavior may be classified as higher risk, while customers demonstrating stronger engagement and spending patterns may be classified as lower risk.

---

Business Risks of Using a Proxy

Although proxy targets provide a practical solution, they introduce several risks:

• The proxy may not perfectly represent real default behavior.

• Some customer groups may be incorrectly categorized.

• Model performance depends heavily on how the proxy is defined.

• Bias can be introduced if the segmentation strategy is poorly designed.

For these reasons, proxy-based models should be carefully validated and continuously monitored.

---

Model Selection: Accuracy vs Interpretability

Logistic Regression

Advantages:

✓ Easy to explain

✓ Regulatory-friendly

✓ Fast training

✓ Transparent predictions

Limitations:

✗ May struggle with complex patterns

✗ Lower predictive performance

---

Gradient Boosting / XGBoost

Advantages:

✓ Higher predictive accuracy

✓ Captures non-linear relationships

✓ Handles complex interactions

✓ Strong performance on tabular data

Limitations:

✗ Harder to interpret

✗ More difficult to explain to regulators

✗ Requires additional interpretability tools

---

TECHNOLOGY STACK

Programming & Data Science

• Python
• Pandas
• NumPy
• Scikit-Learn
• XGBoost

Experiment Tracking

• MLflow

API Development

• FastAPI
• Pydantic

Testing

• Pytest

Containerization

• Docker
• Docker Compose

Version Control & Automation

• Git
• GitHub
• GitHub Actions

---

PROJECT STRUCTURE

credit-risk-model/

├── .github/workflows/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
├── src/
│   ├── api/
│   ├── data_processing.py
│   ├── train.py
│   └── predict.py
├── tests/
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── README.md

---

EXPECTED OUTCOMES

By the end of this project, Bati Bank will have:

✓ A complete credit risk scoring pipeline

✓ A machine learning model capable of estimating customer risk

✓ Credit score generation capabilities

✓ A production-ready REST API

✓ Automated testing and deployment workflows

✓ A scalable foundation for future lending decisions

---

Credit Scoring Business Understanding

1. How does the Basel II Accord's emphasis on risk measurement influence the need for an interpretable and well-documented model?

The Basel II Accord establishes international standards for managing and measuring credit risk within financial institutions. One of its core principles is that risk assessment processes must be transparent, reliable, and auditable. As a result, credit scoring models cannot be treated as "black boxes" whose decisions are impossible to explain.

An interpretable model allows risk managers, auditors, regulators, and other stakeholders to understand how predictions are generated and which factors influence lending decisions. Proper documentation ensures that model assumptions, data sources, feature engineering processes, validation procedures, and performance metrics can be reviewed and reproduced when required.

In a regulated financial environment, model explainability is essential for regulatory compliance, customer fairness, risk governance, and ongoing monitoring. Therefore, both model performance and interpretability must be considered during development.

2. Without a direct "default" label, why is a proxy variable necessary, and what business risks does proxy-based prediction introduce?

The dataset used in this project does not contain a direct indicator showing whether a customer eventually defaulted on a loan. Since supervised machine learning requires a target variable for training, a proxy variable must be created to represent customer risk.

A proxy target can be constructed using customer behavioral characteristics such as Recency, Frequency, and Monetary (RFM) metrics. Customers exhibiting weaker transaction behavior may be classified as higher risk, while customers demonstrating stronger engagement and spending patterns may be classified as lower risk.

However, proxy-based prediction introduces several business risks. The proxy may not perfectly reflect actual default behavior, leading to incorrect classifications. Customers who appear risky based on transaction patterns may not actually default, while some genuinely risky customers may be overlooked. Additionally, biases introduced during proxy creation can affect model fairness and predictive accuracy. For these reasons, proxy targets should be carefully designed, validated, and continuously monitored to ensure they remain meaningful and aligned with business objectives.

3. What are the key trade-offs between a simple, interpretable model (e.g., Logistic Regression with WoE) and a high-performance model (e.g., Gradient Boosting) in a regulated financial context?

Simple models such as Logistic Regression combined with Weight of Evidence (WoE) transformations are widely used in credit scoring because they are transparent and easy to interpret. Stakeholders can clearly understand how each variable contributes to a prediction, making these models easier to validate, audit, and justify to regulators. Their simplicity also reduces implementation complexity and supports regulatory compliance.

In contrast, high-performance models such as Gradient Boosting or XGBoost can capture complex, non-linear relationships within the data and often achieve superior predictive accuracy. These models are particularly effective when working with large datasets containing intricate feature interactions.

The primary trade-off is between predictive performance and explainability. While advanced models may improve risk prediction accuracy, they are more difficult to interpret and require additional explainability techniques such as SHAP values or feature importance analysis. In regulated financial environments, organizations must balance the benefits of improved predictive power against the need for transparency, accountability, and regulatory acceptance.

