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

# 2.2 Statistics
Descriptive statistics summarize and describe dataset characteristics, and are great to give an overview of your data to whomever is approaching your work.
You could calculate these statistics by hand, but `pandas` already offers methods to call them directly from your `df`.

```{code-cell} ipython3
:tags: [remove-input]
import pandas as pd
df = pd.read_csv("./data/child_num_skills.csv")  
```

## 2.1 Measures of Central Tendency

```{code-cell}
mean = df["addit1"].mean()     # Arithmetic mean
median = df["addit1"].median() # Middle value

print(f"Mean: {mean}")
print(f"median: {median}")
```

## 2.2 Measures of Dispersion

```{code-cell}
std_dev = df["addit1"].std()   # Standard deviation
variance = df["addit1"].var()  # Variance
quantiles = df["addit1"].quantile([0.25, 0.5, 0.75])  # Quartiles

print(f"Standard deviation: {std_dev}")
print(f"Variance: {variance}")
print(f"Quantiles: {quantiles}")
```

## 2.3 `.describe()` method
Alternatively, `pandas` offer us a convenient way to get a first statistical summary. The `count` column will tell you how many values were used for the calculations in each column.

```{code-cell}
df.describe()
```

## 2.3 Using `scipy.stats`

The `scipy.stats` module provides extended statistical functions.

```python
from scipy import stats

stats.skew(df["addit1"])       # Measure of asymmetry
stats.kurtosis(df["addit1"])   # Measure of tailedness
```