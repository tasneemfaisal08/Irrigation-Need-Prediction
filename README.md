# Irrigation-Need-Prediction
This project is part of a Kaggle Playground competition focused on predicting irrigation needs using environmental and soil data.

# 🌱 Irrigation Need Prediction using Deep Neural Network 

## 📌 Description

This project is part of a Kaggle Playground competition focused on predicting irrigation needs using environmental and soil data.

---

## 📖 Overview

The objective of this project is to build a robust deep neural network that predicts irrigation requirements (Low, Medium, High) based on environmental conditions, soil characteristics, and agricultural factors.

This helps improve water efficiency and supports smart agriculture systems.

---

## 🎯 Problem Statement

Traditional irrigation methods rely on fixed schedules, which often result in:

* Water overuse or shortage
* Reduced crop productivity
* Inefficient resource utilization

This project addresses these challenges use data-driven predictions.

---

## 📊 Dataset Features

The dataset contains a mix of categorical and numerical features, including:

* Soil_Type, Crop_Type, Crop_Growth_Stage
* Soil_Moisture, Soil_pH, Organic_Carbon
* Temperature_C, Rainfall_mm, Humidity
* Wind_Speed_kmh, Sunlight_Hours
* Irrigation_Type, Water_Source, Region

🎯 Target Variable:

* Irrigation_Need → (Low, Medium, High)

---

## 🧠 Approach

### 🔹 Data Preprocessing

* Removed duplicates and unnecessary columns ( `id`)
* Handled categorical & numerical features using:

  * OneHotEncoder (categorical)
  * StandardScaler (numerical)
* Built preprocessing pipeline using `ColumnTransformer`

---

### 🔹 Exploratory Data Analysis (EDA)

* Count plots for categorical features vs target
* Boxplots for numerical features
* Correlation heatmap
* Class distribution visualization

---

### 🔹 Feature Engineering

Created advanced features such as:

* Temp_Humidity = Temperature × Humidity
* Soil_Temp_Ratio = Soil Moisture / Temperature
* Rain_Temp_Interaction = Rainfall × Temperature
* Wind_Humidity_Interaction

Transformations:

* Log transformation → Soil Moisture
* Square root → Rainfall
* Polynomial features → Temperature², Moisture²

Binary Features:

* Soil_Moisture < 25
* Temperature > 30
* Rainfall < 400
* Humidity < 40

Custom Feature:

* Grouped Crop Growth Stage into categories

---

### 🔹 Handling Imbalance

* Used `compute_class_weight` to balance target classes

---

### 🔹 Model Architecture

A Deep Neural Network built use TensorFlow/Keras:

* Dense Layers: 256 → 128 → 64 → 64 → 32
* Activation: ReLU
* Regularization: L2
* Output Layer: Softmax (3 classes)

---

### 🔹 Training Strategy

* Stratified K-Fold Cross Validation (5 folds)
* Early Stopping to prevent overfitting
* Optimizer: Adam (learning rate = 0.0005)
* Loss: Sparse Categorical Crossentropy

---

### 🔹 Evaluation

* Accuracy per fold
* Mean Cross-Validation Accuracy

---

## 📈 Results

* Model trained using 5-Fold Cross Validation
* Achieved stable performance across folds
* Final predictions generated using averaging (ensemble across folds)

---

## 🛠️ Tech Stack

* Python 🐍
* Pandas & NumPy
* Scikit-learn
* TensorFlow / Keras
* Matplotlib & Seaborn

---

## 📂 Project Structure

```
Irrigation-Need-Prediction/
│
├── notebook.ipynb
├── README.md
├── requirements.txt
```

---

## ▶️ How to Run

```bash
git clone https://github.com/your-username/Irrigation-Need-Prediction.git
cd Irrigation-Need-Prediction
pip install -r requirements.txt
```

Then open:

```
notebook.ipynb
```

---

## 📤 Submission

* Predictions generated using K-Fold ensemble
* Output file:

```
submission_kfold.csv
```

---

## 📬 Author

**Tasneem Faisal**
Data Scientist | AI Engineer
