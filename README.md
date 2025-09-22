# Elevate Labs AI & ML Internship - Task 1: Data Cleaning & Preprocessing

### **Objective**

The primary objective of this task was to demonstrate proficiency in data cleaning and preprocessing, which are foundational steps in any machine learning pipeline. The goal was to prepare a raw, messy dataset for model training by addressing common data issues.

### **Dataset**

The **Titanic Dataset** was used for this task. It is a well-known dataset for practicing data preprocessing, as it contains missing values, categorical features, and outliers.

### **Key Steps Performed**

The following data cleaning and preprocessing steps were executed sequentially to prepare the dataset:

1.  **Initial Data Exploration:**
    * The dataset was loaded using Pandas.
    * `df.info()` and `df.isnull().sum()` were used to identify data types, the number of non-null values, and the exact count of missing values in each column.

2.  **Handling Missing Values:**
    * The `Age` column, which had a moderate number of missing values, was imputed with the **median** age.
    * The `Embarked` column, with only two missing values, was imputed with the **mode** (the most frequent value).
    * The `Cabin` column, which had a significant number of missing values (over 77%), was **dropped** from the dataset.

3.  **Handling Categorical Features:**
    * Irrelevant columns like `Name` and `Ticket` were **dropped**.
    * The binary categorical feature `Sex` was converted to numerical format using **label encoding** (`male` -> 0, `female` -> 1).
    * The nominal categorical feature `Embarked` was converted using **one-hot encoding** (`S`, `C`, `Q`) to avoid an ordinal relationship. The `drop_first=True` parameter was used to prevent multicollinearity.

4.  **Feature Scaling:**
    * The numerical columns, `Age` and `Fare`, were **standardized** using scikit-learn's `StandardScaler`. This process transformed the data to have a mean of 0 and a standard deviation of 1, which helps various machine learning algorithms converge faster and perform better.

5.  **Outlier Handling:**
    * **Boxplots** were used to visually identify outliers in the `Fare` column.
    * The **Interquartile Range (IQR)** method was implemented to programmatically remove the outliers, resulting in a cleaner dataset for model training.

###Tools Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
