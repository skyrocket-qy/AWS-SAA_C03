# AWS Data Pipeline

**AWS Data Pipeline** is a web service for orchestrating and automating the movement and transformation of data between different AWS compute and storage services, as well as on-premises data sources.

## Key Features
- **Data-Driven Workflows**: Define pipelines that specify data sources, destinations, and transformation logic.
- **Scheduling**: Run pipelines on a schedule (e.g., daily, hourly) or on-demand.
- **Fault Tolerance**: Automatically retries failed activities and sends notifications on failures.
- **Distributed Execution**: Uses EC2 instances or EMR clusters to run activities; can also use on-premises resources via Task Runner.
- **Preconditions**: Define conditions that must be met before an activity runs (e.g., data exists, time-based).

## Key Components
| Component | Description |
|-----------|-------------|
| **Pipeline** | The overall workflow definition |
| **Data Node** | Location of input/output data (S3, RDS, DynamoDB, Redshift) |
| **Activity** | An action to perform (CopyActivity, EmrActivity, SqlActivity, ShellCommandActivity) |
| **Schedule** | When and how often the pipeline runs |
| **Resource** | The compute resource that executes activities (EC2, EMR) |
| **Precondition** | A condition that must be true before an activity runs |

## Common Use Cases
- **ETL Workflows**: Extract data from RDS, transform with EMR, load into Redshift.
- **Log Processing**: Move logs from S3, process with EMR, store results.
- **Data Backup**: Scheduled backup of DynamoDB tables to S3.
- **Cross-Region Data Movement**: Copy data between S3 buckets in different regions.

## Pricing
- Pay based on the frequency and type of activities in your pipeline.
- No charge for the pipeline definition itself; you pay for the underlying resources (EC2, EMR, data transfer).

## Exam Tips
- **Legacy service**: AWS Data Pipeline is considered a legacy orchestration service; for new workloads, AWS recommends **AWS Step Functions** or **Amazon MWAA (Managed Workflows for Apache Airflow)**.
- Ideal for **scheduled, data-centric ETL jobs** across AWS services.
- Supports **on-premises data sources** via Task Runner installed on your servers.
- Differentiate from **AWS Glue** (serverless ETL with schema discovery) and **Step Functions** (general-purpose workflow orchestration).
