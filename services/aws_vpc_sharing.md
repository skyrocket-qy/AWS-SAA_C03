# Shared VPC (VPC Sharing)

VPC Sharing allows multiple AWS accounts to create their application resources, such as EC2 instances, RDS databases, Redshift clusters, and Lambda functions, into shared, centrally managed Virtual Private Clouds (VPCs). This model separates the duties of network management from application creation.

## Key Concepts

*   **AWS RAM**: VPC sharing is powered by **AWS Resource Access Manager (RAM)**.
*   **Organization**: You can share subnets with other AWS accounts within the same AWS Organization.
*   **Cost Savings**: Reduces the number of VPCs you need to create and manage, which can lower costs (e.g., fewer NAT Gateways, Interface Endpoints).
*   **Security Groups**: Participants can create their own security groups for their resources.

## Roles and Responsibilities

| Feature | VPC Owner | Participant |
| :--- | :--- | :--- |
| **Manage VPC** | Yes (Create, Delete, Modify) | No |
| **Manage Subnets** | Yes (Create, Delete, Modify) | No |
| **Manage Route Tables** | Yes (Create, Delete, Modify) | No |
| **Manage NACLs** | Yes (Create, Delete, Modify) | No |
| **Manage IGW / NAT** | Yes (Create, Delete, Modify) | No |
| **Launch Instances** | Yes | **Yes** (In shared subnets) |
| **Manage Security Groups** | Yes | **Yes** (For their own resources) |
