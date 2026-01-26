# AWS VPC Endpoints

**VPC Endpoints** enable private connections between your VPC and AWS services without using an Internet Gateway or NAT.

### Key Exam Points
- **Gateway Endpoints**:
    - **Services**: Only **S3** and **DynamoDB**.
    - **How**: Adds a target to the route table.
    - **Cost**: **Free**.
- **Interface Endpoints (PrivateLink)**:
    - **Services**: Most other services (EC2, Kinesis, SNS, sqs, etc.).
    - **How**: Uses an **ENI (Private IP)** in your subnet.
    - **Cost**: Hourly fee + data processing fee.
- **On-Prem Access**: Interface endpoints (PrivateLink) are accessible from on-premises via VPN/DX; Gateway endpoints are not.
