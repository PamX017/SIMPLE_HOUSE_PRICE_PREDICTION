# Activity 2: Simple House Price Prediction

**Course:** Machine Learning [ADPC509]  
**Department:** Artificial Intelligence & Data Science  
**Class:** T.Y. B.Tech (Semester V)  
**Academic Year:** 2026-27  
**Institution:** Zeal College of Engineering and Research, Pune  

---

## 📌 Project Overview
This project implements a **Simple Linear Regression** model to predict property values (`MEDV`) based on structural housing features using the **Boston Housing Dataset** (`HousingData.csv`). The goal is to perform dataset inspection, clean missing values using median imputation, fit an intuitive regression model, evaluate predictions using standard metrics (MAE, RMSE, $R^2$), and visualize actual vs. predicted values.

---

## 📊 Dataset Summary
* **Filename:** `HousingData.csv`
* **Total Records:** 506 rows
* **Total Features:** 14 attributes
* **Selected Input Feature ($X$):** `RM` (Average number of rooms per dwelling)
* **Target Variable ($y$):** `MEDV` (Median value of owner-occupied homes in $1,000s)

---

## 🛠️ Environment & Prerequisites
* **Python Version:** Python 3.8+
* **Required Libraries:**
  * `pandas`
  * `numpy`
  * `matplotlib`
  * `scikit-learn`

To install all dependencies, run:
```bash
pip install pandas numpy matplotlib scikit-learn
```

---

## 🚀 How to Run
1. Place `HousingData.csv` in the same directory as your Python script or notebook.
2. Execute the script or Google Colab/Jupyter Notebook.
3. Outputs including statistics, regression parameter equations, performance metrics, and plots will print directly to the console/output pane.

---

## 📈 Step-by-Step Implementation & Key Results

### 1. Data Cleaning
* Identified missing values across columns such as `CRIM`, `ZN`, `INDUS`, `CHAS`, `AGE`, and `LSTAT`.
* Applied median imputation (`df.fillna(df.median())`) to preserve all 506 records without introducing extreme outlier distortion.

### 2. Train-Test Split
* **Split Ratio:** 80% Training (404 samples) / 20% Testing (102 samples)
* **Random Seed:** `random_state=42`

### 3. Linear Regression Equation
* **Intercept ($b$):** `-36.2463`
* **Slope Coefficient ($m$):** `9.3483`
$$\text{MEDV (\$1,000s)} = -36.2463 + (9.3483 \times \text{RM})$$
* **Interpretation:** Each additional room increases the predicted house value by approximately **\$9,348.30**.

### 4. Model Evaluation Metrics
* **Mean Absolute Error (MAE):** \$3,132.80 (`3.1328` in \$1k units)
* **Root Mean Squared Error (RMSE):** \$4,750.70 (`4.7507` in \$1k units)
* **$R^2$ Score:** `0.4479` (The average number of rooms explains ~44.8% of the price variation)

### 5. Sample Prediction
* **Input Feature:** `RM = 6.5` rooms
* **Predicted Property Value:** **\$24,517.64** (`24.52` in \$1,000s)

---

## 💡 Key Conclusions & Limitations
1. **Linear Relationship:** `RM` shows a strong positive correlation with house value (`MEDV`), confirming that room count serves as a primary driver of home pricing.
2. **Model Limitation:** Single-variable regression offers high interpretability but omits non-linear trends and key regional factors (such as crime rate `CRIM` or pupil-teacher ratio `PTRATIO`). Multi-variable regression will yield better prediction accuracy.