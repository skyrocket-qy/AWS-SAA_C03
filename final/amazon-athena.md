# Amazon Athena

### Function
Serverless interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL.

### Use Case
- Querying logs stored in S3 (e.g., VPC Flow Logs, CloudTrail logs).
- Ad-hoc analysis of data lakes stored in S3 without managing servers.

### Tips
- Pay-per-query (data scanned).
- Use columnar formats like Parquet/ORC and partition data to save costs.
- Serverless, no infrastructure to manage.
