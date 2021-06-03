# Bank XYZ Marketing Campaign in Portugal using Machine Learning

ScipyGroup_JC_DS_12_FinalProject

Member :
- Abdullah Sayyid Ayyash (ayasabdullah4@gmail.com)
- Hendri Tedjo (hendri.tedjo@gmail.com)
- Hizkya Natali (hizkyanatali@gmail.com)

Dataset taken from : [Bank XYZ Marketing Campaign in Portugal Dataset](https://www.kaggle.com/volodymyrgavrysh/bank-marketing-campaigns-dataset)

<hr>

## Background

This project predict Potential Bank Customers in Portugal that want to buy Deposit from Bank XYZ. 

### Dataset Description

__Bank Client Data__:
- __age__
- __job__ : type of job (categorical: "admin.","blue-collar","entrepreneur",...,"unknown")
- __marital__ : marital status (categorical: "divorced","married","single","unknown")
- __education__ : (categorical: "illiterate",...,"university.degree","unknown")
- __default__: has credit in default? (categorical: "no","yes","unknown")
- __housing__: has housing loan? (categorical: "no","yes","unknown")
- __loan__: has personal loan? (categorical: "no","yes","unknown")
    
__Related with The Last Contact of The Current Campaign__:
- __contact__: contact communication type (categorical: "cellular","telephone")
- __month__: last contact month of year (categorical: "jan", …, "nov", "dec")
- __dayofweek__: last contact day of the week (categorical: "mon","tue",...)
- __duration__: last contact duration, in seconds (numeric).
    - __Important note__: this attribute highly affects the output target (e.g., if duration=0 then y="no"). , Can not get this feature before the campaign

__Other Attributes__:
- __campaign__: number of contacts performed during this campaign and for this client (numeric, includes last contact)
    - __Important note__: Can not get this feature before the campaign
- __pdays__: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
- __previous__: number of contacts performed before this campaign and for this client (numeric)
- __poutcome__: outcome of the previous marketing campaign (categorical: "failure","nonexistent","success")

__Social and Economic Context Attributes__ :
- __emp.var.rate__: employment variation rate - quarterly indicator (numeric)
- __cons.price.idx__: consumer price index - monthly indicator (changes in the price level of a weighted average __market basket__ of consumer goods and services purchased by households, affect inflation (numeric))
- __cons.conf.idx__: consumer confidence index - monthly indicator (degree of __consumers optimism__ are expressing through their activities of savings and spending. affect consumer behavior (numeric))
- __euribor3m__: euribor 3 month rate - daily indicator (Euribor (euro interbank offered rate) (numeric))
- __nr.employed__: number of employees - quarterly indicator (Number of employed persons for a quarter (numeric))

__Output Variable (desired target)__:
- __y__ - has the client subscribed a term deposit? (binary: "yes","no")


## Introduction

In this scenario, We are data scientist team working at XYZ Bank in Portugal. The business development team came to us and told us that they needed improvement on marketing campaign result because the result was not good enough compared to the cost.
They are asking if we can propose solutions to either reduce the cost or increase the income generated or both. They gave us customer dataset used at the recent campaign which consist of the bank’s customer data

## Problems

People that subscribed the deposit (from the dataset) is low (11.27%). The Cost expended was too big for the income generated. We Need a way to filtering the potential bank customer or not to buy a deposit

## Goals

1. Predict Potential Bank Customer that will buy deposit or not with Machine Learning Method
2. Give Cost Reduction Simulation after and before using Machine Learning

<hr>

## Data Cleaning & Preprocessing

- Checking Missing Value
<img src="https://github.com/PurwadhikaDev/ScipyGroup_JC_DS_12_FinalProject/blob/main/Pictures/Null.jpg" alt="Missing Value" width="500"/>

- Checking Outliers
<img src="https://github.com/PurwadhikaDev/ScipyGroup_JC_DS_12_FinalProject/blob/main/Pictures/Outliers.JPG" alt="Missing Value" width="200"/>

- Recategorize
1. Recategorizing the Age column into 4 group (Child, Teenager, Adult and Elder)
2. Recategorizing the Duration column every 3 minutes with with the last gorup is '> 18 min' (7 groups)

## Quick Data Analysis

We Separate the analysis into 2 main part __Univariate__ and __Multivariate__ (all columns against the target column)

__Univariate__:
- Most customers were 25 to 60 years old and there is little to none customers in kids and teenager group
- Most customers are working as admin, blue-collar, and technician
- Most customers are married
- Most call durations are 0-3 mins and 3-6 mins
- Most customers only contacted between 1 to 3 times during the campaign

__Multivariate__:
- The adult group dominates deposit subscribed in banks
- The marital status as married dominates deposit subscribed in banks
- Unknown marital status has the highest subscribe percentage
- Group which has no default loan dominates deposit subscribed in banks by quantity and percentage
- Most customer was contacted in May and even though May has the lowest subscribe percentage, the quantity of deposit is the highest
- In March, The Deposit subscriber has the highest percentage but is the second lowest by quantity

[Full Data Analysis](https://github.com/PurwadhikaDev/ScipyGroup_JC_DS_12_FinalProject/blob/main/1.%20Data%20Cleaning%2C%20Preprocessing%2C%20Exploratory%2C%20and%20Explanatory.ipynb)

<hr>

## Machine Learning Classification

The model predict the 'y' column (target) explain a certain bank customer will subscribe the deposit or not. The model used before running the next campaign. Use Features/column that can be obtained before the campaign

