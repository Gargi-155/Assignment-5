# Employee Attrition Prediction using Decision Tree and Random Forest

**Author:** Gargi


**Registration Number:** 23BCE11333


**Application Number:** IN26011023


**Batch Number:** 2B


**Email ID:** [gargi.23bce11333@vitbhopal.ac.in](mailto:gargi.23bce11333@vitbhopal.ac.in)

---

## Objective

The objective of this project is to build and compare **Decision Tree** and **Random Forest** classification models to predict employee attrition using demographic, compensation, and job-related attributes. The project aims to identify the factors influencing employee turnover and evaluate which machine learning algorithm provides better predictive performance.

---

## Dataset Link

* **Kaggle:** IBM HR Analytics Employee Attrition & Performance Dataset
  https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset

---

## Libraries Used

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* kaggle

---

## Methodology

### 1. Data Understanding

* Loaded the IBM HR Analytics Employee Attrition dataset.
* Explored numerical and categorical features.
* Identified **Attrition** as the binary target variable.

### 2. Data Preprocessing

* Verified that the dataset contained no missing values.
* Removed non-informative and constant columns:

  * EmployeeCount
  * EmployeeNumber
  * Over18
  * StandardHours
* Encoded the target variable:

  * Yes → 1
  * No → 0
* Applied one-hot encoding to categorical features using `pd.get_dummies()`.
* Split the dataset into **80% training** and **20% testing** sets using stratified sampling to preserve class distribution.

### 3. Model Development

Two classification models were trained:

* **Decision Tree Classifier**
* **Random Forest Classifier** with **100 estimators**

### 4. Model Evaluation

Both models were evaluated using the following performance metrics:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Feature Importance Analysis

---

## Results

| Metric        | Decision Tree | Random Forest |
| ------------- | ------------: | ------------: |
| **Accuracy**  |        76.53% |    **83.33%** |
| **Precision** |        31.03% |    **41.67%** |
| **Recall**    |    **38.30%** |        10.64% |
| **F1-Score**  |    **34.29%** |        16.95% |

---

## Model Comparison

### Decision Tree

* Achieved better recall, successfully identifying a higher proportion of employees likely to leave the organization.
* Easier to interpret due to its tree-based structure.
* More susceptible to overfitting compared to ensemble methods.

### Random Forest

* Achieved the highest overall accuracy and precision.
* Reduced overfitting by combining predictions from multiple decision trees.
* Produced fewer false positive predictions.
* Lower recall indicated difficulty in detecting the minority attrition class because of class imbalance.

---

## Feature Importance

The Random Forest model identified the following features as the most influential in predicting employee attrition:

* MonthlyIncome
* Age
* TotalWorkingYears

These variables contributed the most to the model's decision-making process and play a significant role in employee retention analysis.

---

## Conclusion

This project demonstrates that the **Random Forest Classifier** provides better overall predictive performance than a single **Decision Tree**, achieving higher accuracy and precision through ensemble learning. However, the Decision Tree achieved a higher recall, making it more effective at identifying employees who are likely to leave.

The relatively low recall of the Random Forest model highlights the impact of class imbalance within the dataset. Future improvements can be made by applying techniques such as **SMOTE (Synthetic Minority Oversampling Technique)**, **class weighting**, or **hyperparameter tuning** to improve minority class prediction while maintaining strong overall performance.

Overall, this project illustrates how machine learning can assist organizations in proactively identifying employee attrition risks and supporting data-driven human resource management.
