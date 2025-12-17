# Elastic Network Interface (ENI)

An Elastic Network Interface (ENI) is a logical networking component in a VPC that represents a virtual network card.

## Key Attributes
An ENI can include the following attributes:
*   **Primary private IPv4 address** from the IPv4 address range of your VPC.
*   **One or more secondary private IPv4 addresses**.
*   **One Elastic IP address (IPv4)** per private IPv4 address.
*   **One public IPv4 address**.
*   **One or more security groups**.
*   **A MAC address**.

## Types of ENI
*   **Primary ENI (eth0)**: The default network interface created with an instance. It **cannot** be detached from the instance.
*   **Secondary ENI**: Can be created independently and attached or detached (hot swap) to instances. This is useful for creating management networks or for failover scenarios.
