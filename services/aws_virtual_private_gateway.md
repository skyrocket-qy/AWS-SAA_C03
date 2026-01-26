# Virtual Private Gateway (VGW)

A **Virtual Private Gateway** is the VPN concentrator on the AWS side of a Site-to-Site VPN or Direct Connect connection.

### Key Exam Points
- **Function**: Receives VPN/DX traffic and routes it into your VPC.
- **Constraints**: You can attach only **one** VGW to a VPC at a time.
- **Customer Gateway (CGW)**: The corresponding physical or software appliance on the on-premises side.
- **Propagation**: Enable **Route Propagation** to automatically update VPC route tables with on-premises routes.
