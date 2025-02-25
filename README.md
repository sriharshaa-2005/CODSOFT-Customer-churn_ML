# CODSOFT-Customer-churn_ML

# Customer Churn Prediction

##  Project Overview
This project aims to predict customer churn for a subscription-based service using machine learning models. Churn prediction helps businesses identify customers likely to leave and take proactive steps to retain them.

##  Dataset
- **Source:** Sample dataset containing information about 10,000 customers.
- **Features:**
  - `CustomerId`: Unique identifier for each customer
  - `CreditScore`: Customer's credit score
  - `Geography`: Customer's location (France, Spain, Germany)
  - `Gender`: Male or Female
  - `Age`: Customer's age
  - `Tenure`: Number of years the customer has been with the company
  - `Balance`: Customer's account balance
  - `NumOfProducts`: Number of products the customer has with the company
  - `HasCrCard`: Whether the customer has a credit card (1 = Yes, 0 = No)
  - `IsActiveMember`: Whether the customer is an active member (1 = Yes, 0 = No)
  - `EstimatedSalary`: Customer's estimated salary
  - `Exited`: Target variable (1 = Churned, 0 = Retained)

##  Data Preprocessing
- **Handling categorical data:**
  - `Geography` was encoded to numerical values: France → 1, Spain → 2, Germany → 3
  - `Gender` was encoded: Female → 1, Male → 2
- **Splitting data:**
  - Used `train_test_split()` to divide data into 80% training and 20% testing.

##  Machine Learning Models
Implemented the following models using Scikit-learn:

### 1. Logistic Regression
- Used `LogisticRegression` with `liblinear` solver and `max_iter=500`
- **Accuracy:** 80.35%

### 2. Random Forest Classifier
- Used `RandomForestClassifier` with default parameters
- **Accuracy:** 86.8%

### 3. Gradient Boosting Classifier
- Used `GradientBoostingClassifier` with default parameters
- **Accuracy:** 86.25%

##  Model Comparison
A bar plot was used to visualize the accuracy of the models:
```python
sns.barplot(x='Models', y='ACC', data=e_fd)
```

##  Predictions
Tested the models with new data:
```python
new_data = pd.DataFrame({
    'CustomerId':[15647305], 'CreditScore':[625], 'Geography':[2], 'Gender':[1], 'Age':[43], 'Tenure':[10],
    'Balance':[0], 'NumOfProducts':[2], 'HasCrCard':[0], 'IsActiveMember':[0], 'EstimatedSalary':[20000]
}, index=[0])
```
All models predicted **[0]**, indicating the customer is likely to stay.


