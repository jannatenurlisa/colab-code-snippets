# colab-data-snippets
A collection of useful code snippets for Colab and data analysis

### Upload a file to Colab
```py
from google.colab import files
uploaded = files.upload()
print(uploaded)
```
### Read CSV & Summary
```py
# Import the pandas library for data handling
import pandas as pd

# Read a CSV file from the given path and store it in a DataFrame
df = pd.read_csv('/CSV file location')

# Show the first 5 rows of the dataset
df.head()

# Display info about the dataset (column names, data types, non-null counts)
df.info()

# Get summary statistics for numerical columns (like mean, min, max)
df.describe()

# Get a list of all column names in the dataset
df.columns.tolist()
```
### Drop columns with too many missing values
```py
# Drop column(s) with too many missing values
df.drop(columns=['column_name'], inplace=True)
```
### Drop rows with missing values 
```py
# Drop rows where key data is missing
df = df[df['column_name'].notnull()]
```
### Convert data types
```py
# Convert column to integer type (nullable)
df['column_name'] = df['column_name'].astype('Int64')
```
### Clean string column
```py
# Strip whitespace and standardize text
df['column_name'] = df['column_name'].str.strip().str.lower()
```


### Show summary statistics for all numeric columns in the DataFrame
```py
df.describe()

# Plot the count of unique values in a numeric column (e.g., release year)
# Replace 'numeric_column' with your own column name (e.g., 'releaseYear')
df['numeric_column'].value_counts().sort_index().plot(
    kind='bar',
    figsize=(15, 5)
)
```
### Get the top 10 rows sorted by a numeric score column (e.g., rating)
```py
# Replace 'score_column' with your own column name (e.g., 'imdbAverageRating')
top_items = df.sort_values(by='score_column', ascending=False).head(10)
```
### Count the most common values in a list-like text column (e.g., genres)
```py
from collections import Counter

# Count the most common items in a list-like text column
# Replace 'list_text_column' with your own column name (e.g., 'genres')
list_column = df['list_text_column'].dropna().str.split(', ')

# Flatten lists into a single list
flat_list = [item for sublist in list_column for item in sublist]

# Show the 10 most common items
Counter(flat_list).most_common(10)
```
### Plot a Histogram

```py
import seaborn as sns

# Plot a histogram of a numeric column
# Replace 'numeric_column' with your own column name (e.g., 'imdbAverageRating')
sns.histplot(df['numeric_column'], bins=20)
```




