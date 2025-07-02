# 🧠 Employee Attrition Prediction

## 📌 Project Overview

This project focuses on predicting **employee attrition** using machine learning models. Employee attrition refers to the gradual reduction of a workforce due to resignations, retirements, or other factors. High attrition rates can significantly affect organizational productivity and increase costs associated with hiring and training new staff.

The goal is to identify patterns and build a predictive model to **anticipate which employees are at risk of leaving**, enabling HR departments to take proactive retention strategies.

## 🎯 Objectives

- Analyze employee data to discover key factors contributing to attrition.
- Build a machine learning model that can predict whether an employee is likely to leave.
- Deploy the model using **Streamlit** to create an interactive web application.
- Allow HR professionals to input employee data and receive real-time attrition risk predictions.

--------------------------------------------------------------------------------------------------------------------------------------------

## 🛠️ Tools & Technologies Used

| Tool/Library           | Purpose                                   |
|------------------------|-------------------------------------------|
| **Python**             | Core programming language                 |
| **Pandas**             | Data manipulation and preprocessing       |
| **NumPy**              | Numerical operations                      |
| **Matplotlib/Seaborn** | Data visualization                        |
| **Scikit-learn**       | Machine learning algorithms and evaluation|
| **Streamlit**          | Web app framework for model deployment    |
| **Pickle**             | Save/load machine learning models         |

----------------------------------------------------------------------------------------------------------------------------------------------------

## 🧠 Machine Learning Model

- **Model Used:** 1.Random Forest Classifier
                  2.Logestic regression
- **Target Variable:** `Attrition` (Yes/No)
- **Important Features:**
  - Age
  - Monthly Income
  - Distance from Home
  - Years at Company
  - Years in Current Role
  - Total Working Years
  - Job Role
  - OverTime
- **Encoding:** One-hot encoding was used for categorical variables.
- **Scaling:** StandardScaler for numerical feature scaling.
- **Tuning:** Tuned  the model using Grid search cv and XG boosting.

⚠️ Dataset Limitation – Class Imbalance
🎯 Problem
One of the major challenges in this project is the severe class imbalance in the target variable Attrition. The dataset contains far more instances of employees who did not leave (Attrition = No) compared to those who did leave (Attrition = Yes).

Typical distribution:

Attrition = No  → 84%
Attrition = Yes → 16%
This imbalance can lead to:

❌ Misleading high accuracy (predicting "No" for all gets 84% accuracy)

❌ Poor recall and precision for the minority class

❌ Model bias toward the majority class (non-attrition)

✅ Solution Applied
To handle this issue, we used oversampling techniques:

SMOTE (Synthetic Minority Over-sampling Technique)
Creates synthetic samples for the minority class to balance the dataset.

RandomOverSampler
Duplicates existing samples of the minority class.

These techniques help the model learn from both classes effectively and improve performance on identifying employees who are likely to leave.
------------------------------------------------------------------------------------------------------------------------------------------------

## ⚙️ Streamlit Application

The Streamlit app provides an intuitive UI where HR users can:

- Input employee attributes (age, income, job role, etc.)
- Click a **“Predict Attrition”** button
- View prediction results with probability and alert messages
