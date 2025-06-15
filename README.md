#  Bank Marketing Term Deposit Subscription Prediction



## **Problem Statement**
Financial institutions often run marketing campaigns to promote term deposit subscriptions. However, targeting the wrong audience leads to inefficiency, increased costs, and customer dissatisfaction. This project aims to develop a predictive model that determines whether a client will subscribe to a term deposit based on various personal, contact, and socio-economic characteristics. This prediction model will help the bank optimize its marketing strategy, reduce unnecessary outreach, and target high-conversion clients , improving overall customer acquisition efficiency.

## **Objective**:
Build a machine learning model that accurately predicts if a client will subscribe to a term deposit using historical data from previous marketing campaigns.

## **Data Overview & Summary Statistics**
(i) Dataset Used: bank-additional-full.csv

(ii) Total Records: 41,188

(iii) Total Features: 20

**Key Variables**:

1. Features: Age, Job, Marital Status, Education, Default, Housing, Loan, Contact, Month, Day of Week, Duration, Campaign, Pdays, Previous, Poutcome, Emp.var.rate, Cons.price.idx, Cons.conf.idx, Euribor3m, Nr.employed.

2. Target Variable: y — whether the client subscribed to a term deposit (yes/no).

3. Age :

- Max_Age: 98(yrs)
- Min_Age: 17(yrs)

4. Duration
- Min: 0
- Max: 4918

5. Campaign
- Min: 0
- Max: 56


## Data Overview

- **Source File**: `bank-additional-full.csv`[[bank-additional-full.csv](https://github.com/user-attachments/files/20743250/bank-additional-full.csv)]
- **Observations**: 41,188
- **Features**: 20 (excluding target)

## Target Variable Distribution
- **"No"**: ~88.5%
- **"Yes"**: ~11.5%

### Age Group Insights
- Highest subscription rate: **30–50 age bracket**

### Job Type
- **Students and Retired** show highest conversion rates
- **Blue-collar** shows the lowest

### Marital Status
- **Single** clients more likely to subscribe

### Day of Week
- Best response on **Tuesdays and Wednesdays**

### Duration of Call
- Positive correlation with subscription, but not used for prediction (leakage)

---

## Machine Learning Pipeline

### Train-Test Split
- **80/20** ratio using `train_test_split`

### Preprocessing
- **Categorical encoding**: Label Encoding
- **Class balancing**: SMOTE (Synthetic Minority Oversampling Technique)
- **Feature selection**: Removed `duration` to prevent data leakage

###  Model: Random Forest Classifier
```python
from sklearn.ensemble import RandomForestClassifier
model = RandomForestClassifier(random_state=42)
model.fit(X_train, y_train)
