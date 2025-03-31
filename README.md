# Data-analysis-pandas-
Adult Income Prediction analyzes the Adult dataset to predict if a person earns over $50K. Includes EDA, handling missing values, duplicates, and bivariate analysis. Uses Pandas, NumPy, Seaborn, and Matplotlib. Titanic Survival Analysis explores survival rates based on class, age, and gender with similar EDA techniques.

# 📊 Titanic & Adult Dataset Analysis

## 📌 Overview
This repository contains an in-depth analysis of the **Titanic** and **Adult** datasets, including data preprocessing, exploratory data analysis (EDA), and visualizations.

---

## 📂 Datasets
- **Titanic Dataset**: Information on Titanic passengers, including demographics and survival status.
- **Adult Dataset**: Census data to predict whether an individual earns more than $50K per year.

---

## 🔧 Data Preprocessing
### ✅ Steps Taken:
1. **Checked for missing values** and handled them accordingly.
2. **Removed duplicate rows** to ensure data integrity.
3. **Converted categorical variables** into numerical representations.
4. **Normalized and cleaned data** for better model performance.

---

## ❓ Questions & Answers

### 🚢 Titanic Dataset

#### 1️⃣ How many rows and columns are in the dataset?
**Answer:** The dataset has **`titanic.shape[0]` rows** and **`titanic.shape[1]` columns**.

#### 2️⃣ What are the data types of each column?
**Answer:**
- `titanic.info()` gives an overview.
- Some columns are **numerical** (e.g., `Age`, `Fare`), while others are **categorical** (e.g., `Sex`, `Embarked`).

#### 3️⃣ Are there missing values in the dataset?
**Answer:**
- Yes, `titanic.isnull().sum()` shows missing values in **Age, Cabin, and Embarked** columns.

#### 4️⃣ How did we handle missing values?
**Answer:**
- `Age`: Filled with the **median** age.
- `Cabin`: Dropped due to too many missing values.
- `Embarked`: Filled with the most **frequent** value.

#### 5️⃣ Are there duplicate rows?
**Answer:**
- Checked using `titanic.duplicated().any()`.
- Removed duplicates with `titanic.drop_duplicates(inplace=True)`.

#### 6️⃣ What is the distribution of age?
**Answer:**
- **Summary:** `titanic['Age'].describe()`.
- **Visualization:** `sns.histplot(titanic['Age'], kde=True)`.

#### 7️⃣ What was the survival rate for different classes?
**Answer:**
- **Survival by class:** `titanic.groupby('Pclass')['Survived'].mean()`.
- **Visualization:** `sns.barplot(x='Pclass', y='Survived', data=titanic)`.

#### 8️⃣ What is the survival rate of males vs. females?
**Answer:**
- `titanic.groupby('Sex')['Survived'].mean()`.
- Women had a higher survival rate than men.

#### 9️⃣ What is the relationship between fare and survival?
**Answer:**
- **Boxplot:** `sns.boxplot(x='Survived', y='Fare', data=titanic)`.
- **Insight:** Higher fares are linked to better survival rates.

---

### 🏠 Adult Dataset

#### 1️⃣ How many rows and columns are in the dataset?
**Answer:** The dataset has **`adult.shape[0]` rows** and **`adult.shape[1]` columns**.

#### 2️⃣ What are the data types of each column?
**Answer:**
- `adult.info()` provides an overview.
- Some columns are **categorical**, while others are **numerical**.

#### 3️⃣ Are there missing values in the dataset?
**Answer:**
- `adult.isnull().sum()` shows missing values in **workclass, occupation, and native-country**.

#### 4️⃣ How did we handle missing values?
**Answer:**
- Replaced `"?"` with `NaN` using `replace()`.
- Dropped missing values using `dropna()`.

#### 5️⃣ Are there duplicate rows?
**Answer:**
- Checked using `adult.duplicated().any()`.
- Removed duplicates using `adult.drop_duplicates(inplace=True)`.

#### 6️⃣ What is the distribution of age?
**Answer:**
- **Summary:** `adult['age'].describe()`.
- **Visualization:** `adult['age'].hist()`.

#### 7️⃣ What is the most common workclass?
**Answer:**
- `adult['workclass'].value_counts()` shows that **"Private"** is the most common workclass.
- **Visualization:** `sns.countplot(x='workclass', data=adult)`.

#### 8️⃣ How many people have a Bachelor's or Master's degree?
**Answer:**
- `sum(adult['education'].isin(['Bachelors','Masters']))` gives the count.

#### 9️⃣ What is the income distribution?
**Answer:**
- **Visualization:** `sns.countplot(x='income', data=adult)`.
- **Observation:** The majority of people earn **<=50K**.

#### 🔟 How was the income column transformed?
**Answer:**
- **Replaced categorical income values:**
  ```python
  adult.replace(to_replace=['<=50K', '>50K'], value=[0,1], inplace=True)
  ```

---

## 📊 Visualizations
- **Histograms for Age Distribution**
- **Bar charts for Categorical Variables**
- **Boxplots for Income and Survival Analysis**

---

## 🚀 Future Improvements
- Implement Machine Learning models for predictions.
- Improve data cleaning and feature engineering.
- Perform deeper statistical analysis.

---

## 📜 License
This project is open-source and available for public use.
