# 🏦 Loan Approval Prediction Model

> **A Machine Learning Predictive Model using Random Forest to assess credit risk with 99.9% ROC-AUC accuracy.**

---

## 1. Business Problem Summary 
The objective of this project is to develop a highly accurate automated predictive model for a financial institution. The goal is to minimize **credit risk** (approving borrowers likely to default) while maximizing **business growth** (ensuring qualified applicants are not unnecessarily rejected). By transitioning from manual review to an algorithmic approach, the bank aims to improve decision consistency and operational efficiency. 

## 2. Dataset Overview 
The model was trained on a dataset containing 4,000 loan applications with the following characteristics: 
* **Target Variable:** Loan Status (0 for Reject, 1 for Approve). 
* **Key Features:** Includes financial metrics (Annual Income, Total Debt, Net Worth, Savings Balance) and credit history (Risk Score, Credit Card Utilization, Length of Credit History). 
* **Data Split:** The data was partitioned into a Training Set (80%) and a Test Set (20%) to ensure unbiased evaluation. 

## 3. Approach & Methodology 
To identify the optimal solution, three distinct machine learning algorithms were tested and tuned: 
* **Algorithms:** K-Nearest Neighbors (KNN), Decision Tree, and Random Forest. 
* **Optimization:** Hyperparameter tuning was performed using `GridSearchCV` with **5-fold Cross-Validation** to ensure model stability. 
* **Metric Selection:** Models were optimized for **ROC-AUC** to balance sensitivity and specificity, ensuring the model can effectively distinguish between safe and risky borrowers. 

## 4. Key Insights 
* **Risk Score is Critical:** Feature importance analysis revealed that the `RiskScore` feature drives over **55%** of the model's logic. 
* **Non-Linear Thresholds:** Partial Dependence Plots (PDP) showed a sharp "cliff" in approval probability as the Risk Score increases, suggesting a specific threshold where risk becomes unacceptable. 
* **Debt-to-Income Impact:** The model effectively identifies a plateau in risk once the `TotalDebtToIncomeRatio` reaches a certain level, allowing for more nuanced decisions than a simple linear cutoff. 

## 5. Final Model Performance 
The **Random Forest Classifier** was selected as the final model due to its superior performance across all metrics: 

| Metric | Score |
| :--- | :--- |
| **Best Cross-Validation ROC-AUC** | 0.9989 |
| **Test Set ROC-AUC** | 0.9990 |
| **Precision (Approval)** | 0.9809 |
| **Recall (Approval)** | 0.9655 |

## 6. How to Run the Project 
To replicate this analysis, follow these steps: 
1.  **Environment Setup:** Ensure you have Python installed with the necessary libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, and `scikit-learn`. 
2.  **Load Data:** Place the dataset in the root directory. 
3.  **Execute Notebook:** Run the cells sequentially to perform data preprocessing, model training, and evaluation. 
4.  **GridSearch Note:** The Random Forest GridSearch may take approximately **5 minutes** to complete due to the complexity of the 180-fit cross-validation process.# Machine-learning
