# Data Preprocessing Report

## Data Preprocessing Summary
[Click here for the Data Preprocessing File](08-wrangling.ipynb)

### Missing Data
We encountered types of missing data as the first, but widely significant topic. There are 3 types of missing data: **MCAR (missing completely at random), MAR (missing at random) and MNAR (missing not at random)**. Each of those types needs a specific and suitable approach.
1. **Identify** - using *isna(), info(), isnull()*. We can also **visualize** the number of missing data by *seaborn.heatmap*, which shows light cells as nan values.
2. **Analyze** - we check whether the missingness of our data impact or correlate with other variables. We can use several *missigno* functions to visualize and find out the reason (for example *matrix()*).
3. **Decide** - we can remove all rows with nan by dropna(). It is an easy and fast solution, but also very straight forward. Another way is to drop only those rows which are irrelevant for our analysis. We can try imputing missing data - by a fixed value (using *fillna()*) or by guessing (finding similar observations with non-missing values). **Hot Deck Imputation (Random or Nearest Neighbour)** maybe useful when searching for a candidate for a nan value.

### Dirty Data
To handle Dirty Data we can:
1. Make a list of rules which will be applied to our data set - this way we can determine number of errors and summarize them.
2. Error correction - we replace data that is not correct with NaN value.
3. Merging - it allows to see how variables relate and interact (using pandas *pd.merge()*). There are several ways of merging:
    - inner
    - left
    - right
    - outer
4. Reshaping data - transforming from one format to another format.

### Tidy Data
Principles:
1. Each variable forms a column.
2. Each observation forms a row.
3. Each type of observational unit forms a table.

**Key goal** - each row represents an observation.

**Useful function** - pd.melt().

### Data Transformations
Transformation methods:
- **Z-score**
- **minmax**
- ***log, log + 1, sqrt, $x^2$, $x^3$***
- **Box - Cox**

### Data Categorization
Ways of binning:
- **Quantile Binning** - using *pd.qcut(data, q=4)* - 4 quantile-based bins
- **Equal - Width Binning**
- **Pretty Binning** - using *pd.qcut(data, bins=5)* - 5 equal-width bins
- **K-Means Binning** - K-Means clustering algorithm
- **Bag Clustering** 

## Data Cleansing Summary
[Click here for the Data Cleansing](Cleaning_Data_in_Python_live_session.ipynb)

In Data Cleansing file we have worked on practical exercies using functions described in Data Preprocessing File. Additionaly, some functions that we have found useful:
1. **value_counts()** - counts each differen value in a column
2. **str.replace(",")** - replaces strings in each column
3. **str.split("")** - splits column in two based on this string
4. **astype()** - converts types
5. **str.strip()** - removes specified string from each row in a column
6. **pd.to_datetime** - converts to a date time
7. **str.lower()** - lowercase a string
8. **replace()** - replaces values
Missigno visualization functions: 
1. **msno.matrix()**
2. **msno.bar()**
3. **msno.dendogram**
And pandas function to show the plot - **plt.show()**.

Worth noticing is the fact that we should not only care about missing values, but also be concerned about data *consistency*.