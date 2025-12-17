# Internet Gateway (IGW)

An Internet Gateway is a horizontally scaled, redundant, and highly available VPC component that allows communication between your VPC and the internet.

## Key Concepts

*   **VPC Internet Access**: It enables resources in your public subnets (such as EC2 instances) to connect to the internet if they have a public IPv4 address or an IPv6 address.
*   **1:1 NAT**: It performs network address translation (NAT) for your instances that have been assigned public IPv4 addresses.
*   **No Availability Risks**: It imposes no availability risks or bandwidth constraints on your network traffic.
*   **One per VPC**: You can attach only one Internet Gateway to a VPC.

## How it works

1.  **Create**: Create an Internet Gateway.
2.  **Attach**: Attach it to your VPC.
3.  **Route**: Add a route to your subnet's route table that directs internet-bound traffic (`0.0.0.0/0` for IPv4) to the Internet Gateway ID.
