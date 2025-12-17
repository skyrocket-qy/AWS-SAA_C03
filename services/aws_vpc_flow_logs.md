# VPC Flow Logs

VPC Flow Logs is a feature that enables you to capture information about the IP traffic going to and from network interfaces in your VPC.

## Key Concepts

*   **Capture Levels**: You can create flow logs at three levels:
    *   **VPC**: Captures traffic for all subnets and network interfaces in the VPC.
    *   **Subnet**: Captures traffic for all network interfaces in the subnet.
    *   **Network Interface (ENI)**: Captures traffic for a specific network interface.
*   **Destinations**: Flow log data can be published to:
    *   **Amazon CloudWatch Logs**
    *   **Amazon S3**
    *   **Amazon Kinesis Data Firehose**
*   **Cost**: You pay for the data ingestion and archival (e.g., CloudWatch Logs vending, S3 storage).
*   **Limitations**:
    *   You cannot change the configuration of a flow log after it's created. You must delete and recreate it.
    *   You cannot tag a flow log. You must tag the resource (VPC, Subnet, ENI).

## Use Cases

1.  **Security Monitoring**: Detect anomalous traffic patterns or unauthorized access attempts.
2.  **Troubleshooting**: Diagnose connectivity issues (e.g., check if traffic is reaching an instance or being blocked by a Security Group/NACL).
3.  **Audit Compliance**: Monitor traffic for compliance and auditing purposes.
