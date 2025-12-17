# AWS Glue

AWS Glue is a serverless data integration service that makes it easy to discover, prepare, and combine data for analytics, machine learning, and application development.

## Key Components

### 1. Data Catalog
*   **Concept**: A central metadata repository. It contains table definitions, job definitions, and other control information to manage your Glue environment.
*   **Hive Compatible**: Serves as a drop-in replacement for the Apache Hive Metastore (e.g., for Athena or EMR).

### 2. Crawlers
*   **Concept**: A program that connects to a data store (S3, RDS, DynamoDB), progresses through a prioritized list of classifiers to determine the schema for your data, and creates metadata tables in the **Data Catalog**.

### 3. ETL Jobs (Extract, Transform, Load)
*   **Concept**: Managed infrastructure to run your ETL logic.
*   **Engine**: Automatically generates **Python** or **Scala** code (Apache Spark) to transform data.
*   **Serverless**: You pay only for the resources used while the job runs.

## Key Features

*   **Glue DataBrew**: Visual data preparation tool for data analysts/scientists to clean and normalize data without writing code.
*   **Event-Driven**: Can trigger jobs based on events (e.g., new file in S3) or on a schedule.
*   **Data Quality**: Automatically measures and monitors the data quality of your data lakes and pipelines.

## Use Case Example
1.  **S3 Bucket** contains raw CSV logs.
2.  **Glue Crawler** scans S3, infers schema, and creates table in **Data Catalog**.
3.  **Athena** uses Data Catalog to run SQL queries on S3 data immediately.
4.  **Glue ETL Job** converts CSV to Parquet and loads it into **Redshift** for high-performance warehousing.
