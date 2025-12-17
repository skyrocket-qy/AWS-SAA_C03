# AWS VPC Endpoints

AWS VPC Endpoints enable you to privately connect your VPC to supported AWS services and VPC endpoint services powered by AWS PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service.

## Types of Endpoints

There are two main types of VPC endpoints: **Gateway Endpoints** and **Interface Endpoints**.

### Gateway Endpoints

*   **Supported Services**: **Amazon S3** and **Amazon DynamoDB**.
*   **Mechanism**: A target in your route table.
*   **Setup**: You specify a route table target for traffic destined for the service.
*   **Cost**: Free of charge.
*   **DNS**: Uses the public DNS name of the service (e.g., `s3.amazonaws.com`), but traffic routes privately.

### Interface Endpoints (AWS PrivateLink)

*   **Supported Services**: Most other AWS services (e.g., EC2, SNS, SQS, Kinesis, Athena, etc.).
*   **Mechanism**: An Elastic Network Interface (ENI) with a private IP address from your VPC subnet range.
*   **Setup**: Creates an ENI in your subnet that acts as an entry point for traffic destined to the service.
*   **Cost**: Hourly charge per VPC endpoint + Data processing charge (per GB).
*   **DNS**: Can use private DNS capability to override default service DNS names.

## Gateway vs. Interface Endpoints

| Feature | Gateway Endpoint | Interface Endpoint |
| :--- | :--- | :--- |
| **Supported Services** | Amazon S3, Amazon DynamoDB. | Most other AWS services. |
| **Data Flow** | Via Route Table entries. | Via ENI (Private IP/NIC). |
| **Cost** | Free. | $ per hour + $ per GB processed. |
| **Cross-Region** | Not supported. | Supported for some services. |
| **On-Prem Access** | Not directly accessible from on-prem (requires proxy). | Accessible from on-prem via VPN/Direct Connect. |
