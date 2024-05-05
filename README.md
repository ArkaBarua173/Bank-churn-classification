# 🏦 Bank-churn-classification

## 🔗 Link - (https://www.kaggle.com/code/arkabarua173/bank-churn-xgboost-roc-89-shap?kernelSessionId=175744081)
- Please go to link to see the interactive plotly graphs.

## 📌 Objective:
- Predicting the probabilities of exiting the bank.

## 📄 Dataset Description:
- **CustomerId**: This is a unique identifier for each customer.
- **Surname**: The surname of each customer. Nominal variable.
- **CreditScore**: The credit score of each customer. Continuous Variable.
- **Geography**: Indicates the country where the customer resides. In this dataset (Germany, Spain & France).
- **Gender**: The gender of each customer.
- **Age**: The age of each customer. Continuous Variable.
- **Tenure**: The number of years the customer has been with the bank. Continuous Variable.
- **Balance**: The account balance of each customer. Continuous Variable.
- **NumOfProducts**: The number of bank products the customer uses.
- **HasCrCard**: Indicates whether the customer has a credit card (1 for yes, 0 for no).
- **IsActiveMember**: Specifies whether the customer is an active member (1 for yes, 0 for no).
- **EstimatedSalary**: Represents the estimated salary of the customer. Continuous Variable.
- **Exited**: This is the target variable and indicates whether the customer has exited the bank (1 for yes, 0 for no).

## 🔨 Data Preprocessing
- **Mutual Information** is used for selecting features.
- **One Hot Encoder** used for categorical value (In this dataset (Gender & Geography))

## 🤖 Model:
- XGBoost is used for this binary classification because dataset is imbalanced.
- XGBoost tends to work well with imbalanced dataset i.e. "scale_pos_weight" parameter can be utilized to handle imbalance.
- RandomizedSearchCV is used with 5 fold and roc_auc score for hypertuning.

## 🔍 Model Evaluation:
- Accuracy, Precision, F1 scroe, Recall and Area Under the Curve Receiver Operating Characteristic score is used for the model
- Best ROC_AUC score is 0.891.
- Class wise result are shown below:

![result](/Snapshot/result.png)

- Confusion matrix are shown below

![Confusion Matrix](/Snapshot/cm.png)

- Feature Importance based on weight, cover and gain are shown below

![weight](/Snapshot/weight.png)

![cover](/Snapshot/cover.png)

![gain](/Snapshot/gain.png)

- Shap was used to understand the model output. Based on mean absolute Shapley values, NumOfProducts is the important feature followed by Age.

![shap](/Snapshot/shap.png)
