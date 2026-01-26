# Amazon RDS (Relational Database Service)

**Amazon RDS** is a managed relational database service supporting MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Aurora.

### Key Exam Points
- **High Availability (Multi-AZ)**: Synchronous replication to a standby instance in another AZ; automatic failover.
- **Read Scalability (Read Replicas)**: Asynchronous replication for scaling read traffic (can be cross-region).
- **RDS Proxy**: 
    - **Connection Pooling**: Reduces DB load by sharing connections; ideal for **Lambda**.
    - **Failover**: Reduces failover time by up to 66%.
    - **Security**: Enforces IAM auth; hides DB behind a VPC endpoint (never public).
- **Storage**: Supports **Storage Auto Scaling** and encryption at rest (KMS).
- **Backup**: Automated backups (up to 35 days) and manual snapshots.
