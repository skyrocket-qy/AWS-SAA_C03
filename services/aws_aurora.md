# Amazon Aurora

**Amazon Aurora** is a MySQL and PostgreSQL-compatible relational database built for the cloud, offering up to 5x performance of MySQL and 3x of PostgreSQL.

## Aurora Global Database

**Aurora Global Database** spans multiple AWS Regions for disaster recovery and low-latency global reads.

### Key Features
- **1 Primary Region**: Handles all write operations.
- **Up to 5 Secondary Regions**: Read-only replicas with typical latency < 1 second.
- **Fast Replication**: Uses dedicated infrastructure with typical lag < 1 second.
- **Disaster Recovery**: Promote a secondary region to primary in < 1 minute (RTO).
- **Low Latency Reads**: Serve read traffic from the closest region to users.

### Use Cases
- Global applications requiring low-latency reads worldwide.
- Disaster recovery with cross-region failover.
- Data residency and compliance (reads in specific regions).

---

## Aurora Serverless

**Aurora Serverless** automatically starts up, shuts down, and scales capacity based on application needs.

### Versions
- **v1**: Original version, scales in ACUs (Aurora Capacity Units).
- **v2**: Near-instant scaling, more granular (scales in 0.5 ACU increments), supports Global Database.

### Use Cases
- Infrequent, intermittent, or unpredictable workloads.
- Development and test databases.
- Multi-tenant applications.

---

## Key Aurora Features
- **Storage Auto-Scaling**: Grows automatically up to 128 TB.
- **High Availability**: 6 copies of data across 3 AZs, automatic failover.
- **Read Replicas**: Up to 15 replicas with auto-scaling.
- **Backtrack**: "Rewind" the database to a previous point in time without restoring from backup.
- **Cloning**: Create a new cluster from an existing one in seconds (copy-on-write).

## Exam Tips
- **Aurora Global Database** = Cross-region DR with < 1 second replication lag, < 1 minute RTO.
- **Aurora Serverless v2** = Near-instant scaling, works with Global Database.
- **Backtrack** = Quickly undo mistakes without restoring from backup (no new cluster).
- **Cloning** = Fast creation of test environment from production (copy-on-write).
