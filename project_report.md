# 🚲 Bike Sharing Demand Prediction with AutoGluon

This project leverages AutoGluon's Tabular Prediction capabilities to forecast daily bike rental counts based on historical data and environmental factors. It was developed as part of a Udacity ML Nanodegree project.

## 📂 Project Overview

The goal of this project is to predict the `count` of total bike rentals per hour using various features such as date-time, weather, temperature, and humidity. The dataset is provided by [Kaggle's Bike Sharing Demand competition](https://www.kaggle.com/c/bike-sharing-demand).

## 📊 Dataset

- **Features**:
  - Date and time
  - Temperature (`temp`, `atemp`)
  - Humidity
  - Weather conditions
  - Binary indicators (holiday, working day)
- **Target**:
  - `count`: Total number of bikes rented
- **Dropped**:
  - `casual` and `registered` columns were excluded as they are not present in the test data.

## 🧰 Tools and Libraries

- **Primary Framework**: [AutoGluon Tabular](https://auto.gluon.ai/)
- **Language**: Python
- **Environment**: Amazon SageMaker Notebook / Jupyter Notebook

## 🔧 Data Preprocessing

- Converted boolean features from categorical inputs
- Applied AutoGluon's built-in feature generators:
  - `AsTypeFeatureGenerator`
  - `FillNaFeatureGenerator`
  - `DatetimeFeatureGenerator` (extracted year, month, day, day of week)
- Final feature set increased to 13 from the original 9

## 🚀 Model Training

- **Framework**: AutoGluon `TabularPredictor`
- **Metric**: Root Mean Squared Error (RMSE)
- **Training Constraints**:
  - Time limit: 10 minutes (600 seconds)
  - Preset: `best_quality`
- **Stacking**: Used multi-level ensemble learning (stacking and bagging)

## 🏆 Best Models

| Rank | Model Name             | RMSE   |
|------|------------------------|--------|
| 🥇   | WeightedEnsemble_L3    | 33.94  |
| 🥈   | CatBoost_BAG_L2        | 34.27  |
| 🥉   | LightGBM_BAG_L2        | 34.62  |

AutoGluon automatically evaluated dozens of base models including LightGBM, CatBoost, Random Forest, KNN, and Neural Networks.

## 📈 Visualization

A line chart tracking validation RMSE across different training stages was generated and saved as `model_val_rmse_progression.png`.

## ✅ Conclusion

The ensemble model `WeightedEnsemble_L3` provided the most accurate predictions with the lowest RMSE. This indicates that ensemble techniques combining multiple model types can significantly boost performance for structured tabular data tasks.

## 🔮 Future Work

- Implement SHAP values or other explainability techniques for feature importance
- Integrate real-time prediction API
- Hyperparameter tuning beyond AutoGluon presets

## 📁 Files

- `bike-sharing-demand-report.html` – Final notebook export (code + outputs)
- `model_val_rmse_progression.png` – RMSE progression chart
