# Amazon NAT Instance

An **Amazon NAT Instance** is a self-managed EC2 instance used to provide internet access to private subnets.

### Key Exam Points
- **Configuration**: Must disable **Source/Destination Check** on the instance to allow traffic forwarding.
- **Management**: You are responsible for patching, scaling (instance size), and high availability (scripts/failover).
- **Security**: Can be used as a **Bastion Host** and supports security groups (unlike NAT Gateway).
- **Recommendation**: AWS recommends **NAT Gateway** for its managed scalability and high availability.
