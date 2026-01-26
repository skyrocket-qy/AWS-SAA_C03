# Amazon CloudWatch

**Amazon CloudWatch** provides monitoring and observability for AWS resources and applications.

### Key Exam Points
- **Default Metrics**: Hypervisor-level data (CPU, Network, Disk I/O).
- **CloudWatch Agent**: Required for **internal OS metrics** (Memory/RAM, Disk Space Usage, Swap) and pushing logs from EC2/on-premises.
- **Detailed Monitoring**: Increases EC2 metric frequency to **1 minute** (Standard is 5 mins). Does NOT include RAM.
- **Alarms**: Triggers actions (Auto Scaling, SNS, EC2 Reboot) when thresholds are crossed.
- **Logs**: Can be exported to **S3** (storage) or streamed to **Kinesis/OpenSearch** (analysis).
