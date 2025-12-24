# 🚗 Vehicle Price Predictor

A machine learning–powered web application that predicts the **estimated price of a vehicle** based on its features such as year, mileage, make, model, fuel type, and more.  
The project uses a **Random Forest Regression model** with a full **scikit-learn pipeline** and a **Streamlit-based UI** for real-time predictions.

---

## 🔍 Project Overview

- **Problem Type:** Regression  
- **Goal:** Predict vehicle prices accurately using historical data  
- **Approach:** End-to-end ML pipeline (preprocessing → model → deployment)  
- **Deployment:** Streamlit Web Application  
- **Model Persistence:** `joblib`

---

## 🧠 Machine Learning Approach

### Model Used
- **Random Forest Regressor**
- Hyperparameter tuning using **RandomizedSearchCV**
- Cross-validation for better generalization

### Why Random Forest?
- Handles **non-linear relationships**
- Works well with **mixed numerical & categorical features**
- Robust against overfitting

---

## 🛠️ Data Preprocessing

### Numerical Features
- `year`
- `cylinders`
- `mileage`
- `doors`

**Steps:**
- Missing values → `SimpleImputer (mean)`
- Feature scaling → `StandardScaler`

### Categorical Features
- `name`, `make`, `model`
- `engine`, `fuel`, `transmission`
- `trim`, `body`
- `exterior_color`, `interior_color`, `drivetrain`

**Steps:**
- Missing values → `SimpleImputer (most_frequent)`
- Encoding → `OrdinalEncoder`
- Handles unseen categories safely

### Pipeline Design
All preprocessing and modeling steps are combined using:
- `Pipeline`
- `ColumnTransformer`

This ensures **clean training and inference consistency**.

---

## 📊 Model Evaluation Metrics

The model was evaluated on a held-out test set using:

- **Mean Squared Error (MSE)**
- **Mean Absolute Error (MAE)**
- **R² Score**

These metrics help measure prediction accuracy and error magnitude.

---

## 🧪 Training Workflow

1. Load and clean dataset
2. Remove outliers (price & mileage)
3. Define preprocessing pipelines
4. Train model with hyperparameter tuning
5. Evaluate on test data
6. Save trained model using `joblib`

---

## 💾 Model Saving

The final trained model (including preprocessing steps) is saved as:

vehicle_price_model.pkl

## ▶️ How to Run the Project

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/vehicle-price-predictor.git
cd vehicle-price-predictor
```

## Install Dependencies
```bash
pip install -r requirements.txt
```

Run the Streamlit App
```bash
streamlit run app.py
```