# Heart Disease Prediction using Data Mining

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Scikit-Learn](https://img.shields.io/badge/sklearn-0.24+-orange.svg)](https://scikit-learn.org/)

One of the leading causes of death worldwide is heart disease. Early recognition is crucial for timely medical interventions and preventing fatal outcomes. This project leverages supervised machine learning and data mining techniques to predict the presence of heart disease using patient clinical indicators. 

By framing this as a binary classification task, we analyze and compare models to provide a reliable, data-driven decision support tool for early healthcare screening.

---

## 📊 Dataset Summary

The project utilizes the **Cleveland subset of the UCI Heart Disease dataset** from the UCI Machine Learning Repository.

* **Sample Size:** 303 patients
* **Attributes:** 14 clinical features (including age, sex, cholesterol levels, thallium stress test results, resting blood pressure, and maximum heart rate).
* **Target Variable:** Converted into a binary format:
    * `1`: Presence of heart disease
    * `0`: Absence of heart disease

### Data Preprocessing
* **Missing Values:** Handled hidden missing values encoded as `?` using **median imputation** to preserve patient records.
* **Feature Scaling:** Applied standard scaling to ensure all clinical variables contribute equally to model performance.

---

## ⚙️ Methodology

We implemented and compared two primary classification models using **stratified sampling** for the train-test split:

1.  **Logistic Regression:** Used as the primary model due to its high interpretability and widespread adoption in healthcare research.
2.  **Decision Tree Classifier:** Used as a baseline comparison model to explore potential non-linear relationships within the clinical data.
3.  **Baseline Dummy Classifier:** Always predicts the most common class to validate that the ML models extract meaningful insights.

---

## 📈 Results & Evaluation

The models were evaluated based on Accuracy, Precision, F1-Score, and **Recall** (the priority metric to minimize false negatives in clinical diagnostics).

| Model | Accuracy | Precision | Recall (Sensitivity) | F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| **Baseline Model** | 54.1% | — | — | — |
| **Decision Tree** | 78.6% | — | — | — |
| **Logistic Regression** | **86.8%** | **81.2%** | **92.8%** | **86.6%** |

### Key Takeaways
* **Logistic Regression** significantly outperformed the Decision Tree and the baseline model, demonstrating that clinical indicators share a strong, highly predictive relationship with the target.
* The **92.8% Recall** achieved by Logistic Regression ensures that the vast majority of high-risk patients are correctly identified for further screening.

---

## 📋 Conclusions & Recommendations

* **Clinical Integration:** Interpretable models like Logistic Regression should be integrated into early screening workflows as clinical decision support tools.
* **Future Scope:** Because the dataset originates from a single population and is relatively small (303 records), future work should focus on testing these models against larger, more diverse datasets and exploring advanced hyperparameter tuning.

---

## 📂 Project Structure

```text
├── data/
│   └── heart_cleveland.csv       # Dataset subset from UCI Repository
├── notebooks/
│   └── heart_disease_eda_ml.ipynb # Data cleaning, EDA, and ML Modeling
├── README.md                     # Project documentation
