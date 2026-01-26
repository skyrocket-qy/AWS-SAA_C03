# Internet Gateway (IGW)

An **Internet Gateway** provides a target in your VPC route tables for internet-bound traffic and performs NAT for instances with public IPv4 addresses.

### Key Exam Points
- **Scope**: Horizontally scaled, redundant, and highly available (managed by AWS). No bandwidth constraints.
- **Constraints**: You can attach only **one** IGW to a VPC at a time.
- **Use Case**: Allows resources in **public subnets** (with public IPs) to connect to the internet and vice versa.
- **Setup**: Create, attach to VPC, and add a route (`0.0.0.0/0`) in the subnet's route table pointing to the IGW.
