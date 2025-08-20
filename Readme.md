# Comparing Classifiers
### Module-17 : Practical Exercise-3 
 
 The goal of this assignment is to compare the performance of the classifiers : k-nearest neighbors, logistic regression, decision trees, and support vector machines. You will use a dataset related to the marketing of bank products over the telephone. For this exercise we will be utilizing the from  UC Irvine Machine Learning Repository. The data is from a Portuguese Banking Institution and is a collection of the results of multiple marketing campaigns.

# Dataset

The Data set link is as provided below
https://archive.ics.uci.edu/dataset/222/bank+marketing

About the Dataset: This dataset comprises data from 17 different marketing campaigns, conducted between May 2008 and November 2010

# How is the project work and deliverables being measured? - Measurement Criteria Table As Below
<img width="842" height="505" alt="image" src="https://github.com/user-attachments/assets/28010461-6ed7-4e4a-a765-3aa3f5efd99e" />

# Note about the Files, Folder and Dataset...
The Folder Structure for this Project is as below under the repository: "Comparing_Classifiers_Portuguese_Bnk"

<img width="278" height="160" alt="image" src="https://github.com/user-attachments/assets/e8824d25-624e-4148-a77f-4a4cc19bb18b" />

# Six Standard Phases of CRISP-DM in Comparing the Performance Classifiers?
## 1. Business Understanding
### Objective: Is to predict whether a bank client will subscribe to a term deposit based on information obtained during direct marketing campaigns like phone calls, along with demographic and economic context data.
### Key Business Questions:
-	Is to predict whether a bank client will subscribe to a term deposit based on information obtained during direct marketing campaigns like phone calls this along with demographic and economic context data.
## 2. Data Understanding
### Data Description: The dataset contains 41188 entires with 21 Column-attributes/Features such as:
-	age (numeric)
-	job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')
-	marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)
-	education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')
-	default: has credit in default? (categorical: 'no','yes','unknown')
-	housing: has housing loan? (categorical: 'no','yes','unknown')
-	loan: has personal loan? (categorical: 'no','yes','unknown')
#### Related with the last contact of the current campaign:
-	contact: contact communication type (categorical: 'cellular','telephone')
-	month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')
-	day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')
-	duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). 
  Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded 
  if the intention is to have a realistic predictive model.
#### Other attributes:
-	campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
-	pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
-	previous: number of contacts performed before this campaign and for this client (numeric)
-	poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')
#### Social and economic context attributes
-	emp.var.rate: employment variation rate - quarterly indicator (numeric)
-	cons.price.idx: consumer price index - monthly indicator (numeric)
-	cons.conf.idx: consumer confidence index - monthly indicator (numeric)
-	euribor3m: euribor 3 month rate - daily indicator (numeric)
-	nr.employed: number of employees - quarterly indicator (numeric)
#### Output variable (desired target):
-	y - has the client subscribed a term deposit? (binary: 'yes','no')
## 3. Data Preparation
- Replace 'unknown' with NaN
- Drop duration (leaks target)
- Convert categorical → one-hot encoding
- Scale/normalize numeric features
- Split into training and test sets
## 4. Modeling
Models used:
- Logistic Regression
- K-Nearest Neighbors
- Decision Tree
- Support Vector Machine

#### Baseline Accuracy: `88.73%`

## 5. Model Validation and Comparison Summary

<img width="1165" height="717" alt="image" src="https://github.com/user-attachments/assets/b83af9bb-5079-461d-88b7-10e94704b24d" />

## Visualizations

<img width="1574" height="902" alt="image" src="https://github.com/user-attachments/assets/b39b3e64-123c-4863-8b15-4b78df0f02e9" />

/*Opted out Plotting SVM: Due to the time it takes for the processor to process the large data set.*//
## Confusion Matrix

<img width="1128" height="891" alt="image" src="https://github.com/user-attachments/assets/1e369c4c-84cc-4da4-ab60-ebb55e946dea" />

<img width="1123" height="890" alt="image" src="https://github.com/user-attachments/assets/09e7b88b-3b41-4790-904d-c73f4b05a251" />

<img width="1125" height="886" alt="image" src="https://github.com/user-attachments/assets/6798ff57-59c2-41f4-b573-2696c2f9a539" />

## ROC Curve Comparison:
The overall performance of a classifier, summarized over all possible classification thresholds, is given by the area under the ROC curve. An ideal ROC curve will hug the top left corner, 
indicating a high true positive rate and a low false positive rate; the larger the AUC( Area Under) the better the classifier.

<img width="1227" height="908" alt="image" src="https://github.com/user-attachments/assets/7c1c0a70-3c6b-4525-82a8-1178a9be3c35" />

## 6.	Recommendations and Deployment Guidelines
### A)	Logistic Regression — Recommended (Best Balance of Performance + Efficiency)
- Highest Test Accuracy (90.13%)
- Very fast training time
-	Low risk of overfitting (train ≈ test accuracy)
-	Interpretable (important for regulatory and business explanations)
  
### B)	Support Vector Machine — Also Strong, but High Cost
- Excellent accuracy (90.08%), nearly identical to Logistic Regression
-	Extremely high train time (343 seconds vs 0.24s)
### C)	K-Nearest Neighbors — Good Accuracy, but Not Scalable
-	Simple, intuitive, no training time
-	Slightly worse test accuracy (89.33%)
-	Inefficient for large-scale prediction (slow at test time)
** With small datasets KNN is ok for prototyping
### D) Decision Tree — Overfitting, Not Reliable
-	Train accuracy too high (99.47%) → classic overfitting
-	Worst test accuracy (84.07%)
# Recommendation Table
** Use of Decision Tree is ruled out may be Random Forest or Gradient Boosting mnaybe a better option.
<img width="1186" height="382" alt="image" src="https://github.com/user-attachments/assets/5033c0c4-9499-4f76-8e79-cb4f67a4176e" />

# In Conclusion
### Answering our key business question Was the Prediction Goal was met? : 
 The models can reasonably predict y = 'yes' or 'no' for new clients.
 This was based on…
 Logistic Regression, KNN, Decision Tree, and SVM models.
### Best Model being : Logistic Regression which gave us:
- Test Accuracy:  ~90%
-	Train Accuracy: ~90%
- Reasonable F1-Score (if computed), especially for an imbalanced dataset.
#### In total, our model can predict term deposit subscription using available client, campaign, and economic data with high accuracy and practical reliability.









