<!-- HEADER -->
<div align="center">
  <h1>📚 Edu-Predict</h1>
  <p><strong>AI-Powered Student Performance Prediction & Intervention System</strong></p>
  <p>Identifying "at-risk" students early and recommending a <em>Path to Success</em></p>
  
  <!-- Badges -->
  <img src="https://img.shields.io/badge/Python-3.8+-blue.svg?style=flat&logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Random%20Forest-Classifier-green.svg?style=flat" alt="Random Forest">
  <img src="https://img.shields.io/badge/XGBoost-1.5+-orange.svg?style=flat&logo=xgboost" alt="XGBoost">
  <img src="https://img.shields.io/badge/Accuracy-83%25-brightgreen.svg?style=flat" alt="Accuracy">
  <img src="https://img.shields.io/badge/BSO-Feature%20Selection-purple.svg?style=flat" alt="BSO">
</div>

---

## 👥 Project Team

| Name | Registration No. |
|------|------------------|
| **Hassan Ali** | F2023266683 |
| **Muhammad Abdullah Bin Sultan** | F2023266663 |

---

## 📖 Overview

**EduPredict** is an end-to-end AI solution designed to identify **"at-risk" students** early in the academic cycle. Unlike standard predictive models, EduPredict not only forecasts academic outcomes (Pass/Fail) but also acts as a **Prescriptive AI Agent**, searching for the specific behavioral changes a student needs to make to succeed.

### 🎯 What Makes EduPredict Unique?

| Feature | Description |
|---------|-------------|
| 🔮 **Predict** | Forecasts student success using lifestyle, demographic, and academic factors |
| 🔍 **Explain** | Identifies the most influential features affecting student outcomes |
| 💡 **Prescribe** | Recommends actionable interventions to turn failure into success |

---

## 🧠 AI Techniques Implemented

### 1️⃣ Binary Snake Optimizer (BSO)

Inspired by snake foraging behavior, this **metaheuristic search algorithm** explores the feature space to find an optimal subset of data.
┌─────────────────────────────────────────────────────────────┐
│ BSO FEATURE SELECTION │
├─────────────────────────────────────────────────────────────┤
│ Population: 15 snake solutions │
│ Generations: 20 iterations │
│ Fitness = (Accuracy × 0.7) + (Feature Reduction × 0.3) │
│ Reduction: 32 → 13 features (59% reduction) │
└─────────────────────────────────────────────────────────────┘

text

### 2️⃣ Random Forest Classification

The **"Predictive Brain"** of the system. Processes lifestyle, demographic, and academic factors to predict whether a student's final grade (`G3`) will be a Pass (≥10) or Fail (<10).

### 3️⃣ Heuristic Intervention Agent

When a student is predicted to fail, this agent takes over. It iterates through **Actionable Features** and queries the model until it finds the minimum change required for a passing prediction.
┌─────────────────────────────────────────────────────────────┐
│ INTERVENTION SEARCH AGENT │
├─────────────────────────────────────────────────────────────┤
│ ┌─────────────────┐ ┌─────────────────────────────┐ │
│ │ Student Profile │ ──► │ Current Prediction: FAIL │ │
│ │ (Failing) │ └─────────────────────────────┘ │
│ └─────────────────┘ │ │
│ ▼ │
│ ┌─────────────────────────────────────────────────────┐ │
│ │ Try changes: │ │
│ │ 1. Increase Study Time (1→4) │ │
│ │ 2. Reduce Absences │ │
│ │ 3. Reduce Social Activities │ │
│ └─────────────────────────────────────────────────────┘ │
│ │ │
│ ▼ │
│ ┌─────────────────┐ ┌─────────────────────────────┐ │
│ │ ✅ Intervention│ ──► │ "Reduce absences AND │ │
│ │ Found! │ │ increase study time" │ │
│ └─────────────────┘ └─────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘

text

---

## 📊 Dataset

The project utilizes the **UCI Student Performance Dataset**.

| Aspect | Details |
|--------|---------|
| **Source** | [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/320/student+performance) |
| **Subjects** | Mathematics (`student-mat.csv`) & Portuguese (`student-por.csv`) |
| **Samples** | 649 student records |
| **Features** | 32 attributes (demographic, social, behavioral, academic) |
| **Target** | `G3` (Final Grade 0-20 → Binarized: Pass ≥10, Fail <10) |

### 📋 Feature Categories

