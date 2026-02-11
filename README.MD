🏦 German Credit Risk Classification (Machine Learning)

Binary classification using Decision Trees and Neural Networks, evaluated on held-out test data with a focus on generalization and feature selection.

📌 Project Overview

This project applies machine learning classification models to the German Credit dataset to predict the binary target variable RESPONSE.
The analysis emphasizes out-of-sample (test set) performance and compares multiple models and feature sets to understand tradeoffs between:

Accuracy

Precision & recall

Model complexity

Interpretability

Models evaluated

Decision Tree Classifier

Neural Network (MLPClassifier)

Each model is trained using:

All available features

Top 5 selected features, chosen via correlation with the target variable

🎯 Objectives

Predict credit response outcomes (RESPONSE)

Compare models using test-set performance metrics

Evaluate how feature selection improves generalization

Understand tradeoffs between recall-heavy vs balanced classifiers

📂 Dataset

File: GermanCredit.csv

Target Variable: RESPONSE

Preprocessing

Missing values handled using forward fill

Categorical variables encoded via one-hot encoding

Cleaned dataset saved as Cleaned_GermanCredit.csv

🛠️ Methodology
1️⃣ Exploratory Data Analysis

Dataset structure and summary statistics

Correlation heatmap across encoded variables

2️⃣ Feature Selection

Selected Top 5 features based on absolute correlation with RESPONSE

Visualized correlation strength using bar charts

3️⃣ Train / Test Split & Scaling

70 / 30 train-test split with stratification

StandardScaler applied for neural network models

4️⃣ Model Training & Tuning

All models were tuned using GridSearchCV (cv = 3).

Decision Tree tuning parameters

Criterion (gini, entropy)

Max depth

Leaf and split constraints

Neural Network tuning parameters

Hidden layer sizes

Activation functions

Maximum iterations

📊 Evaluation Strategy

All reported results are based on a held-out test set to measure real-world generalization.

Metrics used

Accuracy

Precision, Recall, F1-score

Confusion Matrices

✅ Test Set Results
🔍 Classification Performance Summary
Model	Feature Set	Accuracy	Class 1 Recall	Macro F1
Neural Network	Top 5	0.78	0.90	0.71
Decision Tree	Top 5	0.72	0.94	0.56
Neural Network	All Features	0.71	0.82	0.64
Decision Tree	All Features	0.72	0.80	0.67

Key takeaway:
Feature selection significantly improved model performance, especially for the Neural Network.

🔎 Confusion Matrix Insights (Test Data)
Decision Tree (Top 5 Features)

Very high recall for the positive class (0.94)

Very low recall for the negative class (0.20)

Aggressive prediction strategy with many false positives

Useful when maximizing positive detection is the priority

Neural Network (Top 5 Features)

Strong recall for the positive class (0.90)

Much better balance across classes

Fewer false positives and stronger true negative performance

Most stable and generalizable model overall

🧠 Final Interpretation

The Neural Network using the top 5 features achieved the highest test accuracy and best balance between precision and recall.

The Decision Tree using the top 5 features prioritized recall at the expense of negative-class performance.

Model selection depends on the goal:

Balanced classification → Neural Network

Maximum sensitivity to positives → Decision Tree

All conclusions are based strictly on test-set performance, not training results.

🧰 Tools & Libraries

Python

Data: pandas, numpy

Visualization: matplotlib, seaborn

Machine Learning: scikit-learn
