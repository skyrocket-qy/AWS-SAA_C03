# AWS VPC Sharing

**VPC Sharing** allows multiple accounts in the same AWS Organization to launch resources into a centrally managed, shared VPC.

### Key Exam Points
- **Mechanism**: Powered by **AWS Resource Access Manager (RAM)**.
- **Benefits**: Centralized network management; cost savings (fewer NAT Gateways, VPC endpoints); simplified network topology.
- **Roles**:
    - **Owner**: Manages subnets, route tables, NACLs, and gateways.
    - **Participant**: Launches resources (EC2, RDS, etc.) into shared subnets and manages their own security groups.
- **Scope**: Sharing is limited to accounts within the **same AWS Organization**.
