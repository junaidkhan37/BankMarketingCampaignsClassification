Bank Marketing Campaigns Classification



Overview

This project analyzes data from a Portuguese banking institution’s direct marketing campaigns to predict whether a client will subscribe to a term deposit. Multiple machine learning models are developed, evaluated, and compared to identify the most effective approach for this classification task.
The dataset contains client demographic information, campaign interaction details, and macroeconomic indicators. The primary objective is to accurately predict the target variable y, which indicates whether a client subscribed to a term deposit (yes or no).




Dataset

Source: UCI Machine Learning Repository – Bank Marketing Dataset


Dataset Used: bank-additional-full.csv


Number of records: 41,188
Number of features: 20 input variables
Target variable: y (binary: yes / no)
Time period: May 2008 – November 2010
The dataset includes categorical, numerical, and binary features. Several variables contain "unknown" values, which are handled during preprocessing.




Methodology

The project follows a structured machine learning workflow:

Data Loading & Inspection
Data types, missing values, class imbalance
Exploratory Data Analysis (EDA)
Distribution plots
Target imbalance analysis
Feature-level insights
Preprocessing
Handling "unknown" values as a distinct category
One-hot encoding for categorical features
Feature scaling for numerical features
Modeling
Baseline model
Advanced models
Evaluation
Accuracy, Precision, Recall, F1-score
ROC-AUC
Train time
Confusion matrices and ROC curves
Model Comparison & Selection




Models Implemented


Baseline Model


Logistic Regression
Class-weighted to address class imbalance
Serves as a performance benchmark


Advanced Models


K-Nearest Neighbors (KNN)
Distance-based non-parametric classifier

Decision Tree
Interpretable model with depth and leaf constraints


Support Vector Machine (SVM)
RBF kernel
Margin-based optimization




All models use a consistent preprocessing pipeline to ensure fair comparison.



Evaluation Metrics


To properly evaluate performance under class imbalance, multiple metrics were tracked:

Train Time
Train Accuracy
Test Accuracy
Precision
Recall
F1-score
ROC-AUC



Visual diagnostics include:


ROC curves (individual and combined)
Confusion matrices
Bar charts for ROC-AUC and training time comparison




Model Performance Comparison



Model	Train Time (s)	Train Accuracy	Test Accuracy	Precision	Recall	F1-score	ROC-AUC
0	Logistic Regression (Baseline)	NaN	NaN	NaN	0.451200	0.911638	0.603639	0.943838
2	Decision Tree	27.340505	0.847587	0.845836	0.415680	0.908405	0.570365	0.938863
3	SVM (RBF Kernel - Subsampled)	80.879697	0.844800	0.845958	0.418460	0.942888	0.579662	0.938358
1	KNN	10.932382	0.939727	0.898519	0.564426	0.434267	0.490865	0.835175







Results Summary

Model	Strengths	Limitations

Logistic Regression	Fast, stable, interpretable	Limited non-linearity


KNN	Flexible decision boundaries	Sensitive to scaling and k


Decision Tree	Highly interpretable	Prone to overfitting


SVM	Best generalization, strong ROC-AUC	High computational cost



Highlights:

Best ROC-AUC & F1-score: Logistic Regression (Baseline)

Best Recall: SVM (RBF Kernel)

Best Precision & Accuracy: KNN

Fastest Training: KNN and Decision Tree



Final Model Selection

Best Overall Model: Support Vector Machine (SVM)

Why SVM:

Achieved the highest ROC-AUC
Strong recall performance, critical for identifying potential subscribers
Balanced trade-off between false positives and false negatives
Demonstrated superior generalization on unseen data


Key Takeaways

Margin-based models (SVM) perform best for this problem
Class imbalance must be explicitly addressed
Preprocessing consistency is critical for fair model comparison
Simpler models remain strong baselines and provide interpretability


Business Findings & Recommendations

Based on model performance, the Support Vector Machine (SVM) model is recommended for prioritizing clients with a high probability of subscribing to a term deposit. This will help the bank reduce unnecessary marketing calls and improve conversion rates, thereby optimizing marketing costs.

Clients contacted multiple times show diminishing returns.
SVM model best identifies high-probability subscribers.
Marketing efforts should prioritize high-recall predictions.


Next Steps

Incorporate cost-sensitive learning
Evaluate campaign timing effects
Test model on newer campaign data
