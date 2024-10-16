# Apache Spark Transformations and Actions

## Transformations
Transformations return a new RDD/DataFrame but are **lazy**, meaning they are not immediately executed. They build up a plan for execution which is triggered by actions.

| **Transformation**  | **Description**                                                                 |
|---------------------|---------------------------------------------------------------------------------|
| `map()`             | Applies a function to each element in the RDD/DataFrame.                         |
| `flatMap()`         | Similar to `map()`, but each element can map to 0 or more output elements.       |
| `filter()`          | Filters the RDD/DataFrame based on a condition.                                  |
| `distinct()`        | Removes duplicates from the RDD/DataFrame.                                       |
| `union()`           | Combines two RDDs/DataFrames, preserving duplicates.                             |
| `intersection()`    | Returns only the elements present in both RDDs/DataFrames.                       |
| `subtract()`        | Returns elements from one RDD not present in another RDD.                        |
| `cartesian()`       | Returns the Cartesian product of two RDDs.                                       |
| `groupBy()`         | Groups the data in the RDD/DataFrame based on a key or condition.                |
| `sortBy()`          | Sorts an RDD/DataFrame by a key or function.                                     |
| `join()`            | Joins two RDDs/DataFrames based on a key.                                        |
| `coalesce()`        | Reduces the number of partitions in an RDD/DataFrame (typically used for optimization). |
| `repartition()`     | Increases or decreases the number of partitions.                                 |
| `sample()`          | Returns a sample subset of an RDD/DataFrame.                                     |
| `mapPartitions()`   | Similar to `map()`, but works with entire partitions of the RDD.                 |
| `withColumn()`      | Adds a new column or updates an existing column in a DataFrame.                  |
| `select()`          | Selects a subset of columns in a DataFrame.                                      |
| `selectExpr()`      | Runs SQL expressions on selected columns in a DataFrame.                         |
| `agg()`             | Performs an aggregate function on a DataFrame.                                   |
| `filter()`          | Returns rows that match a given condition in a DataFrame.                        |
| `where()`           | Similar to `filter()`, applies a condition to select rows in a DataFrame.        |
| `drop()`            | Removes specified columns from a DataFrame.                                      |
| `limit()`           | Limits the number of rows in a DataFrame.                                        |
| `distinct()`        | Removes duplicate rows from a DataFrame.                                         |
| `groupByKey()`      | Groups an RDD based on the key and returns a dataset of key-value pairs.         |

## Actions
Actions trigger the execution of transformations and either return results to the driver or perform some output operation like writing to storage.

| **Action**           | **Description**                                                                 |
|----------------------|---------------------------------------------------------------------------------|
| `collect()`          | Returns all elements of the RDD/DataFrame to the driver.                         |
| `count()`            | Counts the number of elements in the RDD/DataFrame.                              |
| `take(n)`            | Returns the first `n` elements of the RDD/DataFrame.                             |
| `first()`            | Returns the first element of the RDD/DataFrame.                                  |
| `reduce()`           | Aggregates the elements of the RDD using a function.                             |
| `foreach()`          | Applies a function to each element of the RDD without returning anything.        |
| `saveAsTextFile()`   | Saves the RDD/DataFrame to a text file.                                          |
| `countByKey()`       | Counts the number of elements for each key in an RDD of key-value pairs.         |
| `lookup()`           | Returns the list of values associated with a given key.                          |
| `saveAsHadoopFile()` | Saves the RDD as a Hadoop file.                                                  |
| `saveAsSequenceFile()`| Saves the RDD as a sequence file.                                               |
| `takeSample()`       | Returns a sample subset of the RDD.                                              |
| `show()`             | Displays the first 20 rows (by default) of a DataFrame.                          |
| `write()`            | Writes a DataFrame to external storage (e.g., Parquet, JSON, CSV).               |
| `save()`             | Saves a DataFrame to an external source.                                         |
| `countByValue()`     | Counts the occurrences of each distinct element in an RDD.                       |
| `max()`              | Returns the maximum element in an RDD/DataFrame.                                 |
| `min()`              | Returns the minimum element in an RDD/DataFrame.                                 |
| `mean()`             | Returns the mean of elements in an RDD/DataFrame.                                |
| `sum()`              | Returns the sum of elements in an RDD/DataFrame.                                 |

## Key Points:
- **Transformations** are **lazy**; they don’t execute until an action is called.
- **Actions** trigger execution and typically either return data to the driver or save it to external storage.
