---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---
# 2. Data Handling with `pandas`

## 2.1 Loading Data

```python
import pandas as pd

df = pd.read_csv("data/sample.csv")  # Replace with actual path
df.head()
```

## 2.2 Exploring Data

```python
df.info()
df.describe()
df.columns
df.dtypes
```

## 2.3 Handling Missing Data

```python
df.isna().sum()             # Count missing values
df = df.dropna()            # Drop rows with missing values
df['column'] = df['column'].fillna(value)  # Fill missing values
```

## 2.4 Filtering and Subsetting

```python
df_filtered = df[df["age"] > 30]
df_subset = df[["age", "income"]]
```

## 2.5 Grouping and Aggregation

```python
grouped = df.groupby("gender")["income"].mean()
df.groupby("group").agg({"score": ["mean", "std"]})
```
