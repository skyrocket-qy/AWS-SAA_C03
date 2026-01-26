# Elastic Load Balancing (ELB)

**ELB** automatically distributes incoming traffic across multiple targets like EC2, containers, and IP addresses.

### Key Exam Points
- **Application Load Balancer (ALB)**: Layer 7 (HTTP/HTTPS); content-based routing (path, host, header); supports WAF and Lambda.
- **Network Load Balancer (NLB)**: Layer 4 (TCP/UDP); ultra-high performance/low latency; provides **Static/Elastic IPs**.
- **Gateway Load Balancer (GWLB)**: Layer 3; used for virtual appliances (firewalls, IDS/IPS); communicates via **GENEVE** protocol.
- **Features**:
    - **Cross-Zone Load Balancing**: Even traffic distribution across AZs.
    - **Sticky Sessions**: Binds a user To a specific target (supported by ALB/CLB).
    - **Health Checks**: Periodically monitors target health.
