# Three Tier Architecture

A standard three-tier architecture separates your application into three logical tiers: Presentation, Logic, and Data. In AWS, this is typically implemented using a VPC with public and private subnets.

## Tiers breakdown

### 1. Presentation Tier (Web Tier)
*   **Role**: Handles user interaction and delivers the user interface.
*   **Placement**: **Public Subnets**.
*   **Components**:
    *   **Internet Gateway (IGW)**: Allows internet traffic.
    *   **Application Load Balancer (ALB)**: Distributes incoming traffic to the App Tier.
    *   **NAT Gateway / Bastion Host**: Allows private instances to access the internet (outbound) or allows administration (inbound).
    *   **Security**: Security Groups allow inbound HTTP/HTTPS (80/443) from anywhere (`0.0.0.0/0`).

### 2. Logic Tier (App Tier)
*   **Role**: Processes data, executes business logic/rules.
*   **Placement**: **Private Subnets**.
*   **Components**:
    *   **EC2 Instances**: Running the application code (e.g., Java, Python, Node.js).
    *   **Auto Scaling Group**: automatically adjusts the number of EC2 instances.
    *   **Security**: Security Groups allow inbound traffic **only from the Web Tier Security Group**.

### 3. Data Tier (Database Tier)
*   **Role**: Stores and manages data.
*   **Placement**: **Private Subnets**.
*   **Components**:
    *   **RDS / Aurora**: Managed relational database service.
    *   **DynamoDB**: Managed NoSQL database (accessed via Gateway Endpoint).
    *   **Security**: Security Groups allow inbound traffic **only from the App Tier Security Group**.

## Key Features

*   **Multi-AZ**: Deploy each tier across multiple Availability Zones (AZs) for high availability and fault tolerance.
*   **Security Group Chaining**: Strict access control by referencing Security Group IDs (ALB SG -> App SG -> DB SG) instead of IP ranges.
*   **Scalability**: Each tier can scale independently (e.g., Auto Scaling for App Tier, Read Replicas for DB Tier).
