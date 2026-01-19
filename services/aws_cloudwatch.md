# Amazon CloudWatch

**Amazon CloudWatch** is a monitoring and observability service built for DevOps engineers, developers, site reliability engineers (SREs), and IT managers. It provides data and actionable insights to monitor applications, respond to system-wide performance changes, and optimize resource utilization.

## CloudWatch Metrics

Metrics are data about the performance of your systems. By default, many AWS services provide free metrics for resources.

### Default (Standard) Metrics
- **Frequency**: Every 1-5 minutes (Standard Monitoring is 5 minutes, Detailed Monitoring is 1 minute).
- **Retention**: Metrics are kept for up to 15 months.
- **Examples**:
    - **EC2**: CPUUtilization, DiskReadBytes, NetworkIn, MetadataNoToken.
    - **RDS**: CPUUtilization, DatabaseConnections, FreeStorageSpace.
    - **S3**: BucketSizeBytes, NumberOfObjects (updated daily).

### Custom Metrics
- Metrics you define for your own applications.
- **High-Resolution Metrics**: Can be submitted with a resolution of up to 1 second.
- **Standard Resolution**: 1 minute.

---

## CloudWatch Agent

The **CloudWatch Agent** is a software package that you install on your EC2 instances or on-premises servers to collect more system-level metrics and logs.

### Why use the CloudWatch Agent?
By default, EC2 metrics only include data that the hypervisor can see (e.g., CPU, Network, Disk I/O). The hypervisor **cannot** see internal OS-level metrics.

### Collected Metrics (OS-Level)
- **Memory Utilization** (RAM)
- **Disk Space Utilization** (Internal disk usage)
- **Swap Usage**
- **Processes List**
- **Log Files**: Pushing logs from the OS/Application to CloudWatch Logs.

### Configuration
- Unified agent (supports both Windows and Linux).
- Configuration is stored in a JSON file.
- Can be managed using **AWS Systems Manager (SSM)** Parameter Store to store configuration and push it to multiple instances.

---

## Exam Tips

- **Internal Metrics**: If the exam asks how to monitor **Memory**, **Disk Space (Internal)**, or **Logs**, the answer is almost always the **CloudWatch Agent**.
- **Detailed Monitoring**: Enabling Detailed Monitoring on EC2 changes the metric frequency from 5 minutes to **1 minute**. It does NOT provide memory metrics; you still need the agent for that.
- **Custom Metrics Resolution**: High-resolution metrics allow for 1-second resolution, useful for rapid scaling decisions.
- **Logs**: CloudWatch Logs can be exported to S3 (for long-term storage) or streamed to Kinesis Data Firehose (for real-time analysis in OpenSearch).
