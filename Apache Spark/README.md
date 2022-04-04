# Apache Spark

Apache Spark is a multi-language engine for executing data engineering, data science, and machine learning on single-node machines or clusters. Apache Spark can be used to process batch or streaming data and to analyze data using SQL syntax. It is also built with some machine learning modules. The language compability of Apache Spark are Python, SQL, Scala, Java, and R.


## Installation

1. Go to [download page](https://spark.apache.org/downloads.html) of Apache Spark.
2. Choose the Spark release and package type you want to download.
3. Click the download link, this will redirect the browser to the closest download mirror. Then, save the `.tgz` file.
4. Open a terminal and go to your download folder.
5. Extract the file using following command. 
    
    ```bash
    tar -xvzf spark-3.2.1-bin-hadoop2.7.tgz
    ```

6. (Optional) Rename the extracted folder to `spark` and move to your home directory.


## Configuring environment variables

1. Open the `bashrc` file using your preferred text editor via command line. 
    
    ```bash
    sudo gedit ~/.bashrc
    ```

2. Add the following information to the file and save it. The information will enable us to accessing spark command everywhere.

    ![bashrc-spark](/img/bashrc-spark.png)

3. Make a final change by typing 
    
    ```bash
    source ./bashrc
    ```

## How to run Spark

Open Spark by using one of this following command in the terminal:
- `pyspark` to open PySpark.
- `spark-shell` to open Spark with Scala language.
- `sparkR` to run Spark with R language.
- `spark-sql` to run queries using SQL.
- `spark-submit` to run Spark application, either a Python file or JAR file.

## Running PySpark on Jupyter Notebook

In the shell, install `findspark` by typing `pip install findspark`. After the installation finished, open Jupyter Notebook and write the following code in the first cell.

```python
import findspark

findspark.find()
findspark.init()
```

The `findspark.find()` command will find a local spark installation e.g. `$SPARK_HOME`, and print it.

While the `findspark.init()` command initialize the spark by adding pyspark to `sys.path`, thus make pyspark importable. More details of `findspark` package can be seen using `help(findspark)`.