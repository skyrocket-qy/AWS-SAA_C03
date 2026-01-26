# AWS Glue

**AWS Glue** is a serverless data integration service (ETL) used to discover and prepare data for analytics.

### Key Exam Points
- **Data Catalog**: Central **metadata** repository (Hive-compatible metastore) for Athena, EMR, and Redshift.
- **Crawlers**: Automatically scan data stores (S3, JDBC) to infer schema and populate the Data Catalog.
- **ETL Jobs**: Automatically generates Python/Scala code to transform data; charges only for resources used.
- **Job Bookmarks**: Tracks state to process only **new data** (incremental ETL), avoiding reprocessing.
- **Glue DataBrew**: Visual tool for cleaning/normalizing data without writing code.
