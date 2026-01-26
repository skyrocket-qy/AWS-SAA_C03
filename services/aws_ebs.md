# Amazon Elastic Block Store (EBS)

**Amazon EBS** provides block-level storage volumes for EC2 instances.

### Key Exam Points
- **Scoping**: Volumes are **locked to a specific Availability Zone (AZ)**. To move data, use Snapshots.
- **Snapshots**: Point-in-time, incremental backups stored in S3 (Regional).
- **Volume Types**:
    - **gp3**: Recommended general purpose (independent IOPS/Throughput).
    - **io2 Block Express**: Extreme performance, supports **Multi-Attach**.
    - **st1**: Throughput-optimized HDD (Big Data, Log processing).
    - **sc1**: Cold HDD (infrequently accessed, lowest cost).
- **Multi-Attach**: Allows an **io1/io2** volume to be attached to multiple Nitro-based instances in the *same* AZ.
- **Fast Snapshot Restore (FSR)**: Eliminates latency of first-time block access from snapshots.
