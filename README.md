# 🚢 Titanic EDA with Pandas

<div align="center">

**Master Exploratory Data Analysis**

[![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-blue?style=flat-square&logo=pandas)](https://pandas.pydata.org/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)](https://www.python.org/)

[Features](#-features) • [Installation](#-installation) • [Analysis](#-what-youll-learn)

</div>

---

## 🎯 Overview

Dive deep into the famous Titanic dataset using Pandas. Uncover survival patterns, analyze passenger demographics, and answer real questions with data.

**Understanding data before modeling is the real skill.**

---

## ✨ Features

| Feature | Details |
|---------|---------|
| 🔍 **Data Exploration** | Shape, dtypes, info, describe |
| 🧹 **Data Cleaning** | Handle missing values strategically |
| 📊 **Aggregation** | GroupBy, pivot tables, cross-tabs |
| 👥 **Demographic Analysis** | Survival by class, gender, age |
| 💰 **Fare Analysis** | Price patterns and quartiles |
| 👨‍👩‍👧‍👦 **Family Impact** | How family size affects survival |
| 📈 **Correlation** | Relationships between features |
| 📝 **Reporting** | 10+ insights in markdown format |

---

## 📦 Tech Stack

- **Pandas:** 2.0+
- **NumPy:** (bundled with Pandas)
- **Python:** 3.8+
- **Data:** Kaggle Titanic Dataset

---

## 🚀 Quick Start

### Installation

```bash
# Create virtual environment
python -m venv venv

# Activate it
.\venv\Scripts\activate  # Windows
source venv/bin/activate  # macOS/Linux

# Install Pandas
pip install pandas numpy scipy
```

### Run Analysis

```bash
python analysis.py
```

Output: `titanic_eda_report.md` with findings

---

## 📊 Sample Insights

### Survival Overview
```
Total Passengers: 891
Survived: 342 (38.4%)
Died: 549 (61.6%)
```

### Survival by Gender
```
Women: 74.2% survival rate
Men: 18.9% survival rate
```

### Survival by Class
```
First Class: 63.0%
Second Class: 47.3%
Third Class: 24.2%
```

### Age Patterns
```
Survivors avg age: 28.3 years
Non-survivors avg age: 30.6 years
```

---

## 🔧 Key Pandas Operations

### Data Loading
```python
df = pd.read_csv('data/data_set.csv')
```

### Exploration
```python
df.head()              # First 5 rows
df.info()              # Data types & missing
df.describe()          # Statistics
```

### Aggregation
```python
df.groupby('Sex')['Survived'].mean()        # Survival by gender
df.pivot_table(values='Survived', 
               index='Pclass', 
               columns='Sex')                # Pivot table
```

### Cleaning
```python
df.isnull().sum()                          # Missing values
df.dropna(subset=['Age'])                  # Remove rows
df.fillna(df['Age'].mean())                # Fill with mean
```

### Analysis
```python
df['Age_Group'] = pd.cut(df['Age'], 
                         bins=[0,12,18,35,50,100],
                         labels=['Child','Teen','Adult','Middle','Senior'])

survival_by_age = df.groupby('Age_Group')['Survived'].agg(['count','sum','mean'])
```

---

## 📂 Project Structure

```
Day_07_Pandas_Titanic_EDA/
├── analysis.py
├── data/
│   ├── data_set.csv (Titanic training data)
│   ├── test.csv
│   └── gender_submission.csv
├── titanic_eda_report.md
└── README.md
```

---

## 📊 Dataset Features

### Columns (12)
- **PassengerId** — Unique identifier
- **Survived** — Target (0=died, 1=survived)
- **Pclass** — Ticket class (1,2,3)
- **Name** — Passenger name
- **Sex** — Gender (male/female)
- **Age** — Age in years
- **SibSp** — Number of siblings/spouses
- **Parch** — Number of parents/children
- **Ticket** — Ticket number
- **Fare** — Ticket price
- **Cabin** — Cabin number
- **Embarked** — Port of embarkation (C,Q,S)

### Missing Values
- **Age:** 177 missing (19.9%)
- **Cabin:** 687 missing (77.1%)
- **Embarked:** 2 missing (0.2%)

---

## 🎓 What You'll Learn

✅ Load and inspect data with Pandas  
✅ Handle missing values strategically  
✅ GroupBy operations and aggregations  
✅ Pivot tables for multi-dimensional analysis  
✅ Boolean indexing and filtering  
✅ Feature engineering with pd.cut()  
✅ Correlation analysis  
✅ Exploratory data analysis workflow  
✅ Storytelling with data  

---

## 💡 Real-World EDA Workflow

1. **Load Data** — Read CSV, check shape
2. **Inspect** — View first rows, dtypes, missing values
3. **Clean** — Handle NaNs, remove duplicates, fix errors
4. **Explore** — Statistics, distributions, relationships
5. **Visualize** — Understand patterns (not required here)
6. **Summarize** — Key findings and insights
7. **Report** — Document discoveries

---

## 📈 Analysis Output Sample

```
============================================================
SURVIVAL ANALYSIS
============================================================

Total Passengers: 891
Survived: 342 (38.38%)
Died: 549 (61.62%)

--- Survival by Gender ---
         Total  Survived  Survival_Rate
male       577       109           18.89
female     314       233           74.20

--- Survival by Class ---
     Total  Survived  Survival_Rate
1      216       136           62.96
2      184        87           47.28
3      491        119           24.24
```

---

<div align="center">

**Day 7 of 50 — Django × Data Science Challenge**

Learning Pandas and exploratory data analysis.

</div>

