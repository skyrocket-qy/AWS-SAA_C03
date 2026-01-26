# VPC Flow Logs

**VPC Flow Logs** capture information about IP traffic going to and from network interfaces in your VPC.

### Key Exam Points
- **Capture Levels**: VPC, Subnet, or individual Elastic Network Interface (ENI).
- **Destinations**: CloudWatch Logs, S3, or Kinesis Data Firehose.
- **Use Case**: 
    - **Troubleshooting**: Identify if Security Groups or NACLs are blocking traffic (`REJECT` vs. `ACCEPT`).
    - **Security**: Monitor for unusual traffic patterns.
- **Tip**: Flow logs do NOT capture all traffic (e.g., DNS queries to Amazon DNS, AWS service traffic, or traffic to `169.254.169.254`).
