Comparing Classifiers
Module-17 : Practical Exercise-3
Executive Summary

This project evaluates and compares the performance of four classification algorithms—Logistic Regression, k-Nearest Neighbors (KNN), Decision Trees, and Support Vector Machines (SVM)—on the Portuguese Bank Marketing dataset. The dataset, sourced from the UCI Machine Learning Repository
, consists of 41,188 client records collected across 17 marketing campaigns between 2008 and 2010.

The objective is to predict whether a customer will subscribe to a term deposit based on demographic information, campaign details, and economic indicators. Results show that Logistic Regression achieves the best overall balance of accuracy, efficiency, and interpretability, making it the most suitable model for deployment.

1. Business Understanding
Objective

To assist the bank in predicting customer responses to telemarketing campaigns. By identifying clients most likely to subscribe to term deposits, the bank can:

Improve targeting (focus on high-likelihood clients).

Reduce costs by avoiding inefficient calls.

Enhance marketing effectiveness with data-driven strategies.

Key Business Question

Can we build a predictive model to estimate whether a client will subscribe to a term deposit using customer, campaign, and macroeconomic data?

2. Data Understanding
Dataset

The dataset contains 41,188 entries with 21 features, covering:

Demographics: age, job, marital status, education.

Financials: housing loan, personal loan, credit default.

Campaign details: contact type, last contact month/day, call duration, number of contacts, previous campaign outcome.

Economic context: employment variation rate, consumer price/confidence indices, Euribor rates, number of employees.

Target variable: y (binary: subscribed = “yes” or not subscribed = “no”).

Special Note on Duration

The duration variable strongly correlates with the outcome but is only known after the call. For realistic predictive modeling, it must be excluded to avoid data leakage.

3. Data Preparation

Steps performed:

Replaced "unknown" values with NaN.

Dropped duration feature (target leakage).

Applied one-hot encoding to categorical features.

Normalized and scaled numerical features.

Split dataset into training and testing sets.

4. Modeling

Models applied:

Logistic Regression

K-Nearest Neighbors (KNN)

Decision Tree Classifier

Support Vector Machine (SVM)

Baseline Accuracy

88.73% (based on majority class prediction).

5. Model Validation & Comparison
Performance Overview
<img width="1165" height="717" alt="image" src="https://github.com/user-attachments/assets/b83af9bb-5079-461d-88b7-10e94704b24d" />
Key Visualizations
<img width="1574" height="902" alt="image" src="https://github.com/user-attachments/assets/b39b3e64-123c-4863-8b15-4b78df0f02e9" />

(SVM plotting omitted due to computational expense on full dataset)

Confusion Matrices
<img width="1128" height="891" alt="image" src="https://github.com/user-attachments/assets/1e369c4c-84cc-4da4-ab60-ebb55e946dea" /> <img width="1123" height="890" alt="image" src="https://github.com/user-attachments/assets/09e7b88b-3b41-4790-904d-c73f4b05a251" /> <img width="1125" height="886" alt="image" src="https://github.com/user-attachments/assets/6798ff57-59c2-41f4-b573-2696c2f9a539" />
ROC Curve Comparison

The ROC curve highlights classifier trade-offs. Models with larger AUC (Area Under Curve) are more effective.

<img width="1227" height="908" alt="image" src="https://github.com/user-attachments/assets/7c1c0a70-3c6b-4525-82a8-1178a9be3c35" />
6. Findings & Recommendations
A) Logistic Regression — Best Choice

Highest accuracy (90.13%).

Fastest training (0.24s).

Balanced generalization (train ≈ test accuracy).

Interpretable coefficients → useful for regulatory & business insights.

B) Support Vector Machine (SVM) — Strong but Expensive

Nearly identical accuracy to Logistic Regression (90.08%).

Very high computational cost (343s vs 0.24s).

Better suited for smaller datasets or high-performance environments.

C) K-Nearest Neighbors (KNN) — Good, but Not Scalable

Test accuracy: 89.33%.

No training cost, but slow at prediction with large datasets.

Useful only for prototyping or small-scale tasks.

D) Decision Tree — Overfits Severely

Training accuracy: 99.47% (classic overfitting).

Test accuracy: 84.07% (lowest among models).

Recommendation: Avoid standalone use. Consider Random Forest or Gradient Boosting for improved robustness.

Recommendation Table
<img width="1186" height="382" alt="image" src="https://github.com/user-attachments/assets/5033c0c4-9499-4f76-8e79-cb4f67a4176e" />
7. Conclusion
Business Question Answered

Yes, predictive models can accurately estimate subscription likelihood.

Logistic Regression is the most practical model for deployment, balancing accuracy, efficiency, and explainability.

Best Model Outcome

Test Accuracy: ~90%

Train Accuracy: ~90%

Stable across validation runs

Likely strong F1-score performance on imbalanced classes

8. Next Steps

Ensemble Modeling

Explore Random Forests, Gradient Boosting, and XGBoost for better generalization.

Imbalanced Data Handling

Apply SMOTE or class-weight adjustments to improve recall for minority “yes” class.

Business Deployment

Integrate Logistic Regression into CRM systems for real-time lead scoring.

Cost-Sensitivity Analysis

Prioritize models that minimize false positives/negatives depending on campaign costs.

Future Data Expansion

Incorporate additional external variables (e.g., economic forecasts, customer income).
