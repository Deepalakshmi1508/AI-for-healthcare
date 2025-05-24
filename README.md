# AI-for-healthcare
# Carcinogenicity Prediction Using AI and JME Structure Drawing

## 📘 Project Overview

This project focuses on predicting the carcinogenicity of chemical compounds using AI models built on molecular descriptors. The workflow includes data preprocessing, descriptor generation, feature selection, machine learning model development, and deployment in a mobile application using JME structure drawing.

## 🧪 Dataset Description

* **Source:** Toxicology database
* **Features:** SMILES strings of chemical compounds
* **Labels:**

  * `1` → Carcinogenic
  * `0` → Non-Carcinogenic
* **Preprocessing:**

  * Removal of duplicate compounds
  * Standardization of SMILES strings

## 🧬 Molecular Descriptor Calculation

* **Tool Used:** Mordred (Python-based descriptor generator)
* **Steps:**

  * Conversion of SMILES to molecular descriptors
  * Filtering out non-numeric descriptors
  * Removal of descriptors with missing values

## 🧹 Feature Selection Techniques

Applied four methods to reduce descriptor dimensions:

1. **Variance Threshold:** Removes low-variance descriptors
2. **PCA (Principal Component Analysis):** Reduces features based on variance explained
3. **RFE (Recursive Feature Elimination):** Selects top descriptors recursively
4. **Autoencoder:** Neural network-based dimensionality reduction

## 🤖 Machine Learning Models

Each feature-selected dataset was tested with the following models:

* Support Vector Machine (SVM)
* Decision Tree
* Random Forest
* XGBoost

**Final Chosen Model:**

* **Random Forest**
* **Accuracy:** 79%
* Chosen for deployment due to its better generalization and interpretability.

## 📱 Mobile App Deployment

* **Platform:** Android
* **Feature:** JME Molecular Structure Drawing
* **Functionality:**

  * Users can draw a chemical structure
  * The app converts the structure to SMILES
  * Predicts whether the compound is carcinogenic or non-carcinogenic
* **Model Conversion:**

  * Trained Random Forest model converted to TensorFlow Lite format for integration into the app

## 📊 Evaluation Metrics

* Accuracy
* Confusion Matrix
* ROC-AUC Curve
* Precision, Recall, F1-score

## 📁 Project Structure

```
carcinogenicity-prediction/
│
├── data/                   # Raw and processed data
├── descriptors/            # Generated Mordred descriptors
├── models/                 # Trained model files (.pkl, .tflite)
├── notebooks/              # Jupyter notebooks for EDA and training
├── app/                    # Android application code
├── results/                # Evaluation metrics and visualizations
├── README.md               # Project documentation
└── requirements.txt        # Python dependencies
```

## 🛠️ Requirements

* Python ≥ 3.8
* pandas, numpy, scikit-learn, mordred, tensorflow, xgboost, matplotlib, seaborn

Install dependencies using:

```bash
pip install -r requirements.txt
```

## 📌 Future Work

* Improve accuracy > 80% using ensemble learning or deep learning
* Integrate more user-friendly UI/UX in the mobile app
* Extend prediction to include other toxicity endpoints


