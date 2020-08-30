# pandas
- To load the pandas package and start working with it, import the package. The community agreed alias for pandas is pd, so loading pandas as pd is assumed standard practice for all of the pandas documentation.

### pandas data table representation¶

![pand](https://pandas.pydata.org/pandas-docs/stable/_images/01_table_dataframe1.svg)
```
In [2]: df = pd.DataFrame({
   ...:     "Name": ["Braund, Mr. Owen Harris",
   ...:              "Allen, Mr. William Henry",
   ...:              "Bonnell, Miss. Elizabeth"],
   ...:     "Age": [22, 35, 58],
   ...:     "Sex": ["male", "male", "female"]}
   ...: )
   ...: 

In [3]: df
Out[3]: 
                       Name  Age     Sex
0   Braund, Mr. Owen Harris   22    male
1  Allen, Mr. William Henry   35    male
2  Bonnell, Miss. Elizabeth   58  female
```

- A DataFrame is a 2-dimensional data structure that can store data of different types (including characters, integers, floating point values, categorical data and more) in columns. It is similar to a spreadsheet, a SQL table or the data.frame in R.

![pand](https://pandas.pydata.org/pandas-docs/stable/_images/01_table_series.svg)

## How do I select a subset of a DataFrame?¶
#### How do I select specific columns from a DataFrame?¶


![pand](https://pandas.pydata.org/pandas-docs/stable/_images/03_subset_columns.svg)

```
In [4]: ages = titanic["Age"] 
In [5]: ages.head()
Out[5]: 
0    22.0
1    38.0
2    26.0
3    35.0
4    35.0
Name: Age, dtype: float64 
```
*Each column in a DataFrame is a Series. As a single column is selected, the returned object is a pandas Series. We can verify this by checking the type of the output:*

```
In [6]: type(titanic["Age"])
Out[6]: pandas.core.series.Series
```
```
In [1]: import pandas as pd

In [2]: import matplotlib.pyplot as plt

```
```
In [3]: air_quality = pd.read_csv("data/air_quality_no2.csv",
   ...:                           index_col=0, parse_dates=True)
   ...: 

In [4]: air_quality.head()
Out[4]: 
                     station_antwerp  station_paris  station_london
datetime                                                           
2019-05-07 02:00:00              NaN            NaN            23.0
2019-05-07 03:00:00             50.5           25.0            19.0
2019-05-07 04:00:00             45.0           27.7            19.0
2019-05-07 05:00:00              NaN           50.4            16.0
2019-05-07 06:00:00              NaN           61.9             NaN
```
```
In [5]: air_quality.plot()
Out[5]: <matplotlib.axes._subplots.AxesSubplot at 0x7fe2a79fdeb0>
```

![pand](https://pandas.pydata.org/pandas-docs/stable/_images/04_airqual_quick.png)
*With a DataFrame, pandas creates by default one line plot for each of the columns with numeric data.*