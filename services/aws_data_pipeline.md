# AWS Data Pipeline

**AWS Data Pipeline** orchestrates and automates data movement and transformation between AWS services and on-premises sources.

### Key Exam Points
- **Use Case**: Scheduled ETL jobs (e.g., RDS to Redshift, DynamoDB to S3).
- **On-Premises**: Supports on-premises sources via **Task Runner**.
- **Execution**: Uses EC2 or EMR for data processing tasks.
- **Legacy**: For new workloads, consider **AWS Glue** (serverless ETL) or **Step Functions** (general orchestration).
- **Automation**: Handles retries and sends failure notifications via SNS.
