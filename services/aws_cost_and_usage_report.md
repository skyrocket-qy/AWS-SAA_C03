# AWS Cost and Usage Report (CUR)

The **AWS Cost and Usage Report (CUR)** is the most detailed and granular cost/usage data available.

### Key Exam Points
- **Granularity**: Most comprehensive data (hourly/daily, resource IDs, tags).
- **Delivery**: Reports are delivered to an **Amazon S3** bucket.
- **Analysis**: Use **Amazon Athena** (SQL), **Redshift**, or **QuickSight** (visuals) to analyze the raw data in S3.
- **Use Case**: Deep-dive cost analysis or integration with external BI tools.
