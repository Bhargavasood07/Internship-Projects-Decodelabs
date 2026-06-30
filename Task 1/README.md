# Data Analytics Task 1: Data Cleaning & Preparation

## Project Overview

This project is part of **Task 1: Data Cleaning & Preparation** for the **Data Analyst role at Decodelabs**. The main objective of this project is to clean and prepare a raw dataset for further analysis by handling missing values, removing duplicate records, checking data types, and exporting a cleaned dataset.

Data cleaning is one of the most important steps in the data analytics workflow because poor-quality data can lead to incorrect analysis and unreliable insights.

---

## Objective

The objective of this task is to:

- Load the dataset using Python
- Understand the dataset structure
- Check rows, columns, and data types
- Identify missing values
- Handle missing values in numerical columns
- Detect and remove duplicate records
- Convert data types where possible
- Save the cleaned dataset as a CSV file

---

## Technologies Used

- Python
- Pandas
- NumPy
- Google Colab / Jupyter Notebook

---

## Project Structure

```text
Task-1-Data-Cleaning/
│
├── Dataset for Data Analytics - Sheet1.csv
├── Data_Analytics_(Task_1).ipynb
├── cleaned_dataset.csv
└── README.md
```

---

## Dataset

The dataset used in this project is:

```text
Dataset for Data Analytics - Sheet1.csv
```

The dataset was loaded using Pandas:

```python
df = pd.read_csv("/content/Dataset for Data Analytics - Sheet1.csv")
```

---

## Work Done

### 1. Imported Required Libraries

The project starts by importing the required Python libraries:

```python
import numpy as np
import pandas as pd
```

### 2. Loaded the Dataset

The dataset was loaded using Pandas:

```python
df = pd.read_csv("/content/Dataset for Data Analytics - Sheet1.csv")
```

### 3. Displayed Dataset Preview

The first five rows of the dataset were displayed using:

```python
df.head(5)
```

This helped in understanding the basic structure and sample values of the dataset.

### 4. Checked Dataset Shape

The number of rows and columns was checked using:

```python
df.shape
```

This helped in understanding the size of the dataset.

### 5. Checked Dataset Information

The dataset information was checked using:

```python
df.info()
```

This displayed column names, non-null values, and data types.

### 6. Generated Descriptive Statistics

Basic statistical details were generated using:

```python
df.describe()
```

This helped in understanding numerical columns through values such as mean, standard deviation, minimum, maximum, and quartiles.

### 7. Checked Missing Values

Missing values were checked using:

```python
print(df.isnull().sum())
```

This helped identify columns with null or missing values.

### 8. Handled Missing Values

Numerical columns were selected and missing values were filled using the median value:

```python
num_cols = df.select_dtypes(include=['int64', 'float64']).columns

for col in num_cols:
    df[col].fillna(df[col].median(), inplace=True)
```

Median was used because it is less affected by outliers compared to the mean.

### 9. Removed Duplicate Records

Duplicate records were checked and removed:

```python
print("Duplicate rows:", df.duplicated().sum())

df.drop_duplicates(inplace=True)

print("After removing duplicates:", df.shape)
```

This ensured that repeated records did not affect the quality of analysis.

### 10. Converted Data Types

The code attempted to convert columns into date-time format where possible:

```python
for col in df.columns:
    try:
        df[col] = pd.to_datetime(df[col])
    except:
        pass
```

This step helps correct data formats for columns that may contain date values.

### 11. Checked Final Dataset

After cleaning, the final shape, remaining missing values, and data types were checked:

```python
print(df.shape)
print(df.isnull().sum())
print(df.dtypes)
```

### 12. Saved the Cleaned Dataset

The cleaned dataset was saved as:

```python
df.to_csv("cleaned_dataset.csv", index=False)
```

Output file:

```text
cleaned_dataset.csv
```

---

## Key Features

- Dataset loading using Pandas
- Basic dataset inspection
- Missing value detection
- Missing value handling using median
- Duplicate record detection
- Duplicate record removal
- Data type conversion
- Cleaned dataset export

---

## Output

The final cleaned dataset is saved as:

```text
cleaned_dataset.csv
```

This file can be used for further steps such as Exploratory Data Analysis, visualization, reporting, or machine learning.

---

## How to Run This Project

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/Task-1-Data-Cleaning.git
```

### Step 2: Open the Project Folder

```bash
cd Task-1-Data-Cleaning
```

### Step 3: Install Required Libraries

```bash
pip install pandas numpy
```

### Step 4: Open Jupyter Notebook

```bash
jupyter notebook
```

### Step 5: Run the Notebook

Open the file:

```text
Data_Analytics_(Task_1).ipynb
```

Run all cells sequentially.

---

## GitHub Commands

```bash
git init
git add .
git commit -m "Added Data Cleaning Task 1 project"
git branch -M main
git remote add origin https://github.com/your-username/Task-1-Data-Cleaning.git
git push -u origin main
```

If remote origin already exists:

```bash
git remote remove origin
git remote add origin https://github.com/your-username/Task-1-Data-Cleaning.git
git push -u origin main
```

---

## Learning Outcomes

Through this project, I learned:

- How to load datasets using Pandas
- How to inspect dataset structure
- How to identify missing values
- How to handle missing values using median
- How to remove duplicate records
- How to check and convert data types
- How to save cleaned data for further analysis

---

## Conclusion

This project successfully completed the basic data cleaning and preparation process for the given dataset. The raw dataset was inspected, missing values were handled, duplicate records were checked and removed, data types were verified, and the cleaned dataset was exported for future analysis.

This task helped build a strong foundation in data preprocessing, which is a critical step in every data analytics and machine learning workflow.

---

## Author

**Bhargava Sood**

Data Analyst Intern  
Decodelabs

---

## Repository Description

```text
Task 1 Data Cleaning and Preparation project using Python, Pandas, and NumPy as part of the Data Analyst role at Decodelabs.
```

---

## Tags

`Python` `Pandas` `NumPy` `Data Cleaning` `Data Preparation` `Data Analytics` `Decodelabs` `Jupyter Notebook`
