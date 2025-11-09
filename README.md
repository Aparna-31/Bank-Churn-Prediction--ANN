Project Overview

This project focuses on building a robust classification model to predict customer churn (attrition) at a bank. The core objective is to identify high-risk customers—the minority class—to enable targeted retention strategies, thereby minimizing revenue loss.

Model Used: Artificial Neural Network (ANN)

Problem Statement

Develop an optimal binary classification model that accurately predicts the likelihood of a customer exiting the bank, allowing the bank to proactively intervene with customers whose predicted status is Exited = 1.

Data and Preprocessing

The dataset contains $10,000$ customer records and $14$ features, including demographic and account information.
Target Variable
The target variable is Exited (Binary Classification):
1: Customer has churned.
0: Customer is retained.
Preprocessing Flow
Dropped Irrelevant Features: RowNumber, CustomerId, and Surname.
Categorical Encoding: Geography and Gender were converted using One-Hot Encoding (pd.get_dummies(..., drop_first=True) to avoid the Dummy Variable Trap).
Feature Scaling: All continuous features (Age, CreditScore, Balance, etc.) were standardized using StandardScaler after the train-test split to prevent data leakage.
Data Balancing: The training data was balanced using SMOTE (Synthetic Minority Over-sampling Technique) to address the $4:1$ class imbalance.

Final Model Performance & Conclusion

The model was selected based on its ability to maximize Recall for the minority class, as the cost of missing a churner (False Negative) far outweighs the cost of a false prediction (False Positive).

Conclusion: The SMOTE-trained ANN is the superior model. Although it exhibits lower overall accuracy, its high 73% Recall provides the most valuable tool for the bank's retention strategy by robustly identifying the highest number of customers who are actually leaving.


