# Ventilator Pressure Prediction

This project aims to predict airway pressure in mechanically ventilated patients, enabling the optimization of ventilator settings to improve patient outcomes. By analyzing key respiratory variables, this model provides accurate pressure predictions, supporting data-driven decisions in respiratory care.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Models and Evaluation](#models-and-evaluation)
- [Results](#results)
- [Conclusion](#conclusion)
- [Contributors](#contributors)

## Overview
Ventilator pressure prediction is crucial in intensive care to ensure patients receive the optimal respiratory support. This project uses machine learning to predict airway pressure based on patient data, allowing for improved ventilation strategies and resource allocation in clinical settings.

## Dataset
The dataset contains 1,048,576 observations with the following variables:
- **id**: Unique identifier for each observation
- **breath_id**: Unique identifier for each breath within a single patient
- **R**: Airway resistance
- **C**: Respiratory compliance
- **time_step**: Time in seconds for each observation
- **u_in**: Airflow into the lungs during inspiration
- **u_out**: Airflow out of the lungs during expiration
- **pressure**: The target variable representing airway pressure

### Limitations
The dataset is from a single ventilator type and lacks certain clinical variables like blood gas measurements and patient demographics, which could further improve the prediction accuracy.

## Data Preprocessing
- **Data Integrity**: No null values, missing values, or duplicates were found.
- **Scaling and Transformation**: Features were scaled and transformed to ensure uniformity in model training.

## Exploratory Data Analysis
- **Correlation Analysis**: Analyzed the correlation between pressure and other variables.
- **Data Distribution**: Examined the distribution of the target variable, pressure, across different values of `u_in` and `u_out`.
- **Feature Relationships**: Visualized data point dispersion to understand the relationship between `u_in`, `u_out`, and pressure.

## Models and Evaluation
We experimented with multiple machine learning models, evaluating them on R-squared and Mean Absolute Percentage Error (MAPE) metrics:

1. **Linear Regression**: Simple model assuming a linear relationship.
2. **Random Forest Regressor**: An ensemble model creating multiple decision trees for more stable predictions.
3. **XGBoost Regressor**: Gradient boosting algorithm for handling complex data patterns.
4. **LightGBM**: Gradient boosting with optimized speed and accuracy.
5. **Support Vector Regressor (SVR)**: Non-linear model mapping data to a higher dimension.
6. **Multi-Layer Perceptron (MLP)**: Neural network model with multiple hidden layers.

### Evaluation Metrics
- **R-Squared Score**: Measures the proportion of variance in the target variable explained by the model.
- **MAPE Score**: Evaluates the average absolute percentage difference between predicted and actual values.

## Results
- **Best Model**: LightGBM achieved the highest R-squared value, indicating strong predictive power.
- **Most Accurate Model by MAPE**: SVR achieved the lowest MAPE, reducing error from 37.5% to 31.08%, indicating improved model accuracy.

## Conclusion
The LightGBM model outperformed other models based on R-squared, making it ideal for scenarios prioritizing variance explanation. For scenarios focused on accuracy, SVR proved optimal based on the MAPE metric.

## Contributors
- Manojkumar Yerraguntla
- Sai Narayana Murthy Dontukurti
- Sasank Reddy Chaganti

Thank you for reviewing our project!
