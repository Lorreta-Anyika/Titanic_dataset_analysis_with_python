# Titanic Dataset Analysis


## Table of Contents  
1. [Project Overview](project-overview)  
2. [Data Source](data-source)  
3. [Tools Used](tools-used)  
4. [Data Cleaning](data-cleaning)  
   - Handling Missing Values  
   - Removing Irrelevant Columns  
   - Correcting Data Types  
5. [Exploratory Data Analysis (EDA)](exploratory-data-analysis-eda)  
   - Descriptive Statistics  
   - Data Visualizations  
6. [Insights & Findings](insights--findings)  
   - Factors Affecting Survival  
   - Impact of Passenger Class  
   - Outliers & Anomalies  
7. [Conclusion & Recommendations](conclusion--recommendations)
8. [How to Use](how--to--use)
9. [Author](author)
10. [References](references)  

---

## 1. Project Overview  
This project involves setting up a structured workflow for analyzing the Titanic dataset, performing **Exploratory Data Analysis (EDA)**, and answering key analytical questions using Python.  The dataset contains details such as passenger class, age, gender, fare, and survival status, making it an excellent resource for learning **data manipulation**, **visualization**, and **statistical analysis**.

The goal of this project is to extract meaningful insights, understand the factors influencing survival, and detect outliers. It demonstrates Python skills and techniques commonly used by data analysts to explore, clean, and analyze transportation and logistics data. Using Pandas, NumPy, Matplotlib, and Seaborn, you will clean and explore the dataset, identify trends, and gain insights into survival patterns. This project is ideal for beginners in data analysis and machine learning, providing a strong foundation in data preprocessing, visualization, and feature engineering.

---

## 2. Data Source  
- Dataset: Titanic dataset (`titanic3.xls`)  
- Source: [Kaggle](https://www.kaggle.com)  

---

## 3. Tools Used  
- **Python Libraries:**  
  - `pandas` (data manipulation)  
  - `seaborn` & `matplotlib` (visualization)  
  - `numpy` (numerical analysis)  
  - `scipy.stats` (statistical analysis)  

- **Development Environment:**  
  - Jupyter Notebook  

---

## 4. Data Cleaning  
### Handling Missing Values  
- Replaced missing **Age** values with the median (`28.0`).  
- Replaced missing **Fare** values with the median (`14.45`).  
- Filled missing **Embarkation** values with the most frequent category (`mode`).  
- Filled missing **Boat** values with `"No Boat"`.  
- Filled missing **Home Destination** values with `"Unknown"`.  
- Dropped **Cabin** and **Body** columns (irrelevant to survival analysis).  

### Correcting Data Types  
- Converted categorical features to numerical:  
  - `sex` → `0: Male, 1: Female`  
  - `embarked` → `C: 0, Q: 1, S: 2`  
- Converted `pclass`, `sibsp`, `parch`, `fare`, and `age` to appropriate data types.  

---

## 5. Exploratory Data Analysis (EDA)  
### Descriptive Statistics  
- Summary of numerical data: mean, median, standard deviation.  
- Count of unique values in categorical columns.  

### Data Visualizations  
#### **Survival Count**  
```python  
sns.countplot(x='survived', data=df)  
plt.title("Survival Count")  
plt.show()  
```

#### **Survival Rate by Gender**  
```python  
sns.barplot(x='sex', y='survived', data=df)  
plt.title("Survival Rate by Gender")  
plt.show()  
```

#### **Survival Rate by Passenger Class**  
```python  
sns.barplot(x='pclass', y='survived', data=df)  
plt.title("Survival Rate by Passenger Class")  
plt.show()  
```

#### **Age Distribution**  
```python  
sns.histplot(df['age'], bins=30, kde=True)  
plt.title("Age Distribution")  
plt.show()  
```

#### **Feature Correlation Heatmap**  
```python  
plt.figure(figsize=(10,6))  
sns.heatmap(df.corr(), annot=True, cmap="coolwarm")  
plt.title("Feature Correlation Heatmap")  
plt.show()  
```

---

## 6. Insights & Findings  
### 1. What Factors Contributed to Survival?  
- **Gender:** Women had a significantly higher survival rate than men.  
- **Passenger Class:** First-class passengers had the highest survival rate, while third-class had the lowest.  
- **Age:** Children and younger passengers had a higher survival rate than older passengers.  

### 2. How Did Passenger Class Affect Survival Rates?  
- **First-Class:** Highest survival rate.  
- **Third-Class:** Lowest survival rate.  
- Ticket price was a major factor; expensive tickets correlated with higher survival chances.  

### 3. Were There Any Outliers?  
- **Age:** Outliers observed in passengers over **50+ years**.  
- **Fare:** Some passengers paid **extremely high fares**, indicating potential anomalies.  
- **Boxplots were used to detect these outliers.**  

---

## 7. Conclusion & Recommendations  
- **Findings:**  
  - The **"Women and children first"** policy significantly influenced survival.  
  - Wealthier passengers (First-Class) had better survival chances.  
  - Older passengers had a lower survival rate.  

- **Recommendations for Future Analysis:**  
  - Incorporate more features (e.g., social class beyond ticket class).  
  - Explore predictive modeling with **Machine Learning (Logistic Regression, Decision Trees)**.  
  - Investigate relationships between **family size** and survival probability.

 ---

 ## 8. How to Use  

### i. Clone the Repository  
Clone this project repository from GitHub using:  
```bash
git clone https://github.com/your-username/titanic-analysis.git
cd titanic-analysis
```

### ii. Set Up the Environment
Ensure you have Python installed, then create a virtual environment and install the required dependencies:

```python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install -r requirements.txt
```

### iii. Load the Dataset
The Titanic dataset is provided in Excel (.xlsx) format. Load it using Pandas:

```import pandas as pd
df = pd.read_excel("titanic.xlsx")
df.head()
```

### iv. Run Exploratory Data Analysis (EDA)
Execute the eda.py script to generate insights: python eda.py
Or open and run it in a Jupyter Notebook

 ---

 ## 9. Author - Lorreta Anyika
 This project is part of my portfolio, showcasing the python skills essential for data analyst roles. If you have any questions, feedback, or would like to collaborate, feel free to get in touch!

---

## 10. References  
- Titanic Dataset Source: [Kaggle](https://www.kaggle.com)  
- Python Libraries: Pandas, Matplotlib, Seaborn, Scipy  

---
## Stay Updated and Join the Community
- **LinkedIn**: [Linkedin](https://www.linkedin.com/in/uchechukwu-lorreta-anyika-7b5b4a253/)
- **Email**: [Email](lorretaucheanyika@outlook.com)

Thank you for your support, and I look forward to connecting with you!
