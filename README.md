# bigdata_analysis

*CAMPANY*: CODTECH IT SOLUTIONS

*NAME*: POLU AKHILA

*INTERN ID*: CT04DZ2019

*DOMAIN*: DATA ANALYTICS

*DURATION*: 4 WEEKS

*MENTOR* : NEELA SANTOSH


The notebook begins by installing and importing the PySpark library, which is an open-source framework for distributed data processing. PySpark allows handling of very large datasets that cannot fit into memory on a single machine by distributing computations across clusters. The installation command !pip install pyspark ensures that PySpark is available in the Colab environment. Following that, the SparkSession class is imported from the pyspark.sql module. This class is the entry point for working with DataFrames in Spark, similar to how a connection works in SQL. The notebook creates a SparkSession object using SparkSession.builder.appName('Pyspark').getOrCreate(). The appName method assigns a name to the session, and getOrCreate ensures either a new session is created or an existing one is returned.
Next, the notebook loads data into a Spark DataFrame. The dataset used here is student_data.csv, which is stored in the Colab environment under /content/student_data.csv. The function spark.read.csv() is used for reading CSV files, with header=True to treat the first row as column names and inferSchema=True to automatically detect data types for each column. After reading the file, the command df.show(3) displays the first three rows of the DataFrame. This is similar to the head() function in pandas and helps in getting a quick look at the dataset. The df.printSchema() command shows the schema of the DataFrame, listing columns, their data types, and whether they allow null values. This is crucial in big data processing because Spark works with strongly typed schemas.
The notebook then performs some exploratory analysis. The df.count() command returns the total number of rows in the dataset, while len(df.columns) counts the number of columns. Together, these give a sense of the dataset size. Next, the df.describe().show() function computes descriptive statistics such as mean, standard deviation, minimum, and maximum for numeric columns. This provides useful insights into the distribution of the data. In addition, the column names are retrieved using df.columns, which lists all available fields in the dataset. At one point, the data is converted into a pandas DataFrame using df.toPandas(). This is done to access specific Python and pandas functionalities such as extracting unique values. For example, df.toPandas()['freetime'].unique() returns the unique categories in the "freetime" column, and len(...) counts how many distinct values exist.
Another set of operations in the notebook demonstrates how to select and manipulate columns. The command df.select('school').show() extracts just the "school" column, while selecting multiple columns like ['Mjob','Fjob'] allows comparison of parents’ jobs. A new column is also created with df.withColumn('new_studytime', df.studytime + 2). Here, the withColumn method is used to add a transformed version of an existing column. Specifically, two hours are added to the studytime column, producing a new column named new_studytime. Finally, displaying the DataFrame again with df.show() confirms the successful addition of this new feature.
Overall, this notebook is designed to introduce PySpark basics for big data analysis. It covers starting a Spark session, reading and inspecting data, performing descriptive statistics, selecting columns, and creating new derived columns. Each operation demonstrates how Spark DataFrames offer a distributed, scalable alternative to pandas DataFrames, enabling processing of large datasets efficiently. Even though the dataset used here (student data) may be small, the techniques illustrated are directly applicable to very large datasets. This notebook helps beginners become comfortable with PySpark syntax, while reinforcing fundamental big data operations that form the backbone of data engineering and analysis pipelines.

OUTPUT:
<img width="1920" height="864" alt="Image" src="https://github.com/user-attachments/assets/55c4abcd-fa12-4b0d-affd-bd46bd4912d4" />

<img width="1920" height="864" alt="Image" src="https://github.com/user-attachments/assets/d7aba016-8121-4bd1-9e72-9a07478563bc" />

<img width="1465" height="864" alt="Image" src="https://github.com/user-attachments/assets/1d1cd73c-6f49-44d9-b3f1-819ad679669a" />

<img width="1729" height="856" alt="Image" src="https://github.com/user-attachments/assets/8564310c-63e7-4a6b-8441-a5d9b5b2d137" />

<img width="1815" height="865" alt="Image" src="https://github.com/user-attachments/assets/610cc2f2-b384-46c3-bd3a-f36687999bd6" />
