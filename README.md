# Predict Bike Sharing Demand 🧮🚲

## 📘 Overview
This repository presents a machine learning pipeline using **AutoGluon** to forecast bike-sharing demand based on the Kaggle **‘Bike Sharing Demand’** dataset.  
Originally developed as a project for **Udacity’s AWS AIML Advanced Cohort Scholarship Machine Learning course**, it includes feature engineering, model training & tuning, and performance analysis.

---

## 📂 Contents
- **Jupyter Notebook** – `bike-sharing-demand-project-notebook.ipynb`: Complete data pipeline from loading to model evaluation.  
- **HTML Snapshot** – `bike-sharing-demand-report.html`: Exported version of the notebook for easy viewing.  
- **Report** – `project_report.md`: Narrative of methodology, results, and improvements.  
- **Training & Test Metrics** – `model_training_score.png`, `model_test_score.png`: Visualizations comparing model performance.  

---

## ✅ Key Features
- Utilizes **AutoGluon TabularPredictor** for automated model selection and ensembling.  
- Comprehensive **feature engineering**, including date/time extraction and weather integration.  
- **Iterative improvements**: added features and tuned hyperparameters to boost leaderboard ranking.  
- Includes both **code and markdown report** detailing methodology and results.  

---

## 🛠️ Setup & Dependencies
- Python (3.7+ recommended)  
- AutoGluon (v0.2.0)  
- MXNet  
- pandas (v1.2.4+)  
- Jupyter Notebook  

---

## 🚀 How to Run

1. **Clone the repo**:
   ```bash
   git clone https://github.com/kratzburste14/Predict-Bike-Sharing-Demand.git
2. **Install dependencies**:
   ```bash
   pip install autogluon mxnet pandas jupyter
3. **Open and run the notebook**:
   ```bash
   jupyter notebook bike-sharing-demand-project-notebook.ipynb
  
## 📈 Results & Insights
Visual metrics (model_training_score.png, model_test_score.png) show how model accuracy evolved across iterations.
Detailed discussions are available in project_report.md.


