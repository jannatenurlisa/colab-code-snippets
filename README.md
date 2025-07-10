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










