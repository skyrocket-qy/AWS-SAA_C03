# Amazon VPC (Virtual Private Cloud)

Amazon Virtual Private Cloud (Amazon VPC) enables you to launch AWS resources into a virtual network that you've defined. This virtual network closely resembles a traditional network that you'd operate in your own data center, with the benefits of using the scalable infrastructure of AWS.

## Subnets

A subnet is a range of IP addresses in your VPC. You can launch AWS resources into a specified subnet. Use a public subnet for resources that must be connected to the internet, and a private subnet for resources that won't be connected to the internet.

### Reserved IP Addresses

In each subnet CIDR block, the first four IP addresses and the last IP address are reserved for use by AWS. These cannot be assigned to an instance.

For example, in a subnet with CIDR block `10.0.0.0/24`, the following five IP addresses are reserved:

*   **10.0.0.0**: Network address.
*   **10.0.0.1**: Reserved by AWS for the VPC router.
*   **10.0.0.2**: Reserved by AWS for mapping to Amazon-provided DNS.
*   **10.0.0.3**: Reserved by AWS for future use.
*   **10.0.0.255**: Network broadcast address. AWS does not support broadcast in a VPC, therefore the address is reserved.

## Route Tables (Subnet Routing)

A route table contains a set of rules, called routes, that determine where network traffic from your subnet or gateway is directed.

*   **Association**: Each subnet must be associated with exactly one route table at a time. However, you can associate the same route table with multiple subnets.
*   **Implicit Association**: If you don't explicitly associate a subnet with a route table, it implicitly uses the **Main Route Table**.

### Main Route Table
The route table that automatically comes with your VPC. It controls the routing for all subnets that are not explicitly associated with any other route table.

### Custom Route Table
A route table that you create and associate with specific subnets.

### Subnet Types
Based on their routing configuration, subnets are generally classified as:

*   **Public Subnet**: Has a route table entry that routes internet-bound traffic (`0.0.0.0/0`) to an **Internet Gateway (IGW)**.
*   **Private Subnet**: Does not have a route to the internet gateway. For outbound internet access, it may route traffic (`0.0.0.0/0`) to a **NAT Gateway** or **NAT Instance**.

## Security

You can secure your VPC instances using two main features: **Security Groups** and **Network Access Control Lists (NACLs)**.

| Feature | Security Group (SG) | Network ACL (NACL) |
| :--- | :--- | :--- |
| **Level of Security** | Instance level. | Subnet level. |
| **State** | **Stateful**: Return traffic is automatically allowed, regardless of any outbound rules. | **Stateless**: Return traffic must be explicitly allowed by rules. |
| **Rules Support** | Supports **Allow** rules only. | Supports **Allow** and **Deny** rules. |
| **Rule Application** | Evaluates all rules before deciding whether to allow traffic. | Processed in number order (lowest number first). |
| **Default Rule** | Denies all inbound traffic by default. | Allows all inbound/outbound traffic by default. |

