# Data Manipulation and Visualization

## NumPy

- Core Object: ndarray (homogenous data type).

- Broadcasting Rules: Dimensions are compared element-wise from right to left. Two dimensions are compatible if they are equal OR one of them is 1.

- Vectorized Operations: Operating on entire arrays without explicit for loops.

```python
import numpy as np

arr = np.array([[1, 2, 3], [4, 5, 6]])
mean = arr.mean(axis=0)  # Column-wise mean -> [2.5, 3.5, 4.5]
```

<br/>

## Pandas

- Core Objects: Series (1D) and DataFrame (2D).

- Indexing: .loc[] (label-based) vs. .iloc[] (integer-position-based).

```python
import pandas as pd

df = pd.read_csv("data.csv")
df.dropna(inplace=True)                        # Drop missing values
df['feature'] = df['feature'].fillna(df['feature'].median())
grouped = df.groupby('category')['target'].mean() # GroupBy aggregation
```

<br/>

## 3. Matplotlib & Seaborn

- Matplotlib: Low-level, explicit control (`plt.plot()`, `plt.xlabel()`, `plt.show()`).

- Seaborn: High-level statistical visualization (`sns.scatterplot()`, `sns.heatmap()`).

<br/>

Common Exam Pitfalls

- Shape Mismatches in NumPy: Adding arrays with incompatible shapes (e.g., `shape (3, 3)` and `shape (2,)`) throws a broadcasting error.

- Views vs. Copies in Pandas: Chained indexing (`df['col'][0] = 5`) triggers SettingWithCopyWarning. Use `df.loc[0, 'col'] = 5` instead.
