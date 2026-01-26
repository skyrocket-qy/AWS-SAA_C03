# Amazon VPC Peering

**VPC Peering** is a networking connection between two VPCs that allows traffic to flow privately using AWS's internal network.

### Key Exam Points
- **Connectivity**: Private (stays on AWS backbone); no internet involved. Works cross-account and cross-region.
- **Constraints**: **Not transitive** (A-B, B-C does NOT mean A-C). CIDR blocks must **not overlap**.
- **Management**: No gateway or VPN device; it's a logical link in the VPC routing layer.
- **Use Case**: Simple connection between a few VPCs where full bandwidth is required.
- **vs. Transit Gateway**: Use Transit Gateway for complex hub-and-spoke needs (more than a few VPCs).
