# Amazon NAT Instance

An Amazon NAT (Network Address Translation) Instance is an EC2 instance that you configure to allow resources in a private subnet to connect to the internet or other AWS services, but prevent the internet from initiating a connection with those instances.

## Key Concepts

*   **Self-Managed**: You are responsible for provisioning, configuring, patching, and maintaining the EC2 instance and the NAT software on it.
*   **Source/Destination Check**: You must disable the Source/Destination check on the EC2 instance to allow it to forward traffic.
*   **Security Groups**: You must configure security groups to allow traffic from your private subnet.

## Key Limitations

*   **Scalability**: Bandwidth is limited by the instance type and size. You must manually scale up or scale out.
*   **Availability**: It is a single point of failure unless you configure a high-availability setup (e.g., using Auto Scaling and a script to take over the elastic IP).
*   **Performance**: Performance depends on the instance's network capabilities.

## NAT Instance vs. NAT Gateway

| Feature | NAT Gateway | NAT Instance |
| :--- | :--- | :--- |
| **Management** | Fully managed by AWS. | Managed by you (User). |
| **Availability** | Highly available within an AZ. | Script required for HA/failover. |
| **Bandwidth** | Scales up to 100 Gbps. | Depends on EC2 instance type. |
| **Maintenance** | None (AWS handles patching). | You manage OS and software updates. |
| **Cost** | Hourly charge + data processing fee. | Hourly charge (EC2) + data transfer. |
| **Public IP** | Elastic IP required (for public NAT). | Elastic IP or Public IP. |
| **Security Groups** | Cannot associate Security Groups. | Can associate Security Groups. |
| **Port Forwarding** | Not supported. | Supported (manually configured). |
| **Bastion Host** | No. | Can be used as a Bastion Server. |