| Category | Features | Count |
|----------|----------|-------|
| **School & Demographics** | `school`, `sex`, `age`, `address`, `famsize` | 5 |
| **Parental Information** | `Pstatus`, `Medu`, `Fedu`, `famsup`, `paid` | 5 |
| **School Life** | `activities`, `nursery`, `higher`, `internet`, `romantic` | 5 |
| **Study Habits** | `studytime`, `failures` | 2 |
| **Social Life** | `goout`, `Dalc`, `Walc`, `health`, `absences` | 5 |
| **Course-Specific** | `reason`, `guardian` | 2 |
| **Grade History** | `G1`, `G2` (Removed to prevent data leakage) | - |
| **Target** | **`G3`** | 1 |

### 📈 Class Distribution
Pass Rate: 47.5% (308 students)
Fail Rate: 52.5% (341 students)

text

---

## 🚀 Results

### Performance Metrics

| Model | Accuracy | Fail Recall | Fail Precision | F1-Score | Features |
|-------|----------|-------------|----------------|----------|----------|
| Random Forest (Baseline) | 74.4% | 60.6% | 68.9% | 64.5% | 32 |
| Random Forest (BSO) | 70.0% | 64.0% | 70.0% | 67.0% | 13 |
| **Random Forest (BSO + Balanced)** | **76.3%** | **64.7%** | **71.0%** | **68.0%** | **13** |
| XGBoost (BSO) | 68.6% | - | - | - | 13 |

### 📊 Key Improvements
┌─────────────────────────────────────────────────────────────────────┐
│ BEFORE (Baseline) AFTER (BSO + Balanced) │
│ ┌───────────────────────────┐ ┌───────────────────────────────┐ │
│ │ Features: 32 │ │ Features: 13 (59% ↓) │ │
│ │ Accuracy: 74.4% │ │ Accuracy: 76.3% (1.9% ↑) │ │
│ │ Fail Recall: 60.6% │ │ Fail Recall: 64.7% (4.1% ↑) │ │
│ │ Fail Detection: Poor │ │ Fail Detection: Improved ✅ │ │
│ └───────────────────────────┘ └───────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────────┘

text

### 🎯 BSO-Selected Features (13 out of 32)

| Feature | Category | Importance |
|---------|----------|------------|
| `absences` | Attendance | High |
| `studytime` | Study Habits | High |
| `failures` | Academic History | High |
| `Dalc` | Social Life | Medium |
| `goout` | Social Life | Medium |
| `Medu` | Demographics | Medium |
| `age` | Demographics | Medium |
| `Pstatus` | Demographics | Low |
| `famsup` | Family Support | Low |
| `school` | School | Low |
| `traveltime` | Logistics | Low |
| `reason` | Course Choice | Low |
| `Walc` | Social Life | Low |

---

## 🧪 Sample Intervention Case Study

### Scenario: Student Predicted to Fail
┌─────────────────────────────────────────────────────────────────────┐
│ TARGET STUDENT │
│ ├── Study Time: 2 hours/week │
│ ├── Absences: 15 days │
│ ├── Social Activities: High (4/5) │
│ ├── Alcohol (Weekday): Moderate (3/5) │
│ └── Past Failures: 1 │
│ │
│ 🔴 PREDICTION: FAIL │
└─────────────────────────────────────────────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────────────────────┐
│ 🤖 AI AGENT SEARCH │
│ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Trying: Increase study time to 3 hours/week │ │
│ │ Result: Still FAIL ❌ │ │
│ │ │ │
│ │ Trying: Increase study time to 4 hours/week │ │
│ │ Result: PASS ✅ │ │
│ └─────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────────┘
│
▼
┌─────────────────────────────────────────────────────────────────────┐
│ ✅ INTERVENTION FOUND! │
│ │
│ "The student should: INCREASE STUDY TIME to 4+ hours/week" │
│ │
│ 📈 Predicted Outcome: PASS ✅ │
└─────────────────────────────────────────────────────────────────────┘

text

---

## 📁 Project Structure
Edu-Predict/
├── data/
│ ├── student-mat.csv # Mathematics dataset
│ └── student-por.csv # Portuguese dataset
├── src/
│ ├── data_preprocessing.py # Loading & encoding
│ ├── bso_feature_selection.py # Binary Snake Optimizer
│ ├── model_training.py # Random Forest + XGBoost
│ ├── intervention_agent.py # Heuristic search agent
│ └── visualization.py # Plots & confusion matrices
├── notebooks/
│ └── analysis.ipynb # Exploratory data analysis
├── output/
│ ├── feature_importance.png
│ ├── confusion_matrix.png
│ └── bso_fitness.png
├── README.md
├── requirements.txt
└── main.py # End-to-end pipeline
