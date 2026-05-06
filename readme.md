This is GenAI Beginners Guide to get started
  
## Basics of Pandas (from Basics_Pandas/pandas_test.ipynb)

This section summarizes basic pandas operations demonstrated in the notebook:

### 1. Creating a DataFrame
```python
import pandas as pd
df = pd.DataFrame({
	'Name': ['A','B','C','D','E','F','G','H'],
	'Age': [23,45,31,35,62,18,29,40],
	'Gender': ['M','F','M','F','F','M','M','F'],
	'Salary': [50000,60000,55000,65000,70000,40000,52000,58000],
	'Department': ['HR','IT','IT','HR','Finance','IT','HR','Finance']
})
```

### 2. Viewing Data
- `df.head()` : First 5 rows
- `df.tail()` : Last 5 rows
- `df.shape` : Shape (rows, columns)
- `df.columns` : Column names
- `df.index` : Row indices

### 3. Data Information
- `df.info()` : Data types and non-null counts
- `df.describe()` : Statistical summary
- `df.memory_usage()` : Memory usage
- `df.dtypes` : Data types of columns

### 4. Selecting Data
- `df[['Name','Salary']]` : Select specific columns
- `df.loc[0:3, ['Name','Salary']]` : Select rows by label
- `df.at[1,'Name']` : Value at row 1, column 'Name'

### 5. Filtering Data
- `df[df['Age'] < 30]` : Rows where Age < 30
- `df[(df['Age'] > 30) & (df['Salary'] > 50000)]` : Multiple conditions
- `df[df['Name'].str.contains('B')]` : Name contains 'B'
- `df.query('Age > 30 & Salary > 50000')` : Query method
- `df.query('Age > 30 and Gender == "M"')` : Query with multiple conditions

### 6. Sorting Data
- `df.sort_values(by='Age')` : Sort by Age ascending
- `df.sort_values(by='Age', ascending=False)` : Sort by Age descending
- `df.sort_index(ascending=False)` : Sort by index descending

### 7. Creating New Columns
- `df['Bonus'] = df['Salary'] * 0.1` : New column based on Salary
- `df['Bonus'] = df.apply(lambda row: row['Salary'] * 0.2 if row['Department'] == 'HR' else row['Salary'] * 0.1, axis=1)` : Conditional new column

---
These examples cover the basics of pandas DataFrame creation, inspection, selection, filtering, sorting, and column operations. For more, see the notebook in `Basics_Pandas/pandas_test.ipynb`.
