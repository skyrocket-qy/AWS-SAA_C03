# Amazon RDS (Relational Database Service)

**Amazon RDS** is a managed relational database service that supports multiple database engines: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Amazon Aurora.

## RDS Proxy

**Amazon RDS Proxy** is a fully managed, highly available database proxy that makes applications more scalable, more resilient, and more secure.

### Key Benefits
- **Connection Pooling**: Shares database connections across many application connections. Reduces database load from opening/closing connections.
- **Reduced Failover Time**: Reduces failover time by up to 66% by maintaining connections during failover.
- **IAM Authentication**: Enforce IAM authentication for database access (store credentials in Secrets Manager).
- **Never Publicly Accessible**: RDS Proxy is deployed in your VPC and cannot be accessed from the internet.

### Use Cases
- **Serverless Applications (Lambda)**: Lambda functions can create many concurrent connections; RDS Proxy pools them to prevent overwhelming the database.
- **Applications with Unpredictable Workloads**: Connection pooling handles spikes gracefully.
- **High Availability Requirements**: Faster failover for production databases.

---

## Key RDS Features
- **Multi-AZ Deployments**: Synchronous standby replica in another AZ for high availability (automatic failover).
- **Read Replicas**: Asynchronous replication for read scaling (can be cross-region).
- **Automated Backups**: Point-in-time recovery within retention period (up to 35 days).
- **Storage Auto Scaling**: Automatically increases storage when running low.
- **Encryption**: At-rest (KMS) and in-transit (SSL/TLS).

## Exam Tips
- **RDS Proxy** = **Lambda + RDS** (connection pooling for serverless).
- RDS Proxy is **VPC only** (not publicly accessible).
- **Multi-AZ** = High Availability (HA), **Read Replicas** = Read Scaling.
- RDS Proxy reduces failover time and enforces IAM authentication via Secrets Manager.
