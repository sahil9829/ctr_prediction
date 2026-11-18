# 🖱️ Click-Through Rate (CTR) Prediction using Machine Learning and Graph Attention Networks (GAT)

This project focuses on predicting **Click-Through Rate (CTR)** using machine learning models and **Explainable AI (XAI)** techniques. The Avazu dataset from Kaggle was utilized to train and evaluate multiple models, including traditional classifiers and advanced deep learning approaches such as **Graph Attention Networks (GAT)**.

---

## 📂 Project Overview

Click-Through Rate prediction is a critical task in **digital advertising**, helping optimize ad placement and improve marketing strategies.  
In this project, we:
- Performed **Exploratory Data Analysis (EDA)** on the Avazu dataset.
- Preprocessed the data (SMOTE balancing, Target Encoding, MinMax Scaling).
- Developed and evaluated several models:
  - Logistic Regression  
  - Gaussian Naïve Bayes (GNB)  
  - Histogram-based Gradient Boosting (HistGBM)  
  - Graph Attention Network (GAT)
- Applied **Explainable AI (XAI)** techniques using SHAP for model interpretability.

---

## 📊 Dataset
We used the **[Avazu CTR Dataset](https://www.kaggle.com/c/avazu-ctr-prediction/data)** from Kaggle, which contains over **40 million records** of mobile ad interactions with features such as:
- **Context features:** Hour, Day of week, Banner position, etc.
- **Device & app features:** Device ID, IP, App ID, Site category, etc.
- **Target variable (`click`)**: Binary label (1 = clicked, 0 = not clicked).

Due to memory constraints, the dataset was sampled for efficient modeling.

---

## 🔧 Preprocessing Steps
1. **Exploratory Data Analysis (EDA)**  
   - Explored feature distributions and categorical relationships.
   - Visualized correlations among features.

2. **Handling Imbalance (SMOTE):**  
   - Applied Synthetic Minority Oversampling Technique (SMOTE) to balance click vs. no-click classes.

3. **Encoding Categorical Features:**  
   - Used **Target Encoding** to handle high-cardinality categorical variables.

4. **Feature Scaling:**  
   - Applied **MinMaxScaler** to normalize numerical features between 0 and 1.

---

## 🧠 Models and Results

### 1️⃣ Logistic Regression
- **Cross-Validation Accuracy:** `0.9028 ± 0.0010`  
- **ROC-AUC Score:** `0.9630`  

---

### 2️⃣ Gaussian Naïve Bayes (GNB)
- **Cross-Validation Accuracy:** `0.8589 ± 0.0016`  
- **ROC-AUC Score:** `0.9057`  

---

### 3️⃣ Histogram-based Gradient Boosting (HistGBM)
- **Cross-Validation Accuracy:** `0.9493 ± 0.0006`  
- **ROC-AUC Score:** `0.9928`  

---

### 4️⃣ Graph Attention Network (GAT)
- **Accuracy:** `0.90`  
- **ROC-AUC Score:** `0.9631`  
- *Note: measured on the training graph (664,123 nodes), not a held-out test set.*

---

## 🔍 Explainable AI (XAI)
- **SHAP** was applied to the HistGBM model to understand feature contributions.
- Insights revealed that features like **device_id counts**, **hour of day**, and **app category** significantly influenced CTR predictions.
