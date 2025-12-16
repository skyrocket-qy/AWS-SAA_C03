# AWS Transit Gateway

AWS Transit Gateway is a service that connects your Amazon Virtual Private Clouds (VPCs) and on-premises networks through a central hub. This simplifies your network and puts an end to complex peering relationships.

## Key Concepts

*   **Hub and Spoke Model**: Acts as a central cloud router (hub) where each new connection is a "spoke".
*   **Attachments**: You can attach the following to a Transit Gateway:
    *   **VPC**: Connect your VPCs.
    *   **VPN**: Connect an IPsec Site-to-Site VPN.
    *   **Direct Connect Gateway**: Connect via AWS Direct Connect.
    *   **Transit Gateway Connect**: Connect SD-WAN appliances.
    *   **Peering Connection**: Peer with another Transit Gateway (even in a different region).
*   **Route Tables**: Transit Gateway has its own route tables to control how traffic is routed between the attached networks. You can isolate networks or create shared services.
*   **Regional**: It is a regional resource, but you can peer Transit Gateways across regions.

## How It Works

1.  **Create a Transit Gateway**: Initialize the resource in your region.
2.  **Attach Resources**: Connect your VPCs and VPNs to the Transit Gateway.
3.  **Configure Routing**: Update VPC route tables to point to the Transit Gateway for specific destinations. Configure the Transit Gateway route tables to control traffic flow between attachments.

## Benefits

*   **Simplified Connectivity**: Reduces the complexity of connecting multiple VPCs. Instead of a full mesh of VPC peering (N*(N-1)/2 connections), you connect each VPC to the Transit Gateway.
*   **Centralized Management**: Manage all your network connections in one place.
*   **Scalability**: Supports thousands of VPCs and VPN connections.
*   **Better Visibility**: Easier to monitor and debug network traffic.
*   **Multicast Support**: Supports IP multicast traffic.

## Transit Gateway vs. VPC Peering

| Feature | AWS Transit Gateway | VPC Peering |
| :--- | :--- | :--- |
| **Topology** | Hub-and-spoke (Star). | Point-to-point (Mesh). |
| **Complexity** | Low complexity as network grows. | High complexity (N^2) as network grows. |
| **Transitive Routing** | Supported (A can talk to C via Hub). | Not supported (A peered to B, B peered to C, A cannot talk to C). |
| **Bandwidth** | Total bandwidth per attachment varies (up to 50 Gbps per VPC attachment). | No aggregate bandwidth limit (limited by instance network performance). |
| **Use Case** | Large scale, many VPCs, hybrid connectivity, centralized control. | Small scale, few VPCs, full bandwidth requirement between two specific VPCs. |
