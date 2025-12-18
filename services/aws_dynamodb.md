# Amazon DynamoDB

**Amazon DynamoDB** is a fully managed, serverless, NoSQL database service that provides fast and predictable performance with seamless scalability.

## Backup and Recovery

### Point-in-Time Recovery (PITR)
- **Continuous Backups**: Once enabled, PITR provides continuous backups of your DynamoDB table data.
- **Retention**: Data is backed up for the last **35 days**.
- **Restore Granularity**: You can restore your table to any point in time during the last 35 days, down to the second.
- **New Table**: Restoring from PITR always creates a **new table**.
- **Use Case**: Protects against accidental deletes or writes (human error).

### On-Demand Backup
- **Manual Backups**: Create full backups of your tables for long-term retention and archival.
- **No Performance Impact**: Backing up doesn't affect table performance or availability.
- **Retention**: Backups are preserved until you explicitly delete them.

## Key Features
- **Serverless**: No servers to manage, no software to install or patch.
- **Performance**: Single-digit millisecond latency at any scale.
- **Scaling**: 
    - **Provisioned Mode**: Specify read/write capacity units (RCUs/WCUs).
    - **On-Demand Mode**: Pays for actual request volume.
- **Global Tables**: Fully managed, multi-region, multi-active database. Replicates data across AWS Regions automatically.
- **DynamoDB Accelerator (DAX)**: In-memory cache for DynamoDB that reduces response times from milliseconds to microseconds.
- **DynamoDB Streams**: Capture item-level changes in a table and push them to a Kinesis stream or trigger a Lambda function.

## Consistency Models
- **Eventually Consistent Reads** (Default): Maximize read throughput, but may return stale data for a short time.
- **Strongly Consistent Reads**: Returns the most up-to-date data, but uses more throughput (2x RCUs) and may have higher latency.

## Exam Tips
- **PITR** is for the last 35 days.
- **Global Tables** require DynamoDB Streams to be enabled.
- **DAX** is for read-intensive workloads where microsecond latency is needed.
- **Partition Key** vs. **Sort Key**: Understand how they affect data distribution and query flexibility.
