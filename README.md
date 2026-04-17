# Experiment 14: Data Binning and Data Formatting using Python

**Author:** Ronit Mehta  
**PRN:** 25070123094  

---


## AIM
To systematically transform and structure datasets by implementing Data Binning (categorizing continuous data) and Data Formatting (type conversion, string manipulation, and numerical rounding) using the Python Pandas library.

---

## Theory & Command Reference

Data transformation is a vital part of data preprocessing. It ensures that raw numerical data is categorized appropriately and text/numerical formats are standardized for analysis. Below are all the specific Pandas commands utilized in this experiment:

### 1. DataFrame Creation
* `pd.DataFrame(data)`: Converts a standard Python dictionary (where keys act as column headers and lists act as row values) into a structured Pandas DataFrame.

### 2. Data Binning (Discretization)
Data Binning groups continuous numerical data into discrete intervals ("bins") to create categorical features.
* `pd.cut(df['Column'], bins=[...], labels=[...])`: Segments, sorts, and maps continuous data values into distinct categories. 
  * *Example Usage:* Dividing `Price` into `[0, 10000, 30000, 60000]` assigned to labels `['Low', 'Medium', 'High']`.

### 3. Data Formatting & Type Conversion
Ensuring columns possess the correct data type is critical for avoiding operational errors.
* `df.dtypes`: Returns the current data type (e.g., `int64`, `float64`, `object`, `category`) for every column in the dataset.
* `df['Column'] = df['Column'].astype(float)`: Casts the data within a specific column to a new type (e.g., converting integer units sold to floating-point numbers). *Note: The result must be reassigned to the column to overwrite the memory.*

### 4. String Manipulation
Standardizing text data prevents mismatches caused by inconsistent capitalization.
* `df['Column'].str.upper()`: Converts all string values in the specified column to entirely UPPERCASE letters.
* `df['Column'].str.title()`: Converts string values to Title Case, capitalizing the first letter of each word (e.g., "the tiger" becomes "The Tiger").

### 5. Numerical Formatting
Rounding values ensures cleaner data presentation, especially for calculated metrics, distances, or currencies.
* `df['Column'].round(2)`: Rounds floating-point values in the targeted column to exactly 2 decimal places.

### 6. Sorting & Unique Values
Sorting data reveals extremes (highs and lows), while checking unique values confirms categorical operations were successful.
* `df.sort_values(by='Column')`: Sorts the entire DataFrame in ascending order (lowest to highest) based on the targeted column.
* `df.sort_values(by='Column', ascending=False)`: Sorts the DataFrame in descending order (highest to lowest) based on the targeted column.
* `df['Column'].unique()`: Returns an array of all distinct, unique categorical values present in a column.

---


## Conclusion
In this experiment, advanced data manipulation and formatting techniques were successfully implemented across two distinct datasets (Product Sales and Food Delivery Orders). Using the `pd.cut()` command, we executed continuous data binning on multiple variables—including Prices, Units Sold, Order Values, Delivery Times, and Distances—effectively categorizing them into manageable groups like "Fast", "Medium", and "Slow". Furthermore, we standardized the data structure by converting integer columns to floats using `.astype()`, manipulating string casing with `.str.upper()`, and rounding financial figures. Finally, sorting operations were applied to establish a logical sequence, ensuring the data is clean, formatted, and fully primed for analytical modeling.
