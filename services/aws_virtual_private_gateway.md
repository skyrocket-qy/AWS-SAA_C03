# Virtual Private Gateway (VGW)

A Virtual Private Gateway is a logical, fully managed, and highly available VPC component that serves as the **VPN concentrator** on the Amazon side of an AWS Site-to-Site VPN connection.

## Key Concepts

*   **VPN Concentrator**: It acts as the gateway for your VPC to receiving traffic from your on-premises network via a VPN connection.
*   **Customer Gateway**: The VGW connects to a **Customer Gateway** (CGW) which is the physical device or software application on your side of the Site-to-Site VPN connection.
*   **Direct Connect**: It can also be used as the target for an AWS Direct Connect Private Virtual Interface.
*   **One per VPC**: You can attach only one Virtual Private Gateway to a VPC.
*   **Route Propagation**: You can enable route propagation in your route tables to automatically propagate routes from the VGW to the route table.
