# Breast Cancer Diagnosis — Machine Learning Classification

##  Project Overview

This project applies and compares different **Machine Learning classification algorithms** for breast cancer diagnosis using the **Breast Cancer Wisconsin (Diagnostic)** dataset.

The main goal is to understand how different classification algorithms and ensemble techniques perform on the same dataset, with special attention to **Malignant Recall**, since missing a malignant case is particularly important in a medical diagnosis problem.

---

##  Dataset

The dataset is the **Breast Cancer Wisconsin (Diagnostic)** dataset available through `scikit-learn`.

* **Samples:** 569
* **Features:** 30 numerical features
* **Classes:** 2
* **Missing Values:** None

### Target Classes

| Target | Class     |
| ------ | --------- |
| 0      | Malignant |
| 1      | Benign    |

The dataset contains features describing characteristics of cell nuclei extracted from breast mass images, such as:

* Radius
* Texture
* Perimeter
* Area
* Smoothness
* Compactness
* Concavity
* Symmetry
* Fractal Dimension

---

##  Data Preparation

The following steps were performed:

1. Loaded the dataset using `scikit-learn`.
2. Performed basic exploratory data analysis.
3. Checked for missing values.
4. Examined feature distributions and class differences.
5. Detected potential outliers using the IQR method.
6. Outliers were **not removed**, since extreme values in medical data may represent real disease cases.
7. Split the data into training and testing sets using stratification.
8. Applied `StandardScaler` for algorithms that depend on feature scale.

### Train/Test Split

* Training set: **455 samples**
* Testing set: **114 samples**
* Test size: **20%**
* `random_state = 42`
* Stratified by target class

---

##  Classification Algorithms

The following classification algorithms were implemented and compared:

* Logistic Regression
* Support Vector Machine (SVM)
* Decision Tree
* Random Forest
* Naive Bayes
* K-Nearest Neighbors (KNN)

---

##  Ensemble Learning

Four ensemble learning techniques were also implemented:

### Voting

Soft Voting was used with:

* Logistic Regression
* SVM
* KNN

### Bagging

Bagging was applied using **Decision Trees** as the base estimator.

### Boosting

`GradientBoostingClassifier` was used as the boosting algorithm.

### Stacking

Stacking was implemented using:

* Logistic Regression
* SVM
* KNN

with Logistic Regression as the final estimator.

---

##  Results

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score

Because this is a medical classification problem, **Malignant Recall** was given special attention.

### Individual Models

| Model               |   Accuracy | Malignant Recall |
| ------------------- | ---------: | ---------------: |
| Logistic Regression | **98.25%** |       **97.62%** |
| SVM                 | **98.25%** |       **97.62%** |
| KNN                 |     95.61% |           93.00% |
| Random Forest       |     95.61% |           93.00% |
| Decision Tree       |     91.23% |           93.00% |
| Naive Bayes         |     92.98% |           90.00% |

### Ensemble Models

| Technique |   Accuracy | Malignant Recall |
| --------- | ---------: | ---------------: |
| Voting    | **98.25%** |       **97.62%** |
| Stacking  | **98.25%** |       **97.62%** |
| Boosting  |     95.61% |           90.00% |
| Bagging   |     94.74% |           93.00% |

---

##  Results Summary

The best performance on the test set was achieved by:

* Logistic Regression
* SVM
* Voting
* Stacking

All four achieved:

**98.25% Accuracy**
**97.62% Malignant Recall**

The ensemble methods did not improve the performance beyond the best individual models, showing that increasing model complexity does not necessarily lead to better results on this dataset.

---

##  Key Concepts Applied

This project was used to practice and compare important Machine Learning concepts:

* Exploratory Data Analysis
* Train/Test Split
* Stratified Sampling
* Feature Scaling
* Outlier Detection
* Logistic Regression
* SVM
* Decision Trees
* Random Forest
* Naive Bayes
* KNN
* Voting
* Bagging
* Boosting
* Stacking
* Classification Metrics
* Confusion Matrix
* Malignant Recall

---

##  Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## Author

**Karim Kesba**

AI / Machine Learning Developer
