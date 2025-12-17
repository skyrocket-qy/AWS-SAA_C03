# Amazon VPC Peering

Amazon VPC Peering is a networking connection that enables you to route traffic between two Virtual Private Clouds (VPCs) privately. Instances in either VPC can communicate with each other as if they are within the same network.

## Key Concepts

*   **Private Connectivity**: Traffic stays on the AWS global backbone and never traverses the public internet, ensuring security and better performance.
*   **Inter-Region Peering**: You can peer VPCs across different AWS Regions.
*   **Cross-Account Peering**: You can peer VPCs that belong to different AWS accounts.
*   **No Gateway Bottleneck**: There is no gateway or VPN appliance to manage; the connection is a logical link.

## Key Limitations

*   **No Transitive Peering**: If VPC A is peered with VPC B, and VPC B is peered with VPC C, VPC A **cannot** talk to VPC C directly. You must create a peering connection between A and C.
*   **No Overlapping CIDR Blocks**: You cannot create a peering connection between VPCs with matching or overlapping IPv4 or IPv6 CIDR blocks.

## How It Works

1.  **Request**: The owner of the requester VPC sends a peering connection request to the accepter VPC.
2.  **Accept**: The owner of the accepter VPC accepts the peering connection request.
3.  **Update Route Tables**: Both VPC owners must manually update their VPC route tables to point to the peering connection ID (`pcx-xxxx`) for the destination CIDR block.
4.  **Update Security Groups**: Update security group rules to allow ingress/egress traffic from the peer VPC CIDR.

## VPC Peering vs. Transit Gateway

For a detailed comparison between VPC Peering and Transit Gateway, see [AWS Transit Gateway](aws_transit_gateway.md#transit-gateway-vs-vpc-peering).
