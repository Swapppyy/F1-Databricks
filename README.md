# Analyzing F1 Dominant Drivers and teams using Databricks(PySpark)

What is this pipeline exactly doing?

1. Extracting data from Yahoo finance API.
2. Storing the raw data into an Minio bucket using Airflow.
3. Transforming the data for Analytics using PySpark (which runs seperately on the docker container).
4. Load the transformed data into Postgres for analytics.
5. Using Metabase as a service through Docker for analytics.

## Architecture
![Architecture](assets/F1.jpg)
1. **Yahoo API**: Source of the stock data.
2. **Apache Airflow**: Orchestrates the ETL process and manages task distribution. For this Airflow congifurations i am using Astronomer to setup my Airflow.
3. **Spark**: Transforming all the data fetched from the API.
4. **Postgres**: Storing all the transformed data from the spark job.
5. **Metabase**: Analytics platform for the data stored after the transformation.

## Dashboard
