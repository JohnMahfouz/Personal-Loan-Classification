# 🏦 Personal Bank Loan Classification

This project is a **machine learning pipeline** for classifying whether a customer is likely to accept a personal bank loan offer. It includes **Exploratory Data Analysis (EDA)**, **data preprocessing**, **model training**, and **evaluation** using multiple classification algorithms.

---

## 📁 Dataset

The dataset used is an Excel file: `Personal Bank Loan Classification.xlsx`, containing customer information such as:

- Age
- Experience
- Income
- Family size
- CCAvg (Credit Card Average)
- Mortgage
- Personal Loan (Target variable: 1 = Accepted, 0 = Not Accepted)

The columns `ID` and `ZIP Code` are dropped as they are not useful for prediction.

---

## 🔍 Exploratory Data Analysis (EDA)

- Checked for missing values.
- Removed unnecessary columns (`ID`, `ZIP Code`).
- Visualized numeric features using boxplots to detect outliers.
- Analyzed feature correlation with a heatmap.
- Displayed sample records and dataset statistics.

---

## 🛠️ Models Used

The following machine learning models were trained and evaluated:

| Model                     | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **Decision Tree**         | Built using varying tree depths to examine overfitting/underfitting        |
| **Logistic Regression**   | Trained on standardized features                                            |
| **K-Nearest Neighbors**   | Trained with `k=3`, using scaled features                                   |
| **Polynomial Regression** | Linear Regression on polynomial-transformed features + output rounding     |

> ✅ Accuracy of each model is recorded and compared in a final accuracy table.

---

## 📊 Model Evaluation

Each model was evaluated using the following metrics:

- **Accuracy Score**
- **Confusion Matrix**
- **Classification Report (Precision, Recall, F1-score)**

---

## 🌲 Decision Tree Depth Tuning

A decision tree classifier was trained using different `max_depth` values from 1 to 15. Accuracy was recorded for both:

- Training set
- Validation set (10% of training data)

A plot was generated to visualize model complexity and help choose the optimal depth that avoids both underfitting and overfitting.

---

## 🧪 Polynomial Regression for Classification

Polynomial features of degree 2 were generated to transform the input space into a higher-dimensional space. A **Linear Regression** model was trained, and the continuous predictions were rounded to the nearest class (0 or 1). While this is not standard, it provides a creative workaround to simulate classification using regression.

---

## 📈 Accuracy Table

A summary of the performance of all models:

| Model                    | Accuracy      |
|-------------------------|---------------|
| Decision Tree           | (based on best validation score) |
| Polynomial Regression   | (rounded predictions accuracy)   |
| K-Nearest Neighbors     | (with k=3)                        |

---

## ▶️ How to Run the Code

1. Make sure you have Python installed (version 3.7 or above).
2. Install the required libraries using pip:

   ```bash
   pip install pandas numpy matplotlib seaborn openpyxl scikit-learn
