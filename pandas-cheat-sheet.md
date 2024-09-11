# Pandas Cheat Sheet

## Data Structures in Pandas

### Series (1-D)

Create a Series
```python
s = pd.Series([1, 3, 5, 7, 9])
print(s)
```
### DataFrame (2-D)

#### Creating DataFrames

From Dictionaries
```python
data = {
    'Name': ['John', 'Anna', 'Peter', 'Linda'],
    'Age': [28, 24, 35, 32]
}
df = pd.DataFrame(data)
print(df)
```

From Lists
```python
data = [['John', 28], ['Anna', 24], ['Peter', 35], ['Linda', 32]]
df = pd.DataFrame(data, columns=['Name', 'Age'])
print(df)
```

From CSV Files
```python
df = pd.read_csv('data.csv')
print(df.head())
```

#### Data Inspection

Viewing Data
```python
# Display the first 5 rows
print(df.head())

# Display the last 5 rows
print(df.tail())
```

Getting Data Info
```python
# Display DataFrame info
print(df.info())
```

Descriptive Statistics
```python
# Get descriptive statistics
print(df.describe())
```

#### Data Selection

Selecting Columns
```python
# Select a single column
print(df['Name'])
# Select multiple columns
print(df[['Name', 'Age']])
```

Selecting Rows
```python
# Select rows by index
print(df.iloc[0])  # First row
print(df.iloc[1:3])  # Second and third rows
# Select rows by label
print(df.loc[0])
```

Conditional Selection
```python
# Select rows based on condition
print(df[df['Age'] > 30])
```

#### Data Cleaning

Handling Missing Values
```python
# Fill missing values
df.fillna(0, inplace=True)
# Drop missing values
df.dropna(inplace=True)
```

Removing Duplicates
```python
# Remove duplicate rows
df.drop_duplicates(inplace=True)
```

#### Data Transformation

Adding New Columns
```python
# Add a new column
df['Salary'] = [50000, 60000, 70000, 80000]
print(df)
```

Applying Functions
```python
# Apply a function to a column
df['Age'] = df['Age'].apply(lambda x: x + 1)
print(df)
```

Merging Data
```python
# Merge DataFrames
df1 = pd.DataFrame({'Name': ['John', 'Anna'], 'Age': [28, 24]})
df2 = pd.DataFrame({'Name': ['John', 'Anna'], 'Salary': [50000, 60000]})
merged_df = pd.merge(df1, df2, on='Name')
print(merged_df)
```

#### Grouping and Aggregating

GroupBy
```python
# Group by a column
grouped_df = df.groupby('Age')
print(grouped_df.size())
```

Aggregation Functions
```python
# Aggregate data
print(df.groupby('Age')['Salary'].sum())
```

#### Data Visualization

Plotting with Pandas
```python
import matplotlib.pyplot as plt

# Plotting a column
df['Age'].plot(kind='bar')
plt.show()
```

### A Pandas coding example

```python
# Creating DataFrames
data = {
    'Name': ['John', 'Anna', 'Peter', 'Linda'],
    'Age': [28, 24, 35, 32]
}
df = pd.DataFrame(data)
print(df)

# Data Ispection
print(df.head())
print(df.info())
print(df.describe())

# Data Selection
print(df['Name'])
print(df.iloc[1:3])
print(df[df['Age'] > 30])

# Handling Missing Values
df.fillna(0, inplace=True)
print(df)

# Removing Duplicates
df.drop_duplicates(inplace=True)
print(df)

# Adding New Columns
df['Salary'] = [50000, 60000, 70000, 80000]
print(df)

# Applying Functions
df['Age'] = df['Age'].apply(lambda x: x + 1)
print(df)

# Merging Data
df1 = pd.DataFrame({'Name': ['John', 'Anna'], 'Age': [28, 24]})
df2 = pd.DataFrame({'Name': ['John', 'Anna'], 'Salary': [50000, 60000]})
merged_df = pd.merge(df1, df2, on='Name')
print(merged_df)

# Grouping Data
print(df.groupby('Age').size())

# Plotting Data
import matplotlib.pyplot as plt

df['Age'].plot(kind='bar')
plt.show()
```

