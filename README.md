<p align="center">

![Python](https://img.shields.io/badge/Python-3.11-blue)
![XGBoost](https://img.shields.io/badge/XGBoost-Regressor-green)
![Streamlit](https://img.shields.io/badge/Streamlit-Deployed-red)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

</p>

# EstateIQ

EstateIQ is an end-to-end machine learning application that estimates residential property prices using the Ames Housing dataset. The project demonstrates the complete machine learning lifecycle, including exploratory data analysis, data preprocessing, feature engineering, model development, hyperparameter optimization, and deployment through a Streamlit web application.


**Try the application:**: [https://estateiq.streamlit.app ](https://estateiq.streamlit.app/ )

---

## Overview

EstateIQ predicts residential property prices based on key property characteristics such as living area, construction quality, garage capacity, bathroom count, and house age.

The project follows a complete machine learning workflow:

* Data Cleaning and Preprocessing
* Missing Value Handling
* Exploratory Data Analysis (EDA)
* Feature Engineering
* Categorical Encoding
* Model Training and Evaluation
* Hyperparameter Optimization
* Model Deployment

---

## Dataset

Dataset: Ames Housing Dataset

Location: Ames, Iowa, United States

The dataset contains detailed information about residential properties and their sale prices, making it a widely used benchmark for regression and predictive modeling tasks.

Target Variable:

* SalePrice – Final sale price of the property

---

## Exploratory Data Analysis

The dataset was analyzed to identify:

* Missing values
* Outliers
* Feature distributions
* Correlations with SalePrice
* Relationships between key housing characteristics and property values

---

## Data Preprocessing

### Missing Value Handling

Different imputation strategies were applied based on feature type:

* Median Imputation for numerical variables
* Mode Imputation for categorical variables
* "None" category assignment where missing values represented the absence of a feature

### Feature Engineering

The following features were created to improve predictive performance:

| Feature           | Description                   |
| ----------------- | ----------------------------- |
| TotalSF           | Total property square footage |
| HouseAge          | Property age at time of sale  |
| YearsSinceRemodel | Time since last remodel       |
| TotalBathrooms    | Combined bathroom count       |
| TotalPorchSF      | Total porch area              |

### Encoding

Categorical variables were transformed using One-Hot Encoding to make them suitable for machine learning algorithms.

---

## Model Development

The following regression models were evaluated:

| Model                   |
| ----------------------- |
| Linear Regression       |
| Random Forest Regressor |
| XGBoost Regressor       |

Evaluation metrics:

* Root Mean Squared Error (RMSE)
* Mean Absolute Error (MAE)
* R² Score
* Cross Validation

---

## Hyperparameter Optimization

The final XGBoost model was optimized using RandomizedSearchCV.

Best Parameters:

```python
{
    'subsample': 0.7,
    'n_estimators': 1000,
    'max_depth': 4,
    'learning_rate': 0.01,
    'colsample_bytree': 0.7
}
```

---

## Results

### Validation Performance

| Metric   |  Score |
| -------- | -----: |
| RMSE     | 0.1019 |
| MAE      | 0.0720 |
| R² Score | 0.9291 |

The tuned XGBoost model delivered the strongest overall performance and was selected as the final model.

---

## Deployment

EstateIQ is deployed as an interactive Streamlit application that allows users to estimate residential property values based on key housing characteristics.

User Inputs:

* Overall Quality
* Total Square Footage
* Garage Capacity
* Total Bathrooms
* Living Area
* House Age
* Number of Fireplaces

Application Output:

* Estimated Property Value
* Estimated Price Range

---

## Project Structure

```text
EstateIQ/
│
├── app.py
├── requirements.txt
├── README.md
│
├── models/
│   └── deploy_model.pkl
│
├── notebooks/
│   ├── house_price_prediction.ipynb
│   └── final_model_submission.ipynb
│
│
└── data/
```

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Streamlit
* Joblib
* Matplotlib
* Seaborn

---

## Disclaimer

Predictions are generated using a machine learning model trained on historical housing data and are intended for educational and informational purposes only. Actual property values may vary based on market conditions and property characteristics not captured by the model.
