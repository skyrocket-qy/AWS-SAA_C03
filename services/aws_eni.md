# Elastic Network Interface (ENI)

An **ENI** is a logical networking component in a VPC representing a virtual network card.

### Key Exam Points
- **Attributes**: Includes a primary private IPv4, secondary IPs, Elastic IPs, a public IP, and security groups.
- **Primary ENI (eth0)**: Created with the instance; **cannot** be detached.
- **Secondary ENI**: Can be hot-swapped between instances for failover or management networks.
- **Security**: Security groups are attached to the ENI, not the instance.
