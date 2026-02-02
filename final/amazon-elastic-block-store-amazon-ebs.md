# Amazon Elastic Block Store (Amazon EBS)

### Function
High-performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction-intensive workloads.

### Use Case
- Root volume for an EC2 instance.
- Highly available and reliable storage for databases.

### Tips
- Types: gp2/gp3 (general), io1/io2 (high performance), st1 (throughput), sc1 (cold storage).
- Snapshots are incremental and stored in S3.
