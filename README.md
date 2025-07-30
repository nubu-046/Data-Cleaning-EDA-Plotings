# Sales Transaction Data Analysis

This repository contains an exploratory data analysis (EDA) of a retail sales transactions dataset. It includes data cleaning, preprocessing, and visualization using Python libraries such as pandas, matplotlib, and seaborn.

---

## 📁 Dataset Overview

- Each row represents a sales transaction.
- Key columns:
  - `Transaction ID`
  - `Customer ID`
  - `Category`
  - `Item`
  - `Price Per Unit`
  - `Quantity`
  - `Total Spent`
  - `Payment Method`
  - `Location`
  - `Transaction Date`
  - `Discount Applied`

---

## 🧹 Data Cleaning

- Checked and handled **missing values**:
  - Filled `Price Per Unit`, `Quantity`, and `Total Spent` missing values based on logical imputations or dropped where required.
  - Filled `Discount Applied` nulls with `'False'`.

```python
df['Discount Applied'] = df['Discount Applied'].fillna('False')
```

- Converted `Transaction Date` to proper datetime format:

```python
df['Transaction Date'] = pd.to_datetime(df['Transaction Date'], format='%d-%m-%Y', errors='coerce')
```

---

## 📊 Exploratory Data Analysis (EDA)

### 1. Monthly Revenue Trend

- Grouped data by month and visualized total revenue.

```python
monthly_sales = df.groupby(df['Transaction Date'].dt.to_period('M'))['Total Spent'].sum()
monthly_sales.plot(kind='line', marker='o')
```

---

### 2. Revenue Distribution by Product Category

```python
category_revenue = df.groupby('Category')['Total Spent'].sum()
category_revenue.plot(kind='pie', autopct='%1.1f%%', startangle=90)
```

---

### 3. Top 10 Items by Revenue

```python
top_items = df.groupby('Item')['Total Spent'].sum().sort_values(ascending=False).head(10)
sns.barplot(x=top_items.values, y=top_items.index)
```

---

### 4. Payment Method Distribution

```python
df['Payment Method'].value_counts().plot.pie(autopct='%1.1f%%', startangle=90)
```

---

### 5. Impact of Discounts on Sales

```python
sns.boxplot(x='Discount Applied', y='Total Spent', data=df)
```

---

### 6. Revenue by Location

```python
location_sales = df.groupby('Location')['Total Spent'].sum().sort_values(ascending=False)
sns.barplot(x=location_sales.values, y=location_sales.index)
```

---

### 7. Quantity Sold per Category

```python
category_quantity = df.groupby('Category')['Quantity'].sum().sort_values()
sns.barplot(x=category_quantity.values, y=category_quantity.index)
```

---

## 🛠️ Tools Used

- Python (pandas, matplotlib, seaborn)
- Jupyter Notebook / VSCode
- Git and GitHub

---

## 📈 Insights

- Certain categories/items contribute significantly more to total revenue.
- Discounts slightly influence customer spending behavior.
- Some locations outperform others in total sales volume.

---

## 📎 Future Work

- Build an interactive dashboard using Plotly or Power BI.
- Predictive analysis: Forecast sales or recommend items.
- Customer segmentation based on purchase behavior.

---
