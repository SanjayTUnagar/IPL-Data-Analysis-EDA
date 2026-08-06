# 🏏 IPL Data Analysis using Python | Exploratory Data Analysis (EDA)

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green)
![NumPy](https://img.shields.io/badge/NumPy-Numerical-orange)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-red)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-purple)

---

# 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on the Indian Premier League (IPL) dataset (2008–2025).

The analysis includes:

- Dataset Understanding
- Data Cleaning
- Missing Value Analysis
- Duplicate Detection
- Statistical Summary
- NumPy Calculations
- Feature Engineering
- Univariate Analysis
- Bivariate Analysis
- Multivariate Analysis
- Outlier Detection
- Correlation Analysis
- Important Business Insights
- Data Visualization using Matplotlib & Seaborn

---

# 📂 Dataset

Dataset Source

https://www.kaggle.com/datasets/chaitu20/ipl-dataset2008-2025

The dataset contains:

- Match Details
- Teams
- Players
- Ball-by-Ball Data
- Match Results
- Venues
- Cities
- Seasons
- Awards
- Toss Details

---

# 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Colab / Jupyter Notebook

---

# 📦 Installation

Install required libraries

```bash
pip install pandas numpy matplotlib seaborn
```

---

# 📚 Import Libraries

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
```

---

# 📥 Load Dataset

```python
df = pd.read_csv("IPL.csv")
df.head()
```

---

# 🔍 Dataset Understanding

The following functions are used to understand the dataset.

```python
df.shape
df.head()
df.tail()
df.columns
df.info()
df.describe()
df.dtypes
```

---

# 🧹 Data Cleaning

## Missing Values

```python
df.isnull().sum()
```

Percentage of Missing Values

```python
df.isnull().mean()*100
```

Visualization

```python
sns.heatmap(df.isnull(), cbar=False)
plt.show()
```

---

## Duplicate Records

```python
df.duplicated().sum()
```

---

# 📊 Exploratory Data Analysis (EDA)

## 1️⃣ Univariate Analysis

Analyzing one variable at a time.

Examples

- Match Type
- Event Name
- Year

```python
df["match_type"].value_counts()
```

Visualization

```python
sns.countplot(data=df,x="match_type")
plt.show()
```

Histogram

```python
sns.histplot(data=df,x="year")
plt.show()
```

---

## 2️⃣ Bivariate Analysis

Analyzing relationships between two variables.

Example

```python
sns.countplot(data=df,x="match_type",hue="year")
plt.show()
```

Scatter Plot

```python
sns.scatterplot(data=df,
                x="innings",
                y="year")
plt.show()
```

---

## 3️⃣ Multivariate Analysis

Analyzing more than two variables.

```python
sns.scatterplot(
    data=df,
    x="match_type",
    y="innings",
    hue="year"
)
plt.show()
```

---

# 📦 Outlier Detection

Box Plot

```python
sns.boxplot(data=df,x="year")
plt.show()
```

---

# 📈 Correlation Analysis

```python
numeric_df = df[["year","innings"]]

numeric_df.corr()

sns.heatmap(
    numeric_df.corr(),
    annot=True,
    cmap="coolwarm"
)
plt.show()
```

---

# 💡 Important Insights

Examples

### Matches Played Per Year

```python
df["year"].value_counts().sort_index()
```

---

### Most Popular IPL Host City

```python
df["city"].value_counts()
```

---

### Player of the Match Winners

```python
df["player_of_match"].value_counts()
```

---

# ⚙ Feature Engineering

Examples

✔ Extract Match Year

✔ Match Month

✔ Match Day

✔ Day Name

Example

```python
df["date"] = pd.to_datetime(df["date"])

df["year"] = df["date"].dt.year
df["month"] = df["date"].dt.month
df["day"] = df["date"].dt.day
df["day_name"] = df["date"].dt.day_name()
```

---

# 📊 Visualizations Included

- Count Plot
- Histogram
- Scatter Plot
- Heatmap
- Box Plot
- Correlation Matrix

---

# 📁 Project Structure

```
IPL-Data-Analysis/

│

├── IPL_Data_Analysis_EDA.ipynb

├── IPL.csv

├── README.md

└── images/
```

---

# 🚀 Skills Demonstrated

- Data Cleaning
- Data Wrangling
- Exploratory Data Analysis
- Pandas
- NumPy
- Data Visualization
- Feature Engineering
- Statistical Analysis
- Business Insights

---

# 📚 Libraries Used

- Pandas
- NumPy
- Matplotlib
- Seaborn

---

# 🎯 Learning Outcomes

After completing this project, you will understand:

- Loading datasets
- Data inspection
- Handling missing values
- Duplicate detection
- Data visualization
- Feature engineering
- Correlation analysis
- Business insights generation
- Exploratory Data Analysis workflow

---

# 👨‍💻 Author

**Sanjay Unagar**

Data Analyst

- LinkedIn: https://www.linkedin.com/in/sanjayunagar/
- Portfolio: https://sanjayunagar.netlify.app/
- GitHub: https://github.com/SanjayTUnagar

---

# ⭐ If you found this project useful, don't forget to Star the repository!
