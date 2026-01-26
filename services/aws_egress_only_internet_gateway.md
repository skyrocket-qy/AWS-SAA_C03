# Egress-only Internet Gateway

An **Egress-only Internet Gateway** allows outbound communication over IPv6 while preventing the internet from initiating inbound connections.

### Key Exam Points
- **IPv6 Only**: Designed specifically for IPv6. Use NAT Gateway for IPv4.
- **Outbound Only**: Stateful; return traffic is allowed for connections initiated from the VPC.
- **Use Case**: Private subnets that need internet access (e.g., for updates) via IPv6 but must remain shielded from inbound unsolicited traffic.
