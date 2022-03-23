# Apache Spark

Apache Spark is a multi-language engine for executing data engineering, data science, and machine learning on single-node machines or clusters. Apache Spark can be used to process batch or streaming data and to analyze data using SQL syntax. It is also built with some machine learning modules. The language compability of Apache Spark are Python, SQL, Scala, Java, and R.

## Installation

1. Go to [download page](https://spark.apache.org/downloads.html) of Apache Spark.
2. Choose the Spark release and package type you want to download.
3. Click the download link, this will redirect the browser to the closest download mirror. Then, save the `.tgz` file.
4. Open a terminal and go to your download folder.
5. Extract the file using following command, `tar -xvzf spark-3.2.1-bin-hadoop2.7.tgz`.
6. (Optional) Rename the extracted folder to `spark` and move to your home directory.

## Configuring environment variables

1. Open the `bashrc` file using youtr preferred text editor via command line, `sudo gedit ~/.bashrc`.
2. Add the following information to the file and save it. The information will enable us to accessing spark command everywhere.
![bashrc-spark](/img/bashrc-spark.png)
3. Make a final change by typing `source ./bashrc`.

## How to run Spark

Open Spark by using one of this following command in the terminal:
- `pyspark` to open PySpark.
- `spark-shell` to open Spark with Scala language.
- `sparkR` to run Spark with R language.
- `spark-sql` to run queries using SQL.
- `spark-submit` to run Spark application, either a Python file or JAR file.