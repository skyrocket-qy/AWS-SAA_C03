# AWS Data Exchange vs. AWS Data Pipeline

### Comparison Overview
- **Data Exchange**: Used to acquire **third-party (external)** data from providers. Data is delivered to S3.
- **Data Pipeline**: Used to orchestrate and automate the movement/transformation of **internal** data (e.g., RDS to Redshift).

### Key Exam Points
- **Source**: Exchange = External vendors; Pipeline = Your own AWS infrastructure.
- **Modern Alternatives for Pipeline**: **AWS Glue** (ETL), **Step Functions** (Orchestration), or **Amazon MWAA** (Airflow).
- **Scenario**: Choose **Data Exchange** for buying data; choose **Data Pipeline/Glue** for moving your own data.
