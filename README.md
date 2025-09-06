Data Analysis Workflow with Python

This project demonstrates a basic data analysis workflow using Python. It covers:

Entering data

Data cleaning using Pandas

Math calculations using NumPy

Visualizations using Matplotlib and Seaborn

1. Entering Data

We can create or load data into Python in multiple ways:

Manually creating a dataset using Python dictionaries or lists

Importing from a CSV/Excel file using Pandas

Example:
import pandas as pd

# Load data from a CSV file
df = pd.read_csv("sales_data.csv")

# Display first few rows
print(df.head())

2. Data Cleaning with Pandas

Data cleaning is essential to make data consistent and analysis-ready.

Common tasks:

Handling missing values

Converting data types

Renaming columns

Removing duplicates

Example:
# Check for missing values
print(df.isnull().sum())

# Fill missing values
df['Revenue'] = df['Revenue'].fillna(0)

# Convert Date column to datetime
df['Date'] = pd.to_datetime(df['Date'])

# Remove duplicates if any
df.drop_duplicates(inplace=True)

3. Math Calculations using NumPy

NumPy is great for numerical computations:

Summation

Mean, Median, Standard Deviation

Matrix operations

Example:
import numpy as np

# Convert a column to NumPy array
revenue = df['Revenue'].to_numpy()

# Basic calculations
print("Total Revenue:", np.sum(revenue))
print("Average Revenue:", np.mean(revenue))
print("Standard Deviation:", np.std(revenue))

4. Visualizations
A. Basic Visualization using Matplotlib
import matplotlib.pyplot as plt

# Line plot
plt.plot(df['Date'], df['Revenue'], marker='o')
plt.title("Revenue Over Time")
plt.xlabel("Date")
plt.ylabel("Revenue")
plt.show()

B. Advanced Visualization using Seaborn
import seaborn as sns

# Barplot with Seaborn
sns.barplot(x="Region", y="Revenue", data=df, estimator=sum, errorbar=None)
plt.title("Total Revenue by Region")
plt.show()
