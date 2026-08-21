# Explainable XGBoost Framework for Maternal and Child Health Risk Prediction

An end-to-end machine learning framework designed to predict and stratify maternal and infant health risk levels in primary healthcare settings. This project combines gradient boosting models with local explainability tools (SHAP) to provide transparent, clinical-grade decision support.

> 🚧 **Status:** Active Research & Machine Learning Model Development (MSc Dissertation Project)

---

## 📌 Research Overview & Impact
Early detection of high-risk pregnancies and infant health complications is critical for timely intervention in primary healthcare centers. This project addresses the "black box" challenge of complex machine learning models by integrating SHAP (SHapley Additive exPlanations) to ensure healthcare practitioners understand the underlying risk factors driving each prediction.

---

## 🛠️ Tech Stack & Architecture
- **Database Architecture:** PostgreSQL (Structured schema for primary healthcare indicators)
- **Programming Language:** Python 3.10+
- **Data Engineering & Manipulation:** Pandas, NumPy
- **Machine Learning Algorithms:** XGBoost, Scikit-learn
- **Model Explainability & XAI:** SHAP (Global feature importance & patient-level waterfall plots)
- **Development Environment:** Google Colab / Visual Studio Code

---

## 📂 Repository Structure
```text
├── data/                  <-- Anonymized sample datasets & schema mappings
├── notebooks/             <-- Jupyter Notebooks for data cleaning, EDA, & XGBoost/SHAP pipelines
├── sql/                   <-- PostgreSQL schemas & relational database queries
├── README.md              <-- Research project documentation
└── requirements.txt       <-- Dependencies & environment setup
