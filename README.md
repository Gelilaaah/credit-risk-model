\# Credit Risk Probability Model for Alternative Data



\## Project Overview



This project develops an end-to-end credit risk scoring solution for Bati Bank.



The objective is to use alternative transaction data from an eCommerce platform to predict customer credit risk and support Buy-Now-Pay-Later decisions.



\## Project Structure



\- data/

\- notebooks/

\- src/

\- tests/

\- .github/workflows/



\## Technologies



\- Python

\- Scikit-Learn

\- FastAPI

\- MLflow

\- Docker

\- GitHub Actions



\## Task 1: Credit Scoring Business Understanding



\### Basel II and Model Interpretability



The Basel II Accord requires financial institutions to maintain transparent and well-documented risk assessment processes. As a result, credit scoring models must be explainable, reproducible, and auditable. Interpretability allows risk teams and regulators to understand how predictions are generated and ensures compliance with regulatory requirements.



\### Why a Proxy Target is Necessary



The dataset does not contain a direct default label. Therefore, a proxy target must be created to represent credit risk. Customer behavior patterns such as Recency, Frequency, and Monetary value can be used to estimate potential default risk.



\### Risks of Proxy-Based Prediction



A proxy may not perfectly represent actual default behavior. Incorrect assumptions during proxy creation can introduce bias and reduce model accuracy. Continuous monitoring and validation are necessary.



\### Trade-Off Between Interpretable and Complex Models



Simple models such as Logistic Regression provide transparency and easier regulatory approval but may achieve lower predictive performance.



More complex models such as Gradient Boosting often improve prediction accuracy but reduce interpretability. Financial institutions must balance performance and regulatory compliance.

