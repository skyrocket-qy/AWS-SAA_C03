# Amazon Redshift

**Amazon Redshift** is a petabyte-scale, columnar data warehouse optimized for OLAP (Online Analytical Processing).

### Key Exam Points
- **Performance**: Columnar storage reduces I/O for complex analytical queries; uses a cluster-based architecture (Leader + Compute nodes).
- **Redshift Spectrum**: Query data **directly from S3** (data lake) without loading it into Redshift.
- **Concurrency Scaling**: Automatically adds transient capacity to handle spikes in concurrent users/queries.
- **Materialized Views**: Pre-computed results for faster query performance on predictable workloads.
- **Redshift vs. RDS**: Redshift is for **Analytics (OLAP)**; RDS is for **Transactions (OLTP)**.
- **Backup**: Replicates data within the cluster and can back up to S3 (cross-region snapshot support).
