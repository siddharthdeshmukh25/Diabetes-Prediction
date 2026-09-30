# 🩸 Diabetes Prediction using Machine Learning

A machine learning classification project that predicts whether a patient is **Diabetic** or **Non-Diabetic** using a Support Vector Machine (SVM) classifier trained on the Pima Indians Diabetes dataset.

> 🎓 **Internship Project** — Machine Learning (Healthcare)

---

## 📖 Project Overview

Diabetes affects over 500 million people worldwide. Early detection prevents serious complications (kidney failure, heart disease, vision loss), but routine screening is costly and time-consuming.

**Goal:** Build an ML model that predicts diabetes status from 8 diagnostic measurements — a fast, low-cost screening assistant.

---

## 📊 Dataset

**Pima Indians Diabetes Dataset** (included: `diabetes.csv`)

| Property | Value |
|---|---|
| Total Records | 768 female patients (age 21+) |
| Features | 8 diagnostic measurements |
| Non-Diabetic (0) | 500 (65.1%) |
| Diabetic (1) | 268 (34.9%) |
| Missing Values | 0 |

**Features:** Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age

---

## 🔬 Methodology

1. **Data Loading** — CSV → pandas DataFrame (768 × 9)
2. **Statistical Analysis** — `describe()` summary + groupby comparison (diabetic patients show higher glucose: 141 vs 110)
3. **Feature/Label Split** — X = 8 features, Y = Outcome
4. **Train-Test Split** — `test_size=0.2, stratify=Y` → 614 train / 154 test (stratification preserves class ratio)
5. **Standardization** — `StandardScaler` (fit on train, transform on test — no data leakage)
6. **Model Training** — SVM (`SVC` with linear kernel)
7. **Evaluation** — accuracy on train & test sets
8. **Predictive System** — end-to-end inference on new patient data

---

## 🤖 Model

**Support Vector Machine (SVC, linear kernel)**

- Finds the optimal hyperplane separating diabetic and non-diabetic patients
- Maximizes margin between classes → better generalization
- Linear kernel is well-suited for this dataset size

---

## 📈 Results & Key Findings

| Metric | Value |
|---|---|
| **Test Accuracy** | **77.27%** |
| Training Accuracy | 78.66% |
| Overfitting Gap | ~1.4% (excellent generalization) |

**Key findings:**
- ✅ Small train-test gap → model generalizes well
- ✅ Predictive system verified: sample input → `[1]` → "The person is diabetic"
- 📌 77% is a solid baseline for Pima dataset — models rarely exceed 80% without heavy feature engineering

---

## 🚀 How to Run

```bash
pip install -r requirements.txt
jupyter notebook Diabetes_Prediction.ipynb
# Kernel → Restart & Run All
```

Sample prediction (last cell of notebook):
```python
input_data = (5, 166, 72, 19, 175, 25.8, 0.587, 51)
# Output: [1] → "The person is diabetic"
```

---

## 🛠 Tech Stack

Python 3.10 • Scikit-learn • Pandas • NumPy • Jupyter

---

## ⚠️ Limitations & Future Scope

- Only female patients (Pima) — limited generalizability
- Insulin/SkinThickness contain 0 values (likely missing data — could impute)
- **Future:** KNN/median imputation, Random Forest/XGBoost comparison, GridSearchCV tuning, Streamlit deployment

---

## 📁 Files

| File | Description |
|---|---|
| `Diabetes_Prediction.ipynb` | Main executed notebook |
| `Diabetes_Prediction_Presentation.pptx` | 10-slide presentation |
| `diabetes.csv` | Dataset |
| `README.md` | This documentation |
| `requirements.txt` | Dependencies |

---
*🤖 Generated with Codebuff*
