# Amazon Route 53

**Amazon Route 53** is a highly available and scalable DNS, domain registration, and health checking service.

### Key Exam Points
- **Routing Policies**:
    - **Simple**: Returns one/all records; no health checks.
    - **Weighted**: Distributes traffic by % (useful for A/B testing/canary releases).
    - **Latency**: Directs users to the region with the lowest latency.
    - **Failover**: Active-Passive configuration for disaster recovery.
    - **Geolocation**: Routes based on the user's actual physical location (e.g., show European users an EU-localized site).
    - **Geoproximity**: Routes based on geography plus a "bias" to expand/shrink the reach of a specific region.
    - **Multi-value Answer**: Returns up to 8 healthy records randomly for simple load balancing.

### Hosted Zones
- **Public Hosted Zone**: Responds to queries on the public internet.
- **Private Hosted Zone**: Responds to queries within one or more VPCs (requires setting `enableDnsHostnames` and `enableDnsSupport` to true in VPC).

### Alias vs. CNAME
- **CNAME**: Maps one domain name to another; **cannot be used for the Zone Apex (Root Domain)**.
- **Alias Record**: Route 53 specific; maps the Zone Apex to an AWS resource (e.g., `example.com` -> `lb-123.aws.com`). Unlike CNAME, **Alias queries are free** for most AWS resources and always return an IP (improving performance).

### Route 53 Resolver
- **Inbound Endpoint**: Allows on-premises networks to resolve DNS names in your AWS VPC.
- **Outbound Endpoint**: Allows VPC instances to resolve DNS names in your on-premises network.
- **Hybrid DNS**: Key for SAA-C03; establishes a bridge between on-prem and cloud DNS.

### Health Checks & Traffic Flow
- **Calculated Health Checks**: Combine results from multiple health checks using OR/AND/NOT logic.
- **Traffic Flow**: Visual editor for complex routing logic (e.g., Latency + Geoproximity).

