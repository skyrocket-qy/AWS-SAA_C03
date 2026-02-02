# Elastic Load Balancing (ELB)

### Function
Service that automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, Lambda functions, and virtual appliances.

### Use Case
- Distributing HTTP/HTTPS traffic (ALB).
- Decoupling clients from servers for high availability.

### Tips
- ALB (Layer 7 - URL/Path/Host based).
- NLB (Layer 4 - TCP/UDP, ultra-high performance, static IP).
- GWLB (Layer 3 - Third-party appliances).
- CLB (Legacy).
- Health Checks.
