# 🏗️ Bulldozer Price Prediction — End-to-End Machine Learning Project

## 🚜 Overview

How do you accurately estimate the value of heavy equipment at auction?

In this project, I built a machine learning model to predict the **sale price of bulldozers** using historical auction data — effectively creating a **data-driven “blue book” valuation system**.

This project simulates a real-world ML workflow:
- Handling messy, real-world data  
- Engineering meaningful features  
- Iterating through models and tuning  
- Evaluating performance using proper metrics  

---

## 🎯 Problem Statement

Auction prices for heavy equipment can vary significantly based on:
- Machine specifications  
- Usage and configuration  
- Market conditions over time  

The objective is to build a model that can **accurately predict the SalePrice**, enabling:
- Better pricing decisions  
- Reduced uncertainty in auctions  
- Data-driven valuation systems  

---

## 📊 Dataset

The dataset is split into three time-based sets:

- **Train Set** → Data up to 2011  
- **Validation Set** → Jan 2012 – April 2012  
- **Test Set** → May 2012 – Nov 2012  

This structure mimics real-world forecasting, where models are trained on past data and evaluated on future data.

> ⚠️ Due to size limitations, the dataset is not included in this repository.

👉 Download here:  
https://www.kaggle.com/competitions/bluebook-for-bulldozers/data  

---

## ⚙️ Machine Learning Workflow

### 🧹 Data Preprocessing
- Converted `saledate` to datetime format  
- Extracted time-based features:
  - Year, Month, Day, Day of Week  
- Handled missing values:
  - Numerical → median imputation  
  - Categorical → encoded as numerical values  

---

### 🧠 Feature Engineering
- Created time-based features from sale date  
- Leveraged machine attributes and configuration data  
- Improved model performance through iterative feature refinement  

---

### 🌲 Model Used

**RandomForestRegressor**

Why?
- Handles non-linear relationships well  
- Works great with structured/tabular data  
- Robust to noise and missing values  

---

## 📈 Results

| Metric | Training | Validation |
|------|--------|-----------|
| MAE | 2953.82 | 5951.25 |
| RMSLE | 0.1447 | 0.2452 |
| R² | 0.9588 | 0.8818 |

---

## 🔁 Iteration Journey (What Actually Happened)

This project wasn’t a straight line — and that’s where the real learning happened.

| Stage | Validation RMSLE |
|------|----------------|
| Baseline Model | 0.2936 |
| First Tuning Attempt | 0.5638 ❌ |
| Final Optimized Model | **0.2452 ✅** |

### 💡 Key Takeaway:
Better hyperparameters don’t guarantee better performance — experimentation does.

---

## 🔧 Hyperparameter Tuning

Used **RandomizedSearchCV (100 iterations)** to explore the parameter space.

**Best parameters:**
```python
n_estimators=40
min_samples_leaf=1
min_samples_split=14
max_features=0.5


💡 Key Insights
Feature engineering had the biggest impact on performance
Poor tuning can significantly degrade model accuracy
Time-based splits are crucial for realistic evaluation
Iteration and experimentation are core ML skills


🚀 Future Improvements
Apply log transformation to improve RMSLE
Experiment with LightGBM / XGBoost
Build a deployment-ready app (Streamlit)
Add feature importance visualization

📁 Project Structure
bulldozer-price-prediction/
│
├── notebook.ipynb
├── README.md
├── .gitignore
└── requirements.txt

🧑‍💻 Author
Toby Chuks
GitHub: https://github.com/tobychuks01
LinkedIn: https://www.linkedin.com/in/toby-chuks-630b44217

⭐ Final Note
This project reflects more than just building a model —
it demonstrates the importance of iteration, experimentation, and learning from failure in machine learning.

---

