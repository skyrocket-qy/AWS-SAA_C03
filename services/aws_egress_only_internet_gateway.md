# Egress-only Internet Gateway

An Egress-only Internet Gateway is a horizontally scaled, redundant, and highly available VPC component that allows outbound communication over IPv6 from instances in your VPC to the internet, and prevents the internet from initiating an IPv6 connection with your instances.

## Key Concepts

*   **IPv6 Only**: It is specifically designed for IPv6 traffic. For IPv4, you would use a NAT Gateway or NAT Instance.
*   **Outbound Only**: It enables instances to access the internet (e.g., for software updates) but prevents inbound connections from the internet (stateful).
*   **Stateful**: It tracks network connections and allows the return traffic for connections initiated by your instances.

## Comparison

| Feature | Internet Gateway (IGW) | Egress-only Internet Gateway | NAT Gateway |
| :--- | :--- | :--- | :--- |
| **IP Version** | IPv4 & IPv6 | **IPv6 Only** | IPv4 Only |
| **Direction** | Inbound & Outbound | Outbound Only (Stateful) | Outbound Only (Stateful) |
| **Use Case** | Public Subnets (Web Servers) | Private Subnets (IPv6) | Private Subnets (IPv4) |
