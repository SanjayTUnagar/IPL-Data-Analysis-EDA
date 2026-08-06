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
import pandas as pd
df = pd.read_csv('/content/drive/MyDrive/IPL.csv')
df.head()
```

<img width="1690" height="482" alt="image" src="https://github.com/user-attachments/assets/644daecf-1d89-45b1-a90d-b1814213c015" />






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
<img width="268" height="532" alt="image" src="https://github.com/user-attachments/assets/ba1f75c7-2db3-4239-b876-a521e85fef47" />


Percentage of Missing Values

```python
df.isnull().mean()*100
```
<img width="315" height="551" alt="image" src="https://github.com/user-attachments/assets/a0049076-8784-47a1-8c0f-77794ff1e2e3" />


Visualization

```python
sns.heatmap(df.isnull(), cbar=False)
plt.show()
```
<img width="758" height="658" alt="image" src="https://github.com/user-attachments/assets/c18f3ada-6964-4635-bf1b-bd41a5666e64" />


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
<img width="307" height="172" alt="image" src="https://github.com/user-attachments/assets/5f5f12ee-06ea-40b8-90bb-828858017303" />


Visualization

```python
sns.countplot(data=df,x="match_type")
plt.show()
```
<img width="816" height="552" alt="image" src="https://github.com/user-attachments/assets/aa81f108-1787-4fa3-847d-e7d816f4b941" />


Histogram

```python
sns.histplot(data=df,x="year")
plt.show()
```
<img width="803" height="552" alt="image" src="https://github.com/user-attachments/assets/26c24e09-991a-4723-90e5-6ef38c300961" />



---

## 2️⃣ Bivariate Analysis

Analyzing relationships between two variables.

Example

```python
sns.countplot(data=df,x="match_type",hue="year")
plt.show()
```
<img width="813" height="541" alt="image" src="https://github.com/user-attachments/assets/f72cbfc2-c6a3-436f-96e5-7fa7bab00f77" />


Scatter Plot

```python
sns.scatterplot(data=df,
                x="innings",
                y="year")
plt.show()
```
<img width="818" height="542" alt="image" src="https://github.com/user-attachments/assets/3d001024-3b68-4c5a-912e-c48ed06d6eb9" />


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
<img width="770" height="548" alt="image" src="https://github.com/user-attachments/assets/2263c40e-42e1-479e-9bff-39fd588c9ab2" />

---

# 📦 Outlier Detection

Box Plot

```python
sns.boxplot(data=df,x="year")
plt.show()
```
<img width="768" height="552" alt="image" src="https://github.com/user-attachments/assets/6739b0f5-d750-4556-b529-463fe45a5bc2" />

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
<img width="691" height="552" alt="image" src="https://github.com/user-attachments/assets/9fba2341-cc03-46a7-a8f3-dcf50ec1813f" />

---

# 💡 Important Insights

Examples

### Matches Played Per Year

```python
df["year"].value_counts().sort_index()
```
<img width="215" height="696" alt="image" src="https://github.com/user-attachments/assets/231dad3c-d1d6-4012-891a-a54d224cb8ce" />

---

### Most Popular IPL Host City

```python
df["city"].value_counts()
```
<img width="302" height="628" alt="image" src="https://github.com/user-attachments/assets/bcf184ba-a795-4aa6-b070-7a33cadcbec5" />

---

### Player of the Match Winners

```python
df["player_of_match"].value_counts()
```
<img width="335" height="596" alt="image" src="https://github.com/user-attachments/assets/4e55b788-c6a0-470f-9ce2-4b082ad05f52" />

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

Visualization:

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(data=df, x="day_name", 
              order=df["day_name"].value_counts().index)

plt.title("IPL Matches by Day of Week")
plt.xticks(rotation=45)
plt.show()
```
<img width="802" height="637" alt="image" src="https://github.com/user-attachments/assets/855485ab-ca3f-4f73-995d-ff71c1fcd640" />



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

### Sanjay Unagar
**Data Analyst | Python | SQL | Excel | Power BI | Pandas | Numpy | Matplotlib | Seaborn | Data Visualization**

🌐 **Portfolio:** https://sanjayunagar.netlify.app

💼 **LinkedIn:** https://www.linkedin.com/in/sanjayunagar/

🐙 **GitHub:** https://github.com/SanjayTUnagar

---

# ⭐ Support

If you found this project useful, please consider giving it a ⭐ on GitHub.

