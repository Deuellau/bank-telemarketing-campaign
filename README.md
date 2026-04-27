# Bank Telemarketing Campaign Prediction 🏦📞

**Predicting Term Deposit Subscriptions Using a Stacked Ensemble**

## 📄 Quick Links
* [**Jupyter Notebook**](./Code/Project%20Workflow.ipynb)
* [**Full Project Report (PDF)**](./Project%20Report.pdf)

## 📌 Project Overview
Telephone-based telemarketing is a primary customer acquisition channel for retail banks, yet average subscription rates rarely exceed 10-15%, making most calls wasteful. This project addresses the inefficiency of mass-calling by developing a machine learning triage layer to score customers based on their predicted likelihood to subscribe to a term deposit. By identifying high-probability leads, banks can allocate finite call budgets much more effectively.

## 🏗️ Methodology
The pipeline enforces strict standards for prospective deployability:
* **Leakage Prevention:** The `duration` feature (call duration) was strictly excluded, as it is only known *post-contact* and falsely inflates model performance in standard literature.
* **Stacked Generalization Ensemble:** The architecture combines four diverse Level-0 base learners (XGBoost, Random Forest, K-Nearest Neighbors, and Gaussian Naive Bayes). A Level-1 Logistic Regression meta-classifier is then trained on their out-of-fold predictions to learn the optimal weighting.
* **Nested Cross-Validation:** A rigorous nested 5x5 stratified CV was used to decouple hyperparameter tuning from generalization error estimation, avoiding optimism bias.

## 💼 Business Impact
Translating standard ML metrics into actionable banking economics (assuming €3.00 cost-per-call and €62.50 revenue-per-conversion), the Stacked Ensemble delivers massive efficiency gains over a random dialling strategy:
* **Saves 14,279 wasteful calls** (a 36.2% reduction).
* **Drives a 7.6% net profit uplift**, generating €182,125 at the profit-maximising threshold.
* Under a resource-constrained scenario (top-10% budget), it yields a **4.40x lift** in conversions.

## 👥 Team
* Edwin Lim Jia Xian
* Chee Keng Wai Cornelius
* Lau Tze Chong Deuel
* Tan Yi Cheng

*Developed at the National University of Singapore.*
