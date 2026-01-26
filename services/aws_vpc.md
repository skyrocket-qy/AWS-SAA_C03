# Amazon VPC

**Amazon VPC** lets you launch AWS resources into a defined virtual network.

### Key Exam Points
- **Subnets**:
    - **Public**: Has a route to an **Internet Gateway (IGW)**.
    - **Private**: No direct route to IGW; uses **NAT Gateway** for outbound-only access.
- **Reserved IPs**: AWS reserves **5 IP addresses** in every subnet (first 4 and last 1).
- **Routing**: Each subnet must be associated with a **Route Table**. Unassociated subnets use the **Main Route Table**.
- **Security**:
    - **Security Groups**: Stateful; instance-level; Allow-only rules.
    - **NACLs**: Stateless; subnet-level; Allow/Deny rules; processed in order.
- **Peering**: Direct connection between two VPCs; **not transitive**.
