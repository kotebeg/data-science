# Section 5: Pandas
## 29. Pandas - Useful Methods - Statistical Information and Sorting
Here are 20 questions, including both conceptual and coding questions, about the text:

### Conceptual Questions:
1. What is the purpose of the `df.describe()` method in Pandas?
2. How can you sort a DataFrame by multiple columns in Pandas?
3. What does the `ascending` parameter in `sort_values()` control?
4. How does `idxmax()` and `idxmin()` help when analyzing a DataFrame?
5. What does `df.corr()` return, and what does it represent?
6. Why is it important to understand correlations between columns in a dataset?
7. How can you use the `value_counts()` method, and for what type of data is it useful?
8. What's the difference between `unique()` and `nunique()` in Pandas?
9. When would you use the `replace()` method instead of the `map()` method in a DataFrame?
10. How do the `duplicated()` and `drop_duplicates()` methods work?
11. What does the `between()` method allow you to do with a DataFrame?
12. How do `nlargest()` and `nsmallest()` differ from just using `sort_values()`?
13. When would it be useful to use `df.sample()` on a DataFrame?
14. What is the main difference between using `sample(n=5)` and `sample(frac=0.1)`?

### Coding Questions:
15. Write a code snippet to sort the "total_bill" column in descending order.
16. How would you find the row in a DataFrame with the highest "tip" value using `idxmax()`?
17. Using Pandas, write a code snippet that shows how to replace all instances of "female" with "F" and "male" with "M" in a DataFrame column.
18. Write a code snippet to drop duplicated rows in a DataFrame.
19. How can you filter a DataFrame to only include rows where the "total_bill" is between 10 and 50, inclusive?
20. Write a code snippet to find the 5 smallest values in the "tip" column.


### more complex Coding Questions:

1. Write a Pandas script that reads a CSV file, sorts the DataFrame by multiple columns (`tip` and `size`), and returns the top 5 rows.
2. Using `df.corr()`, create a heatmap of the correlation matrix for numeric columns in a DataFrame.
3. How would you filter a DataFrame to return rows where the `tip` value is in the top 10% of the entire dataset?
4. Write a function that takes a Pandas DataFrame and returns the row with the smallest `total_bill` value using both `nsmallest()` and `idxmin()`. 
5. Using Pandas, how can you create a copy of a DataFrame but only with rows that do **not** have any duplicated values in the `tip` column?
6. How would you compute the correlation coefficient between `tip` and `total_bill` for a subset of the data where the `total_bill` is greater than 20?
7. Write a Pandas script that replaces all null values in a DataFrame's `total_bill` column with the column's median, but only if `total_bill` has at least 10 null values.
8. Create a function that takes a DataFrame and a column name, and returns a new DataFrame where the column values are sorted in descending order, along with their index locations (`idxmax`).
9. Using the `between()` method, write a Pandas function that returns all rows where the `size` column is between 2 and 5 (inclusive), but only if the `total_bill` is greater than the dataset's average.
10. Write a function that takes a DataFrame and column name and returns the number of unique values in that column, using the `unique()`, `nunique()`, and `value_counts()` methods.
11. Write a script that replaces values in the `sex` column (where "female" becomes "F" and "male" becomes "M"), but instead of replacing them directly, uses a mapping dictionary passed as an argument to the function.
12. Implement a Pandas script that drops rows where the `size` and `tip` columns have the exact same value for multiple rows, leaving only the first occurrence.
13. Write a function that selects a random sample from a DataFrame, but ensures that the sampling maintains a proportionate distribution of values from the `day` column (i.e., stratified sampling).
14. Using Pandas, write a script that sorts by `tip` in descending order, then selects the largest 10 rows and returns the average `total_bill` for these rows.
15. Write a Pandas function that performs a left join between two DataFrames, filters for rows where the `total_bill` in the left DataFrame is less than the `total_bill` in the right DataFrame, and returns the resulting DataFrame. 


## 30. Missing Data - Overview
The main subjects covered in the lecture on missing data are:

1. **Overview of Missing Data Options**: The instructor discusses three main approaches—keeping, removing, or replacing missing data.
2. **Impact on Models**: Missing data can affect machine learning and statistical methods.
3. **Pandas Handling of Missing Data**: Using NaN, pd.NaT for timestamps, and handling missing values with specific methods in pandas.
4. **Pros and Cons**: Discussion on the advantages and drawbacks of each method.
5. **Feature Engineering and Domain Knowledge**: Importance of domain expertise when deciding on handling missing data.


### Conceptual Questions:
1. What are the three main options for dealing with missing data?
2. Why can missing data cause problems for machine learning models?
3. How does pandas represent missing values by default?
4. What does the NaN value in pandas stand for?
5. What is pd.NaT in pandas used for?
6. Why might pd.NaT be a useful replacement for NaN in some cases?
7. What are the pros of keeping missing data as NaN?
8. What are the cons of leaving missing data as NaN?
9. Why might a NaN value sometimes represent a zero?
10. What are the pros of removing missing data from a dataset?
11. What are the cons of dropping rows or columns with missing data?
12. How can dropping a feature column limit future models?
13. When does it make sense to drop a row with missing data?
14. When is it more appropriate to drop a column with missing data instead of rows?
15. What are the advantages of filling in missing data?
16. What are the cons of filling in missing data?
17. What does it mean to fill missing data with an interpolated value?
18. Why is filling missing data with a guess sometimes risky?
19. In what situations might it be appropriate to fill missing data with zeros?
20. What are the challenges associated with making assumptions when filling missing data?


















## statistics

## Standard Deviation (STD): A Measure of Spread

**Standard deviation** is a statistical measure that quantifies the amount of variation or dispersion of a set of data values from their mean. In simpler terms, it tells you how much the data points are spread out from the average.

### Key Points:

* **High standard deviation:** Indicates that the data points are widely spread out from the mean.
* **Low standard deviation:** Indicates that the data points are clustered closely around the mean.

### How is it calculated?

The standard deviation is calculated by finding the square root of the variance. Variance is the average squared distance of each data point from the mean.

### Why is it important?

Standard deviation is a crucial tool in various fields, including:

* **Statistics:** To analyze data distribution and make inferences.
* **Finance:** To assess risk and volatility in investments.
* **Quality control:** To monitor product consistency and identify outliers.
* **Research:** To evaluate the variability of experimental results.

### Example:

Consider two sets of test scores:

* **Set A:** 85, 88, 90, 92, 95
* **Set B:** 70, 80, 90, 100, 110

Both sets have the same mean (90), but Set B has a higher standard deviation because the scores are more spread out.

**In summary,** standard deviation is a valuable metric for understanding the distribution of data and making informed decisions based on that information.
 
**Would you like to see an example calculation or learn more about its applications in a specific field?**

