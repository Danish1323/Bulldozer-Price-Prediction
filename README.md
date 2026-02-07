# Bulldozer Sale Price Prediction

This project focuses on predicting the sale price of bulldozers using machine learning. The goal is simple: given historical sales data and equipment characteristics, how accurately can we estimate what a bulldozer might sell for in the future?

This notebook follows a structured, end-to-end workflow — starting from understanding the problem and preparing the data, all the way to training a model and evaluating its performance.

---

## 📌 Project Overview

Predicting equipment prices is a real-world business problem. Auction companies, dealerships, and construction firms rely on accurate pricing to make informed buying and selling decisions.

In this project, I built a regression model trained on historical bulldozer sales data to forecast future prices. Because the dataset includes timestamps, this also becomes a **time-series flavored regression problem**, where respecting the chronological order of data is important.

The approach is inspired by practical industry workflows and draws ideas from the fast.ai machine learning methodology.

---

## 🎯 Problem Statement

> **How well can we predict the future sale price of a bulldozer given its characteristics and past sales data?**

Since the target variable is numeric (`SalePrice`), this is treated as a regression task.

---

## 📊 Dataset

The dataset comes from the **Kaggle Bluebook for Bulldozers** competition and includes detailed information about past sales.

**Data splits:**

* **Train.csv** – Historical sales data up to 2011 (~400k rows)
* **Valid.csv** – Sales from early 2012 used for validation
* **Test.csv** – Later 2012 data where prices must be predicted

Each record includes attributes such as:

* Model type
* Machine size
* Year of manufacture
* Drive system
* Location of sale
* Sale date
* And many other equipment-related features

---

## 📏 Evaluation Metric

The model is evaluated using **Root Mean Squared Log Error (RMSLE)**.

Why RMSLE?

* Penalizes large prediction errors
* Handles wide price ranges well
* Commonly used for price prediction problems

Lower RMSLE indicates better model performance.

---

## ⚙️ Project Workflow

### 1. Data Exploration

Started by inspecting the dataset structure, checking missing values, and understanding feature types.

### 2. Date Parsing & Time Features

Since sale timing plays a major role in price trends:

* Converted the `saledate` column into datetime format
* Extracted useful components like year and month
* Sorted the dataset chronologically

This helps prevent data leakage and keeps the training process realistic.

### 3. Data Cleaning & Preprocessing

* Handled missing values
* Converted categorical variables into numerical representations
* Created a working copy of the dataset before transformations

### 4. Feature Engineering

Additional date-based features improved the model’s ability to capture market patterns over time.

### 5. Model Training

A tree-based model (well suited for structured/tabular data) was trained on the prepared dataset to learn pricing patterns from historical examples.

### 6. Validation

Performance was measured using RMSLE to ensure the model generalizes well to unseen data.

---

## 🛠️ Tech Stack

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook

---

## 🚀 How to Run This Project

### Clone the repository

```bash
git clone https://github.com/your-username/bulldozer-price-prediction.git
cd bulldozer-price-prediction
```

### Install dependencies

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
```

### Launch the notebook

```bash
jupyter notebook Bulldozer_model.ipynb
```

---

## 📁 Project Structure

```
├── Bulldozer_model.ipynb   # Main project notebook
├── data/                  # Dataset files (not included if too large)
└── README.md
```

---

## 💡 Key Learnings

* Time-aware validation is critical when working with historical data.
* Feature engineering often matters more than model complexity.
* Tree-based models perform extremely well on structured datasets.
* A clear workflow makes debugging and improving models much easier.

---

## 🔮 Possible Improvements

* Try advanced boosting models like XGBoost or LightGBM
* Perform deeper hyperparameter tuning
* Build a small web app for live price predictions
* Track experiments for better reproducibility
* Explore model interpretability tools

---

## 🤝 Contributions

Suggestions and improvements are always welcome.
If you found this project useful, consider giving it a ⭐.

---

