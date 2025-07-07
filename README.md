# Fraud Detection Using Machine Learning Techniques 🕵️‍♂️💻
This project develops a fraud detection system using machine learning applied to a transactional dataset sourced from Kaggle. The entire workflow was implemented in a Jupyter Notebook within the Anaconda environment. Below is a detailed description of the data exploration, preparation, splitting, and model training processes.

## Data Exploration, Preparation, and Splitting 🔍
The dataset exhibited a strong class imbalance, with most transactions being legitimate and only a small fraction classified as fraudulent. To address this and prepare the data for modeling, the following steps were undertaken:

### Exploratory Data Analysis (EDA):

Duplicate records were identified and removed.

Missing values and null entries were detected and appropriately handled.

Correlation analysis was performed between features and with respect to the target variable to understand relationships.

Categorical variables were identified and transformed using encoding techniques suitable for machine learning.

### Data Splitting:
The cleaned dataset was split into training and testing sets using a 70/30 ratio, maintaining the original class distribution in the test set to ensure reliable model evaluation.

### Handling Class Imbalance and Model Training ⚙️:
Given the significant imbalance, models were trained under two main conditions:

#### Without Oversampling (Baseline):
Four algorithms—Random Forest, XGBoost, CatBoost, and SVM—were trained on the imbalanced training data. These baseline models showed high accuracy on legitimate transactions but very low recall for fraud detection.

##### With Oversampling Using SMOTE Variants:
To improve detection of the minority class, three different Synthetic Minority Oversampling Techniques were applied separately on the training set:

Classic SMOTE

Borderline-SMOTE

ADASYN

For each oversampling method, the four models were retrained. This comprehensive evaluation showed a significant increase in recall and sensitivity for fraud detection compared to the baseline. However, improvements were moderate and carefully balanced against maintaining a low false positive rate, prioritizing operational reliability alongside fraud detection performance. XGBoost combined with SMOTE variants consistently delivered the best balance between precision and recall.

## Model Explainability:
SHAP (SHapley Additive exPlanations) was used to interpret model predictions. The analysis highlighted key features such as income, device_os, payment_type, and credit_risk_score as the most influential factors for fraud classification.
