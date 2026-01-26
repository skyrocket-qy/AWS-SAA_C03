# AWS Transit Gateway

**AWS Transit Gateway** acts as a central hub (router) to connect multiple VPCs and on-premises networks.

### Key Exam Points
- **Topology**: Hub-and-spoke model; simplifies connectivity by avoiding a full mesh of VPC peering.
- **Transitive Routing**: Allows VPC A to talk to VPC C through the hub (not possible with standard peering).
- **Attachments**: Supports VPCs, VPNs, Direct Connect Gateways, and peering with other Transit Gateways.
- **Security**: Centralized control via Transit Gateway route tables; supports **IP Multicast**.
- **Use Case**: Connecting dozens or hundreds of VPCs and site-to-site VPNs.
