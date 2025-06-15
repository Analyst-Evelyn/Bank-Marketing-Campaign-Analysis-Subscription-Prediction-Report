#  Bank Marketing Term Deposit Subscription Prediction

## Table of Contents
- [Problem Statement](#problem-statement)
- [ Key Objectives](#objective)
- [Tools & Analysis Used for this Project](#tools-and-analysis-used-for-this-project) 
- [Data Overview & Summary Statistics](#data-overview-and-summary-statistics)
- [Data Overview](#data-overview)
- [Machine Learning Pipeline](#machine-learning-pipeline)
-
- [EDA (Exploratory Data Analysis)](#exploratory-data-analysis)
- [Recommendations](#recommendations)


## **Problem Statement**
Financial institutions often run marketing campaigns to promote term deposit subscriptions. However, targeting the wrong audience leads to inefficiency, increased costs, and customer dissatisfaction. This project aims to develop a predictive model that determines whether a client will subscribe to a term deposit based on various personal, contact, and socio-economic characteristics. This prediction model will help the bank optimize its marketing strategy, reduce unnecessary outreach, and target high-conversion clients , improving overall customer acquisition efficiency.

## **Objective**
Build a machine learning model that accurately predicts if a client will subscribe to a term deposit using historical data from previous marketing campaigns.

## **Tools and Analysis Used for this Project**

Type of Analysis Performed

| **Stage**                     | **Description**                                             |
|------------------------------|-------------------------------------------------------------|
| **Exploratory Data Analysis (EDA)** | Examined data distribution, missing values, outliers, and relationships between variables. |
| **Univariate Analysis**       | Analyzed individual features such as `age`, `job`, `marital`, and `education` using histograms, count plots, and summary statistics. |
| **Bivariate Analysis**        | Explored relationships between independent features and the target variable (`y`) through bar plots and cross-tabulations. |
| **Correlation Analysis**      | Investigated correlations among numerical variables using a heatmap to identify potential multicollinearity issues. |
| **Feature Engineering**       | Created new features such as `age_group` and performed encoding of categorical variables for machine learning readiness. |
| **Class Imbalance Handling**  | Applied **SMOTE (Synthetic Minority Oversampling Technique)** to balance the 'yes' and 'no' target classes. |
| **Predictive Modeling**       | Built and trained a **Random Forest Classifier** to predict client subscription. |
| **Model Evaluation**          | Assessed model performance using **Accuracy**, **Precision**, **Recall**, **F1 Score**, and **ROC-AUC Score**. |
| **Recommendations Development** | Generated business recommendations based on data insights and model output. |

---

## 🧰 Tools and Libraries Used

| **Tool / Library**            | **Purpose**                                  |
|------------------------------|--------------------------------------------|
| **Python 3.x**                | Core programming language                   |
| **Pandas**                    | Data manipulation and preprocessing         |
| **NumPy**                     | Numerical operations                        |
| **Matplotlib / Seaborn**      | Data visualization and plotting             |
| **Scikit-learn (sklearn)**    | Machine Learning modeling, evaluation, preprocessing |
| **Imbalanced-learn (imblearn)**| Handling class imbalance via SMOTE          |
| **Jupyter Notebook**          | Development environment for data science tasks |


## **Data Overview and Summary Statistics**
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

6. **Source File**: `bank-additional-full.csv`[[bank-additional-full.csv](https://github.com/user-attachments/files/20743250/bank-additional-full.csv)]
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
  


 ## **Recommendations**
**For Marketing Team**
- Prioritise clients with previous success: Use past campaign results to target only those with a history of positive responses.
- Use cellular contact method: Increase usage of mobile numbers where available.
- Lengthen engagement time: Train sales reps to spend more time per call.
- Avoid repetitive contacts without success: If a client has rejected multiple times, skip them unless there’s a new offer.
- Segment by age and job type: Target 25–40-year-olds in admin., technician, and service jobs.
  
**For Business Strategy**
- Incorporate the model into CRM: Automate lead scoring based on likelihood to convert.
- Track campaign KPIs: Monitor duration, poutcome, and contact frequency as key metrics.
- Dynamic offer creation: Tailor offers based on client profile and timing.

