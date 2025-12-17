# Amazon Elastic Block Store (EBS)

Amazon EBS provides scalable, high-performance block storage volumes for use with Amazon EC2 instances.

## Key Concepts

*   **Block Storage**: Acts like a raw, unformatted hard drive. You can mount it as a device on an EC2 instance.
*   **Availability Zone Specific**: An EBS volume is **locked** to a specific Availability Zone (AZ). It cannot be attached to an instance in a different AZ.
    *   *To move across AZs*: Create a snapshot -> Copy snapshot (optional, for region transfer) -> Create volume from snapshot in target AZ.
*   **Persistence**: Data persists independently of the instance's life (unlike Instance Store, which is ephemeral).
*   **Encryption**: EBS supports seamless encryption of data at rest, data in transit, and all snapshots created from the volume using AWS KMS.

## Volume Types

### Volume Types Comparison

| Type | Name | Description | Use Case | Max IOPS | Max Throughput |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **General Purpose SSD** | **gp3** | Balanced price/performance. **Independent** IOPS & Throughput scaling. | Boot volumes, Virtual desktops, Dev/Test environments. | 16,000 | 1,000 MiB/s |
| **General Purpose SSD** | **gp2** | IOPS linked to volume size (3 IOPS/GB). | Boot volumes, Low-latency interactive apps. | 16,000 | 250 MiB/s |
| **Provisioned IOPS SSD** | **io2 Block Express** | Highest performance, Sub-millisecond latency. **Multi-Attach** support. | Mission-critical DBs (SAP HANA, Oracle, MS SQL), High throughput. | 256,000 | 4,000 MiB/s |
| **Provisioned IOPS SSD** | **io1** | Sustained IOPS performance. | Critical business applications. | 64,000 | 1,000 MiB/s |
| **Throughput Optimized HDD** | **st1** | Low cost, throughput-oriented. | Big Data, Data Warehousing, Log processing (Kafka, Splunk). | 500 | 500 MiB/s |
| **Cold HDD** | **sc1** | Lowest cost EBS volume. | Infrequently accessed data, File servers. | 250 | 250 MiB/s |

> **Note**: **SSD** volumes are optimized for transactional workloads (small, random I/O), while **HDD** volumes are optimized for large streaming workloads (large, sequential I/O). Boot volumes must be **Key Concepts** (SSD).

## Features

*   **Snapshots**: Point-in-time backup of an EBS volume.
    *   **Incremental**: Only blocks changed since the last snapshot are saved.
    *   **Regional**: Stored in S3 (regionally), but can be copied to other regions.
*   **Data Lifecycle Manager (DLM)**: Automates the creation, retention, and deletion of EBS snapshots.
*   **Fast Snapshot Restore (FSR)**: Enables you to create a volume from a snapshot that is fully initialized at creation (no lazy loading latency).
