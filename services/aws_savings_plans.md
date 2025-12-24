# AWS Savings Plans

**Savings Plans** is a flexible pricing model that offers lower prices compared to On-Demand pricing, in exchange for a specific usage commitment (measured in $/hour) for a one or three-year period.

## Types of Savings Plans

### 1. Compute Savings Plans
- **Flexibility**: **Highest**. Applies to usage across:
    - **Amazon EC2**
    - **AWS Fargate**
    - **AWS Lambda**
- **Attributes**: Automatically applies regardless of:
    - Instance Family (e.g., M5 to C5)
    - Region (e.g., us-east-1 to eu-west-1)
    - Operating System (e.g., Windows to Linux)
    - Tenancy (e.g., Shared to Dedicated)
- **Discount**: Up to **66%** off On-Demand.
- **Use Case**: Dynamic workloads, changing instance types, or moving between EC2/Fargate/Lambda.

### 2. EC2 Instance Savings Plans
- **Flexibility**: **Lower**. Applies to a specific **Instance Family** in a specific **Region** (e.g., M5 instances in N. Virginia).
- **Attributes**: Automatically applies regardless of:
    - Availability Zone
    - Size (e.g., m5.xlarge to m5.2xlarge)
    - OS
    - Tenancy
- **Discount**: Up to **72%** off On-Demand (deepest discount).
- **Use Case**: Committed usage for a specific instance type in a specific region.

### 3. SageMaker Savings Plans
- **Flexibility**: Applies to SageMaker instance usage.
- **Discount**: Up to **64%** off On-Demand.

## Comparison vs Reserved Instances (RIs)
| Feature | Savings Plans | Reserved Instances |
| :--- | :--- | :--- |
| **Commitment** | Monetary ($/hr) | Capacity (Instance count) |
| **Flexibility** | Higher (Compute Savings Plans cover Fargate/Lambda) | Lower (Standard RIs are rigid) |
| **Management** | Easier (Auto-applies to eligible usage) | Harder (Need to manage specific RI attributes) |

## Exam Tips
- **Compute Savings Plans** = **Max Flexibility** (Regions, Families, Services: EC2 + Fargate + Lambda).
- **EC2 Instance Savings Plans** = **Max Discount** (Ec2 only, specific Region + Family).
- If the question asks for the "most cost-effective and flexible option for a mix of Fargate and EC2", choose **Compute Savings Plans**.
