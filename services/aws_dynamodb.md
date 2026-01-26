# Amazon DynamoDB

**Amazon DynamoDB** is a fully managed, serverless, NoSQL database for fast and predictable performance.

### Key Exam Points
- **Scaling**: **Provisioned** (RCUs/WCUs) or **On-Demand** (pay-per-request).
- **Persistence/Backup**:
    - **PITR**: Continuous backups for the last **35 days** (restores to a new table).
    - **On-Demand Backup**: Manual backups for long-term archival.
- **Global Tables**: Multi-region, multi-active replication (requires DynamoDB Streams).
- **Performance**: 
    - **DAX**: In-memory cache for microsecond read latency.
    - **DynamoDB Streams**: Capture real-time changes to trigger Lambda or Kinesis.
- **Consistency**: **Eventually Consistent** (default) vs. **Strongly Consistent** (requires more RCUs).
