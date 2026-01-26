# AWS Network Firewall

**AWS Network Firewall** is a managed, stateful firewall and IDS/IPS for your VPC.

### Key Exam Points
- **Inspection**: Layer 3-7 deep packet inspection; supports Suricata rules.
- **Web Filtering**: Filter outbound traffic based on **domain names** (FQDN).
- **Deployment**: Requires a dedicated **firewall subnet** in each AZ; route tables must be updated to redirect traffic to the firewall endpoint.
- **vs. others**:
    - **Security Groups**: Stateful, instance-level, IP/Port only.
    - **NACLs**: Stateless, subnet-level, IP/Port only.
    - **Network Firewall**: Stateful, VPC-level, deep inspection (Layer 7).
- **Automation**: Managed high availability and automatic scaling.
