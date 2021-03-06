# General Information
Pywasher will make it easier to clean data and prepare it for analysis.

```python
import pywasher
```

If you wish to use this cleaner locally for testing purposes you can install it using:
```bash
pip install pywasher as pw
```

Now the interface is accessible in your code by prefixing with 'pw'.

# Exposed Classes
In this section all the available functions of the module will be described.

## Column based

### explore_datatypes
The explore_datatypes function returns the index, datatype, columnname and datatype given by pandas for each column in the dataframe. 
The difference between the datatype and the datatype by pandas is that the datatype is ignore the datatype of empty values and gives a more general datatype (string, number, datetime, boolean, list)
```python
df.pw.explore_datatypes
```

### column_merge
The column_merge function merges all the given columns. It adds the values of the column if the first column is empty. If delete is True the columns that will be added will be deleted. 
```python
df.pw.column_merge([columns], delete = False)
```

### column_to_numeric
The numbering checks if all the values in the given columns can be converted to an float or integer. If this is possible it will convert every value in the column to an int or float. If the force value is True it will change every cell it cant convert to numbers to NA
It returns an dataframe in which the values of the given columns are made into numbers.
```python
df.pw.column_to_numeric([columns], force = False)
```

### explore_column_names
The explore_column_names functions shows how the column names will be changed if they will be send towards the Clappform database
```python
df.pw.explore_columnnames
```

### replace_double_column_names
The explore_column_names function adds numbers to the columnnames of columnnames which are multiple times in the dataframe
```python
df.pw.replace_double_column_names
```

### sorting
The sorting function changes the order of the columns to an alphabetic order
```python
df.pw.sorting()
```

### explore_double
The explore_double function shows all the double columns in a dataframe
```python
df.pw.explore_double()
```

### cleaning
The cleaning functions cleans the dataframe. It removes double spaces, replaces spaces with underscores in the columns and makes sure the column names are valid variable names for Javascript
```python
df.pw.cleaning()
```

## Cell based
### list_splitter
The list_splitter function returns a dataframe in which all the values of the chosen columns are given a column. These columns consist of True or False based on the values in the chosen columns. 
The input is an list with all the names of the columns which need to be split, the output is a modified dataframe
```python
df.pw.list_splitter([columns])
```