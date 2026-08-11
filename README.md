# Task 1 – Big Data Analytics

## 📌 Project Overview

This project is part of **Big Data Analytics (BDA)** and focuses on performing basic data analysis and preprocessing using Python.

The analysis is performed on a **Superstore sales dataset** using Python libraries such as **Pandas, NumPy, Matplotlib, and Seaborn**.

## 🎯 Objectives

* Load and inspect the dataset.
* Understand the structure and data types of the dataset.
* Perform basic statistical analysis.
* Convert date columns into proper datetime format.
* Calculate delivery duration.
* Check for missing values.
* Explore different product categories.
* Analyze sales based on product categories.
* Visualize sales data using charts.

## 📊 Dataset

The project uses the `samplesuperstore.csv` dataset.

The dataset contains **10,194 records and 21 columns** before feature creation.

Important columns include:

* Row ID
* Order ID
* Order Date
* Ship Date
* Ship Mode
* Customer ID
* Customer Name
* Segment
* Country/Region
* City
* State/Province
* Postal Code
* Region
* Product ID
* Category
* Sub-Category
* Product Name
* Sales
* Quantity
* Discount
* Profit

A new column called **Delivery Days** is created by calculating the difference between Ship Date and Order Date.

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Google Colab / Jupyter Notebook

## 🔍 Data Analysis Performed

### 1. Data Loading

The dataset is loaded using Pandas:

```python
df = pd.read_csv("samplesuperstore.csv")
```

### 2. Data Inspection

The following functions are used to understand the dataset:

```python
df.head()
df.info()
df.describe()
```

The dataset initially contains **10,194 rows and 21 columns**.

### 3. Date Conversion

The `Order Date` and `Ship Date` columns are converted into datetime format:

```python
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])
```

### 4. Feature Creation

A new feature, `Delivery Days`, is created:

```python
df['Delivery Days'] = (df['Ship Date'] - df['Order Date']).dt.days
```

This represents the number of days taken between ordering and shipping.

### 5. Missing Value Check

Missing values are checked using:

```python
df.isnull().sum()
```

The analysis shows **0 missing values** across the available columns.

### 6. Category Analysis

The dataset contains three main product categories:

* Office Supplies
* Furniture
* Technology

Total sales are grouped by category using:

```python
category_sales = df.groupby('Category')['Sales'].sum()
```

### 📈 Sales by Category

| Category        |  Total Sales |
| --------------- | -----------: |
| Furniture       | 754,747.7613 |
| Office Supplies | 731,893.3140 |
| Technology      | 839,893.2790 |

Based on the analysis, **Technology has the highest total sales** among the three categories.

## 📊 Visualization

A bar chart is created to visualize sales by category:

```python
category_sales.plot(kind='bar', figsize=(8,5))
plt.title("Sales by Category")
plt.ylabel("Total Sales")
plt.show()
```

## 📁 Project Structure

```text
Task-1-BDA/
│
├── Task_1_BDA.ipynb
├── samplesuperstore.csv
└── README.md
```

## ✅ Conclusion

This project demonstrates the basic workflow of data analysis in Big Data Analytics using Python. The dataset was loaded, inspected, transformed, checked for missing values, and analyzed based on product categories.

The analysis also demonstrates how Python visualization libraries can be used to understand sales patterns and derive useful insights from business data.

## 👨‍💻 Author

**Ajay**

BCA – Big Data Analytics
