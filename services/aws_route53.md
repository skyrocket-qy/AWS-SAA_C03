# Amazon Route 53

**Amazon Route 53** is a highly available and scalable Domain Name System (DNS) web service. It also offers domain registration and health checking.

## Routing Policies

Route 53 supports several routing policies to determine how DNS queries are answered:

| Policy | Description | Use Case |
| :--- | :--- | :--- |
| **Simple** | Returns a single resource. If multiple values, returns all (client chooses randomly). | Basic routing, no health checks needed. |
| **Weighted** | Distributes traffic based on assigned weights (0-255). | A/B testing, gradual deployments. |
| **Latency-based** | Routes to the region with lowest latency for the user. | Multi-region deployments for best performance. |
| **Failover** | Active-passive setup. Routes to secondary if primary health check fails. | Disaster recovery. |
| **Geolocation** | Routes based on user's **geographic location** (continent, country, state). | Content localization, regulatory compliance. |
| **Geoproximity** | Routes based on **geographic distance** + optional bias. Requires Traffic Flow. | Shift traffic between regions. |
| **IP-based** | Routes based on client's **IP address** (CIDR blocks). | Specific users/ISPs. |
| **Multi-value Answer** | Returns up to 8 healthy records randomly. Each can have health checks. | Simple load balancing with health checks. |

## Health Checks
- Monitor endpoints (HTTP, HTTPS, TCP).
- Can trigger DNS failover.
- Can monitor other health checks (Calculated Health Checks).
- Can monitor CloudWatch Alarms (for private resources).

## Key Features
- **Domain Registration**: Register and manage domain names.
- **Alias Records**: Route traffic to AWS resources (ELB, CloudFront, S3, etc.) without charges for alias queries.
- **Traffic Flow**: Visual editor for complex routing configurations (uses Geoproximity).
- **DNSSEC**: Protect against DNS spoofing.

## Exam Tips
- **Latency** ≠ **Geoproximity**: Latency is based on actual network latency; Geoproximity is based on physical distance with bias.
- **Geolocation** = "Where is the user?" (legal/compliance); **Latency** = "Fastest route?"
- **Failover** requires health checks on the primary.
- **Alias** records are free for AWS resources (unlike CNAME).
