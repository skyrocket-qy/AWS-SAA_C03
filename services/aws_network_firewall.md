# AWS Network Firewall

AWS Network Firewall is a managed, stateful network firewall and intrusion detection and prevention service (IDS/IPS) for your Virtual Private Cloud (VPC). It enables you to easily deploy and manage network protection for all of your VPCs.

## Key Concepts

*   **Stateful Inspection**: It tracks the state of network connections and allows you to write rules based on the context of traffic flows (e.g., protocol, port, source/destination).
*   **Web Filtering**: You can filter outbound traffic based on domain names (e.g., allow `*.example.com` but deny everything else).
*   **IDS/IPS**: It provides Intrusion Detection and Prevention capabilities to inspect traffic for malicious patterns using Suricata-compatible rules.
*   **Managed Service**: Automatically scales with your traffic and offers high availability.

## Deployment Model

To deploy AWS Network Firewall, you typically follow these steps:

1.  **Firewall Subnet**: Create a dedicated subnet for the firewall endpoint in each Availability Zone where you want protection.
2.  **Firewall Endpoints**: When you create the firewall, AWS creates an endpoint (similar to a VPC Interface Endpoint) in the firewall subnet.
3.  **Route Tables**: You must update your VPC route tables to redirect traffic to the firewall endpoint for inspection.
    *   **Ingress Routing**: Update IGW route table to send traffic destined for your subnets to the firewall endpoint.
    *   **Egress Routing**: Update your subnet route tables to send internet-bound traffic to the firewall endpoint.

## Comparison with other Security Services

| Feature | Security Groups | Network ACLs | AWS Network Firewall |
| :--- | :--- | :--- | :--- |
| **Scope** | Instance Level | Subnet Level | VPC Level (Centralized) |
| **State** | Stateful | Stateless | Stateful |
| **Inspection** | Layer 3-4 (IP/Port) | Layer 3-4 (IP/Port) | Layer 3-7 (Deep Packet Inspection), Domain names |
| **Action** | Allow Only | Allow & Deny | Allow, Deny, Drop, Alert |
